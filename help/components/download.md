---
title: Ladda ned komponent
description: Med komponenten Core Component Download kan du skapa ett nedladdningsalternativ på en sida.
role: Architect, Developer, Administrator, Business Practitioner
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 1%

---


# Ladda ned komponent{#download-component}

Med komponenten Core Component Download kan du skapa ett nedladdningsalternativ på en sida.

## Användning {#usage}

Med komponenten Core Component Download kan du inkludera ett nedladdningsalternativ och tillhörande resurser på en sida.

* Hämtningsalternativets egenskaper kan väljas i [konfigurationsdialogrutan](#configure-dialog).
* Standardvärden för nedladdningskomponenten kan definieras i [designdialogrutan](#design-dialog).

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Download Component är v1, som introducerades i version 2.5.0 av Core Components i juni 2019, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Kompatibel | Kompatibel | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempelkomponentutdata {#sample-component-output}

Om du vill visa Download Component och se exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_download).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om nedladdningskomponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_download_v1).

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen till Core Components developer](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera nedladdningsobjektet och hur det kommer att fungera och visas för en besökare på sidan.

![Fliken Resurser i dialogrutan Redigera i nedladdningskomponenten](/help/assets/download-edit-asset.png)

### Fliken Resurs {#asset-tab}

Valet av en hämtningsresurs liknar funktionen hos [Image Component](image.md) och utnyttjar även AEM DAM.

* **Hämta resurs**
   * Släpp en resurs från [resursläsaren](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) eller tryck på **bläddra** om du vill överföra från ett lokalt filsystem.
   * Tryck eller klicka på **Rensa** för att avmarkera den markerade bilden.
   * Tryck eller klicka på **Redigera** för att [hantera återgivningarna av resursen](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) i resursredigeraren.

### Fliken Egenskaper {#properties-tab}

![Egenskaper-fliken i dialogrutan Redigera i Download Component](/help/assets/download-edit-properties.png)

* **Titel**  - Visar som rubrik för nedladdningsartikeln
   * **Hämta titel från DAM-resurs**  - När du väljer det här alternativet fylls titeln automatiskt i med DAM-resursens titel.
* **Beskrivning**  - Visar en beskrivande underrubrik för nedladdningsartikeln
   * **Hämta beskrivning från DAM-resurs**  - När du väljer det här alternativet fylls beskrivningen automatiskt i med DAM-resursens beskrivning.
* **Åtgärdstext**  - Visar som åtgärdstext för nedladdningsobjektet
   * Det här fältet är obligatoriskt när du överför en resurs från filsystemet.
   * **Visa textbundet**  - När du väljer det här alternativet visas  **funktionsmakrotexten** textbundet.
* **ID**  - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i  [datalagret](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

## Designdialog {#design-dialog}

I designdialogrutan kan mallskaparen definiera de alternativ som är tillgängliga för den innehållsförfattare som använder komponenten Download.

### Fliken Egenskaper {#properties-tab-design}

![Designdialogrutan för komponenten Download Component](/help/assets/download-design.png)

* **Tillåt överföring från filsystem**  - Innehållsförfattaren kan överföra en resurs från sitt lokala filsystem som hämtningsresurs.
   * Standardvärdet är omarkerat.
* **Titeltyp**  - HTML-elementet som används för nedladdningskomponentens titel.
   * Om inget värde är markerat är standardvärdet H3.
* **Visa filstorlek**  - När du väljer det här alternativet visas resursens filstorlek i hämtningskomponenten.
   * Standardvärdet är valt.
* **Visa filformat**  - När du väljer det här alternativet visas resursens filformat i hämtningskomponenten.
   * Standardvärdet är valt.
* **Visa filnamn**  - När du väljer det här alternativet visas resursens filnamn i hämtningskomponenten.
   * Standardvärdet är valt.

### Fliken Format {#styles-tab}

Bildkomponenten stöder AEM [Style System](/help/get-started/authoring.md#component-styling).
