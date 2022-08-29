---
title: Ladda ned komponent
description: Med komponenten Core Component Download kan du skapa ett nedladdningsalternativ på en sida.
role: Architect, Developer, Admin, User
exl-id: 48e7ade0-b849-4d1f-b836-51196e5ac507
source-git-commit: 327c239b02e0aecee878784c918bfa98d960530e
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 1%

---

# Ladda ned komponent{#download-component}

Med komponenten Core Component Download kan du skapa ett nedladdningsalternativ på en sida.

## Användning {#usage}

Med komponenten Core Component Download kan du inkludera ett nedladdningsalternativ och tillhörande resurser på en sida.

* Hämtningsalternativets egenskaper kan väljas i [konfigurera dialogruta](#configure-dialog).
* Standardvärden för nedladdningskomponenten kan definieras i [designdialogruta](#design-dialog).

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Download Component är v2, som introducerades i version 2.18.0 av Core Components i februari 2022, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v2 | - | Kompatibel | Kompatibel |
| [v1](v1/download.md) | Kompatibel | Kompatibel | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Huvudkomponentversioner](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill visa Download Component och se exempel på dess konfigurationsalternativ samt HTML och JSON-utdata går du till [Komponentbibliotek](https://adobe.com/go/aem_cmp_library_download).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om nedladdningskomponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_download_v2).

Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera nedladdningsobjektet och hur det kommer att fungera och visas för en besökare på sidan.

![Fliken Resurser i dialogrutan Redigera i nedladdningskomponenten](/help/assets/download-edit-asset.png)

### Fliken Resurser {#asset-tab}

Valet av en hämtningsresurs liknar funktionen i [Bildkomponent](image.md) och använder också AEM DAM.

* **Hämta resurs**
   * Släpp en resurs från [resursläsare](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) eller tryck på **bläddra** om du vill överföra från ett lokalt filsystem.
   * Tryck eller klicka **Rensa** för att avmarkera den markerade bilden.
   * Tryck eller klicka **Redigera** till [hantera återgivningar av resursen](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) i resursredigeraren.

### Fliken Egenskaper {#properties-tab}

![Egenskaper-fliken i dialogrutan Redigera i Download Component](/help/assets/download-edit-properties.png)

* **Titel** - Visar en rubrik för nedladdningsobjektet
   * **Hämta titel från DAM-resurs** - När du väljer det här alternativet fylls titeln automatiskt i med DAM-resursens namn.
* **Beskrivning** - Visar som en beskrivande underrubrik för nedladdningsobjektet
   * **Hämta beskrivning från DAM-resurs** - När du väljer det här alternativet fylls beskrivningen automatiskt i med DAM-resursens beskrivning.
* **Åtgärdstext** - Visar som åtgärdstext för nedladdningsobjektet
   * Det här fältet är obligatoriskt när du överför en resurs från filsystemet.
   * **Visa textbunden** - När det här alternativet har valts **Åtgärdstext** kommer att visas textbundet.
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [Datalager](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

### Fliken Format {#styles-tab-edit}

![Fliken Stilar i redigeringsdialogrutan för komponenten Download](/help/assets/download-edit-styles.png)

Komponenten Download har stöd för AEM [Formatsystem.](/help/get-started/authoring.md#component-styling).

Använd listrutan för att välja de format som du vill använda på komponenten. Markeringar som görs i redigeringsdialogrutan har samma effekt som de som väljs i komponentverktygsfältet.

Format måste konfigureras för den här komponenten i [designdialogruta](#design-dialog) för att den nedrullningsbara menyn ska vara tillgänglig.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera de alternativ som är tillgängliga för den innehållsförfattare som använder komponenten Download.

### Fliken Egenskaper {#properties-tab-design}

![Designdialogrutan för komponenten Download Component](/help/assets/download-design.png)

* **Tillåt överföring från filsystem** - Innehållsförfattaren kan överföra en resurs från sitt lokala filsystem som hämtningsresurs.
   * Standardvärdet är omarkerat.
* **Titeltyp** - Det HTML-element som används för nedladdningskomponentens titel.
   * Om inget värde är markerat är standardvärdet H3.
* **Visa filstorlek** - När du väljer det här alternativet visas resursens filstorlek i nedladdningskomponenten.
   * Standardvärdet är valt.
* **Visa filformat** - När du väljer det här alternativet visas resursens filformat i hämtningskomponenten.
   * Standardvärdet är valt.
* **Visa filnamn** - När du väljer det här alternativet visas resursens filnamn i nedladdningskomponenten.
   * Standardvärdet är valt.

### Fliken Format {#styles-tab}

Bildkomponenten stöder AEM [Formatsystem](/help/get-started/authoring.md#component-styling).
