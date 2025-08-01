---
title: Använda Adobe Client Data Layer med Core Components
description: Använda Adobe Client Data Layer med Core Components
feature: Core Components, Adobe Client Data Layer
role: Architect, Developer, Admin
exl-id: 55c984d3-deb7-4eda-a81d-7768791d2b46
source-git-commit: 5994133947ff697f7c866fe61598c58e37e77008
workflow-type: tm+mt
source-wordcount: '952'
ht-degree: 0%

---


# Använda Adobe Client Data Layer med Core Components {#data-layer-core-components}

Målet med Adobe Client Data Layer är att minska ansträngningarna att instrumentera webbplatser genom att tillhandahålla en standardiserad metod för att exponera och få tillgång till alla typer av data för alla typer av skript.

Adobe Client Data Layer är plattformsoberoende, men är helt integrerad i de centrala komponenterna för användning med AEM.

Precis som Core-komponenterna är koden för Adobe Client Data Layer tillgänglig på GitHub tillsammans med utvecklardokumentationen. Det här dokumentet ger en översikt över hur kärnkomponenterna interagerar med datalagret, men fullständig teknisk information finns i GitHub-dokumentationen.

>[!TIP]
>
>Mer information om Adobe Client Data Layer finns i [resurserna i dess GitHub-databas.](https://github.com/adobe/adobe-client-data-layer)
>
>Mer teknisk information om integrationen av Adobe Client Data Layer med Core Components finns i filen [`DATA_LAYER_INTEGRATION.md`](https://github.com/adobe/aem-core-wcm-components/blob/master/DATA_LAYER_INTEGRATION.md) i Core Components-databasen.

{{traditional-aem}}

## Installation och aktivering {#installation-activation}

Från och med Core Components version 2.9.0 distribueras datalagret med Core Components som ett AEM-klientbibliotek och ingen installation behövs. Alla projekt som genereras av [AEM Project Archetype v. 24+](/help/developing/archetype/overview.md) innehåller som standard ett aktiverat datalager.

Om du vill aktivera datalagret manuellt måste du skapa en [kontextmedveten konfiguration](/help/developing/context-aware-configs.md) för den:

1. Skapa följande struktur under mappen `/conf/<mySite>`, där `<mySite>` är namnet på webbplatsens projekt:
   * `/conf/<mySite>/sling:configs/com.adobe.cq.wcm.core.components.internal.DataLayerConfig`
   * Där varje nod har en `jcr:primaryType` inställd på `nt:unstructured`.
1. Lägg till en boolesk egenskap med namnet `enabled` och ställ in den på `true`.

   ![Plats för DataLayerConfig i WKND-referensplats](/help/assets/datalayer-contextaware-sling-config.png)

   *Plats för DataLayerConfig i WKND-referensplats*

1. Lägg till en `sling:configRef`-egenskap till `jcr:content`-noden för din webbplats under `/content` (t.ex. `/content/<mySite>/jcr:content`) och ställ in den på `/conf/<mySite>` från föregående steg.

1. När den är aktiverad kan du verifiera aktiveringen genom att läsa in en sida utanför redigeraren, till exempel med alternativet **Visa som publicerad** i redigeraren. Kontrollera sidkällan och taggen `<body>` ska innehålla attributet `data-cmp-data-layer-enabled`

   ```html
   <body class="page basicpage" id="page-id" data-cmp-data-layer-enabled>
       <script>
         window.adobeDataLayer = window.adobeDataLayer || [];
         adobeDataLayer.push({
             page: JSON.parse("{\x22page\u002D6c5d4b9fdd\x22:{\x22xdm:language\x22:\x22en\x22,\x22repo:path\x22:\x22\/content\/wknd\/language\u002Dmasters\/en.html\x22,\x22xdm:tags\x22:[],\x22xdm:template\x22:\x22\/conf\/wknd\/settings\/wcm\/templates\/landing\u002Dpage\u002Dtemplate\x22,\x22@type\x22:\x22wknd\/components\/page\x22,\x22dc:description\x22:\x22WKND is a collective of outdoors, music, crafts, adventure sports, and travel enthusiasts that want to share our experiences, connections, and expertise with the world.\x22,\x22dc:title\x22:\x22WKND Adventures and Travel\x22,\x22repo:modifyDate\x22:\x222020\u002D09\u002D29T07:50:13Z\x22}}"),
             event:'cmp:show',
             eventInfo: {
                 path: 'page.page\u002D6c5d4b9fdd'
             }
         });
       </script>
   ```

1. Du kan också öppna utvecklarverktygen i webbläsaren och i konsolen ska JavaScript-objektet `adobeDataLayer` vara tillgängligt. Ange följande kommando för att hämta den aktuella sidans datalagerstatus:

   ```javascript
   window.adobeDataLayer.getState();
   ```

## Komponenter som stöds {#supported-components}

Följande komponenter har stöd för datalagret.

* [Dragspel](/help/components/accordion.md)
* [Breadcrumb](/help/components/breadcrumb.md)
* [Knapp](/help/components/button.md)
* [Karusell](/help/components/carousel.md)
* [Innehållsfragment](/help/components/content-fragment-component.md)
* [Bild](/help/components/image.md)
* [Språknavigering](/help/components/language-navigation.md)
* [Lista](/help/components/list.md)
* [Navigering](/help/components/navigation.md)
* [Sida](/help/components/page.md)
* [Förloppsfält](/help/components/progress-bar.md)
* [Tabbar](/help/components/tabs.md)
* [Teaser](/help/components/teaser.md)
* [Text](/help/components/text.md)
* [Titel](/help/components/title.md)

Se även de [händelser som utlöses av komponenterna.](#events-components)

## Datascheman för kärnkomponenter {#data-schemas}

Här följer en lista med scheman som kärnkomponenterna använder med datalagret.

### Komponent-/behållarobjektschema {#item}

Schemat för komponent-/behållarobjekt används i följande komponenter:

* [Breadcrumb](/help/components/breadcrumb.md)
* [Knapp](/help/components/button.md)
* [Språknavigering](/help/components/language-navigation.md)
* [Lista](/help/components/list.md)
* [Navigering](/help/components/navigation.md)
* [Teaser](/help/components/teaser.md)
* [Text](/help/components/text.md)
* [Titel](/help/components/title.md)

Schemat för komponent-/behållarobjektet definieras enligt följande.

```javascript
id: {                   // component ID
    @type               // resource type
    repo:modifyDate     // last modified date
    dc:title            // title
    dc:description      // description
    xdm:text            // text
    xdm:linkURL         // link URL
    parentId            // parent component ID
}
```

Följande [händelse](#events) är relevant för schema för komponent-/behållarobjekt:

* `cmp:click`

### Sidschema {#page}

Sidschemat används av följande komponent:

* [Sida](/help/components/page.md)

Sidschemat definieras enligt följande.

```javascript
id: {
    @type
    repo:modifyDate
    dc:title
    dc:description
    xdm:text
    xdm:linkURL
    parentId
    xdm:tags            // page tags
    repo:path           // page path
    xdm:template        // page template
    xdm:language        // page language
}
```

En `cmp:show`-händelse utlöses vid sidinläsning. Den här händelsen skickas från den infogade JavaScript direkt under den inledande `<body>`-taggen, vilket gör den till den tidigaste händelsen i datalagrets händelsekö.

### Behållarschema {#container}

Behållarschemat används av följande komponenter:

* [Dragspel](/help/components/accordion.md)
* [Tabbar](/help/components/tabs.md)
* [Karusell](/help/components/carousel.md)

Behållarschemat definieras så här.

```javascript
id: {
    @type
    repo:modifyDate
    dc:title
    dc:description
    xdm:text
    xdm:linkURL
    parentId
    shownItems          // array of the displayed item IDs
}
```

Följande [händelser](#events) är relevanta för behållarschemat:

* `cmp:click`
* `cmp:show`
* `cmp:hide`

### Bildschema {#image}

Bildschemat används av följande komponent:

* [Bild](/help/components/image.md)

Bildschemat definieras så här.

```javascript
id: {
    @type
    repo:modifyDate
    dc:title
    dc:description
    xdm:text
    xdm:linkURL
    parentId
    image               // asset detail (see below section)
}
```

Följande [händelse](#events) är relevant för bildschemat:

* `cmp:click`

### Resursschema {#asset}

Resursschemat används inuti [Image-komponenten.](/help/components/image.md)

Resursschemat definieras så här.

```javascript
id: {
    repo:id             // asset UUID
    repo:path           // asset path
    @type               // asset resource type
    xdm:tags            // asset tags
    repo:modifyDate
}
```

Följande [händelse](#events) är relevant för resursschemat:

* `cmp:click`

### Innehållsfragmentschema {#content-fragment}

Innehållsfragmentschemat används av komponenten [Innehållsfragment.](/help/components/content-fragment-component.md)

Schemat Innehållsfragment definieras så här.

```javascript
id: {
    @type
    repo:modifyDate
    dc:title
    dc:description
    xdm:text
    xdm:linkURL
    parentId
    elements            // array of the Content Fragment elements
}
```

Schemat som används för elementet Content Fragment är följande.

```javascript
{
    xdm:title           // title
    xdm:text            // text
}
```

## Kärnkomponentshändelser {#events}

Det finns ett antal händelser som kärnkomponenter utlöser via datalagret. Det bästa sättet att interagera med datalagret är att [registrera en händelseavlyssnare](https://github.com/adobe/adobe-client-data-layer/wiki#addeventlistener) och *sedan* vidta en åtgärd baserat på händelsetypen och/eller komponenten som utlöste händelsen. På så sätt undviks potentiella konkurrensförhållanden med asynkrona skript.

Nedan visas några av de färdiga händelserna som ingår i AEM Core Components:

* **`cmp:click`** - Om du klickar på ett klickbart element (ett element som har ett `data-cmp-clickable` -attribut) utlöser datalagret en `cmp:click` -händelse.
* **`cmp:show`** och **`cmp:hide`** - Om du ändrar dragspelet (utöka/komprimera), karusellen (nästa/föregående knappar) och flikarna (tabbmarkera) utlöser datalagret `cmp:show` - respektive `cmp:hide` -händelser. En `cmp:show`-händelse skickas också vid sidinläsning och förväntas vara den första händelsen.
* **`cmp:loaded`** - När datalagret har fyllts i med kärnkomponenterna på sidan utlöser datalagret en `cmp:loaded` -händelse.

### Händelser som utlösts av komponent {#events-components}

I följande tabeller visas de standardkomponenter som utlöser händelser tillsammans med dessa händelser.

| Komponent | Händelser |
|---|---|
| [Dragspel](/help/components/accordion.md) | `cmp:show` och `cmp:hide` |
| [Knapp](/help/components/button.md) | `cmp:click` |
| [Breadcrumb](/help/components/breadcrumb.md) | `cmp:click` |
| [Carousel](/help/components/carousel.md) | `cmp:show` och `cmp:hide` |
| [Språknavigering](/help/components/language-navigation.md) | `cmp:click` |
| [Navigering](/help/components/navigation.md) | `cmp:click` |
| [Sida](/help/components/page.md) | `cmp:show` |
| [Tabbar](/help/components/tabs.md) | `cmp:show` och `cmp:hide` |
| [Teaser](/help/components/teaser.md) | `cmp:click` |

### Information om händelsens sökväg {#event-path-info}

Varje datalagerhändelse som utlöses av en AEM Core-komponent kommer att innehålla en nyttolast med följande JSON-objekt:

```json
eventInfo: {
    path: '<component-path>'
}
```

Där `<component-path>` är JSON-sökvägen till komponenten i datalagret som utlöste händelsen.  Värdet, som är tillgängligt via `event.eventInfo.path`, är viktigt eftersom det kan användas som en parameter till `adobeDataLayer.getState(<component-path>)` som hämtar det aktuella tillståndet för komponenten som utlöste händelsen, vilket gör att anpassad kod kan komma åt ytterligare data och lägga till dem i datalagret.

Till exempel:

```javascript
function logEventObject(event) {
    if(event.hasOwnProperty("eventInfo") && event.eventInfo.hasOwnProperty("path")) {
        var dataObject = window.adobeDataLayer.getState(event.eventInfo.path);
        console.debug("The component that triggered this event: ");
        console.log(dataObject);
    }
}

window.adobeDataLayer = window.adobeDataLayer || [];
window.adobeDataLayer.push(function (dl) {
     dl.addEventListener("cmp:show", logEventObject);
});
```

## Självstudiekurs

Vill du utforska datalagret och kärnkomponenterna mer i detalj? [Kolla in den här självstudiekursen](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/integrations/adobe-client-data-layer/data-layer-overview.html?lang=sv-SE).

>[!TIP]
>
>Om du vill utforska datalagrets flexibilitet ytterligare kan du granska integreringsalternativen, inklusive hur du aktiverar datalagret för dina anpassade komponenter.
