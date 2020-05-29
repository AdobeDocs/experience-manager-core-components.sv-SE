---
title: Integrera kärnkomponenter och Adobe Analytics med Adobe Client Data Layer
description: Så här konfigurerar du Adobe Analytics för att registrera Core Component Events
translation-type: tm+mt
source-git-commit: f930a0d6004a29369b189137dd9c52e637ea3a61
workflow-type: tm+mt
source-wordcount: '1000'
ht-degree: 0%

---


# Integrera kärnkomponenter och Adobe Analytics med Adobe Client Data Layer {#analytics-integration}

I det här dokumentet beskrivs hur du konfigurerar en totallösning baserad på AEM, Adobe Client Data Layer, Adobe Launch och Adobe Analytics för att spåra:

* Det sid-ID som lagras i Adobe Client Data Layer när en sida läses in
* Den bildsökväg som lagras i Adobe Client Data Layer när någon klickar på en bild

Detta använder kärnkomponenterna som exempel, men kan användas för dina egna anpassade komponenter.

##  Steg 1 - Skapa rapportsviten i Adobe Analytics {#create-report-suite}

To aggregate and analyze your data, a report suite first must be created.

1. Gå till `https://analytics.adobe.com`.
1. Logga in med ditt Adobe ID.
1. Klicka på **Analytics** -ikonen.
1. Go to **Admin -> Report Suites**.
1. Click **Create New -> Report Suite**.
1. Fill the form:
   1. **Report Suite ID**: `yourSuiteID`
   1. **Site Title**: `Your suite description`
   1. **Time Zone**: As appropriate
   1. **Go Live Date**: dagens datum eller, om det är lämpligt
   1. **Beräknade sidvisningar per dag**: 100 eller
1. Click **Create Report Suite**.

Om du lyckas får du följande meddelande i grönt: `Report Suite <yourReportSuite> has been successfully created.`

## Step 2 - Make the Report Suite Visible {#make-visible}

To use the new report suite, it has to be visible.

