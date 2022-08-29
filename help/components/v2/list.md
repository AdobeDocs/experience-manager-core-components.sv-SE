---
title: List Component (v2)
description: Med Core Component List Component kan du enkelt skapa både dynamiska och statiska listor.
role: Architect, Developer, Admin, User
exl-id: fa34be64-b345-45cd-baf3-571973414852
source-git-commit: 241c86240377858a73f4a022368d428da9c11100
workflow-type: tm+mt
source-wordcount: '1022'
ht-degree: 0%

---

# List Component (v2) {#list-component}

Med Core Component List Component kan du enkelt skapa både dynamiska och statiska listor.

## Användning {#usage}

List-komponenten kan användas för att skapa t.ex. en dynamisk lista med underordnade sidor eller en statisk lista med godtyckligt definierade objekt. Vilka typer av listor som är tillgängliga och formateringsalternativen kan definieras av mallförfattaren i [designdialogruta](#design-dialog). Innehållsredigeraren kan välja bland tillgängliga listtyper och hur listelementen ska formateras i [redigeringsdialogruta](#edit-dialog).

## Version och kompatibilitet {#version-and-compatibility}

I det här dokumentet beskrivs v1 i List Component, som introducerades i version 2.0.0 av Core Components i januari 2018.

>[!CAUTION]
>
>Det här dokumentet beskriver v2 för List-komponenten.
>
>Mer information om den aktuella versionen av List Component finns i [List-komponent](/help/components/list.md) -dokument.

## Omdirigeringar i listor {#redirects}

När en sida har ett omdirigeringsmål (oavsett om det pekar på en extern URL eller en annan AEM sida), är det en lista som innehåller länkar till den punkten direkt till URL:en för omdirigeringsmålet.

### Exempel {#redirect-example}

* Skapa en sida A som dirigeras om till sida B.
* Skapa en sida C som dirigeras om till `https://aemcomponents.dev`
* På en sida D infogar du en listkomponent som innehåller sidorna A och C
* De länkar som skapas pekar sedan direkt på sidan B och `https://aemcomponents.dev`

## Exempel på komponentutdata {#sample-component-output}

Om du vill visa List-komponenten samt exempel på dess konfigurationsalternativ samt HTML och JSON-utdata går du till [Komponentbibliotek](https://adobe.com/go/aem_cmp_library_list).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om List Component [finns på GitHub](https://adobe.com/go/aem_cmp_tech_list_v2).

Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Dialogrutan Redigera {#edit-dialog}

I redigeringsdialogrutan kan innehållsförfattaren konfigurera listan och listobjekten.

### Fliken Listinställningar {#list-settings-tab}

Listan kan byggas på olika sätt.

* [Underordnade sidor](#child-pages)
* [Fast lista](#fixed-list)
* [Sökning](#search-options)
* [Taggar](#tags)

Oavsett hur listan byggs finns det [Alternativ för sortering och ID](#sort-options) som alltid kan konfigureras.

![Redigeringsdialogrutan för List-komponenten](/help/assets/v2/list-edit.png)

Beroende på hur innehållsförfattaren väljer att skapa listan ändras de ytterligare konfigurationsalternativen.

#### Underordnade sidor {#child-pages}

Listan kan byggas av de underordnade sidorna för den aktuella sidan eller en annan sida.

![Alternativ för underordnade sidor](/help/assets/v2/list-edit-child-pages.png)

* **Överordnad sida**
   * Den sida vars underordnade sidor ska skapa listan
   * Lämna tomt om du vill använda den aktuella sidan

* **Underordnat djup**
Hur många nivåer i hierarkin som ska användas

#### Fast lista {#fixed-list}

Listan kan skapas med en fast lista med objekt.

![Alternativ för fast lista](/help/assets/v2/list-edit-fixed-list.png)

Tryck eller klicka på **Lägg till** om du vill dra in ett nytt objekt i listan.

* Ange text för objektet i listan eller använd **Dialogrutan Markering** om du vill välja ett objekt från AEM.
* Använd draghandtaget för att ordna om objekten i listan.
* Använd papperskorgsikonen för att ta bort objekt i listan.

#### Sökning {#search-options}

Listan kan skapas med hjälp av resultatet av en sökning AEM innehåll.

![Alternativ för söklistor](/help/assets/v2/list-edit-search.png)

* **Sökfråga**
Strängen som en fulltextsökning ska köras för att generera listelementen
* **Sök i**
Var sökningen ska utföras
   * Använd **Dialogrutan Markering** för att välja plats i AEM
   * Använd aktuell sida om inget anges

#### Taggar {#tags}

Listan kan byggas med sidor som matchar vissa taggar under en viss plats.

![Alternativ för tagglistor](/help/assets/v2/list-edit-tags.png)

* **Överordnad sida**
Där taggmatchningen ska börja
   * Använd **Dialogrutan Markering** för att välja plats i AEM
   * Använd aktuell sida om inget anges
* **Taggar**
Vilka taggar som ska matchas
   * Använd **Bläddra** för att markera taggarna
* **Matcha**
Definiera vilken typ av matchning som ska kvalificera en sida som ska tas med i listan
   * **valfri tagg**
   * **alla taggar**

#### Sorteringsalternativ {#sort-options}

Oavsett hur du väljer att skapa listan finns det vissa sorteringsalternativ som alltid kan definieras.

![Sorteringsalternativ](/help/assets/v2/list-edit-sort-options.png)

* **Beställ av**
Hur elementen ska ordnas
   * **Titel**
   * **Senast ändrat den**
* **Sorteringsordning**
Den ordning i vilken artiklarna ska ordnas
   * **stigande**
   * **fallande**
* **Max. objekt**
Maximalt antal objekt som visas i listan.
   * Lämna tomt om du vill returnera alla objekt.
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [Datalager](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

### Fliken Objektinställningar {#item-settings-tab}

På fliken Objektinställningar kan du konfigurera formateringen för listelementen.

![Objektinställningar](/help/assets/v2/list-edit-item-settings.png)

* **Länka objekt**
Länka objekt till motsvarande sida
* **Visa beskrivning**
Visa beskrivningar av länkelementet
* **Visa datum**
Visa ändringsdatum för länkobjektet

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera vilka typer av listor som ska tillåtas för innehållsförfattarna samt de tillgängliga objektinställningarna.

### Listinställningar {#list-settings}

På **Listinställningar** kan datumformatet definieras liksom vilken typ av listor som ska vara tillgängliga i komponenten för innehållsförfattarna.

![Listkomponentens inställning för designdialogrutelista](/help/assets/v2/list-design-list-settings.png)

* **Datumformat**
Format som ska användas för att visa det senaste ändringsdatumet
* **Inaktivera underordnade**
Inaktivera listtypen för underordnade i komponenten
* **Inaktivera statisk**
Inaktivera den statiska listtypen i komponenten
* **Inaktivera sökning**
Inaktivera typen av söklista i komponenten
* **Inaktivera taggar**
Inaktivera tagglisttypen i komponenten

### Objektinställningar {#item-settings}

På **Objektinställningar** kan du definiera formateringsalternativen för de enskilda listelementen som ska vara tillgängliga i komponenten för innehållsförfattarna.

![Inställningar för designdialogruteobjekt i List Components](/help/assets/v2/list-design-item-settings.png)

* **Länka objekt**
Alternativet Aktivera länkobjekt i [redigeringsdialogruta](#edit-dialog)
* **Visa beskrivningar**
Aktivera alternativet Visa beskrivningar i dialogrutan [redigeringsdialogruta](#edit-dialog)
* **Visa datum**
Aktivera alternativet Visa datum i dialogrutan [redigeringsdialogruta](#edit-dialog)

### Fliken Format {#styles-tab}

Bildkomponenten stöder AEM [Formatsystem](/help/get-started/authoring.md#component-styling).

## Adobe-klientdatalager {#data-layer}

List-komponenten har stöd för [Adobe Client Data Layer.](/help/developing/data-layer/overview.md)
