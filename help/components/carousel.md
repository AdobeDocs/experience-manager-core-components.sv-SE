---
title: Carousel-komponent
description: Med Carousel Component kan innehållsförfattaren presentera innehållet i en roterande karusell.
role: Architect, Developer, Admin, User
exl-id: 3331214c-a05c-47e1-b54c-fbfd1045bd60
source-git-commit: dd30def59a8f037864da875ef4c831b11f766e57
workflow-type: tm+mt
source-wordcount: '1317'
ht-degree: 0%

---


# Carousel-komponent{#carousel-component}

Med Core Component Carousel Component kan innehållsförfattaren presentera innehållet i en navigerbar karusell.

{{traditional-aem}}

## Användning {#usage}

Med hjälp av Carousel Component kan innehållsförfattaren ordna innehållet i en roterande karusell med bilder.

I dialogrutan [Redigera](#edit-dialog) kan innehållsförfattaren skapa, namnge och ordna flera bilder samt aktivera automatisk övergång med fördröjning. Med hjälp av [designdialogrutan](#design-dialog) kan mallskaparen definiera vilka komponenter som kan läggas till i karusellen, aktivera eller inaktivera automatiska övergångar och anpassa formaten.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Carousel Component är v1, som introducerades i version 2.2.0 av Core Components i oktober 2018, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponenterna är kompatibla med samt länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|--- |--- |--- |---|---|
| v1 | Kompatibel med <br>[version 2.17.4](/help/versions.md) och tidigare | Kompatibel | Kompatibel | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill visa Carousel-komponenten och se exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_carousel).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Carousel-komponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_carousel_v1).

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).

## Djuplänkning till en panel {#deep-linking}

Carousel, [Tabbar,](tabs.md) och [dragspelskomponenter](accordion.md) har stöd för att länka direkt till en panel i komponenten.

Så här gör du:

1. Visa sidan med komponenten med alternativet **[Visa som publicerad](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)** i sidredigeraren.
1. Granska sidans innehåll och identifiera panelens ID.
   * Till exempel `id="carousel-bfe4fa6647-item-47f1a7ca67-tabpanel"`
1. ID:t blir det ankare som du kan lägga till i URL:en med hjälp av ett hash-tecken (`#`).
   * Till exempel `https://wknd.site/content/wknd/language-masters/en/magazine/western-australia.html#carousel-bfe4fa6647-item-47f1a7ca67-tabpanel`

Om du navigerar till URL-adressen med panel-ID som ankarpunkt, rullar webbläsaren direkt till den aktuella komponenten och visar den angivna panelen. Om panelen inte är konfigurerad att visas som standard rullas den automatiskt.

## Carousel och responsiv design {#responsive-design}

Alla kärnkomponenter är utformade för att vara fullt responsiva och ger en sömlös upplevelse på alla enheter.

Vissa avancerade komponenter som Carousel Component kan kräva särskild hänsyn i samband med implementeringsprojektet för att kunna behålla sin lyhördhet under alla förhållanden. Mer information finns i dokumentet [Responsiv design för kärnkomponenterna](/help/responsive.md).

## Dialogrutan Redigera {#edit-dialog}

I redigeringsdialogrutan kan innehållsförfattaren lägga till, byta namn på och ordna om bilder samt definiera inställningarna för automatisk övergång.

### Fliken Objekt {#items-tab}

![Fliken Objekt i redigeringsdialogrutan för Carousel-komponenten](/help/assets/carousel-edit-items.png)

Använd knappen **Lägg till** för att öppna komponentväljaren och välja vilken komponent som ska läggas till som en flik. När du har lagt till en post läggs den till i listan, som innehåller följande kolumner:

* **Ikon** - Ikonen för flikens komponenttyp, vilket gör det enkelt att identifiera i listan. För musen över för att se det fullständiga komponentnamnet som ett verktygstips.
* **Beskrivning** - Den beskrivning som används som tabbtext och som standard används som namn på den komponent som har valts för fliken.
* **Ta bort** - Tryck eller klicka för att ta bort fliken från flikkomponenten.
* **Ändra ordning** - Tryck eller klicka och dra för att ordna flikarna.

