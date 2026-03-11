---
title: Huvudkomponentversioner
description: Kärnkomponenter publiceras som releaser som kan innehålla mer än en version av samma kärnkomponenter. I det här dokumentet förklaras vad som är en release och version och hur man förstår kompatibiliteten med Core Components och AEM.
role: Architect, Developer, Admin, User
exl-id: 7d4dbe46-4013-4217-b815-cdb1462072c6
source-git-commit: 3e49862f958e50f095c944c33d1983ae46ab8ace
workflow-type: tm+mt
source-wordcount: '3887'
ht-degree: 5%

---

# Huvudkomponentversioner {#core-components-versions}

Core-komponenterna är kompatibla med [AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html) och [ AEM](https://experienceleague.adobe.com/docs/experience-manager-65/user-guide/home.html)-installationer på plats.

## Versionshistorik och kompatibilitet {#release-history-and-compatibility}

Core Components är utformade för att vara flexibla och kompatibla med alla AEM-versioner som stöds. På grund av detta kan en version av komponenterna innehålla flera versioner av samma komponent.

I följande tabeller visas kompatibiliteten för de versioner av kärnkomponenterna som ingår i releaserna.

### Versionshistorik och krav {#release-history-requirements}

Följande tabell, vars innehåll är [tillgängligt på GitHub med fullständig versionsinformation](https://github.com/adobe/aem-core-wcm-components/releases), ger en översikt över de olika versionerna av kärnkomponenterna och deras kompatibilitet med AEM-versioner och Java-versioner.

| Frigör | Beskrivning | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service | Java | Releasedatum |
|---|---|---|---|---|---|---|---|
| [2.30.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.30.4) | Den här versionen korrigerade ett sökvägsvalideringsfel. | - | 6.5.21.0+ | 6,5 LTS GA | Kontinuerlig | 8, 11, 17, 21 | 30 januari 2026 |
| [2.30.3](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.30.3) | Den här versionen korrigerade en regression i dialogrutan Princip för titelkomponent. | - | 6.5.21.0+ | 6,5 LTS GA | Kontinuerlig | 8, 11, 17, 21 | 5 december 2025 |
| [2.30.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.30.2) | Den här versionen korrigerade en olokaliserad sträng som är relaterad till PDF-visningsprogrammet. | - | 6.5.21.0+ | 6,5 LTS GA | Kontinuerlig | 8, 11, 17, 21 | 23 oktober 2025 |
| [2.30.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.30.0) | Den här versionen åtgärdade ett antal problem med resurser och dynamiska media, klargör LTS-stödet och åtgärdar flera felkorrigeringar. | - | 6.5.21.0+ | 6,5 LTS GA | Kontinuerlig | 8, 11, 17, 21 | 4 september 2025 |
| [2.29.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.29.0) | I den här versionen finns stöd för redigering av förhandsgranskningsversioner av resurser i kärnkomponenten för webbplatser, och många felkorrigeringar har åtgärdats. | - | 6.5.21.0+ | 6,5 LTS GA | Kontinuerlig | 8, 11, 17, 21 | 21 april 2025 |
| [2.28.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.28.0) | Den här versionen åtgärdar flera felkorrigeringar. | - | 6.5.21.0+ | 6,5 LTS GA | Kontinuerlig | 8, 11, 17, 21 | 17 mars 2025 |
| [2.27.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.27.0) | Den här versionen åtgärdar flera felkorrigeringar. | - | 6.5.21.0+ | - | Kontinuerlig | 11 | 10 september 2024 |
| [2.26.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.26.0) | Den här versionen åtgärdar flera felkorrigeringar. | - | 6.5.21.0+ | - | Kontinuerlig | 11 | 31 juli 2024 |
| [2.25.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.25.4) | Det här är en mindre release som åtgärdar vissa IT-fel. | - | 6.5.21.0+ | - | Kontinuerlig | 8, 11 | 10 maj 2024 |
| [2.25.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.25.2) | Det här är en mindre release som åtgärdar vissa IT-fel. | - | 6.5.21.0+ | - | Kontinuerlig | 8, 11 | 9 maj 2024 |
| [2.25.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.25.0) | Den här versionen innehåller stöd för namngivna smartbeskärningar i Dynamic Media, bland annat prestanda- och tillgänglighetsförbättringar samt olika felkorrigeringar. | - | 6.5.21.0+ | - | Kontinuerlig | 8, 11 | 2 maj 2024 |
| [2.24.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.24.6) | Den här korrigeringsversionen innehåller förbättringar för initiering av datalager. | - | 6.5.21.0+ | - | Kontinuerlig | 8, 11 | 22 april 2024 |
| [2.24.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.24.4) | Den här korrigeringsversionen åtgärdar en initiering av en Sling-modell. | - | 6.5.21.0+ | - | Kontinuerlig | 8, 11 | 1 april 2024 |
| [2.24.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.24.2) | Den här korrigeringsversionen förbättrar stabiliteten i integrationstester. | - | 6.5.21.0+ | - | Kontinuerlig | 8, 11 | 22 februari 2024 |
| [2.24.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.24.0) | Den här versionen har stöd för Google Tag Manager-datalagret och innehåller olika felkorrigeringar. | - | 6.5.21.0+ | - | Kontinuerlig | 8, 11 | 14 februari 2024 |
| [2.23.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.23.4) | Den här korrigeringsversionen innehåller olika felkorrigeringar. | - | 6.5.17.0+ | - | Kontinuerlig | 8, 11 | 15 september 2023 |
| [2.23.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.23.2) | Den här korrigeringen lade till smart beskärning av dynamiska media för fjärrresurser i [bilden](/help/components/image.md) och [Teaser Components](/help/components/teaser.md) och åtgärdade ett antal fel. | - | 6.5.17.0+ | - | Kontinuerlig | 8, 11 | 4 augusti 2023 |
| [2.23.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.23.0) | Den här versionen har lagt till stöd för [nästa generations dynamiska mediefunktioner.](/help/developing/remote-assets.md) | - | 6.5.17.0+ | - | Kontinuerlig | 8, 11 | 6 juni 2023 |
| [2.22.12](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.22.12) | Den här korrigeringsversionen åtgärdar två problem. | - | 6.5.14.0+ | - | Kontinuerlig | 8, 11 | 25 maj 2023 |
| [2.22.10](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.22.10) | Den här korrigeringsversionen åtgärdar två regressioner. | - | 6.5.14.0+ | - | Kontinuerlig | 8, 11 | 11 maj 2023 |
| [2.22.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.22.8) | Den här korrigeringsversionen återför funktioner som togs bort av misstag i en tidigare version. | - | 6.5.14.0+ | - | Kontinuerlig | 8, 11 | 9 maj 2023 |
| [2.22.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.22.6) | Den här korrigeringsversionen åtgärdar en regression i [behållarkomponenten.](/help/components/container.md) | - | 6.5.14.0+ | - | Kontinuerlig | 8, 11 | 21 april 2023 |
| [2.22.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.22.4) | Det här är en korrigeringsversion som åtgärdar ett problem i [listkomponenten för innehållsfragment.](/help/components/content-fragment-list.md) | - | 6.5.14.0+ | - | Kontinuerlig | 8, 11 | 5 april 2023 |
| [2.22.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.22.2) | Det här är en underhållsversion som åtgärdar två problem som introducerades i 2.22.0 | - | 6.5.14.0+ | - | Kontinuerlig | 8, 11 | 31 mars 2023 |
| [2.22.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.22.0) | Den här versionen innehåller en ny version av [List Component](/help/components/list.md) plus förbättringar av [Teaser](/help/components/teaser.md) och uppdatering av [PDF Viewer](/help/components/pdf-viewer.md) och [Carousel](/help/components/carousel.md) | - | 6.5.14.0+ | - | Kontinuerlig | 8, 11 | 9 februari 2023 |
| [2.21.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.21.2) | Det här är en korrigeringsrelease som åtgärdar ett problem med v1 och v2 [Teaser Components.](/help/components/teaser.md) | - | 6.5.13.0+ | - | Kontinuerlig | 8, 11 | 12 september 2022 |
| [2.21.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.21.0) | Den här versionen innehåller ett antal förbättringar, bland annat publicering av LinkHandler-API:t, förbättringar av [Image Component](/help/components/image.md) och [ Data Layer,](/help/developing/data-layer/overview.md) samt förbättringar av komponenter för flera paneler. | - | 6.5.13.0+ | - | Kontinuerlig | 8, 11 | 12 september 2022 |
| [2.20.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.20.8) | Den här versionen åtgärdar ett problem med leveransen av SVG-bilder via AdaptiveImageServlet. | - | 6.5.13.0+ | - | Kontinuerlig | 8, 11 | 4 augusti 2022 |
| [2.20.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.20.6) | Den här korrigeringsversionen åtgärdar ett problem med den nya komponenten [Innehållsförteckning.](/help/components/tableofcontents.md) | - | 6.5.13.0+ | - | Kontinuerlig | 8, 11 | 7 juli 2022 |
| [2.20.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.20.4) | Den här korrigeringsversionen åtgärdar ett problem med den nya komponenten [Innehållsförteckning.](/help/components/tableofcontents.md) | - | 6.5.13.0+ | - | Kontinuerlig | 8, 11 | 29 juni 2022 |
| [2.20.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.20.2) | Det här är en korrigeringsversion som åtgärdar ett problem i den nya webboptimerade tjänsten AEMaaCS [för leverans av resurser.](/help/developing/web-optimized-image-delivery.md) | - | 6.5.13.0+ | - | Kontinuerlig | 8, 11 | 20 juni 2022 |
| [2.20.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.20.0) | Den här versionen lägger till en ny [innehållsförteckningskomponent](/help/components/tableofcontents.md), lägger till stöd för den webboptimerade tjänsten [AEMaaCS,](/help/developing/web-optimized-image-delivery.md) och innehåller felkorrigeringar. | - | 6.5.13.0+ | - | Kontinuerlig | 8, 11 | 9 juni 2022 |
| [2.19.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.19.0) | Den här versionen lägger till en ny version i [sökkomponenten](/help/components/quick-search.md) och funktioner i [knappkomponenten](/help/components/button.md) samt många tillgänglighetsförbättringar och felkorrigeringar. | - | 6.5.10.0+ | - | Kontinuerlig | 8, 11 | 7 april 2022 |
| [2.18.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.18.8) | Den här versionen åtgärdar ett problem med AEMaaCS. | - | 6.5.10.0+ | - | Kontinuerlig | 8, 11 | 17 mars 2022 |
| [2.18.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.18.6) | Det här är en patch-release. | - | 6.5.10.0+ | - | Kontinuerlig | 8, 11 | 3 mars 2022 |
| [2.18.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.18.0) | I den här större releasen av huvudkomponenterna introduceras en ny länkhanterare för nya versioner av flera komponenter tillsammans med många tillgänglighetsförbättringar och felkorrigeringar. | - | 6.5.10.0+ * | - | Kontinuerlig | 8, 11 | 16 februari 2022 |
| [2.17.14](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.12) | Det här är en patch-release. | 6.4.8.4+ | 6.5.6.0+ | - | Kontinuerlig | 8, 11 | 13 december 2021 |
| [2.17.12](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.12) | Det här är en korrigeringsversion som korrigerar en regression som introducerades i den tidigare versionen. | 6.4.8.4+ | 6.5.6.0+ | - | Kontinuerlig | 8, 11 | 1 oktober 2021 |
| [2.17.10](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.10) | Den här korrigeringen förbättrar komponenterna [List](/help/components/list.md) och [Navigation](/help/components/navigation.md) så att den externa URL:en för omdirigeringsmål visas, aktiverar sidbildsarv för den kommande v2-komponenten i [Teaser](/help/components/teaser.md) och innehåller ytterligare felkorrigeringar. | 6.4.8.4+ | 6.5.6.0+ | - | Kontinuerlig | 8, 11 | 31 augusti 2021 |
| [2.17.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.8) | Den här korrigeringsversionen Det här är en korrigeringsversion som åtgärdar en inkompatibel ändring bakåt som introducerades tidigare. | 6.4.8.4+ | 6.5.6.0+ | - | Kontinuerlig | 8, 11 | 2 augusti 2021 |
| [2.17.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.6) | Den här korrigeringsversionen har stöd för webbplatskartor för sidor och innehåller olika tillgänglighetsförbättringar. | 6.4.8.4+ | 6.5.6.0+ | - | Kontinuerlig | 8, 11 | 29 juli 2021 |
| [2.17.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.2) | Den här korrigeringsversionen innehåller en korrigering för [datalagret](/help/developing/data-layer/overview.md) som inte fungerar med AEMaaCS. | 6.4.8.4+ | 6.5.6.0+ | - | Kontinuerlig | 8, 11 | 8 juli 2021 |
| [2.17.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.0) | Den här versionen innehåller tekniska förhandsvisningar av många nya komponentversioner med stöd för länkhanterarfunktioner samt en teknisk förhandsvisning av en bildfunktion för [sidkomponenten.](/help/components/page.md) Flera felkorrigeringar ingår också. | 6.4.8.4+ | 6.5.6.0+ | - | Kontinuerlig | 8, 11 | 16 juni 2021 |
| [2.16.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.16.4) | Det här är en patch som åtgärdar ett problem med den nya länkhanteraren. | 6.4.8.1+ | 6.5.5.0+ | - | Kontinuerlig | 8, 11 | 19 maj 2021 |
| [2.16.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.16.2) | Det här var en korrigeringsversion som huvudsakligen åtgärdade ett problem med den nya länkhanteraren och lade till en förbättring som stöder flersidiga program för [PWA.](/help/components/page.md#pwa-support) | 6.4.8.1+ | 6.5.5.0+ | - | Kontinuerlig | 8, 11 | 15 maj 2021 |
| [2.16.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.16.0) | Den här versionen fokuserar på tillgänglighetsförbättringar och introducerar en ny länkhanterare för befintliga komponenter. | 6.4.8.1+ | 6.5.5.0+ | - | Kontinuerlig | 8, 11 | 22 april 2021 |
| [2.15.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.15.2) | Det här var en korrigeringsrelease som huvudsakligen åtgärdar problem med bakåtkompatibilitet för [datalager](/help/developing/data-layer/overview.md) och IT-tester misslyckas i vissa situationer. | 6.4.8.1+ | 6.5.5.0+ | - | Kontinuerlig | 8, 11 | 16 mars 2021 |
| [2.15.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.15.0) | Den här versionen har stöd för [progressiva webbprogram (PWA) i Page Component](/help/components/page.md#pwa-support) och har stöd för version 2.0.0 i [Adobe Data Layer.](/help/developing/data-layer/overview.md) | 6.4.8.1+ | 6.5.5.0+ | - | Kontinuerlig | 8, 11 | 23 februari 2021 |
| [2.14.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.14.0) | Den här versionen innehåller nya alternativ för [inbäddningskomponenten](/help/components/embed.md) och introducerar varumärkesinstruktionen på [sidnivå](/help/components/page.md) samt åtgärdar många problem. | 6.4.8.1+ | 6.5.5.0+ | - | Kontinuerlig | 8, 11 | 9 februari 2021 |
| [2.13.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.13.2) | Det här var en patch som åtgärdade ett problem med RTE när den användes i AEMaaCS | 6.4.8.1+ | 6.5.5.0+ | - | Kontinuerlig | 8, 11 | 16 december 2020 |
| [2.13.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.13.0) | Den här versionen innehåller nya dynamiska mediefunktioner för [Image-komponenten.](/help/components/image.md) | 6.4.8.1+ | 6.5.5.0+ | - | Kontinuerlig | 8, 11 | 4 december 2020 |
| [2.12.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.2) | Det här var en patch-version för 2.12.0 med smärre korrigeringar. | 6.4.8.1+ | 6.5.5.0+ | - | Kontinuerlig | 8, 11 | 11 november 2020 |
| [2.12.1](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.1) | Det här var en korrigeringsversion för 2.12.0 som åtgärdar ett större fel i [Image Component.](/help/components/image.md) | 6.4.8.1+ | 6.5.5.0+ | - | Kontinuerlig | 8, 11 | 5 november 2020 |
| [2.12.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.0) | I den här versionen introducerades [en ny POST-formulärhanterare;](/help/components/forms/form-container.md#post-data) möjlighet att inkludera anpassade CSS-, Javascript- och metadata [-taggar via kontextmedveten konfiguration;](/help/developing/including-clientlibs.md#context-aware-loading) och ett `DataLayerBuilder`-verktyg för att [förenkla integrering av datalager i anpassade komponenter.](/help/developing/data-layer/integrations.md#enabling-custom-components) | 6.4.8.1+ | 6.5.5.0+ | - | Kontinuerlig | 8, 11 | 29 oktober 2020 |
| [2.11.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.11.0) | I den här versionen introducerades [AMP-stöd.](/help/developing/amp.md) | 6.4.8.1+ | 6.5.5.0+ | - | Kontinuerlig | 8, 11 | 20 juli 2020 |
| [2.10.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.10.0) | Den här versionen innehåller [PDF Viewer-komponenten.](/help/components/pdf-viewer.md) | 6.4.8.1+ | 6.5.5.0+ | - | Kontinuerlig | 8, 11 | 17 juni 2020 |
| [2.9.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.9.0) | Den här versionen aktiverade integrering med [Adobe Client Data Layer](/help/developing/data-layer/overview.md) och introducerade komponenten [Progress Bar.](/help/components/progress-bar.md) | 6.4.8.0+ | 6.5.4.0+ | - | Kontinuerlig | 8, 11 | 29 maj 2020 |
| [2.8.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.8.0) | Den här versionen fokuserar på korrigeringar med små förbättringar. | 6.4.4.0+ | 6.5.0.0+ | - | Kontinuerlig | 8, 11 | 5 december 2019 |
| [2.7.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.7.0) | I den här versionen introducerades den nya [inbäddningskomponenten.](/help/components/embed.md) | 6.4.4.0+ | 6.5.0.0+ | - | Kontinuerlig | 8, 11 | 25 september 2019 |
| [2.6.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.6.0) | I den här versionen introducerades den nya [Experience Fragment-komponenten.](/help/components/experience-fragment.md) | 6.4.4.0+ | 6.5.0.0+ | - | Kontinuerlig | 8, 11 | 6 september 2019 |
| [2.5.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.5.0) | I den här versionen introducerades den nya [dragspelsversionen,](/help/components/accordion.md) [Button,](/help/components/button.md) [Container,](/help/components/container.md) och [Ladda ned komponenter.](/help/components/download.md) | 6.4.2.0+ | 6.5.0.0+ | - | Kontinuerlig | 8, 11 | 25 juni 2019 |
| [2.4.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.4.0) | I den här versionen introducerades [listkomponenten för innehållsfragment.](/help/components/content-fragment-list.md) | 6.4.2.0+ | 6.5.0.0+ | - | Kontinuerlig | 8, 11 | 7 maj 2019 |
| [2.3.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.2) | Den här versionen fokuserade på förbättringar av [komponentbiblioteket](https://aemcomponents.dev) men innehåller också vissa funktionsförbättringar för [avgränsarkomponenten.](/help/components/separator.md) | 6.4.2.0+ | 6.5.0.0+ | - | Kontinuerlig | 8 | 14 mars 2019 |
| [2.3.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.0) | Den här versionen fokuserade på [komponentbiblioteket](https://aemcomponents.dev) och introducerade den nya [separatorkomponenten](/help/components/separator.md), men innehåller också vissa funktionsförbättringar för [bildkomponenten.](/help/components/image.md) | 6.4.2.0+ | - | - | - | 8 | 11 februari 2019 |
| [2.2.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.2) | Den här versionen fokuserade främst på felkorrigeringar, men innehåller också vissa funktionsförbättringar för [Carousel-komponenten.](/help/components/carousel.md) | 6.4.2.0+ | - | - | - | 8 | 27 november 2018 |
| [2.2.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.0) | I den här versionen introducerades [flikkomponenten](/help/components/tabs.md) och [Carousel-komponenten](/help/components/carousel.md) samt förbättringar av [bildkomponenten,](/help/components/image.md) [sidkomponenten,](/help/components/page.md) och [titelkomponenten](/help/components/title.md) och förbättrad spårning. | 6.4.2.0+ | -- |  | - | 8 | 16 oktober 2018 |
| [2.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.1.0) | I den här versionen introducerades [Teaser Component](/help/components/teaser.md) tillsammans med förbättringar av [Image Component](/help/components/image.md) och flera felkorrigeringar. | 6.4.2.0+ | -- |  | - | 8 | 13 juli 2018 |
| [2.0.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.8) | Det här var en felfri version. | 6.4.0.0+ | -- |  | - | 8 | 12 juni 2018 |
| [2.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.6) | Den här versionen innehåller förbättringar under huven, felkorrigeringar och små förbättringar, inklusive stöd för bildvändning i [bildkomponenten.](/help/components/image.md) | 6.4.0.0+ | - | - | - | 8 | 11 april 2018 |
| [2.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.4) | Den här versionen fokuserade mest på förbättringar under huven, felkorrigeringar och några mindre förbättringar av [bildkomponenten,](/help/components/image.md) [sidkomponenten,](/help/components/page.md) och [innehållskomponenten.](/help/components/content-fragment-component.md) | 6.4.0.0+ | - | - | 8 | 7 mars 2018 |
| [2.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.0) | I den här versionen introducerades [navigeringskomponenten,](/help/components/navigation.md) [språknavigeringskomponenten,](/help/components/language-navigation.md) och [snabbsökningskomponenten](/help/components/quick-search.md) och [formatsystemet](/help/get-started/authoring.md#component-styling) implementerades för alla komponenter. | 6.4.0.0+ | - | - | - | 8 | 16 januari 2018 |
| [1.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.1.0) | Den här versionen implementerar JSON-export för alla komponenter och introducerar komponenten [Content Fragment.](/help/components/content-fragment-component.md) | 6.4.0.0+ | -- |  | - | 8 | 10 oktober 2017 |
| [1.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.6) | Den här versionen innehåller flera korrigeringar för [Image-komponenten.](/help/components/image.md) | 6.4.0.0+ | - | - | 8 | 4 augusti 2017 |
| [1.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.4) | Den här versionen lägger till korrigeringar för [sidkomponenten,](/help/components/page.md) [bildkomponenten,](/help/components/image.md) och olika globala korrigeringar och förbättringar. | 6.4.0.0+ | -- |  | - | 8 | 26 april 2017 |
| [1.0.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.all-1.0.2) | Den här versionen lägger till korrigeringar för animerade GIF-bilder i [Image Component.](/help/components/image.md) | 6.4.0.0+ | - | - | - | 7 | 22 mars 2017 |
| [1.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.0) | Ursprunglig version av kärnkomponenter. | 6.4.0.0+ | - | - | - | 7 | 20 mars 2017 |

>[!TIP]
>
>Precis som med AEM rekommenderar Adobe att utvecklare använder den [senaste utgåvan och de versioner av kärnkomponenterna](https://github.com/adobe/aem-core-wcm-components/releases/latest) som är kompatibla med den version av AEM som de kör för att dra nytta av de senaste korrigeringarna och funktionerna.

### Komponentversioner och releaser {#component-versions-and-releases}

Tabellen nedan visar vilka versioner av vilka komponenter som ingår i vilka versioner av kärnkomponenterna släpps.

|  | Version 1.0.0 - 1.0.6 | Version 1.1.0 | Version 2.0.0 - 2.0.8 | Version 2.1.0 | Version 2.2.0-2.2.0 | Version 2.3.0-2.3.2 | Version 2.4.0 | Version 2.5.0 | Version 2.6.0 | Version 2.7.0-2.8.0 | Version 2.9.0-2.17.14 | Version 2.18.0 | Version 2.19.0 | Version 2.20.0-2.21.2 | Version 2.2.0+ |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| **[Sida](components/page.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2, v3 | v1, v2, v3 | v1, v2, v3 | v1, v2, v3 |
| **[Titel](components/title.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2, v3 | v1, v2, v3 | v1, v2, v3 | v1, v2, v3 |
| **[Bild](components/image.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2, v3 | v1, v2, v3 | v1, v2, v3 | v1, v2, v3 |
| **[Lista](components/list.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2, v3 | v1, v2, v3 | v1, v2, v3 | v1, v2, v3, v4 |
| **[Breadcrumb](components/breadcrumb.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2, v3 | v1, v2, v3 | v1, v2, v3 | v1, v2, v3 |
| **[Delning av sociala medier](components/sharing.md)** | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1, borttagen | v1, borttagen | v1, borttagen | v1, borttagen |
| **[Formulärbehållare](components/forms/form-container.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Formulärtext](components/forms/form-text.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Formuläralternativ](components/forms/form-options.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Formuläret dolt](components/forms/form-hidden.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Formulärknapp](components/forms/form-button.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Innehållsfragment](components/content-fragment-component.md)** |  | Sandbox | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Navigering](components/navigation.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Språknavigering](components/language-navigation.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Snabbsökning](components/quick-search.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1, v2 | v1, v2 | v1, v2 |
| **[Teaser](components/teaser.md)** |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Tabbar](components/tabs.md)** |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Carousel](components/carousel.md)** |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Avgränsare](components/separator.md)** |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Innehållsfragmentlista](components/content-fragment-list.md)** |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Dragspel](components/accordion.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Knapp](components/button.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Behållare](components/container.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Hämta](components/download.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Upplevelsefragment](components/experience-fragment.md)** |  |  |  |  |  |  |  |  | v1 | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Bädda in](components/embed.md)** |  |  |  |  |  |  |  |  |  | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Förloppsindikator](components/progress-bar.md)** |  |  |  |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 |
| **[PDF Viewer](components/pdf-viewer.md)** |  |  |  |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 |
| **[Innehållsförteckning](components/tableofcontents.md)** |  |  |  |  |  |  |  |  |  |  |  |  |  | v1 | v1 |

## Versioner och releaser {#versions-and-releases}

Kärnkomponenter distribueras via GitHub. Detta gör att Adobe snabbare kan lägga till funktioner i komponenterna och även ge möjlighet till communityindata utanför AEM releasecykel.

Core-komponenterna är tillgängliga med definierade AEM-versioner som de är kompatibla med. Detta innebär att en AEM-version kan ha stöd för flera versioner eller versioner av de centrala komponenterna.

### Versioner {#versions}

Huvudupprepningen av kärnkomponenterna är **versionerna**. Varje komponent har en version. Versioner markeras med **v** som har ett positivt heltal som inte är noll, till exempel v1 och v2. Versionerna ökas endast för ändringar som inte är bakåtkompatibla, vilket vanligtvis är fallet när nya funktioner införs.

Utvecklare och administratörer kan känna igen versioner av kärnkomponenterna med ett antal i sina resurstypssökvägar och i de fullständiga Java-klassnamnen för sina implementeringar. Det här versionsnumret representerar en huvudversion enligt definitionen i [riktlinjerna för semantisk versionshantering](https://semver.org/).

Mer information om kärnkomponentversioner finns i [utvecklardokumentationen för kärnkomponenterna](developing/guidelines.md).

### Utgåvor {#releases}

Kärnkomponenterna är tillgängliga via **releaser** och [representerar de faktiska publicerade artefakterna som är tillgängliga på GitHu.](https://github.com/adobe/aem-core-wcm-components/releases) Releaser anges med ett decimaltal i formatet `X.Y.Z` och samlar ihop alla kärnkomponenter som ett levererbart paket.

* I **större versioner** introduceras helt nya komponenter, förbättringar av befintliga versioner av komponenter samt standardfelkorrigeringar. Detta representeras av en ökning i komponenten `X` i versionsnumret.
* **Mindre versioner** innehåller nya komponenter, nya funktioner för befintliga versioner av komponenter samt felkorrigeringar. Detta representeras av en ökning i komponenten `Y` i versionsnumret.
* **Patch-versioner** innehåller bara felkorrigeringar. Detta representeras av en ökning i komponenten `Z` i versionsnumret.

>[!NOTE]
>
>Releaser kan innehålla flera versioner av samma komponent.
>
>Samma version av en komponent kan visas i flera versioner.

## Stöd för kärnkomponenter {#core-components-support}

Core Components är en integrerad del av AEM och stöds enligt samma villkor som om de levererades som en del av QuickStart.

I likhet med andra produktfunktioner är den allmänna regeln om produktlivslängd:

* Komponenterna meddelas först att bli borttagna innan de tas bort
* Som tidigast tas de bort från AEM-utgåvan efter meddelandet.

Detta ger kunderna minst en releasecykel att gå över till den nya versionen av komponenten innan supporten upphör.

Versionen för varje komponent anger tydligt vilka AEM-versioner som stöds. När supporten för en version av AEM upphör, gör det också stödet för Core Components för den versionen av AEM.

Mer information om stöd för komponentanpassningar finns på sidan [Anpassa kärnkomponenter](developing/customizing.md) i den relevanta Core Components-versionen.

## Stöd för Foundation Component {#foundation-component-support}

Adobe betoning på utveckling har gått över till kärnkomponenterna och nya funktioner kommer att läggas till.

[Nästan alla Foundation-komponenter har ersatts med AEM 6.5](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/siteandpage/default-components-foundation.html) och endast större felkorrigeringar kommer att övervägas för Foundation-komponenterna som fortsätter.
