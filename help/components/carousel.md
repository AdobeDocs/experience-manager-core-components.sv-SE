---
title: Carousel-komponent
description: Med Carousel Component kan innehållsförfattaren presentera innehållet i en roterande karusell.
translation-type: tm+mt
source-git-commit: d3ebcea5fa1523c1a986841cd3d1a64e16e85f6d
workflow-type: tm+mt
source-wordcount: '1125'
ht-degree: 0%

---


# Carousel-komponent{#carousel-component}

Med Core Component Carousel Component kan innehållsförfattaren presentera innehållet i en navigerbar karusell.

## Användning {#usage}

Med hjälp av Carousel Component kan innehållsförfattaren ordna innehållet i en roterande karusell med bilder.

I [redigeringsdialogrutan](#edit-dialog) kan författaren skapa, namnge och ordna flera bilder samt aktivera automatisk övergång med fördröjning. Med hjälp av [designdialogrutan](#design-dialog) kan mallskaparen definiera vilka komponenter som kan läggas till i karusellen, aktivera eller inaktivera automatiska övergångar och anpassa formaten.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Carousel Component är v1, som introducerades i version 2.2.0 av Core Components i oktober 2018, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v1 | Kompatibel | Kompatibel | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempelkomponentutdata {#sample-component-output}

Om du vill visa Carousel-komponenten och se exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_carousel).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Carousel-komponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_carousel_v1).

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen till Core Components developer](/help/developing/overview.md).

## Redigera dialogruta {#edit-dialog}

I redigeringsdialogrutan kan innehållsförfattaren lägga till, byta namn på och ordna om bilder samt definiera inställningarna för automatisk övergång.

### Fliken Objekt {#items-tab}

![Fliken Objekt i redigeringsdialogrutan för Carousel-komponenten](/help/assets/carousel-edit-items.png)

Använd knappen **Lägg till** för att öppna komponentväljaren och välja vilken komponent som ska läggas till som en flik. När du har lagt till en post läggs den till i listan, som innehåller följande kolumner:

* **Ikon**  - Ikonen för flikens komponenttyp, vilket gör det enkelt att identifiera i listan. För musen över för att se det fullständiga komponentnamnet som ett verktygstips.
* **Beskrivning**  - Beskrivningen som används som tabbtext och används som standard för namnet på komponenten som är markerad för fliken.
* **Ta bort** - Tryck eller klicka för att ta bort fliken från flikkomponenten.
* **Ändra ordning**  - Tryck eller klicka och dra för att ordna tabbarna.

>[!TIP]
>
>Om sidans visningsruta minskas så att redigeringsdialogrutan blir helskärm, döljs knappen **Lägg till**. Komponenter kan fortfarande läggas till i Carousel-komponenten genom att [dra från komponentwebbläsaren och släppa på Carousel-komponenten i sidredigeraren](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#inserting-a-component-from-the-components-browser).

### Fliken Egenskaper {#properties-tab}

![Fliken Egenskaper i redigeringsdialogrutan för Carousel-komponenten](/help/assets/carousel-edit-properties.png)

På fliken **Egenskaper** kan författaren ange att bildrutorna ska övergå automatiskt.

* **Överför bilder**  automatiskt - När komponenten är aktiv flyttas den automatiskt till nästa bild efter en viss fördröjning.
* **Övergångsfördröjning**  - När automatiskt övergångsklipp är markerade används det här värdet för att definiera fördröjningen mellan övergångar (i millisekunder).
* **Inaktivera automatisk paus vid hovring**  - När  **Överför** bildspel automatiskt väljs pausas karusellövergången automatiskt när pekaren hålls över karusellen. Välj det här alternativet så att övergången inte pausas.
* **ID**  - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i  [datalagret](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

>[!NOTE]
>
>Avancerade kontroller för bildrutor är inte aktiverade i läget **Redigera**. Använd [**Förhandsgranska** mode](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#preview-mode) eller **[Visa som publicerad](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)** om du vill interagera med karusellen som en läsare av det publicerade innehållet.
>
>Funktionen för automatiskt framflyttning är inte aktiverad i **redigeringsläget**. Använd alternativet **[Visa som publicerat](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)** om du vill se funktionen för automatiskt fortsättning som en läsare av det publicerade innehållet skulle göra.

### Hjälpmedelsfliken {#accessibility-tab}

![Fliken Tillgänglighet i redigeringsdialogrutan för Carousel-komponenten](/help/assets/carousel-edit-accessibility.png)

På fliken **Accessibility** kan värden anges för [ARIA accessibility](https://www.w3.org/WAI/standards-guidelines/aria/)-etiketter för komponenten.

* **Etikett**  - Värdet för ett ARIA-etikettattribut för komponenten

## Välj panel {#select-panel}

Innehållsförfattaren kan använda alternativet **Välj panel** i komponentverktygsfältet för att ändra till en annan bildruta för redigering och även enkelt ordna om bildrutorna.

![Ikonen Välj panel](/help/assets/select-panel-icon.png)

När du har valt alternativet **Välj panel** i komponentverktygsfältet visas de konfigurerade bildrutorna som en listruta.

* Listan ordnas efter bildrutornas tilldelade placering och återspeglas i numreringen.
* Bildrutans komponenttyp visas först, följt av bildbeskrivningen med ett ljusare teckensnitt.

![Välj panel](/help/assets/select-panel-popover.png)

* Om du trycker eller klickar på en post i listrutan växlar vyn i redigeraren till den bildrutan.
* Du kan ordna om bilden på plats med hjälp av draghandtagen.

## Designdialog {#design-dialog}

I designdialogrutan kan mallskaparen definiera vilka komponenter som kan läggas till som bilder i karusellkomponenten samt definiera standardvärden för automatisk övergång och vilka anpassade format som är tillgängliga för innehållsförfattaren.

### Fliken Egenskaper {#properties-tab-1}

Fliken **Egenskaper** används för att definiera standardinställningarna för bildruteövergångarna när en innehållsförfattare lägger till karusellkomponenten på en sida.

![Designdialogrutan för Carousel-komponenten](/help/assets/carousel-design.png)

* **Överför bilder**  automatiskt - Anger om alternativet att automatiskt flytta karusellen till nästa bild är aktiverat som standard när innehållsförfattaren lägger till karusellkomponenten på en sida.
* **Övergångsfördröjning**  - Definierar standardvärdet för övergångsfördröjningen mellan bildrutor (i millisekunder) när en innehållsförfattare lägger till karusellkomponenten på en sida.
* **Inaktivera automatisk paus vid hovring**  - Anger om som standard alternativet att inaktivera den automatiska pausningen av bildrutor är aktiverat när  **Automatisk övergång av** bildrutor väljs av innehållsförfattaren.

### Fliken Tillåtna komponenter {#allowed-components-tab}

Fliken **Tillåtna komponenter** används för att definiera vilka komponenter som innehållsförfattaren kan lägga till som bildrutor till Carousel-komponenten.

Fliken Tillåtna komponenter fungerar på samma sätt som fliken med samma namn när [du definierar principen och egenskaperna för en layoutbehållare i mallredigeraren.](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)

### Fliken Format {#styles-tab}

Carousel-komponenten stöder AEM [Style System](/help/get-started/authoring.md#component-styling).

## Adobe-klientdatalagret {#data-layer}

Carousel-komponenten stöder [Adobe-klientdatalagret.](/help/developing/data-layer/overview.md)
