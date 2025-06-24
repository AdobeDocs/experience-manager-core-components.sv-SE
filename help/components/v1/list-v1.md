---
title: List Component (v1)
description: Med Core Component List Component kan du enkelt skapa både dynamiska och statiska listor.
index: n
role: Architect, Developer, Admin, User
exl-id: 510d059c-e60a-40aa-9032-66a901109f6e
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: tm+mt
source-wordcount: '836'
ht-degree: 0%

---


# List Component (v1) {#list-component-v}

Med Core Component List Component kan du enkelt skapa både dynamiska och statiska listor.

## Användning {#usage}

List-komponenten kan användas för att skapa t.ex. en dynamisk lista med underordnade sidor eller en statisk lista med godtyckligt definierade objekt.

Typen av tillgängliga listor och formateringsalternativ kan definieras av mallförfattaren i [designdialogrutan](#design-dialog). Innehållsredigeraren kan välja bland tillgängliga listtyper och hur listelementen ska formateras i [redigeringsdialogrutan](#edit-dialog).

## Version och kompatibilitet {#version-and-compatibility}

I det här dokumentet beskrivs v1 i List Component, som ursprungligen introducerades i version 1.0.0 av Core Components med AEM 6.3.

I följande tabell visas kompatibiliteten för v1 för List-komponenten.

| AEM Version | List Component v1 |
|--- |--- |
| 6,3 | Kompatibel |
| 6,4 | Kompatibel |

>[!CAUTION]
>
>Det här dokumentet beskriver v1 för List-komponenten.
>
>Mer information om den aktuella versionen av List-komponenten finns i dokumentet [List Component](/help/components/list.md).

## Exempel på komponentutdata {#sample-component-output}

Följande är ett exempel från [We.Retail](https://helpx.adobe.com/se/experience-manager/6-4/sites/developing/using/we-retail.html).

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
>JSON-export från Core Components kräver version 1.1.0 av Core Components. Mer information finns i [kompatibilitetsinformationen för kärnkomponenter v1](/help/versions.md).

## Dialogrutan Redigera {#edit-dialog}

I redigeringsdialogrutan kan innehållsförfattaren konfigurera listan och listelementen.

### Listinställningar {#list-settings}

Listan kan byggas på olika sätt.

* [Underordnade sidor](#child-pages)
* [Fast lista](#fixed-list)
* [Sök](#search-list)
* [Taggar](#tags)

Oavsett hur listan är uppbyggd finns det [Alternativ för sortering](#sort-options) som alltid kan konfigureras.

![](/help/assets/chlimage_1-38.png)

Beroende på hur innehållsförfattaren väljer att skapa listan ändras de ytterligare konfigurationsalternativen.

#### Underordnade sidor {#child-pages}

Listan kan byggas av de underordnade sidorna för den aktuella sidan eller en annan sida.

![](/help/assets/chlimage_1-39.png)

* **Överordnad sida**
   * Den sida vars underordnade sidor ska skapa listan
   * Lämna tomt om du vill använda den aktuella sidan
* **Underordnat djup** - Hur många nivåer ned i hierarkin ska användas

#### Fast lista {#fixed-list}

Listan kan skapas med en fast lista med objekt.

![](/help/assets/chlimage_1-40.png)

Tryck eller klicka på knappen **Lägg till** om du vill infoga ett nytt objekt i listan.

* Ange text för objektet i listan eller använd dialogrutan **Markering** för att välja ett objekt från AEM.
* Använd draghandtaget för att ordna om objekten i listan.
* Använd papperskorgsikonen för att ta bort objekt i listan.

#### Sök {#search-list}

Listan kan byggas med hjälp av resultatet från en sökning i AEM-innehåll.

![](/help/assets/chlimage_1-41.png)

* **Sökfråga** - Strängen som en fulltextsökning ska köras för att generera listelementen
* **Sök i** - Där sökningen ska köras
   * Använd dialogrutan **Markering** för att välja plats i AEM
   * Använd aktuell sida om inget anges

#### Taggar {#tags}

Listan kan byggas med sidor som matchar vissa taggar under en viss plats.

![](/help/assets/chlimage_1-42.png)

* **Överordnad sida** - Där taggmatchningen ska börja
   * Använd dialogrutan **Markering** för att välja plats i AEM
   * Använd aktuell sida om inget anges
* **Taggar** - Vilka taggar ska matchas
   * Välj taggarna i dialogrutan **Bläddra**
* **Matcha** - Definiera vilken typ av matchning som ska kvalificera en sida som ska tas med i listan
   * **valfri tagg**
   * **alla taggar**

#### Sorteringsalternativ {#sort-options}

Oavsett hur du väljer att skapa listan finns det vissa sorteringsalternativ som alltid kan definieras.

![](/help/assets/chlimage_1-43.png)

* **Beställ av** - Hur elementen ska ordnas
   * **Titel**
   * **Senaste ändringsdatum**
* **Sorteringsordning** - Den ordning som objekten ska sorteras i
   * **stigande**
   * **fallande**
* **Max antal objekt** - Maximalt antal objekt som visas i listan.
   * Lämna tomt om du vill returnera alla objekt.

### Objektinställningar {#item-settings}

På fliken **Objektinställningar** kan du konfigurera formateringen för listelementen.

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

På fliken **Listinställningar** kan datumformatet definieras liksom vilken typ av listor som ska vara tillgängliga i komponenten för innehållsförfattarna.

![](/help/assets/chlimage_1-45.png)

* **Datumformat** - Format som ska användas för visning av det senaste ändringsdatumet
* **Inaktivera underordnade** - Inaktivera listtypen för underordnade i komponenten
* **Inaktivera statisk** - Inaktivera den statiska listtypen i komponenten
* **Inaktivera sökning** - Inaktivera typen av söklista i komponenten
* **Inaktivera taggar** - Inaktivera taggliststypen i komponenten

### Objektinställningar {#item-settings-1}

På fliken **Objektinställningar** kan du definiera formateringsalternativen för de enskilda listelementen som ska vara tillgängliga i komponenten för innehållsförfattarna.

![](/help/assets/chlimage_1-46.png)

* **Länkobjekt** - Aktivera alternativet Länkobjekt i dialogrutan [redigera](#edit-dialog)
* **Visa beskrivningar** - Aktivera alternativet Visa beskrivningar i dialogrutan [redigera](#edit-dialog)
* **Visa datum** - Aktivera alternativet Visa datum i dialogrutan [redigera](#edit-dialog)

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om List-komponenten [finns på GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/list/v1/list).

Hela kärnkomponentprojektet kan hämtas från GitHub.

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).
