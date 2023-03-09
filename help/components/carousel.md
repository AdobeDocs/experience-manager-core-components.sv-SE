---
title: Carousel-komponent
description: Med Carousel Component kan innehållsförfattaren presentera innehållet i en roterande karusell.
role: Architect, Developer, Admin, User
exl-id: 3331214c-a05c-47e1-b54c-fbfd1045bd60
source-git-commit: e0d3790b265ab27ac2116f0d8daf1a18ecd3d714
workflow-type: tm+mt
source-wordcount: '1312'
ht-degree: 0%

---

# Carousel-komponent{#carousel-component}

Med Core Component Carousel Component kan innehållsförfattaren presentera innehållet i en navigerbar karusell.

## Användning {#usage}

Med hjälp av Carousel Component kan innehållsförfattaren ordna innehållet i en roterande karusell med bilder.

The [redigeringsdialogruta](#edit-dialog) gör att innehållsförfattaren kan skapa, namnge och ordna flera bilder samt aktivera automatisk övergång med fördröjning. Använda [designdialogruta](#design-dialog)kan mallskaparen definiera vilka komponenter som kan läggas till i karusellen, aktivera eller inaktivera automatiska övergångar och anpassa formaten.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Carousel Component är v1, som introducerades i version 2.2.0 av Core Components i oktober 2018, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v1 | Kompatibel med<br>[version 2.17.4](/help/versions.md) och tidigare | Kompatibel | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Huvudkomponentversioner](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill se exempel på Carousel-komponenten och dess konfigurationsalternativ samt HTML och JSON-utdata går du till [Komponentbibliotek](https://adobe.com/go/aem_cmp_library_carousel).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Carousel-komponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_carousel_v1).

Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Djuplänkning till en panel {#deep-linking}

Carousel, [Tabbar,](tabs.md) och [Dragspelskomponenter](accordion.md) har stöd för att länka direkt till en panel i komponenten.

Så här gör du:

1. Visa sidan med komponenten med hjälp av **[Visa som publicerad](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)** i sidredigeraren.
1. Inspect innehållet på sidan och identifierar panelens ID.
   * Till exempel `id="carousel-bfe4fa6647-item-47f1a7ca67-tabpanel"`
1. ID:t blir det ankare som du kan lägga till i URL:en med ett hash-tecken (`#`).
   * Till exempel `https://wknd.site/content/wknd/language-masters/en/magazine/western-australia.html#carousel-bfe4fa6647-item-47f1a7ca67-tabpanel`

Om du navigerar till URL-adressen med panel-ID som ankarpunkt, rullar webbläsaren direkt till den aktuella komponenten och visar den angivna panelen. Om panelen inte är konfigurerad att visas som standard rullas den automatiskt.

## Dialogrutan Redigera {#edit-dialog}

I redigeringsdialogrutan kan innehållsförfattaren lägga till, byta namn på och ordna om bilder samt definiera inställningarna för automatisk övergång.

### Fliken Objekt {#items-tab}

![Fliken Objekt i redigeringsdialogrutan för Carousel-komponenten](/help/assets/carousel-edit-items.png)

Använd **Lägg till** för att öppna komponentväljaren och välja vilken komponent som ska läggas till som en tabb. När du har lagt till en post läggs den till i listan, som innehåller följande kolumner:

* **Ikon** - Ikonen för flikens komponenttyp, vilket gör det enkelt att identifiera i listan. För musen över för att se det fullständiga komponentnamnet som ett verktygstips.
* **Beskrivning** - Beskrivningen som används som tabbtext och används som standard för namnet på komponenten som är markerad för tabben.
* **Ta bort** - Tryck eller klicka för att ta bort fliken från flikkomponenten.
* **Ändra ordning** - Tryck eller klicka och dra för att ordna tabbarna.

>[!TIP]
>
>Om sidans visningsruta minskas så att redigeringsdialogrutan blir helskärm, **Lägg till** knappen döljs. Komponenter kan fortfarande läggas till i Carousel-komponenten med [dra från komponenternas webbläsare och släppa på Carousel-komponenten i sidredigeraren](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#inserting-a-component-from-the-components-browser).

### Fliken Egenskaper {#properties-tab}

![Fliken Egenskaper i redigeringsdialogrutan för Carousel-komponenten](/help/assets/carousel-edit-properties.png)

På **Egenskaper** kan författaren ställa in att bildrutorna ska övergå automatiskt.

* **Aktivt objekt** - Innehållsförfattaren kan definiera vilken flik som är aktiv när sidan läses in.
* **Överför bilder automatiskt** - När komponenten är aktiv flyttas den automatiskt till nästa bild efter en angiven fördröjning.
* **Övergångsfördröjning** - När Överför bildrutor automatiskt är markerat används det här värdet för att definiera fördröjningen mellan övergångar (i millisekunder).
* **Inaktivera automatisk paus vid hovring** - När **Överför bilder automatiskt** när du väljer det här alternativet pausas karusellövergången automatiskt när pekaren förs över karusellen. Välj det här alternativet så att övergången inte pausas.
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [Datalager](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

>[!NOTE]
>
>Avancerade kontroller för bildrutor är inte aktiverade i **Redigera** läge. Använd [**Förhandsgranska** läge](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#preview-mode) eller **[Visa som publicerad](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)** möjlighet att interagera med karusellen på samma sätt som en läsare av det publicerade innehållet.
>
>Funktionen för automatiskt framflyttning är inte aktiverad när du är **Redigera** läge. Använd **[Visa som publicerad](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)** om du vill se funktionen för autospolning som en läsare av det publicerade innehållet.

### Fliken Tillgänglighet {#accessibility-tab}

![Fliken Tillgänglighet i redigeringsdialogrutan för Carousel-komponenten](/help/assets/carousel-edit-accessibility.png)

På **Tillgänglighet** -tabb kan värden anges för [Tillgänglighet för ARIA](https://www.w3.org/WAI/standards-guidelines/aria/) -etiketter för komponenten.

* **Etikett** - Värdet på ett ariemärkningsattribut för karusellen, som beskriver karusellens innehåll
* **Föregående** - Värdet på ett aria-label-attribut för Carousel-navigeringens föregående knappetikett
* **Nästa** - Värdet på ett aria-label-attribut för Carousel-navigeringens nästa knappetikett
* **Spela upp** - Värdet på ett aria-label-attribut för Carousel-navigeringens play-knappetikett
* **Pausa** - Värdet på ett aria-label-attribut för karusellnavigeringens pause-knappetikett
* **Tablist** - Värdet på ett aria-label-attribut för Carousel-navigeringens lista över punktetiketter
* **Ange objektets aria-etikett till dess titel** - Om det här alternativet är markerat får karusellobjektets rubrik automatiskt sin ariaetikettbeskrivning.

## Välj panel {#select-panel}

Innehållsförfattaren kan använda **Välj panel** i komponentverktygsfältet för att byta till en annan bildruta för redigering samt för att enkelt ordna om bildrutorna.

![Ikonen Välj panel](/help/assets/select-panel-icon.png)

När du har valt **Välj panel** i komponentverktygsfältet visas de konfigurerade bildrutorna som en listruta.

* Listan ordnas efter bildrutornas tilldelade placering och återspeglas i numreringen.
* Bildrutans komponenttyp visas först, följt av bildbeskrivningen med ett ljusare teckensnitt.

![Välj panel](/help/assets/select-panel-popover.png)

* Om du trycker eller klickar på en post i listrutan växlar vyn i redigeraren till den bildrutan.
* Du kan ordna om bilden på plats med hjälp av draghandtagen.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera vilka komponenter som kan läggas till som bilder i karusellkomponenten samt definiera standardvärden för automatisk övergång och vilka anpassade format som är tillgängliga för innehållsförfattaren.

### Fliken Egenskaper {#properties-tab-1}

The **Egenskaper** -fliken används för att definiera standardinställningarna för bildruteövergångarna när en innehållsförfattare lägger till Carousel-komponenten på en sida.

![Designdialogrutan för Carousel-komponenten](/help/assets/carousel-design.png)

* **Överför bilder automatiskt** - Anger om alternativet att automatiskt flytta karusellen till nästa bild ska aktiveras som standard när innehållsförfattaren lägger till karusellkomponenten på en sida.
* **Lägga till kontrollelement** - När detta är markerat placeras kontrollelementen framför karusellobjekten för att förbättra tillgängligheten.

### Fliken Tillåtna komponenter {#allowed-components-tab}

The **Tillåtna komponenter** -fliken används för att definiera vilka komponenter som innehållsförfattaren kan lägga till som bildrutor till Carousel-komponenten.

Fliken Tillåtna komponenter fungerar på samma sätt som fliken med samma namn när [definiera policyn och egenskaperna för en layoutbehållare i mallredigeraren.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)

### Fliken Format {#styles-tab}

Carousel-komponenten stöder AEM [Formatsystem](/help/get-started/authoring.md#component-styling).

## Adobe-klientdatalager {#data-layer}

Carousel-komponenten stöder [Adobe Client Data Layer.](/help/developing/data-layer/overview.md)
