---
title: Ladda ned komponent (v1)
description: Med komponenten Core Component Download kan du skapa ett nedladdningsalternativ på en sida.
role: Architect, Developer, Admin, User
source-git-commit: f8aa86d58ba71ede3c3cd867c45aafff06923325
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 0%

---


# Ladda ned komponent (v1) {#download-component}

Med komponenten Core Component Download kan du skapa ett nedladdningsalternativ på en sida.

## Användning {#usage}

Med komponenten Core Component Download kan du inkludera ett nedladdningsalternativ och tillhörande resurser på en sida.

* Hämtningsalternativets egenskaper kan väljas i [konfigurera dialogruta](#configure-dialog).
* Standardvärden för nedladdningskomponenten kan definieras i [designdialogruta](#design-dialog).

## Version och kompatibilitet {#version-and-compatibility}

I det här dokumentet beskrivs v1 i Download Component, som introducerades i version 2.5.0 av Core Components i juni 2019.

>[!CAUTION]
>
>I det här dokumentet beskrivs v1 för komponenten Download.
>
>Information om den aktuella versionen av komponenten Download finns i [Ladda ned komponent](/help/components/download.md) -dokument.

## Exempel på komponentutdata {#sample-component-output}

Om du vill visa Download Component och se exempel på dess konfigurationsalternativ samt HTML och JSON-utdata går du till [Komponentbibliotek](https://adobe.com/go/aem_cmp_library_download).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om nedladdningskomponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_download_v1).

Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera nedladdningsobjektet och hur det kommer att fungera och visas för en besökare på sidan.

![Fliken Resurser i dialogrutan Redigera i nedladdningskomponenten](/help/assets/download-edit-asset.png)

### Fliken Resurser {#asset-tab}

Valet av en hämtningsresurs liknar funktionen i [Bildkomponent](image-v1.md) och använder också AEM DAM.

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
