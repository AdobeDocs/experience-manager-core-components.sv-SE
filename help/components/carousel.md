---
title: Carousel-komponent
description: Med Carousel Component kan innehållsförfattaren presentera innehållet i en roterande karusell.
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# Carousel-komponent{#carousel-component}

Med Core Component Carousel Component kan innehållsförfattaren presentera innehållet i en navigerbar karusell.

## Användning {#usage}

Med hjälp av Carousel Component kan innehållsförfattaren ordna innehållet i en roterande karusell med bilder.

I [redigeringsdialogrutan](#edit-dialog) kan skribenten skapa, namnge och ordna flera bilder samt aktivera automatisk övergång med fördröjning. I [designdialogrutan](#design-dialog)kan mallskaparen definiera vilka komponenter som kan läggas till i karusellen, aktivera eller inaktivera automatiska övergångar och anpassa formaten.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Carousel Component är v1, som introducerades i version 2.2.0 av Core Components i oktober 2018, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponentversionerna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |--- |---|
| v1 | Kompatibel | Kompatibel | Kompatibel | Kompatibel |

Mer information om Core Component-versioner och -versioner finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill visa Carousel-komponenten samt se exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_carousel).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Carousel-komponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_carousel_v1).

Mer information om hur du utvecklar kärnkomponenter finns i dokumentationen till [Core Components Developer](/help/developing/overview.md).

## Dialogrutan Redigera {#edit-dialog}

I redigeringsdialogrutan kan innehållsförfattaren lägga till, byta namn på och ordna om bilder samt definiera inställningarna för automatisk övergång.

### Fliken Objekt {#items-tab}

![](/help/assets/screen-shot-2019-08-29-12.01.39.png)

Använd knappen **Lägg** till för att öppna komponentväljaren och välja vilken komponent som ska läggas till som en tabb. När du har lagt till en post läggs den till i listan, som innehåller följande kolumner:

* **Ikon** - Ikonen för flikens komponenttyp, vilket gör den enkel att identifiera i listan. För musen över för att se det fullständiga komponentnamnet som ett verktygstips.
* **Beskrivning** - Den beskrivning som används som tabbtext och används som standard för namnet på komponenten som är markerad för fliken.
* **Ta bort** - Tryck eller klicka för att ta bort fliken från flikkomponenten.
* **Ändra ordning** - Tryck eller klicka och dra för att ordna tabbarna.

>[!TIP]
>
>Om sidans visningsruta minskas så att redigeringsdialogrutan blir helskärm, döljs knappen **Lägg till** . Komponenter kan fortfarande läggas till i Carousel-komponenten genom att [dra från komponentwebbläsaren och släppa på Carousel-komponenten i sidredigeraren](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#inserting-a-component-from-the-components-browser).

### Fliken Egenskaper {#properties-tab}

![](/help/assets/screen-shot-2019-08-29-12.01.57.png)

På fliken **Egenskaper** kan innehållsförfattaren ställa in bildrutorna så att de automatiskt övergår.

* **Överför bilder** automatiskt - När komponenten är aktiv flyttas den automatiskt till nästa bild efter en viss fördröjning.
* **Övergångsfördröjning** - När automatiskt övergå bildrutor är markerat används det här värdet för att definiera fördröjningen mellan övergångar (i millisekunder).
* **Inaktivera automatisk paus vid hovring** - När **automatiskt överför bilder** automatiskt är markerat pausas karusellövergången automatiskt när markören hålls över karusellen. Välj det här alternativet så att övergången inte pausas.

>[!NOTE]
>
>Avancerade kontroller för bildrutor är inte aktiverade i **redigeringsläge** . Använd [**förhandsgranskningsläget **eller alternativet](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#preview-mode)Visa som publicerat **[](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)**om du vill interagera med karusellen på samma sätt som en läsare av det publicerade innehållet.
>
>Funktionen för automatiskt framflyttning är inte aktiverad i **redigeringsläge** . Använd **[alternativet Visa som publicerat](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)**om du vill se funktionen för automatiska framsteg som en läsare av det publicerade innehållet skulle göra.

### Fliken Tillgänglighet {#accessibility-tab}

![](/help/assets/screen-shot-2019-08-29-12.02.22.png)

På fliken **Tillgänglighet** kan du ange värden för [ARIA-hjälpmedelsetiketter](https://www.w3.org/WAI/standards-guidelines/aria/) för komponenten.

* **Etikett** - Värdet för ett ARIA-etikettattribut för komponenten

## Välj panel {#select-panel}

Innehållsförfattaren kan använda alternativet **Välj panel** i komponentverktygsfältet för att ändra till en annan bildruta för redigering och även för att enkelt ordna om bildrutorna.

![](/help/assets/screenshot_2018-10-11at165417.png)

När du har valt alternativet **Välj panel** i komponentverktygsfältet visas de konfigurerade bildrutorna som en listruta.

* Listan ordnas efter bildrutornas tilldelade placering och återspeglas i numreringen.
* Bildrutans komponenttyp visas först, följt av bildbeskrivningen med ett ljusare teckensnitt.

![](/help/assets/opera_snapshot_2018-11-28141537localhost.png)

* Om du trycker eller klickar på en post i listrutan växlar vyn i redigeraren till den bildrutan.
* Du kan ordna om bilden på plats med hjälp av draghandtagen.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera vilka komponenter som kan läggas till som bilder i karusellkomponenten samt definiera standardvärden för automatisk övergång och vilka anpassade format som är tillgängliga för innehållsförfattaren.

### Fliken Egenskaper {#properties-tab-1}

Fliken **Egenskaper** används för att definiera standardinställningarna för bildövergångarna när en innehållsförfattare lägger till karusellkomponenten på en sida.

![](/help/assets/screenshot_2018-11-28at141824.png)

* **Överför bilder** automatiskt - Anger om alternativet att automatiskt flytta karusellen till nästa bild är aktiverat som standard när innehållsförfattaren lägger till karusellkomponenten på en sida.
* **Övergångsfördröjning** - Definierar standardvärdet för övergångsfördröjningen mellan bildrutor (i millisekunder) när en innehållsförfattare lägger till karusellkomponenten på en sida.
* **Inaktivera automatisk paus vid hovring** - Anger om som standard alternativet att inaktivera den automatiska pausningen av bildrutor är aktiverat när **Automatisk övergång av bildrutor** har valts av innehållsförfattaren.

### Fliken Tillåtna komponenter {#allowed-components-tab}

Fliken **Tillåtna komponenter** används för att definiera vilka komponenter som innehållsförfattaren kan lägga till som bildrutor i Carousel-komponenten.

Fliken Tillåtna komponenter fungerar på samma sätt som fliken med samma namn när du [definierar principen och egenskaperna för en layoutbehållare i mallredigeraren.](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)

### Fliken Format {#styles-tab}

Carousel-komponenten stöder AEM [Style System](/help/get-started/authoring.md#component-styling).
