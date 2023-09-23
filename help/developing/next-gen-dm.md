---
title: Nästa generations Dynamic Media-support
description: Lär dig konfigurera Core Component Image och Teaser Components som stöd för nästa generations Dynamic Media-resurser.
role: Architect, Developer, Admin, User
source-git-commit: 9b8930c2e268f52a1377906725db9a05a089e233
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 0%

---


# Nästa generations Dynamic Media-support {#next-gen-dm-support}

Lär dig konfigurera Core Component Image och Teaser Components som stöd för nästa generations Dynamic Media-resurser.

## Hämta den senaste AEM versionen {#latest}

Stöd för nästa generations Dynamic Media-fjärrresurser kräver:

* AEM 6.5 SP 18+ eller AEM as a Cloud Service
* Core Components version 2.23.2 eller senare

## Konfigurera HTTPS {#https}

Det rekommenderas i allmänhet att du kör alla dina produktions- AEM instanser med HTTP. Dina lokala utvecklingsmiljöer kanske inte konfigureras som sådana. Nästa generations Dynamic Media fjärrresurser kräver dock HTTPS för att fungera.

[Använd den här guiden](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/security/use-the-ssl-wizard.html) för att konfigurera HTTPS var du vill använda fjärrresurser, inklusive utvecklingsmiljöer.

## Konfigurera OSGi {#osgi}

Platsen för fjärrresurserna måste definieras i en OSGi-konfiguration. Konfigurera **Nästa generations Dynamic Media Config** OSGi-konfigurationen så här ersätter du värdena med värdena i din resursmiljö.

```text
imsClient="<ims-client-name>"
enabled=B"true"
imsOrg="<ims-org>@AdobeOrg"
repositoryId="<repo-id>.adobeaemcloud.com"
```

![Konfigurationsfönstret för nästa generations Dynamic Media Config OSGi](/help/assets/remote-assets-osgi.png)

Mer information om hur du konfigurerar OSGi finns i följande dokument:

* [Konfigurera OSGi för Adobe Experience Manager as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/deploying/configuring-osgi.html) för AEM as a Cloud Service
* [Konfigurerar OSGi](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/configuring/configuring-osgi.html) för AEM 6.5

## Verifiera konfiguration {#verify}

Nu kan du kontrollera att funktionen för Dynamic Media-fjärrresurser i nästa generation fungerar. Det gör du genom att installera WKND-exempelplatsen och kärnkomponenterna.

* [Kärnkomponenter](https://github.com/adobe/aem-core-wcm-components/releases/download/core.wcm.components.reactor-2.23.2/core.wcm.components.all-2.23.2.zip) version 2.23.2 eller senare krävs.
* [WKND Sample site](https://github.com/adobe/aem-guides-wknd/releases/download/aem-guides-wknd-3.2.0/aem-guides-wknd.all-3.2.0-classic.zip) version 3.2.0 eller senare krävs.

När du har installerat Core Components och WKND kan du testa funktionen på alla WKND-sidor.

1. Öppna AEM med HTTPS.

1. Öppna en WKND-demosida i sidredigeraren, till exempel `https://<host>:<httpsPort>/editor.html/content/wknd/language-masters/en/magazine/arctic-surfing.html`

1. Lägg till en bildkomponent på sidan.

1. Avmarkera alternativet i dialogrutan Konfigurera för komponenten **Ärv bild från sida** på **Tillgång** och klicka **Välj**.

1. Om konfigurationen är korrekt visas en listruta med alternativen **Lokal** och **Fjärr**. Välj **Fjärr**.

   ![Alternativ för fjärrval och lokala val av bild](/help/assets/remote-asset-selection.png)

1. En dialogruta öppnas och du måste autentisera till fjärrtjänsten.

1. När den har autentiserats öppnas en resurshanterare för fjärrtjänsten. Välj önskad resurs och tryck eller klicka på **Välj**.

   ![Välja en fjärrresurs](/help/assets/remote-asset-picker.png)

Fjärrresursen läggs till på den lokala AEM sidan och du har verifierat att funktionen är korrekt konfigurerad.

## Använda fjärrresurser {#using}

När konfigurationen är klar kan du välja fjärrresurser där du vill välja resurser med hjälp av kärnkomponenterna, som i [Bildkomponent](/help/components/image.md) och [Teaser Component.](/help/components/teaser.md)
