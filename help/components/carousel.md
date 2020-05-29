---
title: Carousel Component
description: Med Carousel Component kan innehållsförfattaren presentera innehållet i en roterande karusell.
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '1112'
ht-degree: 0%

---


# Carousel Component{#carousel-component}

Med Core Component Carousel Component kan innehållsförfattaren presentera innehållet i en navigerbar karusell.

## Användning {#usage}

Using the Carousel Component, the content author to organize content in a rotating carousel of slides.

The [edit dialog](#edit-dialog) allows the content author to create, name, and order multiple slides as well as enable auto-transition with delay. Using the [design dialog](#design-dialog), the template author can define which components can be added to the carousel, enable or disable automatic transitions, and customize the styles.

## Version och kompatibilitet {#version-and-compatibility}

The current version of the Carousel Component is v1, which was introduced with release 2.2.0 of the Core Components in October 2018, and is described in this document.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponentversionerna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v1 | Kompatibel | Kompatibel | Kompatibel |

Mer information om Core Component-versioner och -versioner finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

To experience the Carousel Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_carousel).

### Teknisk information {#technical-details}

The latest technical documentation about the Carousel Component [can be found on GitHub](https://adobe.com/go/aem_cmp_tech_carousel_v1).

Mer information om hur du utvecklar kärnkomponenter finns i dokumentationen till [Core Components Developer](/help/developing/overview.md).

## Dialogrutan Redigera {#edit-dialog}

The edit dialog allows the content author to add, rename, and rearrange slides as well as define the auto-transition settings.

### Fliken Objekt {#items-tab}

![Items tab of the edit dialog of the Carousel Component](/help/assets/carousel-edit-items.png)

Använd knappen **Lägg** till för att öppna komponentväljaren och välja vilken komponent som ska läggas till som en tabb. Once added, an entry is added to the list, which contains the following columns:

* **Ikon** - Ikonen för flikens komponenttyp, vilket gör den enkel att identifiera i listan. För musen över för att se det fullständiga komponentnamnet som ett verktygstips.
* **Beskrivning** - Den beskrivning som används som tabbtext och används som standard för namnet på komponenten som är markerad för fliken.
* **Delete** - Tap or click to delete the tab from the tabs component.
* **Ändra ordning** - Tryck eller klicka och dra för att ordna tabbarna.

>[!TIP]
>
>Om sidans visningsruta minskas så att redigeringsdialogrutan blir helskärm, döljs knappen **Lägg till** . Components can still be added to the Carousel Component by [dragging from the components browser and dropping on the Carousel Component in the page editor](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#inserting-a-component-from-the-components-browser).

### Fliken Egenskaper {#properties-tab}

![Properties tab of the edit dialog of the Carousel Component](/help/assets/carousel-edit-properties.png)

On the **Properties** tab, the content author can set the slides to automatically transition.

* **Automatically transition slides** - When active, the component will automatically advance to the next slide after a specified delay.
* **Transition Delay** - When Automatically transition slides is selected, this value is used to define the delay between transitions (in milliseconds).
* **Disable automatic pause on hover** - When **Automatically transition slides** is selected, the carousel transition will automatically pause whenever the cursor hovers over the carousel. Select this option so that the transition will not pause.
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [datalagret](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

>[!NOTE]
>
>The slide advance controls are not enabled when in **Edit** mode. Använd [**förhandsgranskningsläget **eller alternativet](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#preview-mode)Visa som publicerat **[](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)**om du vill interagera med karusellen på samma sätt som en läsare av det publicerade innehållet.
>
>The auto-advance feature is not enabled when in **Edit** mode. Använd **[alternativet Visa som publicerat](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)**om du vill se funktionen för automatiska framsteg som en läsare av det publicerade innehållet skulle göra.

### Fliken Tillgänglighet {#accessibility-tab}

![Fliken Tillgänglighet i redigeringsdialogrutan för Carousel-komponenten](/help/assets/carousel-edit-accessibility.png)

På fliken **Tillgänglighet** kan du ange värden för [ARIA-hjälpmedelsetiketter](https://www.w3.org/WAI/standards-guidelines/aria/) för komponenten.

* **Etikett** - Värdet för ett ARIA-etikettattribut för komponenten

## Välj panel {#select-panel}

Innehållsförfattaren kan använda alternativet **Välj panel** i komponentverktygsfältet för att ändra till en annan bildruta för redigering och även för att enkelt ordna om bildrutorna.

![Ikonen Välj panel](/help/assets/select-panel-icon.png)

När du har valt alternativet **Välj panel** i komponentverktygsfältet visas de konfigurerade bildrutorna som en listruta.

* Listan ordnas efter bildrutornas tilldelade placering och återspeglas i numreringen.
* The component type of the slide is displayed first, followed by the description of the slide in lighter font.

![Välj panel](/help/assets/select-panel-popover.png)

* Om du trycker eller klickar på en post i listrutan växlar vyn i redigeraren till den bildrutan.
* Du kan ordna om bilden på plats med hjälp av draghandtagen.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera vilka komponenter som kan läggas till som bilder i karusellkomponenten samt definiera standardvärden för automatisk övergång och vilka anpassade format som är tillgängliga för innehållsförfattaren.

### Fliken Egenskaper {#properties-tab-1}

Fliken **Egenskaper** används för att definiera standardinställningarna för bildövergångarna när en innehållsförfattare lägger till karusellkomponenten på en sida.

![Design dialog of the Carousel Component](/help/assets/carousel-design.png)

* **Överför bilder** automatiskt - Anger om alternativet att automatiskt flytta karusellen till nästa bild är aktiverat som standard när innehållsförfattaren lägger till karusellkomponenten på en sida.
* **Transition Delay** - Defines the default value of the transition delay between slides (in milliseconds) when a content author adds the carousel component to a page.
* **Inaktivera automatisk paus vid hovring** - Anger om som standard alternativet att inaktivera den automatiska pausningen av bildrutor är aktiverat när **Automatisk övergång av bildrutor** har valts av innehållsförfattaren.

### Allowed Components Tab {#allowed-components-tab}

Fliken **Tillåtna komponenter** används för att definiera vilka komponenter som innehållsförfattaren kan lägga till som bildrutor i Carousel-komponenten.

Fliken Tillåtna komponenter fungerar på samma sätt som fliken med samma namn när du [definierar principen och egenskaperna för en layoutbehållare i mallredigeraren.](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)

### Fliken Format {#styles-tab}

Carousel-komponenten stöder AEM [Style System](/help/get-started/authoring.md#component-styling).
