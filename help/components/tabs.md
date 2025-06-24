---
title: Tabbar-komponent
description: Med flikkomponenten kan du skapa flera flikar för att ordna innehåll på en sida.
role: Architect, Developer, Admin, User
exl-id: 0031c5f3-447c-4932-898f-2f453801e492
source-git-commit: dd30def59a8f037864da875ef4c831b11f766e57
workflow-type: tm+mt
source-wordcount: '1038'
ht-degree: 0%

---


# Tabbar-komponent {#tabs-component}

Med komponenten Core Component Tabs kan du ordna innehåll på flera flikar.

{{traditional-aem}}

## Användning {#usage}

Med flikkomponenten kan innehållsförfattaren ordna sidinnehåll på flera flikar.

I [redigeringsdialogrutan](#edit-dialog) kan innehållsförfattaren definiera flera flikar samt ställa in den aktiva fliken. Med hjälp av [designdialogrutan](#design-dialog) kan mallskaparen definiera vilka komponenter som kan läggas till på flikar och anpassa formaten.

>[!TIP]
>
>Kapslade flikkomponenter (tabbar på flikar) stöds.
>
>Enkla (ej kapslade) flikkomponenter kan hittas/väljas med [innehållsträdet](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html#content-tree), men det går inte att hitta kapslade flikar.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av komponenten Tabs är v1, som introducerades i version 2.2.0 av Core Components i oktober 2018, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponenterna är kompatibla med samt länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|--- |--- |--- |---|---|
| v1 | Kompatibel med <br>[version 2.17.4](/help/versions.md) och tidigare | Kompatibel | Kompatibel | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill se både flikkomponenten och exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_tabs).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om flikkomponenten [ finns på GitHub](https://adobe.com/go/aem_cmp_tech_tabs_v1).

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).

## Djuplänkning till en panel {#deep-linking}

Flikarna, [Carousel,](carousel.md) och [dragspelskomponenter](accordion.md) har stöd för att länka direkt till en panel i komponenten.

Så här gör du:

1. Visa sidan med komponenten med alternativet **[Visa som publicerad](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)** i sidredigeraren.
1. Granska sidans innehåll och identifiera panelens ID.
   * Till exempel `id="accordion-86196c94d3-item-ca319dbb0b"`
1. ID:t blir det ankare som du kan lägga till i URL:en med hjälp av ett hash-tecken (`#`).
   * Till exempel `https://wknd.site/content/wknd/language-masters/en/magazine/western-australia.html#accordion-86196c94d3-item-ca319dbb0b`

Om du navigerar till URL-adressen med panel-ID som ankarpunkt, rullar webbläsaren direkt till den aktuella komponenten och visar den angivna panelen. Om panelen inte är konfigurerad att expanderas som standard kommer den att expanderas automatiskt.

## Flikdesign och responsiv design {#responsive-design}

Alla kärnkomponenter är utformade för att vara fullt responsiva och ger en sömlös upplevelse på alla enheter.

Vissa avancerade komponenter som Tab-komponenten kan kräva särskild hänsyn i samband med implementeringsprojektet för att behålla svarstiden under alla förhållanden. Mer information finns i dokumentet [Responsiv design för kärnkomponenterna](/help/responsive.md).

## Dialogrutan Redigera {#edit-dialog}

I redigeringsdialogrutan kan den som skapar innehållet skapa, byta namn på och ordna om flikar samt definiera den aktiva fliken.

### Fliken Objekt {#items-tab}

![Flikkomponentens objektflik i dialogrutan Redigera](/help/assets/tabs-edit-items.png)

Använd knappen **Lägg till** för att öppna komponentväljaren och välja vilken komponent som ska läggas till som en flik. När du har lagt till en post läggs den till i listan, som innehåller följande kolumner:

* **Ikon** - Ikonen för flikens komponenttyp, vilket gör det enkelt att identifiera i listan. För musen över för att se det fullständiga komponentnamnet som ett verktygstips.
* **Beskrivning** - Den beskrivning som används som tabbtext och som standard används som namn på den komponent som har valts för fliken.
* **Ta bort** - Tryck eller klicka för att ta bort fliken från flikkomponenten.
* **Ordna om** - Tryck eller klicka och dra för att ordna om flikarna.

>[!TIP]
>
>Om sidans visningsruta minskas så att redigeringsdialogrutan blir helskärm, döljs knappen **Lägg till**. Komponenter kan fortfarande läggas till i flikkomponenten genom att [dra från komponentwebbläsaren och släppa på flikkomponenten i sidredigeraren](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#inserting-a-component).

### Fliken Egenskaper {#properties-tab}

![Flikkomponentens egenskapflik i dialogrutan Redigera](/help/assets/tabs-edit-properties.png)

* **Aktivt objekt** - Innehållsförfattaren kan definiera vilken flik som är aktiv när sidan läses in.
   * Med alternativet **Standard** markeras den första fliken.
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [datalagret](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

### Fliken Tillgänglighet {#accessibility-tab}

![Flikkomponentens hjälpmedelsflik i redigeringsdialogrutan](/help/assets/tabs-edit-accessibility.png)

På fliken **Hjälpmedel** kan värden anges för [ARIA-hjälpmedelsetiketter](https://www.w3.org/WAI/standards-guidelines/aria/) för komponenten.

* **Etikett** - Värdet för ett ARIA-etikettattribut för komponenten

## Välj panel {#select-panel}

Innehållsförfattaren kan använda alternativet **Välj panel** i komponentens verktygsfält för att ändra till en annan panel för redigering samt för att enkelt ordna om flikarna.

![Välj panelikon](/help/assets/select-panel-icon.png)

När du har valt alternativet **Välj panel** i komponentverktygsfältet visas de konfigurerade flikarna som en listruta.

* Listan ordnas efter flikarnas tilldelade ordning och återspeglas i numreringen.
* Flikens komponenttyp visas först, följt av tabbbeskrivningen med ett ljusare teckensnitt.

![Välj panelläge](/help/assets/select-panel-popover.png)

* Om du trycker eller klickar på en post i listrutan växlar vyn i redigeraren till den fliken.
* Du kan ordna om flikarna på plats med hjälp av draghandtagen.

>[!NOTE]
>
>Flikar kan inte markeras av författaren i läget **Redigera**. Använd läget **[Förhandsgranska](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#preview-mode)** eller alternativet **[Visa som publicerad](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)** om du vill interagera med flikarna på samma sätt som en läsare av det publicerade innehållet.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera vilka komponenter som kan läggas till som objekt i flikkomponenten samt definiera vilka anpassade format som är tillgängliga för innehållsförfattaren.

### Fliken Tillåtna komponenter {#allowed-components-tab}

Fliken **Tillåtna komponenter** används för att definiera vilka komponenter som innehållsförfattaren kan lägga till som objekt i flikkomponenten.

Fliken Tillåtna komponenter fungerar på samma sätt som fliken med samma namn när [du definierar principen och egenskaperna för en layoutbehållare i mallredigeraren.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)

### Fliken Format {#styles-tab}

Tabbar-komponenten stöder AEM [Style System](/help/get-started/authoring.md#component-styling).

## Adobe Client Data Layer {#data-layer}

Tabb-komponenten stöder [Adobe-klientdatalagret.](/help/developing/data-layer/overview.md)
