---
title: Använda e-postkärnkomponenter
description: Lär dig mer om grundläggande installation, konfiguration och användning av e-postkärnkomponenterna.
role: Architect, Developer, Admin, User
exl-id: 0e79ca8f-eb0a-4519-b1e8-a9d3b0b99987
source-git-commit: 33976c0e745ad091a142109f70541f01a31edc5b
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 1%

---


# Använda e-postkärnkomponenter {#using}

Lär dig mer om grundläggande installation, konfiguration och användning av e-postkärnkomponenterna.

## Installera e-postkärnkomponenterna {#installation}

E-postkärnkomponenterna kan användas med AEM 6.5. Se [Krav-avsnittet i introduktionsdokumentet för e-postkomponenter](introduction.md#requirements) för mer information.

### Installera kärnkomponenter {#core-components}

E-postkärnkomponenterna bygger på AEM kärnkomponenter. Eftersom kärnkomponenterna inte levereras med AEM 6.5 måste du först installera de AEM kärnkomponenterna innan du installerar e-postkärnkomponenterna.

Se avsnittet [Hämta och installera](/help/get-started/using.md#download-and-install) i dokumentet Using Core Components för mer information om hur du installerar Core Components.

### Installera e-postkärnkomponenter {#email-core-components}

När kärnkomponenterna har installerats i din instans måste du även installera e-postkärnkomponenterna. E-postkärnkomponenterna är ännu inte en del av den AEM projektarkitekturen, så du måste lägga till dem manuellt i projektet. Följ dokumentationen i [E-postkärnkomponenterna GitHub wiki som ska installeras.](https://github.com/adobe/aem-core-email-components/wiki/Adding-to-Existing-Project)

Du kan följa samma anvisningar om du vill anpassa ett befintligt projekt till att använda e-postkärnkomponenterna.

## Konfiguration {#configuration}

När du har installerat Core Components bör du slutföra två viktiga konfigurationssteg.

### Konfigurera kampanj {#configure-campaign}

Du måste konfigurera integreringen mellan AEM och Adobe Campaign för att de två lösningarna ska kunna kommunicera.

* Konfigurera Adobe Campaign-integreringen
   * Adobe Campaign Classic: [Integrera med Adobe Campaign Classic](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignonpremise.html)
   * Adobe Campaign Standard: [Integrera med Adobe Campaign Standard](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html)
* [Länka integrationskonfigurationen för Adobe Campaign](/help/email/components/page.md#cloud-services-tab) till innehållssidan där du ska använda e-postkärnkomponenterna

### Lägg till AEM resurstypfilter för e-postkomponenter {#aem-resource-filter}

För att Adobe Campaign ska kunna återge e-postmeddelanden baserat på e-postkärnkomponenter måste ett filter justeras i Campaign.

1. Logga in på Adobe Campaign som administratör med klientkonsolen.

1. Välj **verktyg** -> **Utforskaren** på menyraden.

1. I Utforskaren går du till **Administration** -> **Plattform** -> **Alternativ** nod.

1. Välj `AEMResourceTypeFilter` i listan.

1. I **Värde** fält, lägga till `core/email/components/page/<v1>/page` om den inte redan finns.

   * Ersätt `<v1>` med den aktuella versionen av e-postkärnkomponenterna [Sidkomponent](/help/email/components/page.md) som `v1`.
   * Observera att värdena i **Värden** fältet måste vara kommaavgränsat.

1. Klicka **Spara**.

## Använda e-postkärnkomponenter {#using-components}

När e-postkomponenterna har installerats och integreringen med Adobe Campaign har konfigurerats kan du använda e-postkomponenterna för att skapa e-postinnehåll i AEM och sedan skicka det till mottagare med Adobe Campaign. Här följer en översikt över arbetsflödet.

| Steg | Beskrivning | Lösning |
|---|---|---|
| 1 | Författare skapar en kostnadsfri hierarkisk struktur med mappar och e-postinnehåll som sidor. | AEM |
| 2 | Använda [mallredigerare,](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html) författare konfigurerar ett e-posthuvud och/eller en sidfot som ska delas mellan alla e-postsidor som skapas från den här sidmallen. | AEM |
| 3 | Författare använder [sidredigerare](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/editing-content.html) om du vill skapa e-postinnehåll med textredigeraren där de kan välja Adobe Campaign-variabler och använda Segmenteringskomponenten för att visa villkorsstyrd information om mottagaren uppfyller vissa villkor. | AEM |
| 4 | När e-postinnehållet är klart, [ett arbetsflöde körs](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/workflows/overview.html) för att godkänna innehållet och skicka till Campaign. | AEM |
| 5 | En leverans skapas som definierar en lista med mottagare. | Campaign |
| 6 | Innehållet som skapas i AEM väljs som innehåll i leveransen. | Campaign |
| 7 | Innehållet skickas till mottagarna och Adobe Campaign-variablerna ersätts med mottagarnas personliga information. | Campaign |

Ett exempel på hur du skapar e-postinnehåll i AEM och levererar i Adobe Campaign finns i följande resurser.

* AEM 6.5: [Arbeta med Adobe Campaign Classic och Adobe Campaign Standard](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/campaign.html)
