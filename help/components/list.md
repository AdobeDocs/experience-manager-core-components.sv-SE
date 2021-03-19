---
title: List-komponent
description: Med Core Component List Component kan du enkelt skapa både dynamiska och statiska listor.
role: Arkitekt, utvecklare, administratör, affärsansvarig
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '984'
ht-degree: 1%

---


# List Component{#list-component}

Med Core Component List Component kan du enkelt skapa både dynamiska och statiska listor.

## Användning {#usage}

List-komponenten kan användas för att skapa t.ex. en dynamisk lista med underordnade sidor eller en statisk lista med godtyckligt definierade objekt. Vilka typer av listor som finns tillgängliga och formateringsalternativen kan definieras av mallförfattaren i [designdialogrutan](#design-dialog). Innehållsredigeraren kan välja bland tillgängliga listtyper och hur listelementen ska formateras i [redigeringsdialogrutan](#edit-dialog).

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av List Component är v2, som introducerades i version 2.0.0 av Core Components i januari 2018, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | Kompatibel | Kompatibel | Kompatibel |
| [v1](v1/list-v1.md) | Kompatibel | Kompatibel | - |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempelkomponentutdata {#sample-component-output}

Om du vill visa List-komponenten och se exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_list).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om List-komponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_list_v2).

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen till Core Components developer](/help/developing/overview.md).

## Redigera dialogruta {#edit-dialog}

I redigeringsdialogrutan kan innehållsförfattaren konfigurera listan och listobjekten.

### Fliken Listinställningar {#list-settings-tab}

Listan kan byggas på olika sätt.

* [Underordnade sidor](#child-pages)
* [Fast lista](#fixed-list)
* [Sökning](#search-options)
* [Taggar](#tags)

Oavsett hur listan är uppbyggd finns det [Alternativ för sortering och ID](#sort-options) som alltid kan konfigureras.

![Redigeringsdialogrutan för List-komponenten](/help/assets/list-edit.png)

Beroende på hur innehållsförfattaren väljer att skapa listan ändras de ytterligare konfigurationsalternativen.

#### Underordnade sidor {#child-pages}

Listan kan byggas av de underordnade sidorna för den aktuella sidan eller en annan sida.

![Alternativ för underordnade sidor](/help/assets/list-edit-child-pages.png)

* **Överordnad sida**
   * Den sida vars underordnade sidor ska skapa listan
   * Lämna tomt om du vill använda den aktuella sidan

* **Underordnat**
djupHur många nivåer ned i hierarkin ska användas

#### Fast lista {#fixed-list}

Listan kan skapas med en fast lista med objekt.

![Alternativ för fast lista](/help/assets/list-edit-fixed.png)

Tryck eller klicka på knappen **Lägg till** om du vill infoga ett nytt objekt i listan.

* Ange text för objektet i listan eller använd dialogrutan **Markering** för att välja ett objekt från AEM.
* Använd draghandtaget för att ordna om objekten i listan.
* Använd papperskorgsikonen för att ta bort objekt i listan.

#### Sökning {#search-options}

Listan kan skapas med hjälp av resultatet av en sökning AEM innehåll.

![Alternativ för söklistor](/help/assets/list-edit-search.png)

* **Sök**
frågaSträngen som en fulltextsökning ska köras för att generera listelementen
* **Sök**
iDär sökningen ska köras
   * Använd **urvalsdialogrutan** för att välja plats i AEM
   * Använd aktuell sida om inget anges

#### Taggar {#tags}

Listan kan byggas med sidor som matchar vissa taggar under en viss plats.

![Alternativ för tagglistor](/help/assets/list-edit-tags.png)

* **Överordnad**
sidaDär taggmatchningen ska börja
   * Använd **urvalsdialogrutan** för att välja plats i AEM
   * Använd aktuell sida om inget anges
* ****
TaggarVilka taggar som ska matchas
   * Välj taggarna i dialogrutan **Bläddra**
* ****
MatchaDefiniera vilken typ av matchning som ska kvalificera en sida som ska tas med i listan
   * **valfri tagg**
   * **alla taggar**

#### Sorteringsalternativ {#sort-options}

Oavsett hur du väljer att skapa listan finns det vissa sorteringsalternativ som alltid kan definieras.

![Sorteringsalternativ](/help/assets/list-edit-sort-options.png)

* **Ordna**
efterHur elementen ska ordnas
   * **Titel**
   * **Senast ändrat den**
* **Sorteringsordning**
Den ordning som artiklarna ska sorteras i
   * **stigande**
   * **fallande**
* **Max**
ItemsMaximalt antal objekt som visas i listan.
   * Lämna tomt om du vill returnera alla objekt.
* **ID**  - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i  [datalagret](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

### Fliken Objektinställningar {#item-settings-tab}

På fliken Objektinställningar kan du konfigurera formateringen för listelementen.

![Objektinställningar](/help/assets/list-edit-items.png)

* **Länka**
objektLänka objekt till motsvarande sida
* **Visa**
beskrivningVisa beskrivningar av läntobjektet
* **Visa**
datumVisa ändringsdatum för länkobjektet

## Designdialog {#design-dialog}

I designdialogrutan kan mallskaparen definiera vilka typer av listor som ska tillåtas för innehållsförfattarna samt de tillgängliga objektinställningarna.

### Listinställningar {#list-settings}

På fliken **Listinställningar** kan datumformatet definieras liksom vilken typ av listor som ska vara tillgängliga i komponenten för innehållsförfattarna.

![Listkomponentens inställning för designdialogrutelista](/help/assets/list-design-list-settings.png)

* **Date**
FormatFormat som ska användas för visning av det senaste ändringsdatumet
* **Inaktivera**
underordnadeInaktivera listtypen för underordnade i komponenten
* **Inaktivera**
statiskInaktivera den statiska listtypen i komponenten
* **Inaktivera**
sökningInaktivera söklisttypen i komponenten
* **Inaktivera**
taggarInaktivera tagglisttypen i komponenten

### Objektinställningar {#item-settings}

På fliken **Objektinställningar** kan du definiera formateringsalternativen för de enskilda listelementen som ska vara tillgängliga i komponenten för innehållsförfattarna.

![Inställningar för designdialogruteobjekt i List Components](/help/assets/list-design-item-settings.png)

* **Länka**
objektAktivera alternativet Länka objekt i  [redigeringsdialogrutan](#edit-dialog)
* **Visa**
beskrivningarAktivera alternativet Visa beskrivningar i  [redigeringsdialogrutan](#edit-dialog)
* **Visa**
datumAktivera alternativet Visa datum i  [redigeringsdialogrutan](#edit-dialog)

### Fliken Format {#styles-tab}

Bildkomponenten stöder AEM [Style System](/help/get-started/authoring.md#component-styling).

## Adobe-klientdatalagret {#data-layer}

List-komponenten stöder [Adobe-klientdatalagret.](/help/developing/data-layer/overview.md)
