---
title: Använda Adobe Client Data Layer för att integrera Core Components och Adobe Launch
description: Så här konfigurerar du Adobe Launch för att registrera Core Component-händelser med Adobe Launch
translation-type: tm+mt
source-git-commit: 85fb3612aed12b7bfdc05f0a569ae7c7364e6121
workflow-type: tm+mt
source-wordcount: '1160'
ht-degree: 0%

---


# Använda Adobe Client Data Layer för att integrera Core Components och Adobe Launch {#launch-integration}

Core-komponenterna kan integreras med Adobe Launch genom att använda Adobe Client Data Layer. I det här dokumentet beskrivs hur du konfigurerar Adobe Launch för att spåra klickningshändelser för bildkomponenter som ett exempel.

När Launch är konfigurerat skapas följande utdata i webbläsarkonsolen när någon klickar på en Core Image-komponent.

![Exempel på konsolutdata](/help/assets/launch-console-output.png)

## Starta integrering med AEM {#launch-aem}

Första Adobe Launch måste integreras med AEM.

### Steg 1 - Skapa en integrering i Adobe I/O {#create-io-integration}

Logga först in på Adobe I/O för att börja konfigurera en integrering.

1. Gå till `https://console.adobe.io`.
1. Logga in med din Adobe ID.
1. Klicka på **Skapa integrering** i snabbstartsavsnittet.
1. Välj **Åtkomst till ett API** och klicka på **Fortsätt**.
1. Markera **Experience Platform Launch API** under Adobe Experience Platform och klicka på **Fortsätt**.

### Steg 2 - Skapa en IMS-konfiguration i AEM {#ims-configuration}

I AEM måste du definiera den integration som du började konfigurera i Adobe I/O.

1. Gå till AEM startsida och klicka på **Verktyg -> Säkerhet -> Adobe IMS-konfigurationer**.
1. Klicka på **Skapa**.
1. Som **molnlösning** väljer du **Adobe Launch**.
1. Markera **Skapa nytt certifikat**.
1. Ange ett alias för certifikatet, till exempel **aem-launch-certificate**.
1. Klicka på **Skapa certifikat** och skapa certifikatet genom att klicka på **OK** i popup-fönstret.
1. Klicka på **Hämta offentlig nyckel** och klicka på **Hämta** i popup-fönstret.

### Steg 3 - Slutför konfigurationen av Adobe I/O {#finish-io}

När certifikatet och nyckeln har skapats i AEM IMS-konfiguration kan du slutföra Adobe I/O-konfigurationen.

