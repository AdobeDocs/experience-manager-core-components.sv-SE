---
title: Ladda ned komponent
description: Med komponenten Core Component Download kan du skapa ett nedladdningsalternativ på en sida.
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# Ladda ned komponent{#download-component}

Med komponenten Core Component Download kan du skapa ett nedladdningsalternativ på en sida.

## Användning {#usage}

Med komponenten Core Component Download kan du inkludera ett nedladdningsalternativ och tillhörande resurser på en sida.

* Egenskaperna för nedladdningsalternativet kan väljas i [konfigurationsdialogrutan](#configure-dialog).
* Standardvärden för nedladdningskomponenten kan definieras i [designdialogrutan](#design-dialog).

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Download Component är v1, som introducerades i version 2.5.0 av Core Components i juni 2019, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponentversionerna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|---|
| v1 | Kompatibel | Kompatibel | Kompatibel | Kompatibel |

Mer information om Core Component-versioner och -versioner finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill visa Download Component och se exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [Component Library](https://adobe.com/go/aem_cmp_library_download).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om nedladdningskomponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_download_v1).

Mer information om hur du utvecklar kärnkomponenter finns i dokumentationen till [Core Components Developer](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera nedladdningsobjektet och hur det kommer att fungera och visas för en besökare på sidan.

![](/help/assets/screen-shot-2019-06-17-09.49.14.png)

### Fliken Resurser {#asset-tab}

Valet av en hämtningsresurs liknar funktionen hos [Image Component](image.md) och utnyttjar även AEM:s DAM.

* **Hämta resurs**
   * Släpp en resurs från [resursläsaren](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) eller tryck på **bläddringsalternativet** om du vill överföra den från ett lokalt filsystem.
   * Tryck eller klicka på **Radera** för att avmarkera den markerade bilden.
   * Tryck eller klicka på **Redigera** för att [hantera återgivningarna av resursen](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) i resursredigeraren.

### Fliken Egenskaper {#properties-tab}

![](/help/assets/screen-shot-2019-06-17-09.49.51.png)

* **Titel** - Visar som rubrik för nedladdningsartikeln
   * **Hämta titel från DAM-resurs** - När du väljer det här alternativet fylls titeln automatiskt i med DAM-resursens titel.
* **Beskrivning** - Visar en beskrivande underrubrik för nedladdningsartikeln
   * **Hämta beskrivning från DAM-resurs** - När du väljer det här alternativet fylls beskrivningen automatiskt i med DAM-resursens beskrivning.
* **Åtgärdstext** - Visar som åtgärdstext för nedladdningsobjektet
   * Det här fältet är obligatoriskt när du överför en resurs från filsystemet.
   * **Visa textbundet** - När du väljer det här alternativet visas den angivna **åtgärdstexten** textbundet.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera de alternativ som är tillgängliga för den innehållsförfattare som använder komponenten Download.

### Fliken Egenskaper {#properties-tab-design}

![](/help/assets/screen-shot-2019-06-17-10.04.31.png)

* **Standardåtgärdstext** - Definierar den **standardåtgärdstext** som ges när en författare lägger till hämtningskomponenten på en sida.
* **Tillåt överföring från filsystem** - Innehållsförfattaren kan överföra en resurs från sitt lokala filsystem som hämtningsresurs.
   * Standardvärdet är omarkerat.
* **Titeltyp** - HTML-elementet som används för nedladdningskomponentens titel.
   * Om inget värde är markerat är standardvärdet H3.
* **Visa filstorlek** - När du väljer det här alternativet visas resursens filstorlek i hämtningskomponenten.
   * Standardvärdet är valt.
* **Visa filformat** - När du väljer det här alternativet visas resursens filformat i hämtningskomponenten.
   * Standardvärdet är valt.
* **Visa filnamn** - När du väljer det här alternativet visas resursens filnamn i hämtningskomponenten.
   * Standardvärdet är valt.

### Fliken Format {#styles-tab}

Bildkomponenten stöder AEM [Style System](/help/get-started/authoring.md#component-styling).