1. Gå till `https://adminconsole.adobe.com`.
1. Logga in med ditt Adobe ID.
1. Click the **Adobe Analytics - &lt;yourSite>** card
1. Click the **Adobe Analytics - &lt;yourSite>** link
1. Select the **Permissions** tab
1. Click the **Edit** button of the **Report Suites** row
1. Click the **+** button of the report suite you created in [step 1](#create-report-suite) to add it to the **Included Permission Items** category.
1. Click **Save**.

## Step 3 - Integrate Your AEM Site with Adobe Launch {#integrate-launch}

Launch måste integreras med din AEM-webbplats för att data ska kunna genereras.

Follow the steps in the [Using Adobe Client Data Layer to Integrate Core Components and Adobe Launch](launch-integration.md) document.

## Step 4 - Install and Configure the Adobe Analytics Extension in Adobe Launch {#install-extension}

Med Adobe Analytics Extension kan Analytics integreras med Launch.

1. In Adobe Launch select the newly added property that you created in [step 3.](#integrate-launch)
1. Gå till fliken **Tillägg** och välj **Katalog**.
1. Search for **Adobe Analytics**.
1. Klicka på **Installera**.
1. Konfigurera tillägget.
   1. Ange **Analytics Report Suite-ID** som skapats i [steg 1](#create-report-suite) för rätt miljöer
   1. Ange **teckenuppsättning** till UTF-8
1. Klicka på Spara

## Steg 5 - Skapa ett dataelement i Adobe Launch för sid-ID {#create-data-element}

Ett dataelement krävs i Launch för att kunna spåra sid-ID:t.

1. I Adobe Launch väljer du den egenskap som skapades i [steg 3.](#integrate-launch)
1. Markera fliken **Dataelement** och klicka på **Lägg till dataelement**:
   1. **Namn**: `dl-page-id`
   1. **Tillägg**: **Core**
   1. **Dataelementtyp**: **Egen kod**
1. Klicka på **Öppna redigerare**
1. Ange koden i redigeraren: `return adobeDataLayer.getState().page.id;`
1. Click **Save**.
1. Klicka på **Spara** för att skapa dataelementet.

## Step 6 - Create a Rule in Adobe Launch to Track the Page ID in Analytics {#track-page}

Rules allow tracking of browsing attributes like page ID in Analytics.

Repeat the steps in Part 5b of the [Using Adobe Client Data Layer to Integrate Core Components and Adobe Launch](launch-integration.md#launch-rule) document to add the following rule in Adobe Launch:

* **Namn**: `track-dl-page-id`
* HÄNDELSER:
   * **Tillägg**: **Core**
   * **Event Type**: **Page Bottom**
* ÅTGÄRD 1:
   * **Extension**: **Adobe Analytics**
   * **Action Type**: **Set Variables**
   * **prop1**: `%dl-page-id%`
* ÅTGÄRD 2:
   * **Extension**: **Adobe Analytics**
   * **Action Type**: **Send Beacon**
   * Check **s.t(): Send Data to Adobe Analytics and treat it as a page view**

## Step 7 - Create a Rule in Adobe Launch to Register the Image Click Event {#register-click}

Rules allow tracking of browsing attributes like click events in Analytics.

Repeat the steps in Part 5b of the [Using Adobe Client Data Layer to Integrate Core Components and Adobe Launch](launch-integration.md#launch-rule) document to add the following rule in Adobe Launch:

* **Namn**: `register-dl-image-click`
* HÄNDELSER:
   * **Tillägg**: **Core**
   * **Händelsetyp**: **Sidan nederst**
* ÅTGÄRD 1:
   * **Tillägg**: **Core**
   * **Åtgärdstyp**: **Egen kod**
   * Editor: Enter the following code

      ```
      var myListener = function(event) {
        _satellite.track('dlImageClicked', event.info.path);
      };
      adobeDataLayer.addEventListener('image clicked', myListener());
      ```

## Steg 8 - Skapa en regel i Adobe Launch för att spåra klickningshändelsen i bilden i Analytics {#track-click}

Rules allow tracking of browsing attributes like click events in Analytics.

Repeat the steps in Part 5b of the [Using Adobe Client Data Layer to Integrate Core Components and Adobe Launch](launch-integration.md#launch-rule) document to add the following rule in Adobe Launch:

* **Namn**: `track-dl-image-click`
* HÄNDELSER:
   * **Tillägg**: **Core**
   * **Event Type**: **Direct Call**
   * **Identifierare**: `dlImageClicked`
* ÅTGÄRD 1:
   * **Extension**: **Adobe Analytics**
   * **Action Type**: **Set Variables**
   * **prop2**: Ange som `%event.detail%`
* ÅTGÄRD 2:
   * **Extension**: **Adobe Analytics**
   * **Action Type**: **Send Beacon**
   * Check **s.t(): Send Data to Adobe Analytics and treat it as a page view**

## Step 9 - Publish the Launch Code to Your Website {#publish-launch}

To enable the tracking of these rules and properties in Launch, the code must be published.

1. In the **Adobe Launch** tab, select the **Publishing** tab.
1. Klicka på **Lägg till nytt bibliotek**.
1. As **Name** enter: `data-layer-analytics-1`.
1. As **Environment** select **Development (development)**.
1. Click **Add All Changed Resources**.
1. För var och en av de tre reglerna (`track-dl-page-id`, `register-dl-image-click` och `track-dl-image-click`):
1. Select **Rules -> rule -> Latest** and click **Select &amp; Create a New Revision**.
1. Click **Save &amp; Build for Development**.

## Step 10 - Trigger Your Page to Send Information to Adobe Analytics {#trigger-page}

I det här steget ska du installera Chrome-tillägget **Launch och DTM Switch**. Med det här tillägget behöver du bara skapa och distribuera startkoden till utvecklingsmiljön. Du behöver inte driftsätta miljöer för förproduktion och produktion.

1. Installera Chrome-tillägget **Launch och DTM Switch** från Discovery.
1. Klicka på ikonen **Starta växling** och ställ in felsökningen på *PÅ*.
1. Läs in sidan igen `http://<host>:<port>/content/core-components-examples/library/image.html`.
1. Öppna webbläsarkonsolen så ser du något som liknar följande.

![Utdata från Analytics Console](/help/assets/analytics-console-output.png)

>[!TIP]
>
>Du kan också installera **Experience Cloud Debugger** -tillägget för Chrome om du vill visa Adobe Launch- och Analytics-specifik information om sidan.

## Steg 11 - Visa den spårade informationen i Adobe Analytics {#view-info}

Nu kan du se de händelser du utlöste i Adobe Analytics.

1. Gå till `https://analytics.adobe.com`.
1. Logga in med ditt Adobe ID.
1. Klicka på **Analytics** -ikonen.
1. Select the **Reports** tab.
1. I listrutan högst upp till höger väljer du den rapportserie du skapade i [steg 1.](#create-report-suite)
1. In the first column select **Custom Traffic -> Custom Traffic 1-10 -> Custom Insight 1** to view the tracked page IDs (paths) stored in the Data Layer. Det ska se ut ungefär så här.

   ![Custom insight 1](/help/assets/custom-insight-1.png)

1. Access the **Custom Insight 2** to view the tracked image paths stored in the Data Layer. Det ska se ut ungefär så här.

   ![Custom insight 2](/help/assets/custom-insight-2.png)
