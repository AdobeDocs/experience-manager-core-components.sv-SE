---
title: List-komponent
description: Med Core Component List Component kan du enkelt skapa både dynamiska och statiska listor.
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# List-komponent{#list-component}

Med Core Component List Component kan du enkelt skapa både dynamiska och statiska listor.

## Användning {#usage}

List-komponenten kan användas för att skapa t.ex. en dynamisk lista med underordnade sidor eller en statisk lista med godtyckligt definierade objekt. Vilka typer av listor som är tillgängliga och formateringsalternativen kan definieras av mallförfattaren i [designdialogrutan](#design-dialog). Innehållsredigeraren kan välja bland tillgängliga listtyper och hur listelementen ska formateras i [redigeringsdialogrutan](#edit-dialog).

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av List Component är v2, som introducerades i version 2.0.0 av Core Components i januari 2018, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponentversionerna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |--- |---|
| v2 | Kompatibel | Kompatibel | Kompatibel | Kompatibel |
| [v1](v1/list-v1.md) | Kompatibel | Kompatibel | Kompatibel | - |

Mer information om Core Component-versioner och -versioner finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill se List Component (List-komponenten) och exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata, går du till [Component Library](https://adobe.com/go/aem_cmp_library_list).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om List-komponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_list_v2).

Mer information om hur du utvecklar kärnkomponenter finns i dokumentationen till [Core Components Developer](/help/developing/overview.md).

## Dialogrutan Redigera {#edit-dialog}

I redigeringsdialogrutan kan innehållsförfattaren konfigurera listan och listobjekten.

### Fliken Listinställningar {#list-settings-tab}

Listan kan byggas på olika sätt.

* [Underordnade sidor](#child-pages)
* [Fast lista](#fixed-list)
* [Sökning](#search-options)
* [Taggar](#tags)

Oavsett hur listan är uppbyggd finns det [sorteringsalternativ](#sort-options) som alltid kan konfigureras.

![](/help/assets/chlimage_1-38.png)

Beroende på hur innehållsförfattaren väljer att skapa listan ändras de ytterligare konfigurationsalternativen.

#### Underordnade sidor {#child-pages}

Listan kan byggas av de underordnade sidorna för den aktuella sidan eller en annan sida.

![](/help/assets/chlimage_1-39.png)

* **Överordnad sida**
   * Den sida vars underordnade sidor ska skapa listan
   * Lämna tomt om du vill använda den aktuella sidan

* **Underordnat djup** Hur många nivåer ned i hierarkin ska användas

#### Fast lista {#fixed-list}

Listan kan skapas med en fast lista med objekt.

![](/help/assets/chlimage_1-40.png)

Tryck eller klicka på knappen **Lägg till** för att dra in ett nytt objekt i listan.

* Ange text för objektet i listan eller använd **urvalsdialogrutan** för att välja ett objekt från AEM.
* Använd draghandtaget för att ordna om objekten i listan.
* Använd papperskorgsikonen för att ta bort objekt i listan.

#### Sökning {#search-options}

Listan kan byggas med hjälp av resultaten från en sökning i AEM-innehåll.

![](/help/assets/chlimage_1-41.png)

* **Sökfråga** Strängen som en fulltextsökning ska köras för att generera listelementen
* **Sök i** Där sökningen ska köras
   * Använd dialogrutan **** Markering för att välja plats i AEM
   * Använd aktuell sida om inget anges

#### Taggar {#tags}

Listan kan byggas med sidor som matchar vissa taggar under en viss plats.

![](/help/assets/chlimage_1-42.png)

* **Överordnad sida** där taggmatchningen ska börja
   * Använd dialogrutan **** Markering för att välja plats i AEM
   * Använd aktuell sida om inget anges
* **Taggar** som ska matchas
   * Välj taggarna i dialogrutan **Bläddra**
* **Matcha** Definiera vilken typ av matchning som ska kvalificera en sida som ska tas med i listan
   * **valfri tagg**
   * **alla taggar**

#### Sorteringsalternativ {#sort-options}

Oavsett hur du väljer att skapa listan finns det vissa sorteringsalternativ som alltid kan definieras.

![](/help/assets/chlimage_1-43.png)

* **Beställ efter** hur elementen ska ordnas
   * **Titel**
   * **Senast ändrat den**
* **Sorteringsordning** Den ordning som artiklarna ska sorteras i
   * **stigande**
   * **fallande**
* **Maximalt antal objekt** Maximalt antal objekt som visas i listan.
   * Lämna tomt om du vill returnera alla objekt.

### Fliken Objektinställningar {#item-settings-tab}

På fliken Objektinställningar kan du konfigurera formateringen för listelementen.

![](/help/assets/chlimage_1-44.png)

* **Länka objekt** Länka objekt till motsvarande sida
* **Visa beskrivning** Visa beskrivningar av länkobjektet
* **Visa datum** för länkobjektets ändringsdatum

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera vilka typer av listor som ska tillåtas för innehållsförfattarna samt de tillgängliga objektinställningarna.

### Listinställningar {#list-settings}

På fliken **Listinställningar** kan datumformatet definieras liksom vilken typ av listor som ska vara tillgängliga i komponenten för innehållsförfattarna.

![](/help/assets/chlimage_1-45.png)

* **Datumformatformat** som ska användas för visning av det senaste ändringsdatumet
* **Inaktivera underordnade** Inaktivera listtypen för underordnade i komponenten
* **Inaktivera statisk** Inaktivera den statiska listtypen i komponenten
* **Inaktivera sökning** Inaktivera söklisttypen i komponenten
* **Inaktivera taggar** Inaktivera tagglisttyp i komponenten

### Objektinställningar {#item-settings}

På fliken **Objektinställningar** kan du definiera formateringsalternativen för de enskilda listelementen som ska vara tillgängliga i komponenten för innehållsförfattarna.

![](/help/assets/chlimage_1-46.png)

* **Alternativet Länka objekt** Aktivera länkobjekt i [redigeringsdialogrutan](#edit-dialog)
* **Visa beskrivningar** Aktivera alternativet Visa beskrivningar i [redigeringsdialogrutan](#edit-dialog)
* **Visa alternativet Visa datum** Visa datum i dialogrutan [Redigera](#edit-dialog)

### Fliken Format {#styles-tab}

Bildkomponenten stöder AEM [Style System](/help/get-started/authoring.md#component-styling).
