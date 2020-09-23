---
title: Använda Adobe-klientdatalagret med kärnkomponenterna
description: Använda Adobe-klientdatalagret med kärnkomponenterna
translation-type: tm+mt
source-git-commit: 4a44a5f584efa736320556f6b4e2f4126d058a48
workflow-type: tm+mt
source-wordcount: '575'
ht-degree: 1%

---


# Använda Adobe-klientdatalagret med kärnkomponenterna {#data-layer-core-components}

Målet med Adobe Client Data Layer är att minska ansträngningarna att instrumentera webbplatser genom att tillhandahålla en standardiserad metod för att exponera och få tillgång till alla typer av data för alla typer av skript.

Adobe Client Data Layer är plattformsoberoende, men är helt integrerad i de centrala komponenterna för användning med AEM.

Precis som Core-komponenterna är koden för Adobe-klientdatalagret tillgänglig på GitHub tillsammans med utvecklardokumentationen. Det här dokumentet ger en översikt över hur kärnkomponenterna interagerar med datalagret, men fullständig teknisk information finns i GitHub-dokumentationen.

>[!TIP]
>
>Mer information om Adobe Client Data Layer [finns i resurserna i dess GitHub-databas.](https://github.com/adobe/adobe-client-data-layer)
>
>Mer teknisk information om integreringen av Adobe Client Data Layer med Core Components finns i filen i Core Components-databasen [`DATA_LAYER_INTEGRATION.md`](https://github.com/adobe/aem-core-wcm-components/blob/master/DATA_LAYER_INTEGRATION.md) .

## Installation och aktivering {#installation-activation}

Från och med Core Components version 2.9.0 distribueras datalagret med Core Components som en clientlib. Ingen installation krävs.

Datalagret är dock inte aktiverat som standard. Om du vill aktivera datalagret måste du skapa en [kontextmedveten konfiguration](/help/developing/context-aware-configs.md) för det:

1. Skapa följande struktur under `/conf` noden:
   * `/conf/<mySite>/sling:configs/com.adobe.cq.wcm.core.components.internal.DataLayerConfig`
   * Nodtyp: `nt:unstructured`
1. Lägg till en boolesk egenskap med namnet `enabled` och ställ in den på `true`.
1. Lägg till en `sling:configRef` egenskap till `jcr:content` noden på platsen nedan `/content` (t.ex. `/content/<mySite>/jcr:content`) och ställ in den på `/conf/<mySite>`.

När den är aktiverad kan du verifiera aktiveringen genom att läsa in en sida utanför redigeraren. När du inspekterar sidan ser du att Adobe-klientdatalagret har lästs in.

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

### Behållarschema {#container}

Behållarschemat används av följande komponenter:

* [Dragspel](/help/components/accordion.md)
* [Tabbar](/help/components/tabs.md)
* [Carousel](/help/components/carousel.md)

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

Följande [händelse](#events) är relevant för Image-schemat:

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

## Händelser {#events}

Det finns ett antal händelser som utlöses av datalagret.

* **`cmp:click`** - Om du klickar på ett klickbart element (ett element som har ett `data-cmp-clickable` attribut) utlöser datalagret en `cmp:click` händelse.
* **`cmp:show`** och **`cmp:hide`** - Om du ändrar dragspelsfliken (expanderar/komprimerar), karusellen (nästa/föregående knappar) och flikarna (tabbmarkera) utlöses datalagret `cmp:show` respektive en `cmp:hide` händelse.
* **`cmp:loaded`** - När datalagret har fyllts i med huvudkomponenterna på sidan utlöser datalagret en `cmp:loaded` händelse.

### Händelser utlösta av komponent {#events-components}

I följande tabeller visas de standardkomponenter som utlöser händelser tillsammans med dessa händelser.

| Komponent | Händelser |
|---|---|
| [Navigering](/help/components/navigation.md) | `cmp:click` |
| [Språknavigering](/help/components/language-navigation.md) | `cmp:click` |
| [Breadcrumb](/help/components/breadcrumb.md) | `cmp:click` |
| [Knapp](/help/components/button.md) | `cmp:click` |
| [Carousel](/help/components/carousel.md) | `cmp:show` and `cmp:hide` |
| [Tabbar](/help/components/tabs.md) | `cmp:show` and `cmp:hide` |
| [Dragspel](/help/components/accordion.md) | `cmp:show` and `cmp:hide` |
