---
title: Använda e-postkärnkomponenter
description: Lär dig mer om grundläggande installation, konfiguration och användning av e-postkärnkomponenterna.
role: Architect, Developer, Admin, User
exl-id: 0e79ca8f-eb0a-4519-b1e8-a9d3b0b99987
index: false
source-git-commit: eb77567dc32cccb81a9fc131493d11fb55b7e93b
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 1%

---


# Använda e-postkärnkomponenter {#using}

Lär dig mer om grundläggande installation, konfiguration och användning av e-postkärnkomponenterna.

## Installera e-postkärnkomponenterna {#installation}

E-postkärnkomponenterna kan användas med AEM 6.5. Mer information finns i avsnittet [Krav i introduktionsdokumentet om kärnkomponenter för e-post](introduction.md#requirements).

### Installera kärnkomponenter {#core-components}

E-postkärnkomponenterna bygger på AEM Core-komponenterna. Eftersom kärnkomponenterna inte levereras med AEM 6.5 måste du först installera AEM Core-komponenterna innan du installerar e-postkärnkomponenterna.

Mer information om hur du installerar kärnkomponenterna finns i avsnittet [Hämta och installera](/help/get-started/using.md#download-and-install) i dokumentet Använda kärnkomponenter.

### Installera e-postkärnkomponenter {#email-core-components}

När kärnkomponenterna har installerats i din instans måste du även installera e-postkärnkomponenterna. E-postkärnkomponenterna ingår ännu inte i AEM Project Archetype, så du måste lägga till dem manuellt i ditt projekt. Följ dokumentationen i [e-postkärnkomponenterna GitHub wiki för att installera.](https://github.com/adobe/aem-core-email-components/wiki/Adding-to-Existing-Project)

Du kan följa samma anvisningar om du vill anpassa ett befintligt projekt till att använda e-postkärnkomponenterna.

## Konfiguration {#configuration}

När du har installerat Core Components bör du slutföra två viktiga konfigurationssteg.

### Konfigurera kampanj {#configure-campaign}

Du måste konfigurera integreringen mellan AEM och Adobe Campaign för att de två lösningarna ska kunna kommunicera.

* Konfigurera Adobe Campaign-integreringen
   * Adobe Campaign Classic: [Integrera med Adobe Campaign Classic](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignonpremise.html?lang=sv-SE)
   * Adobe Campaign Standard: [Integrera med Adobe Campaign Standard](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html?lang=sv-SE)
* [Länka integrationskonfigurationen för Adobe Campaign](/help/email/components/page.md#cloud-services-tab) till innehållssidan där du ska använda kärnkomponenterna för e-post

### Lägg till AEM-resurstypfilter för e-postkomponenter {#aem-resource-filter}

För att Adobe Campaign ska kunna återge e-postmeddelanden baserat på e-postkärnkomponenter måste ett filter justeras i Campaign.

1. Logga in på Adobe Campaign som administratör med klientkonsolen.

1. Välj **Verktyg** -> **Utforskaren** på menyraden.

1. Gå till noden **Administration** -> **Plattform** -> **Alternativ** i Utforskaren.

1. Välj alternativet `AEMResourceTypeFilter` i listan.

1. Lägg till `core/email/components/page/<v1>/page` i fältet **Värde** om det inte redan finns.

   * Ersätt `<v1>` med den aktuella versionen av E-postkärnkomponenterna [Sidkomponent](/help/email/components/page.md), till exempel `v1`.
   * Observera att värdena i fältet **Värden** måste vara kommaavgränsade.

1. Klicka på **Spara**.

## Använda e-postkärnkomponenter {#using-components}

När e-postkomponenterna har installerats och integreringen med Adobe Campaign har konfigurerats kan du använda e-postkomponenterna för att skapa e-postinnehåll i AEM och sedan skicka det till mottagare med Adobe Campaign. Här följer en översikt över arbetsflödet.

| Steg | Beskrivning | Lösning |
|---|---|---|
| 1 | Författare skapar en kostnadsfri hierarkisk struktur med mappar och e-postinnehåll som sidor. | AEM |
| 2 | Med mallredigeraren [konfigurerar](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=sv-SE) författare ett e-posthuvud och/eller en sidfot som ska delas mellan alla e-postsidor som skapas från den här sidmallen. | AEM |
| 3 | Författare använder [sidredigeraren](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/editing-content.html?lang=sv-SE) för att skapa e-postinnehåll med textredigeraren där de kan välja Adobe Campaign-variabler och använda Segmenteringskomponenten för att visa villkorsstyrd information om mottagaren uppfyller vissa villkor. | AEM |
| 4 | När e-postinnehållet är klart körs [ett arbetsflöde](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/workflows/overview.html?lang=sv-SE) för att godkänna innehållet och skicka det till Campaign. | AEM |
| 5 | En leverans skapas som definierar en lista med mottagare. | Campaign |
| 6 | Innehållet som skapas i AEM väljs som innehåll i leveransen. | Campaign |
| 7 | Innehållet skickas till mottagarna och Adobe Campaign-variablerna ersätts med mottagarnas personliga information. | Campaign |

Ett exempel på hur du skapar e-postinnehåll i AEM och levererar i Adobe Campaign finns i följande resurser.

* AEM 6.5: [Arbeta med Adobe Campaign Classic och Adobe Campaign Standard](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/campaign.html?lang=sv-SE)
