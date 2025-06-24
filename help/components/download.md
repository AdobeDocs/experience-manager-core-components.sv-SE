---
title: Ladda ned komponent
description: Med komponenten Core Component Download kan du skapa ett nedladdningsalternativ på en sida.
role: Architect, Developer, Admin, User
exl-id: 48e7ade0-b849-4d1f-b836-51196e5ac507
source-git-commit: dd30def59a8f037864da875ef4c831b11f766e57
workflow-type: tm+mt
source-wordcount: '741'
ht-degree: 0%

---


# Ladda ned komponent{#download-component}

Med komponenten Core Component Download kan du skapa ett nedladdningsalternativ på en sida.

{{traditional-aem}}

## Användning {#usage}

Med komponenten Core Component Download kan du inkludera ett nedladdningsalternativ och tillhörande resurser på en sida.

* Hämtningsalternativets egenskaper kan väljas i dialogrutan [Konfigurera](#configure-dialog).
* Standardvärden för den hämtade komponenten kan definieras i [designdialogrutan](#design-dialog).

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Download Component är v2, som introducerades i version 2.18.0 av Core Components i februari 2022, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponenterna är kompatibla med samt länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|--- |--- |---|---|---|
| v2 | - | Kompatibel | Kompatibel | Kompatibel |
| [v1](v1/download.md) | Kompatibel | Kompatibel | - | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill visa Download Component och exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [Component Library](https://adobe.com/go/aem_cmp_library_download).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om nedladdningskomponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_download_v2).

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera nedladdningsobjektet och hur det kommer att fungera och visas för en besökare på sidan.

![Fliken Resurser i dialogrutan Redigera i nedladdningskomponenten](/help/assets/download-edit-asset.png)

### Fliken Resurser {#asset-tab}

Valet av en hämtningsresurs liknar funktionen hos [Image Component](image.md) och använder även AEM DAM.

* **Hämta resurs**
   * Släpp en resurs från [resursläsaren](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) eller tryck på alternativet **bläddra** om du vill överföra från ett lokalt filsystem.
   * Tryck eller klicka på **Radera** för att avmarkera den markerade bilden.
   * Tryck eller klicka på **Redigera** om du vill [hantera återgivningarna av resursen](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) i resursredigeraren.

### Fliken Egenskaper {#properties-tab}

![Fliken Egenskaper i dialogrutan Redigera i nedladdningskomponenten](/help/assets/download-edit-properties.png)

* **Titel** - Visar som rubrik för det hämtade objektet
   * **Hämta titel från DAM-resurs** - När du väljer det här alternativet fylls titeln automatiskt i med DAM-resursens titel.
* **Beskrivning** - Visar en beskrivande underrubrik för det hämtade objektet
   * **Hämta beskrivning från DAM-resurs** - När du väljer det här alternativet fylls beskrivningen automatiskt i med DAM-resursens beskrivning.
* **Åtgärdstext** - Visar som åtgärdstext för det hämtade objektet
   * Det här fältet är obligatoriskt när du överför en resurs från filsystemet.
   * **Visa textbunden** - När det här alternativet är markerat visas **åtgärdstexten** textbundet.
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [datalagret](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

### Fliken Format {#styles-tab-edit}

![Fliken Stilar i redigeringsdialogrutan för komponenten Download (Hämta komponent)](/help/assets/download-edit-styles.png)

Komponenten Download stöder AEM [Style System.](/help/get-started/authoring.md#component-styling).

Använd listrutan för att välja de format som du vill använda på komponenten. Markeringar som görs i redigeringsdialogrutan har samma effekt som de som väljs i komponentverktygsfältet.

Format måste konfigureras för den här komponenten i [designdialogrutan](#design-dialog) för att den nedrullningsbara menyn ska vara tillgänglig.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera de alternativ som är tillgängliga för den innehållsförfattare som använder komponenten Download.

### Fliken Egenskaper {#properties-tab-design}

![Dialogrutan Design för komponenten Download Component](/help/assets/download-design.png)

* **Tillåt överföring från filsystemet** - Innehållsförfattaren kan överföra en resurs från sitt lokala filsystem som hämtningsresurs.
   * Standardvärdet är omarkerat.
* **Titeltyp** - Det HTML-element som används för nedladdningskomponentens rubrik.
   * Om inget värde är markerat är standardvärdet H3.
* **Visa filstorlek** - När du väljer det här alternativet visas resursens filstorlek i hämtningskomponenten.
   * Standardvärdet är valt.
* **Visa filformat** - När du väljer det här alternativet visas resursens filformat i hämtningskomponenten.
   * Standardvärdet är valt.
* **Visa filnamn** - När du väljer det här alternativet visas resursens filnamn i hämtningskomponenten.
   * Standardvärdet är valt.

### Fliken Format {#styles-tab}

Bildkomponenten stöder AEM [Style System](/help/get-started/authoring.md#component-styling).
