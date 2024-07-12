---
title: Ladda ned komponent (v1)
description: Med komponenten Core Component Download kan du skapa ett nedladdningsalternativ på en sida.
role: Architect, Developer, Admin, User
exl-id: ebd63522-218d-4784-bea0-1627c64f5230
source-git-commit: e291d4c1bfd37292d68c236178f9681c4e5ee741
workflow-type: tm+mt
source-wordcount: '621'
ht-degree: 0%

---

# Ladda ned komponent (v1) {#download-component}

Med komponenten Core Component Download kan du skapa ett nedladdningsalternativ på en sida.

## Användning {#usage}

Med komponenten Core Component Download kan du inkludera ett nedladdningsalternativ och tillhörande resurser på en sida.

* Hämtningsalternativets egenskaper kan väljas i dialogrutan [Konfigurera](#configure-dialog).
* Standardvärden för den hämtade komponenten kan definieras i [designdialogrutan](#design-dialog).

## Version och kompatibilitet {#version-and-compatibility}

I det här dokumentet beskrivs v1 i Download Component, som introducerades i version 2.5.0 av Core Components i juni 2019.

>[!CAUTION]
>
>I det här dokumentet beskrivs v1 för komponenten Download.
>
>Mer information om den aktuella versionen av nedladdningskomponenten finns i dokumentet [Hämta komponent](/help/components/download.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill visa hämtningskomponenten och se exempel på dess konfigurationsalternativ samt HTML och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_download).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om nedladdningskomponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_download_v1).

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera nedladdningsobjektet och hur det kommer att fungera och visas för en besökare på sidan.

![Fliken Resurser i dialogrutan Redigera i nedladdningskomponenten](/help/assets/download-edit-asset.png)

### Fliken Resurser {#asset-tab}

Valet av en hämtningsresurs liknar funktionen hos [Image Component](image-v1.md) och utnyttjar även AEM DAM.

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
