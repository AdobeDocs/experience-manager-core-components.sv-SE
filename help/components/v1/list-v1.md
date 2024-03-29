---
title: List Component (v1)
description: Med Core Component List Component kan du enkelt skapa både dynamiska och statiska listor.
index: n
role: Architect, Developer, Admin, User
exl-id: 510d059c-e60a-40aa-9032-66a901109f6e
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '854'
ht-degree: 0%

---

# List Component (v1) {#list-component-v}

Med Core Component List Component kan du enkelt skapa både dynamiska och statiska listor.

## Användning {#usage}

List-komponenten kan användas för att skapa t.ex. en dynamisk lista med underordnade sidor eller en statisk lista med godtyckligt definierade objekt.

Vilka typer av listor som är tillgängliga och formateringsalternativen kan definieras av mallförfattaren i [designdialogruta](#design-dialog). Innehållsredigeraren kan välja bland tillgängliga listtyper och hur listelementen ska formateras i [redigeringsdialogruta](#edit-dialog).

## Version och kompatibilitet {#version-and-compatibility}

I det här dokumentet beskrivs v1 i List Component, som ursprungligen introducerades i version 1.0.0 av Core Components med AEM 6.3.

I följande tabell visas kompatibiliteten för v1 för List-komponenten.

| AEM | List Component v1 |
|--- |--- |
| 6.3 | Kompatibel |
| 6.4 | Kompatibel |

>[!CAUTION]
>
>Det här dokumentet beskriver v1 för List-komponenten.
>
>Mer information om den aktuella versionen av List Component finns i [List-komponent](/help/components/list.md) -dokument.

## Exempel på komponentutdata {#sample-component-output}

Följande prov tas från [Vi.butik](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

### Skärmbild {#screenshot}

![](/help/assets/chlimage_1-47.png)

### HTML {#html}

```
<div class="cmp cmp-list aem-GridColumn aem-GridColumn--default--12">

<ul>
    <li>
    <article>
        <a href="/content/we-retail/us/en/experience/arctic-surfing-in-lofoten.html">
            <span class="cmp-list--item-title">Arctic Surfing In Lofoten</span>
            
        </a>
        
    </article>
</li>

    <li>
    <article>
        <a href="/content/we-retail/us/en/experience/summit-success-in-the-himalayas.html">
            <span class="cmp-list--item-title">Summit Success in the Himalayas</span>
            
        </a>
        
    </article>
</li>

    <li>
    <article>
        <a href="/content/we-retail/us/en/experience/climbing-on-kalymnos-island--greece.html">
            <span class="cmp-list--item-title">Climbing on Kalymnos Island, Greece</span>
            
        </a>
        
    </article>
</li>

    <li>
    <article>
        <a href="/content/we-retail/us/en/experience/running-at-the-great-wall-marathon.html">
            <span class="cmp-list--item-title">Running at the Great Wall Marathon</span>
            
        </a>
        
    </article>
</li>

    <li>
    <article>
        <a href="/content/we-retail/us/en/experience/skiing-deep-powder-in-siberia.html">
            <span class="cmp-list--item-title">Skiing deep powder in Siberia</span>
            
        </a>
        
    </article>
</li>

    <li>
    <article>
        <a href="/content/we-retail/us/en/experience/climbing-in-the-massif-du-mont-blanc.html">
            <span class="cmp-list--item-title">Climbing in the Massif du Mont Blanc</span>
            
        </a>
        
    </article>
</li>
</ul>

</div>
```

### JSON {#json}

```
"articles_list": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              ":type": "weretail/components/content/articleslist",
              "tagsMatch": "any",
              "displayAs": "teaser",
              "feedEnabled": "true",
              "listFrom": "children",
              "limit": "0",
              "orderBy": "cq:lastModified",
              "pageMax": "0"
            }
```

>[!NOTE]
>
>JSON-export från Core Components kräver version 1.1.0 av Core Components. Se [kompatibilitetsinformation för kärnkomponenter v1](/help/versions.md) för mer information.

## Dialogrutan Redigera {#edit-dialog}

I redigeringsdialogrutan kan innehållsförfattaren konfigurera listan och listelementen.

### Listinställningar {#list-settings}

Listan kan byggas på olika sätt.

* [Underordnade sidor](#child-pages)
* [Fast lista](#fixed-list)
* [Sökning](#search-list)
* [Taggar](#tags)

Oavsett hur listan byggs finns det [Sorteringsalternativ](#sort-options) som alltid kan konfigureras.

![](/help/assets/chlimage_1-38.png)

Beroende på hur innehållsförfattaren väljer att skapa listan ändras de ytterligare konfigurationsalternativen.

#### Underordnade sidor {#child-pages}

Listan kan byggas av de underordnade sidorna för den aktuella sidan eller en annan sida.

![](/help/assets/chlimage_1-39.png)

* **Överordnad sida**
   * Den sida vars underordnade sidor ska skapa listan
   * Lämna tomt om du vill använda den aktuella sidan
* **Underordnat djup** - Hur många nivåer i hierarkin som ska användas

#### Fast lista {#fixed-list}

Listan kan skapas med en fast lista med objekt.

![](/help/assets/chlimage_1-40.png)

Tryck eller klicka på **Lägg till** om du vill dra in ett nytt objekt i listan.

* Ange text för objektet i listan eller använd **Dialogrutan Markering** om du vill välja ett objekt från AEM.
* Använd draghandtaget för att ordna om objekten i listan.
* Använd papperskorgsikonen för att ta bort objekt i listan.

#### Sökning {#search-list}

Listan kan skapas med hjälp av resultatet av en sökning AEM innehåll.

![](/help/assets/chlimage_1-41.png)

* **Sökfråga** - Den sträng som en textsökning ska köras för att generera listelementen
* **Sök i** - Var sökningen ska göras
   * Använd **Dialogrutan Markering** för att välja plats i AEM
   * Använd aktuell sida om inget anges

#### Taggar {#tags}

Listan kan byggas med sidor som matchar vissa taggar under en viss plats.

![](/help/assets/chlimage_1-42.png)

* **Överordnad sida** - Där taggmatchningen ska börja
   * Använd **Dialogrutan Markering** för att välja plats i AEM
   * Använd aktuell sida om inget anges
* **Taggar** - Vilka taggar som ska matchas
   * Använd **Bläddra** för att markera taggarna
* **Matcha** - Definiera vilken typ av matchning som ska kvalificera en sida som ska tas med i listan
   * **valfri tagg**
   * **alla taggar**

#### Sorteringsalternativ {#sort-options}

Oavsett hur du väljer att skapa listan finns det vissa sorteringsalternativ som alltid kan definieras.

![](/help/assets/chlimage_1-43.png)

* **Beställ av** - Ordna elementen
   * **Titel**
   * **Senast ändrat den**
* **Sorteringsordning** - Den ordning i vilken artiklarna ska ordnas
   * **stigande**
   * **fallande**
* **Max. objekt** - Maximalt antal objekt som visas i listan.
   * Lämna tomt om du vill returnera alla objekt.

### Objektinställningar {#item-settings}

Använda **Objektinställningar** kan formateringen av listelementen konfigureras.

![](/help/assets/chlimage_1-44.png)

* **Länka objekt**
Länka objekt till motsvarande sida
* **Visa beskrivning**
Visa beskrivningar av länkelementet
* **Visa datum**
Visa ändringsdatum för länkobjektet

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera vilka typer av listor som ska tillåtas för innehållsförfattarna samt de tillgängliga objektinställningarna.

### Listinställningar {#list-settings-1}

På **Listinställningar** kan datumformatet definieras liksom vilken typ av listor som ska vara tillgängliga i komponenten för innehållsförfattarna.

![](/help/assets/chlimage_1-45.png)

* **Datumformat** - Format som ska användas för att visa det senaste ändringsdatumet
* **Inaktivera underordnade** - Inaktivera listtypen för underordnade i komponenten
* **Inaktivera statisk** - Inaktivera den statiska listtypen i komponenten
* **Inaktivera sökning** - Inaktivera typen av söklista i komponenten
* **Inaktivera taggar** - Inaktivera tagglisttyp i komponenten

### Objektinställningar {#item-settings-1}

På **Objektinställningar** kan du definiera formateringsalternativen för de enskilda listelementen som ska vara tillgängliga i komponenten för innehållsförfattarna.

![](/help/assets/chlimage_1-46.png)

* **Länka objekt** - Aktivera alternativet Länkobjekt i [redigeringsdialogruta](#edit-dialog)
* **Visa beskrivningar** - Aktivera alternativet Visa beskrivningar i dialogrutan [redigeringsdialogruta](#edit-dialog)
* **Visa datum** - Aktivera alternativet Visa datum i [redigeringsdialogruta](#edit-dialog)

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om List Component [finns på GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/list/v1/list).

Hela kärnkomponentprojektet kan laddas ned från GitHub.

Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).
