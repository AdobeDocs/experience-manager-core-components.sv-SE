---
title: Tabbar-komponent
description: Med flikkomponenten kan du skapa flera flikar för att ordna innehåll på en sida.
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# Tabbar-komponent

Med komponenten Core Component Tabs kan du ordna innehåll på flera flikar.

## Användning {#usage}

Med flikkomponenten kan innehållsförfattaren ordna sidinnehåll på flera flikar.

I [redigeringsdialogrutan](#edit-dialog) kan innehållsförfattaren definiera flera flikar samt ställa in den aktiva fliken. I [designdialogrutan](#design-dialog)kan mallskaparen definiera vilka komponenter som kan läggas till på flikar och anpassa formaten.

>[!NOTE]
>
>Kapslade flikkomponenter (tabbar på flikar) stöds.
>
>Enkla (ej kapslade) flikkomponenter kan hittas/väljas med [innehållsträdet](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html#content-tree), men det går inte att kapsla flikar.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av komponenten Tabs är v1, som introducerades i version 2.2.0 av Core Components i oktober 2018, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponentversionerna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |--- |---|
| v1 | Kompatibel | Kompatibel | Kompatibel | Kompatibel |

Mer information om Core Component-versioner och -versioner finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill visa flikkomponenten och se exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_tabs).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Tabs-komponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_tabs_v1).

Mer information om hur du utvecklar kärnkomponenter finns i dokumentationen till [Core Components Developer](/help/developing/overview.md).

## Dialogrutan Redigera {#edit-dialog}

I redigeringsdialogrutan kan författaren skapa, byta namn på och ordna om flikar samt definiera den aktiva fliken.

### Fliken Objekt {#items-tab}

![](/help/assets/screen-shot-2019-08-29-12.28.16.png)

Använd knappen **Lägg** till för att öppna komponentväljaren och välja vilken komponent som ska läggas till som en tabb. När du har lagt till en post läggs den till i listan, som innehåller följande kolumner:

* **Ikon** - Ikonen för flikens komponenttyp, vilket gör den enkel att identifiera i listan. För musen över för att se det fullständiga komponentnamnet som ett verktygstips.
* **Beskrivning** - Den beskrivning som används som tabbtext och används som standard för namnet på komponenten som är markerad för fliken.
* **Ta bort** - Tryck eller klicka för att ta bort fliken från flikkomponenten.
* **Ordna** om - Tryck eller klicka och dra för att ordna om flikarna.

>[!TIP]
>
>Om sidans visningsruta minskas så att redigeringsdialogrutan blir helskärm, döljs knappen **Lägg till** . Komponenter kan fortfarande läggas till i flikkomponenten genom att [dra från komponentwebbläsaren och släppa på flikkomponenten i sidredigeraren](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#inserting-a-component).

### Fliken Egenskaper {#properties-tab}

![](/help/assets/screen-shot-2019-08-29-12.28.32.png)

På fliken **Egenskaper** kan innehållsförfattaren definiera vilken flik som ska vara aktiv när sidan läses in. Med alternativet **Standard** markeras den första fliken.

### Fliken Tillgänglighet {#accessibility-tab}

![](/help/assets/screen-shot-2019-08-29-12.28.40.png)

På fliken **Tillgänglighet** kan du ange värden för [ARIA-hjälpmedelsetiketter](https://www.w3.org/WAI/standards-guidelines/aria/) för komponenten.

* **Etikett** - Värdet för ett ARIA-etikettattribut för komponenten

## Välj panel {#select-panel}

Innehållsförfattaren kan använda alternativet **Välj panel** i komponentens verktygsfält för att ändra till en annan panel för redigering samt för att enkelt ordna om flikarna.

![](/help/assets/screenshot_2018-10-11at165417.png)

När du har valt alternativet **Välj panel** i komponentverktygsfältet visas de konfigurerade flikarna som en listruta.

* Listan ordnas efter flikarnas tilldelade ordning och återspeglas i numreringen.
* Flikens komponenttyp visas först, följt av tabbbeskrivningen med ett ljusare teckensnitt.

![](/help/assets/screenshot_2018-10-11at165154.png)

* Om du trycker eller klickar på en post i listrutan växlar vyn i redigeraren till den fliken.
* Du kan ordna om flikarna på plats med hjälp av draghandtagen.

>[!NOTE]
>
>Flikar kan inte markeras av författaren i **redigeringsläge** . Använd **[förhandsgranskningsläget](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#preview-mode)**eller alternativet**[ Visa som publicerat](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)** om du vill interagera med flikarna på samma sätt som en läsare av det publicerade innehållet.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera vilka komponenter som kan läggas till som objekt i flikkomponenten samt definiera vilka anpassade format som är tillgängliga för innehållsförfattaren.

### Fliken Tillåtna komponenter {#allowed-components-tab}

Fliken **Tillåtna komponenter** används för att definiera vilka komponenter som innehållsförfattaren kan lägga till som objekt i flikkomponenten.

Fliken Tillåtna komponenter fungerar på samma sätt som fliken med samma namn när du [definierar principen och egenskaperna för en layoutbehållare i mallredigeraren.](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)

### Fliken Format {#styles-tab}

Tabs-komponenten stöder AEM [Style System](/help/get-started/authoring.md#component-styling).