1. Gå tillbaka till Adobe I/O-konsolen som i [steg 1.](#create-io-integration)
1. I fönstret **Skapa en ny integrering** anger du ett namn och en beskrivning, till exempel **AEM datalagret** Launch.
1. Under certifikat för **offentliga nycklar**&#x200B;överför du certifikatet som du skapade i [steg 2.](#ims-configuration)
1. Välj profilen **** Launch - Prod.
1. Klicka på **Skapa integrering**.
1. Klicka på **Fortsätt för integreringsinformation**. Du behöver dessa uppgifter senare för att slutföra IMS-konfigurationen i din AEM.

### Steg 4 - Slutför IMS-konfiguration {#finish-ims}

Med integreringsinformationen för Adobe I/O kan du slutföra den AEM IMS-konfigurationen.

1. På fliken AEM på fliken Konfiguration **av** Adobe IMS-konto från [steg 2,](#ims-configuration) klickar du på **Nästa**.
1. Ange en titel, till exempel **IMS-konfiguration för Adobe Launch**.
1. På fliken Adobe I/O kopierar du **API-nyckeln (klient-ID)**.
1. Klistra in den tidigare kopierade nyckeln i fältet **** API-nyckel på fliken AEM.
1. I Adobe I/O klickar du på **Hämta klienthemlighet** och kopierar den.
1. Klistra in den i fältet **Klienthemlighet** på fliken AEM.
1. På fliken Adobe I/O väljer du fliken **JWT** och kopierar URL-adressen, till exempel `https://ims-na1.adobelogin.com`.
1. Klistra in URL-adressen i fältet **Auktoriseringsserver** på fliken AEM.
1. På fliken Adobe I/O kopierar du JWT-nyttolasten (koden mellan klammerparenteserna).
1. Klistra in den i fältet **Nyttolast** på fliken AEM.
1. Klicka på **Skapa** för att skapa IMS-konfigurationen i AEM.

### Steg 5a - Skapa en egenskap i Adobe Launch {#create-property}

En egenskap definierar funktioner som kan injiceras på webbplatsen med Launch.

1. Gå till Adobe Launch på `https://launch.adobe.com`.
1. Logga in med din Adobe ID.
1. Klicka på **Ny egenskap**.
1. Ange ett namn som **Starta AEM datalager**.
1. Ange din domän.
1. Click **Save**.

### Steg 5b - Skapa en regel i Launch {#launch-rule}

Med den egenskap du skapade kan du definiera en regel som anger vad som ska hända när en åtgärd utförs.

1. Klicka på den nyligen tillagda egenskapen i [steg 5](#create-property) **Starta AEM datalager**.
1. Välj fliken **Regler** och klicka på **Skapa ny regel**.
1. Ange ett namn, till exempel **bildklickning**.
1. Klicka på **+** under **Händelser**.
1. Välj **Core** som **tillägg**, **klicka** som **händelsetyp** och ange **.cmp-image** **** som¥CSS-väljare¥.
1. Klicka på **Behåll ändringar**.
1. Klicka på **+** -knappen under **Åtgärder**.
1. Välj **Core** as **Extension**, **Custom Code** as **Action Type** och klicka på **Open Editor**.
1. Ange följande kod i redigeraren: `console.log("DOM click event tracked by Launch for image: ", event.target.src);`
1. Click **Save**.
1. Klicka på **Behåll ändringar**.
1. Klicka på **Spara** för att skapa den nya regeln.

### Steg 6 - Publicera startregeln {#publish-rule}

Om du vill göra den nya regeln tillgänglig för din AEM webbplats måste du publicera den.

1. På fliken **Adobe Launch** väljer du fliken **Publishing** .
1. Klicka på **Lägg till nytt bibliotek**.
1. Ange ett **namn** , till exempel **demo-1**.
1. I **Miljö** väljer du lämpligt, till exempel **Utveckling**.
1. Klicka på **Lägg till en resurs**.
1. Välj **Regler -> bild-klicka -> Senaste** och klicka på **Markera och skapa en ny ändring**.
1. Klicka på **Spara och bygg för utveckling**.
1. Klicka på **Använd uppdateringar och fortsätt** på popup-menyn.
1. När biblioteket har byggts klickar du på ellipsikonen och väljer **Skicka för godkännande**.
1. Klicka på **Skicka** på popup-menyn.
1. Klicka på ellipsikonen och välj **Skapa för förproduktion**.
1. När bygget är klart klickar du på ellipsikonen och väljer **Godkänn för publicering**.
1. Klicka på **Godkänn** på popup-menyn.
1. Klicka på ellipsikonen och välj **Skapa och publicera i produktion**.
1. Klicka på **Publicera** på popup-menyn.

### Steg 7 - Aktivera molnkonfigurationer för din webbplats {#enable-configurations}

För att kunna använda integreringen måste den tilldelas i AEM som en molnkonfiguration.

1. I AEM klickar du på **Verktyg -> Allmänt -> Konfigurationsläsaren**.
1. Kontrollera **kärnkomponentexemplen** och klicka på **Egenskaper**.
1. Kontrollera **molnkonfigurationerna** och klicka på **Spara och stäng**.

### Steg 8 - Skapa en startintegrering med din webbplats i AEM {#create-launch-integration}

En Launch-integrering krävs för att AEM ska kunna arbeta med Launch

1. I AEM klickar du på **Verktyg -> Cloud Services -> Starta konfigurationer** för Adobe.
1. Välj Exempel på **kärnkomponent** och klicka på **Skapa**.
1. Ange en **titel** , till exempel **Starta konfiguration**.
1. Välj den IMS-konfiguration som du skapade i [steg 4.](#finish-ims)
1. Som **företag** väljer du det som passar bäst.
1. Som **egenskap** väljer du den nyligen tillagda Launch-egenskapen som skapades i [steg 5.](#create-property)
1. Flytta reglaget **Inkludera produktionskod på författare** åt höger och klicka på **Nästa**.
1. Klicka på **Nästa**.
1. Klicka på **Nästa**.
1. Klicka på **Skapa**.

### Steg 9 - Anslut AEM till startintegreringen {#connect-aem}

För att AEM ska kunna använda Launch-integreringen måste den tilldelas som en molnkonfiguration.

1. I AEM klickar du på **Platser** och kontrollerar **Core** Components-webbplatsen.
1. Klicka på **Egenskaper**.
1. Välj fliken **Avancerat** .
1. Som **molnkonfiguration** väljer du Exempel på **kärnkomponenter** och klickar på **Välj**.
1. Klicka på **Spara och stäng**.

### Steg 10 - Verifiera att startlogiken används på sidan {#verify-launch}

Testa att stegen hittills har slutförts.

1. Öppna bildsidan i Core Components Library i förhandsgranskningsläge: `http://<lhost&gt;:<port&gt;/editor.html/content/core-components-examples/library/page-authoring/image.html`
1. Klicka på en bild och kontrollera att meddelandet `A Core Image was clicked` visas i webbläsarkonsolen.

## Starta integrering med AEM och datalagret {#data-layer-launch}

Nu när integrationen mellan AEM och Launch är klar kan vi integrera med datalagret.

### Steg 1 - Skapa en regel i Adobe Launch {#create-rule}

Upprepa stegen i [steg 5](#launch-rule) för att lägga till en ny regel i Adobe Launch med följande värden.

* Namn: `image-click-data-layer`
* HÄNDELSER:
   * Tillägg: Core
   * Händelsetyp: DOM-klart
* ÅTGÄRDER:
   * Tillägg: Core
   * Åtgärdstyp: Egen kod
   * Kod:

      ```
        function onImageClick(event) {
          console.log("Data layer click event tracked by Launch for image: " + event.info.path);
          console.log("dataLayer.getState(): ", adobeDataLayer.getState()); 
        }
        adobeDataLayer.addEventListener('image clicked', onImageClick);
      ```

### Steg 2 - Publicera startregeln så att den blir tillgänglig för din AEM webbplats {#publish-rule-2}

Upprepa stegen i [steg 6](#publish-rule) för att publicera den nya regeln.

### Steg 3 - Verifiera att startlogiken används på sidan {#verify}

1. Öppna bildsidan i Core Components Library i förhandsgranskningsläge: `http://<host&gt;:<port&gt;/editor.html/content/core-components-examples/library/page-authoring/image.html`
1. Klicka på en bild och kontrollera att följande meddelande visas i webbläsarkonsolen:

   ![Data Layer Console output](/help/assets/data-layer-console-output.png)