>[!TIP]
>
>Om sidans visningsruta minskas så att redigeringsdialogrutan blir helskärm, döljs knappen **Lägg till**. Komponenter kan fortfarande läggas till i Carousel-komponenten genom att [dra från komponentwebbläsaren och släppa på Carousel-komponenten i sidredigeraren](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#inserting-a-component-from-the-components-browser).

### Fliken Egenskaper {#properties-tab}

![Fliken Egenskaper i redigeringsdialogrutan för Carousel-komponenten](/help/assets/carousel-edit-properties.png)

På fliken **Egenskaper** kan innehållsförfattaren ange att bildrutorna ska övergå automatiskt.

* **Aktivt objekt** - Innehållsförfattaren kan definiera vilken flik som är aktiv när sidan läses in.
* **Överför bilder automatiskt** - När komponenten är aktiv flyttas den automatiskt till nästa bild efter en angiven fördröjning.
* **Övergångsfördröjning** - När automatiskt överför bildrutor är markerat används det här värdet för att definiera fördröjningen mellan övergångar (i millisekunder).
* **Inaktivera automatisk paus vid hovring** - När **Överför bilder automatiskt** är markerat pausas karusellövergången automatiskt när pekaren förs över karusellen. Välj det här alternativet så att övergången inte pausas.
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [datalagret](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

>[!NOTE]
>
>Avancerade kontroller för bildrutor är inte aktiverade i läget **Redigera**. Använd [**Förhandsgranska** läge](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#preview-mode) eller alternativet **[Visa som publicerad](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)** om du vill interagera med karusellen på samma sätt som en läsare av det publicerade innehållet.
>
>Funktionen för automatiskt framflyttning är inte aktiverad i läget **Redigera**. Använd alternativet **[Visa som publicerad](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)** om du vill se den automatiska funktionen som en läsare av det publicerade innehållet gör.

### Fliken Tillgänglighet {#accessibility-tab}

![Fliken Tillgänglighet i redigeringsdialogrutan för Carousel-komponenten](/help/assets/carousel-edit-accessibility.png)

På fliken **Hjälpmedel** kan värden anges för [ARIA-hjälpmedelsetiketter](https://www.w3.org/WAI/standards-guidelines/aria/) för komponenten.

* **Etikett** - Värdet på ett aria-label-attribut för karusellen, som beskriver karusellens innehåll
* **Föregående** - Värdet på ett aria-label-attribut för Carousel-navigeringens föregående knappetikett
* **Nästa** - Värdet för ett aria-label-attribut för Carousel-navigeringens nästa knappetikett
* **Spela upp** - Värdet på ett aria-label-attribut för Carousel-navigeringens uppspelningsknappsetikett
* **Paus** - Värdet för ett arienetikettattribut för karusellnavigeringens pause-knappetikett
* **Tablist** - Värdet för ett aria-label-attribut för Carousel-navigeringens lista över objekt-etikett
* **Ange objektets ariaetikett till dess titel** - Om det här alternativet är markerat ställs carousel-objektets titel automatiskt in på dess ariaetikettbeskrivning.

## Välj panel {#select-panel}

Innehållsförfattaren kan använda alternativet **Välj panel** i komponentverktygsfältet för att ändra till en annan bildruta för redigering och även för att enkelt ordna om bildrutorna.

![Välj panelikon](/help/assets/select-panel-icon.png)

När du har valt alternativet **Välj panel** i komponentverktygsfältet visas de konfigurerade bildrutorna som en listruta.

* Listan ordnas efter bildrutornas tilldelade placering och återspeglas i numreringen.
* Bildrutans komponenttyp visas först, följt av bildbeskrivningen med ett ljusare teckensnitt.

![Välj panel](/help/assets/select-panel-popover.png)

* Om du trycker eller klickar på en post i listrutan växlar vyn i redigeraren till den bildrutan.
* Du kan ordna om bilden på plats med hjälp av draghandtagen.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera vilka komponenter som kan läggas till som bilder i karusellkomponenten samt definiera standardvärden för automatisk övergång och vilka anpassade format som är tillgängliga för innehållsförfattaren.

### Fliken Egenskaper {#properties-tab-1}

Fliken **Egenskaper** används för att definiera standardinställningarna för bildövergångarna när en innehållsförfattare lägger till karusellkomponenten på en sida.

![Designdialogrutan för Carousel-komponenten](/help/assets/carousel-design.png)

* **Överför bilder automatiskt** - Anger om alternativet att automatiskt flytta karusellen till nästa bild är aktiverat som standard när innehållsförfattaren lägger till karusellkomponenten på en sida.
* **Lägg till kontrollelement** - När det här alternativet är markerat placeras kontrollelementen framför karusellobjekten för att förbättra tillgängligheten.

### Fliken Tillåtna komponenter {#allowed-components-tab}

Fliken **Tillåtna komponenter** används för att definiera vilka komponenter som innehållsförfattaren kan lägga till som bildrutor i Carousel-komponenten.

Fliken Tillåtna komponenter fungerar på samma sätt som fliken med samma namn när [du definierar principen och egenskaperna för en layoutbehållare i mallredigeraren.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)

### Fliken Format {#styles-tab}

Carousel-komponenten stöder AEM [Style System](/help/get-started/authoring.md#component-styling).

## Adobe Client Data Layer {#data-layer}

Carousel-komponenten stöder [Adobe-klientdatalagret.](/help/developing/data-layer/overview.md)
