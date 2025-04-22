---
title: Huvudversioner av e-postkomponenter
description: Huvudkomponenter för e-post publiceras som versioner.
role: Architect, Developer, Admin, User
exl-id: 9733659a-641c-4a98-8d10-84e93e0e0a5d
source-git-commit: 6fbc781db555bc6abaed1d122a9a8756e3d53222
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 0%

---


# Huvudversioner av e-postkomponenter {#core-components-versions}

Den aktuella versionen av E-postkärnkomponenterna är 1.3.0 och är kompatibel med AEM 6.5 och AEM 6.5 LTS.

Mer information om krav och installation finns i avsnittet [Krav](/help/email/introduction.md#requirements) i introduktionsdokumentet för e-postkärnkomponenter och i avsnittet [Installation](/help/email/using.md#installing-the-email-core-components) i dokumentet Använda E-postkärnkomponenter.

## Versionshistorik och kompatibilitet {#release-history-and-compatibility}

E-postkärnkomponenterna är utformade för att vara flexibla och kompatibla med alla AEM-versioner som stöds. Den fullständiga informationen om versionshistoriken för e-postkärnkomponenterna [ finns på GitHub.](https://github.com/adobe/aem-core-email-components/releases) I följande tabell visas dock en översikt över de utgåvor av E-postkärnkomponenterna som är kompatibla med AEM-versioner och Java-versioner.

| Frigör | Beskrivning | AEM 6.5 | AEM 6.5 LTS | Kärnkomponenter | Java | Releasedatum |
|---|---|---|---|---|---|---|
| [1.3.0](https://github.com/adobe/aem-core-email-components/releases/tag/core.email.components.reactor-1.3.0) | Den här versionen uppdaterar det inbäddade jsop-biblioteket. | 6.5.14.0+ | 6,5 LTS GA | [2.21.2+](/help/versions.md) | 8, 11 | 28 juni 2024 |
| [1.2.2](https://github.com/adobe/aem-core-email-components/releases/tag/core.email.components.reactor-1.2.2) | Den här underhållsreleasen korrigerade väljarfiltrering, löste en `SelectorParseException` och åtgärdade andra fel. | 6.5.14.0+ | - | [2.21.2+](/help/versions.md) | 8, 11 | 24 maj 2023 |
| [1.2.0](https://github.com/adobe/aem-core-email-components/releases/tag/core.email.components.reactor-1.2.0) | I den här versionen introducerades Selenium e2e-tester och ett antal felkorrigeringar ingick. | 6.5.14.0+ | - | [2.21.2+](/help/versions.md) | 8, 11 | 29 november 2022 |
| [1.0.0](https://github.com/adobe/aem-core-email-components/releases/tag/core.email.components.reactor-1.0.0) | Första offentliga versionen, se versionsinformation för utförlig information | 6.5.14.0+ | - | [2.21.2+](/help/versions.md) | 8, 11 | 29 november 2022 |
| [0.18.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.18.0) | Korrigeringar | 6.5.13.0+ |  |  | 8, 11 | 30 september 2022 |
| [0.17.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.17.0) | Korrigeringar | 6.5.13.0+ |  |  | 8, 11 | 27 september 2022 |
| [0.16.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.16.0) | Korrigeringar | 6.5.13.0+ |  |  | 8, 11 | 14 september 2022 |
| [0.14.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.14.0) | Korrigera mediefrågor för Outlook på iOS | 6.5.13.0+ |  |  | 8, 11 | 8 augusti 2022 |
| [0.13.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.13.0) | Prestandakorrigering för omslutnings-DIV, länkar för fast hantering i RTF-text | 6.5.13.0+ |  |  | 8, 11 | 27 juli 2022 |
| [0.11.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.11.0) | Stöd för anpassade segment för segmenteringskomponenter, HTML inliner, korrigeringar | 6.5.13.0+ |  |  | 8, 11 | 6 juli 2022 |
| [0.10.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.10.0) | Aktiverade sidprofiler för kolumninställningar för sidkomponent, uppdateringar av segmenteringskomponenten, förbättringar av kodtäckningen | 6.5.13.0+ |  |  | 8, 11 | 15 juni 2022 |
| [0.9.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.9.0) | Korrigeringar och uppdateringar av titel- och behållarkomponenter | 6.5.13.0+ |  |  | 8, 11 | 1 juni 2022 |
| [0.8.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.8.0) | Lagt till Teaser Components, korrigeringar och kodtäckningsförbättringar | 6.5.13.0+ |  |  | 8, 11 | 19 maj 2022 |
| [0.7.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.7.0) | Korrigeringar | 6.5.13.0+ |  |  | 8, 11 | 4 maj 2022 |
| [0.6.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.6.0) | Lagt till komponenterna Title, Button och Experience Fragment, utökat stöd för ContextHub | 6.5.13.0+ |  |  | 8, 11 | 20 april 2022 |
| [0.5.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.5.0) | Formatinliner och komponent för innehållsfragment har lagts till | 6.5.13.0+ |  |  | 8, 11 | 7 april 2022 |
| [0.4.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.4.0) | Komponenten URL-externalisering, personalisering och segmentering har lagts till | 6.5.13.0+ |  |  | 8, 11 | 23 mars 2022 |
| [0.3.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.3.0) | Lagt till text- och behållarkomponenter, nya redigeringsgränssnitt, korrigeringar | 6.5.13.0+ |  |  | 8, 11 | 9 mars 2022 |
| [0.2.0](https://github.com/adobe/aem-core-email-components/releases/tag/v0.2.0) | Första förhandsversionen med sidkomponenten och olika POC:er | 6.5.13.0+ |  |  | 8, 11 | 24 februari 2022 |
