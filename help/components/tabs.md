---
title: Tabbar-komponent
description: Med flikkomponenten kan du skapa flera flikar för att ordna innehåll på en sida.
role: Architect, Developer, Admin, User
exl-id: 0031c5f3-447c-4932-898f-2f453801e492
source-git-commit: e8b3e55a42b6be6262d6f51b9569c0be3e8ce6c3
workflow-type: tm+mt
source-wordcount: '1033'
ht-degree: 1%

---

# Tabbar-komponent {#tabs-component}

Med komponenten Core Component Tabs kan du ordna innehåll på flera flikar.

## Användning {#usage}

Med flikkomponenten kan innehållsförfattaren ordna sidinnehåll på flera flikar.

The [redigeringsdialogruta](#edit-dialog) gör att innehållsförfattaren kan definiera flera flikar samt ställa in den aktiva fliken. Använda [designdialogruta](#design-dialog)kan mallskaparen definiera vilka komponenter som kan läggas till på flikar och anpassa formaten.

>[!TIP]
>
>Kapslade flikkomponenter (tabbar inom tabbar) stöds.
>
>Du kan hitta/välja enkla (ej kapslade) flikkomponenter med [innehållsträd](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html#content-tree)men kapslade flikar kan inte användas.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av komponenten Tabs är v1, som introducerades i version 2.2.0 av Core Components i oktober 2018, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v1 | Kompatibel med<br>[version 2.17.4](/help/versions.md) och tidigare | Kompatibel | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Huvudkomponentversioner](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill se både flikkomponenten och exempel på dess konfigurationsalternativ samt HTML och JSON-utdata går du till [Komponentbibliotek](https://adobe.com/go/aem_cmp_library_tabs).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Tabs-komponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_tabs_v1).

Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Djuplänkning till en panel {#deep-linking}

Tabbar, [Carousel,](carousel.md) och [Dragspelskomponenter](accordion.md) har stöd för att länka direkt till en panel i komponenten.

Så här gör du:

1. Visa sidan med komponenten med hjälp av **[Visa som publicerad](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)** i sidredigeraren.
1. Inspect innehållet på sidan och identifierar panelens ID.
   * Till exempel `id="accordion-86196c94d3-item-ca319dbb0b"`
1. ID:t blir det ankare som du kan lägga till i URL:en med ett hash-tecken (`#`).
   * Till exempel `https://wknd.site/content/wknd/language-masters/en/magazine/western-australia.html#accordion-86196c94d3-item-ca319dbb0b`

Om du navigerar till URL-adressen med panel-ID som ankarpunkt, rullar webbläsaren direkt till den aktuella komponenten och visar den angivna panelen. Om panelen inte är konfigurerad att expanderas som standard kommer den att expanderas automatiskt.

## Dialogrutan Redigera {#edit-dialog}

I redigeringsdialogrutan kan författaren skapa, byta namn på och ordna om flikar samt definiera den aktiva fliken.

### Fliken Objekt {#items-tab}

![Fliken Alternativ i dialogrutan Redigera flikkomponent](/help/assets/tabs-edit-items.png)

Använd **Lägg till** för att öppna komponentväljaren och välja vilken komponent som ska läggas till som en tabb. När du har lagt till en post läggs den till i listan, som innehåller följande kolumner:

* **Ikon** - Ikonen för flikens komponenttyp, vilket gör det enkelt att identifiera i listan. För musen över för att se det fullständiga komponentnamnet som ett verktygstips.
* **Beskrivning** - Beskrivningen som används som tabbtext och används som standard för namnet på komponenten som är markerad för tabben.
* **Ta bort** - Tryck eller klicka för att ta bort fliken från tabbkomponenten.
* **Ordna om** - Tryck eller klicka och dra för att ändra ordningen på flikarna.

>[!TIP]
>
>Om sidans visningsruta minskas så att redigeringsdialogrutan blir helskärm, **Lägg till** knappen döljs. Komponenter kan fortfarande läggas till i flikkomponenten av [dra från komponentwebbläsaren och släppa på flikkomponenten i sidredigeraren](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#inserting-a-component).

### Fliken Egenskaper {#properties-tab}

![Fliken Egenskaper i dialogrutan Redigera för flikkomponenter](/help/assets/tabs-edit-properties.png)

* **Aktivt objekt** - Innehållsförfattaren kan definiera vilken flik som är aktiv när sidan läses in.
   * Med **Standard** väljer du den första fliken.
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [Datalager](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

### Fliken Tillgänglighet {#accessibility-tab}

![Flikkomponentens flik i dialogrutan Redigera hjälpmedel](/help/assets/tabs-edit-accessibility.png)

På **Tillgänglighet** -tabb kan värden anges för [Tillgänglighet för ARIA](https://www.w3.org/WAI/standards-guidelines/aria/) -etiketter för komponenten.

* **Etikett** - Värdet på ett ARIA-etikettattribut för komponenten

## Välj panel {#select-panel}

Innehållsförfattaren kan använda **Välj panel** i komponentens verktygsfält för att ändra till en annan panel för redigering samt för att enkelt ordna om tabbordningen.

![Ikonen Välj panel](/help/assets/select-panel-icon.png)

När du har valt **Välj panel** i komponentverktygsfältet visas de konfigurerade flikarna som en listruta.

* Listan ordnas efter flikarnas tilldelade ordning och återspeglas i numreringen.
* Flikens komponenttyp visas först, följt av tabbbeskrivningen med ett ljusare teckensnitt.

![Välj panelpekare](/help/assets/select-panel-popover.png)

* Om du trycker eller klickar på en post i listrutan växlar vyn i redigeraren till den fliken.
* Du kan ordna om flikarna på plats med hjälp av draghandtagen.

>[!NOTE]
>
>Flikarna kan inte markeras av författaren i **Redigera** läge. Använd **[Förhandsgranska](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#preview-mode)** eller **[Visa som publicerad](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)** om du vill interagera med flikarna på samma sätt som en läsare av det publicerade innehållet.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera vilka komponenter som kan läggas till som objekt i flikkomponenten samt definiera vilka anpassade format som är tillgängliga för innehållsförfattaren.

### Fliken Tillåtna komponenter {#allowed-components-tab}

The **Tillåtna komponenter** -fliken används för att definiera vilka komponenter som innehållsförfattaren kan lägga till som -objekt till flikkomponenten.

Fliken Tillåtna komponenter fungerar på samma sätt som fliken med samma namn när [definiera policyn och egenskaperna för en layoutbehållare i mallredigeraren.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)

### Fliken Format {#styles-tab}

Tabbar-komponenten har stöd för AEM [Formatsystem](/help/get-started/authoring.md#component-styling).

## Adobe-klientdatalager {#data-layer}

Tabbar-komponenten har stöd för [Adobe Client Data Layer.](/help/developing/data-layer/overview.md)
