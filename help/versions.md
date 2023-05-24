---
title: Huvudkomponentversioner
description: Kärnkomponenter publiceras som releaser som kan innehålla mer än en version av samma kärnkomponenter. I det här dokumentet förklaras vad som är releaser och versioner och hur man förstår kompatibiliteten med kärnkomponenter och AEM.
role: Architect, Developer, Admin, User
exl-id: 7d4dbe46-4013-4217-b815-cdb1462072c6
source-git-commit: 1b419d6f340f8062945f96b1605a67620d5f79af
workflow-type: tm+mt
source-wordcount: '2988'
ht-degree: 12%

---

# Huvudkomponentversioner {#core-components-versions}

Den aktuella versionen av Core Components är 2.2.10 och är kompatibel med [AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html) och [AEM på plats](https://experienceleague.adobe.com/docs/experience-manager-65/user-guide/home.html) installationer.

## Versionshistorik och kompatibilitet {#release-history-and-compatibility}

Core Components är utformade för att vara flexibla och kompatibla med alla AEM som stöds. På grund av detta kan en version av komponenterna innehålla flera versioner av samma komponent.

I följande tabeller visas kompatibiliteten för de versioner av kärnkomponenterna som innehåller de versioner som versionerna ingår i.

### Versionshistorik och krav {#release-history-requirements}

Följande tabell, vars innehåll är [finns på GitHub med fullständig versionsinformation](https://github.com/adobe/aem-core-wcm-components/releases), ger en översikt över de utgåvor av kärnkomponenterna som är kompatibla med AEM och Java-versioner.

| Frigör | Beskrivning | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service | Java | Releasedatum |
|---|---|---|---|---|---|---|
| [2.22.10](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.22.10) | Den här korrigeringsversionen åtgärdar två regressioner. | - | 6.5.14.0+ * | Kontinuerlig | 8, 11 | 11 maj 2023 |
| [2.22.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.22.8) | Den här korrigeringsversionen återför funktioner som togs bort av misstag i en tidigare version. | - | 6.5.14.0+ * | Kontinuerlig | 8, 11 | 9 maj 2023 |
| [2.22.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.22.6) | Den här korrigeringsversionen korrigerar en regression i [Containerkomponent.](/help/components/container.md) | - | 6.5.14.0+ * | Kontinuerlig | 8, 11 | 21 april 2023 |
| [2.22.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.22.4) | Det här är en korrigeringsversion som åtgärdar ett problem i [Content Fragment List Component.](/help/components/content-fragment-list.md) | - | 6.5.14.0+ * | Kontinuerlig | 8, 11 | 5 april 2023 |
| [2.22.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.22.2) | Det här är en underhållsversion som åtgärdar två problem som introducerades i 2.22.0 | - | 6.5.14.0+ * | Kontinuerlig | 8, 11 | 31 mars 2023 |
| [2.22.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.22.0) | Den här versionen innehåller en ny version av [List-komponent](/help/components/list.md) tillsammans med förbättringar av [Teaser](/help/components/teaser.md) och uppdatering av [PDF Viewer](/help/components/pdf-viewer.md) och [Carousel](/help/components/carousel.md) | - | 6.5.14.0+ * | Kontinuerlig | 8, 11 | 9 februari 2023 |
| [2.21.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.21.2) | Det här är en korrigeringsversion som åtgärdar ett problem med v1 och v2 [Teaser Components.](/help/components/teaser.md) | - | 6.5.13.0+ * | Kontinuerlig | 8, 11 | 12 september 2022 |
| [2.21.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.21.0) | Den här versionen innehåller ett antal förbättringar, bland annat publicering av LinkHandler API, förbättringar av [Bildkomponent](/help/components/image.md) och [datalager,](/help/developing/data-layer/overview.md) samt förbättringar av komponenter med flera paneler. | - | 6.5.13.0+ * | Kontinuerlig | 8, 11 | 12 september 2022 |
| [2.20.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.20.8) | Den här versionen åtgärdar ett problem med leveransen av SVG-bilder via AdaptiveImageServlet. | - | 6.5.13.0+ * | Kontinuerlig | 8, 11 | 4 augusti 2022 |
| [2.20.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.20.6) | Den här korrigeringsversionen åtgärdar ett problem med den nya [Innehållsförteckningskomponent.](/help/components/tableofcontents.md) | - | 6.5.13.0+ * | Kontinuerlig | 8, 11 | 7 juli 2022 |
| [2.20.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.20.4) | Den här korrigeringsversionen åtgärdar ett problem med den nya [Innehållsförteckningskomponent.](/help/components/tableofcontents.md) | - | 6.5.13.0+ * | Kontinuerlig | 8, 11 | 29 juni 2022 |
| [2.20.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.20.2) | Det här är en patch som åtgärdar ett problem i nya AEMaaCS [webboptimerad tillgångsleveranstjänst.](/help/developing/web-optimized-image-delivery.md) | - | 6.5.13.0+ * | Kontinuerlig | 8, 11 | 20 juni 2022 |
| [2.20.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.20.0) | Den här versionen lägger till en ny [Innehållsförteckningskomponent](/help/components/tableofcontents.md), lägger till stöd för AEMaaCS [webboptimerad tillgångsleveranstjänst,](/help/developing/web-optimized-image-delivery.md) och innehåller felkorrigeringar. | - | 6.5.13.0+ * | Kontinuerlig | 8, 11 | 9 juni 2022 |
| [2.19.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.19.0) | Den här versionen lägger till en ny version i [Sökkomponent](/help/components/quick-search.md) och funktioner i [Button-komponent](/help/components/button.md) samt många tillgänglighetsförbättringar och felkorrigeringar. | - | 6.5.10.0+ * | Kontinuerlig | 8, 11 | 7 april 2022 |
| [2.18.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.18.8) | Den här versionen åtgärdar ett problem med AEMaaCS. | - | 6.5.10.0+ * | Kontinuerlig | 8, 11 | 17 mars 2022 |
| [2.18.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.18.6) | Det här är en patch-release. | - | 6.5.10.0+ * | Kontinuerlig | 8, 11 | 3 mars 2022 |
| [2.18.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.18.0) | I den här större releasen av huvudkomponenterna introduceras en ny länkhanterare för nya versioner av flera komponenter tillsammans med många tillgänglighetsförbättringar och felkorrigeringar. | - | 6.5.10.0+ * | Kontinuerlig | 8, 11 | 16 februari 2022 |
| [2.17.14](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.12) | Det här är en patch-release. | 6.4.8.4+ * | 6.5.6.0+ * | Kontinuerlig | 8, 11 | 13 december 2021 |
| [2.17.12](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.12) | Det här är en korrigeringsversion som korrigerar en regression som introducerades i den tidigare versionen. | 6.4.8.4+ * | 6.5.6.0+ * | Kontinuerlig | 8, 11 | 1 oktober 2021 |
| [2.17.10](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.10) | Den här korrigeringen förbättrar [Lista](/help/components/list.md) och [Navigering](/help/components/navigation.md) -komponenter för att visa den externa URL:en för omdirigeringsmål, aktiverar arv av sidbilder för kommande v2 i [Teaser](/help/components/teaser.md) och innehåller ytterligare felkorrigeringar. | 6.4.8.4+ * | 6.5.6.0+ * | Kontinuerlig | 8, 11 | 31 augusti 2021 |
| [2.17.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.8) | Den här korrigeringsversionen Det här är en korrigeringsversion som åtgärdar en inkompatibel ändring bakåt som introducerades tidigare. | 6.4.8.4+ * | 6.5.6.0+ * | Kontinuerlig | 8, 11 | 2 augusti 2021 |
| [2.17.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.6) | Den här korrigeringsversionen har stöd för webbplatskartor för sidor och innehåller olika tillgänglighetsförbättringar. | 6.4.8.4+ * | 6.5.6.0+ * | Kontinuerlig | 8, 11 | 29 juli 2021 |
| [2.17.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.2) | Den här korrigeringsversionen innehåller en korrigering för [Datalager](/help/developing/data-layer/overview.md) inte med AEMaaCS. | 6.4.8.4+ * | 6.5.6.0+ * | Kontinuerlig | 8, 11 | 8 juli 2021 |
| [2.17.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.0) | Den här versionen innehåller tekniska förhandsvisningar av många nya komponentversioner med stöd för länkhanterarfunktioner samt en teknisk förhandsgranskning av en bildfunktion för [Sidkomponent.](/help/components/page.md) Flera felkorrigeringar ingår också. | 6.4.8.4+ * | 6.5.6.0+ * | Kontinuerlig | 8, 11 | 16 juni 2021 |
| [2.16.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.16.4) | Det här är en korrigeringsversion som åtgärdar ett problem med den nya länkhanteraren. | 6.4.8.1+ * | 6.5.5.0+ * | Kontinuerlig | 8, 11 | 19 maj 2021 |
| [2.16.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.16.2) | Det här var en korrigeringsversion som huvudsakligen åtgärdade ett problem med den nya länkhanteraren och lade till en förbättring för stöd av flersidiga program för [PWA.](/help/components/page.md#pwa-support) | 6.4.8.1+ * | 6.5.5.0+ * | Kontinuerlig | 8, 11 | 15 maj 2021 |
| [2.16.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.16.0) | Den här versionen fokuserar på tillgänglighetsförbättringar och introducerar en ny länkhanterare för befintliga komponenter. | 6.4.8.1+ * | 6.5.5.0+ * | Kontinuerlig | 8, 11 | 22 april 2021 |
| [2.15.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.15.2) | Det här var en korrigeringsversion som huvudsakligen åtgärdade problem med [Datalager](/help/developing/data-layer/overview.md) bakåtkompatibilitet och IT-tester misslyckas i vissa situationer. | 6.4.8.1+ * | 6.5.5.0+ * | Kontinuerlig | 8, 11 | 16 mars 2021 |
| [2.15.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.15.0) | Den här versionen har stöd för [progressiva webbprogram (PWA) i sidkomponenten](/help/components/page.md#pwa-support) och stöder version 2.0.0 av [Adobe datalager.](/help/developing/data-layer/overview.md) | 6.4.8.1+ * | 6.5.5.0+ * | Kontinuerlig | 8, 11 | 23 februari 2021 |
| [2.14.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.14.0) | Den här versionen innehåller nya alternativ för [Bädda in komponent](/help/components/embed.md) och introducerar Brand Slug på [page](/help/components/page.md) samt många frågor. | 6.4.8.1+ * | 6.5.5.0+ * | Kontinuerlig | 8, 11 | 9 februari 2021 |
| [2.13.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.13.2) | Det här var en patch som åtgärdade ett problem med RTE när den användes i AEMaaCS | 6.4.8.1+ * | 6.5.5.0+ * | Kontinuerlig | 8, 11 | 16 december 2020 |
| [2.13.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.13.0) | Den här versionen innehåller nya Dynamic Media-funktioner för [Bildkomponent.](/help/components/image.md) | 6.4.8.1+ * | 6.5.5.0+ * | Kontinuerlig | 8, 11 | 4 december 2020 |
| [2.12.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.2) | Det här var en patch-version för 2.12.0 med smärre korrigeringar. | 6.4.8.1+ * | 6.5.5.0+ * | Kontinuerlig | 8, 11 | 11 november 2020 |
| [2.12.1](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.1) | Det här var en korrigeringsversion för 2.12.0 som åtgärdar ett större fel i [Bildkomponent.](/help/components/image.md) | 6.4.8.1+ * | 6.5.5.0+ * | Kontinuerlig | 8, 11 | 5 november 2020 |
| [2.12.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.0) | Den här versionen introducerades [en ny formulärhanterare för POST,](/help/components/forms/form-container.md#post-data) möjligheten att inkludera anpassad CSS, Javascript och metadata [taggar via kontextmedveten konfiguration,](/help/developing/including-clientlibs.md#context-aware-loading) och `DataLayerBuilder` verktyg till [förenkla integreringen av datalager i anpassade komponenter.](/help/developing/data-layer/integrations.md#enabling-custom-components) | 6.4.8.1+ * | 6.5.5.0+ * | Kontinuerlig | 8, 11 | 29 oktober 2020 |
| [2.11.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.11.0) | Den här versionen introducerades [Stöd för AMP.](/help/developing/amp.md) | 6.4.8.1+ * | 6.5.5.0+ * | Kontinuerlig | 8, 11 | 20 juli 2020 |
| [2.10.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.10.0) | I den här versionen presenterades [PDF Viewer-komponent.](/help/components/pdf-viewer.md) | 6.4.8.1+ | 6.5.5.0+ | Kontinuerlig | 8, 11 | 17 juni 2020 |
| [2.9.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.9.0) | Den här versionen aktiverade integrering med [Adobe-klientdatalager](/help/developing/data-layer/overview.md) och introducerade [Progress Bar-komponent.](/help/components/progress-bar.md) | 6.4.8.0+ | 6.5.4.0+ | Kontinuerlig | 8, 11 | 29 maj 2020 |
| [2.8.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.8.0) | Den här versionen fokuserar på korrigeringar med små förbättringar. | 6.4.4.0+ | 6.5.0.0+ | Kontinuerlig | 8, 11 | 5 december 2019 |
| [2.7.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.7.0) | Den här versionen presenterade det nya [Bädda in komponent.](/help/components/embed.md) | 6.4.4.0+ | 6.5.0.0+ | Kontinuerlig | 8, 11 | 25 september 2019 |
| [2.6.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.6.0) | Den här versionen presenterade det nya [Experience Fragment-komponent.](/help/components/experience-fragment.md) | 6.4.4.0+ | 6.5.0.0+ | Kontinuerlig | 8, 11 | 6 september 2019 |
| [2.5.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.5.0) | Den här versionen presenterade det nya [Accordion,](/help/components/accordion.md) [Button,](/help/components/button.md) [Behållare,](/help/components/container.md) och [Ladda ned komponenter.](/help/components/download.md) | 6.4.2.0+ | 6.5.0.0+ | Kontinuerlig | 8, 11 | 25 juni 2019 |
| [2.4.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.4.0) | I den här versionen presenterades [Content Fragment List Component.](/help/components/content-fragment-list.md) | 6.4.2.0+ | 6.5.0.0+ | Kontinuerlig | 8, 11 | 7 maj 2019 |
| [2.3.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.2) | Den här versionen fokuserar på förbättringar av [Komponentbibliotek,](https://aemcomponents.dev) men innehåller även vissa funktionsförbättringar för [Avgränsarkomponent.](/help/components/separator.md) | 6.4.2.0+ | 6.5.0.0+ | Kontinuerlig | 8 | 14 mars 2019 |
| [2.3.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.0) | Den här versionen fokuserade på [Komponentbibliotek](https://aemcomponents.dev) samt att vi presenterar nya [Separatorkomponent,](/help/components/separator.md) men innehåller även vissa funktionsförbättringar för [Bildkomponent.](/help/components/image.md) | 6.4.2.0+ | - | - | 8 | 11 februari 2019 |
| [2.2.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.2) | Den här versionen fokuserade främst på felkorrigeringar, men innehåller även vissa funktionsförbättringar för [Carousel Component.](/help/components/carousel.md) | 6.4.2.0+ | - | - | 8 | 27 november 2018 |
| [2.2.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.0) | I den här versionen presenterades [Tabbar-komponent](/help/components/tabs.md) och [Carousel-komponent](/help/components/carousel.md) samt förbättringar av [Bildkomponent,](/help/components/image.md) [Sidkomponent,](/help/components/page.md) och [Titelkomponent](/help/components/title.md) och förbättrad spårning. | 6.4.2.0+ | - | - | 8 | 16 oktober 2018 |
| [2.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.1.0) | I den här versionen presenterades [Teaser Component](/help/components/teaser.md) tillsammans med förbättringar av [Bildkomponent](/help/components/image.md) och många felkorrigeringar. | 6.4.2.0+ | - | - | 8 | 13 juli 2018 |
| [2.0.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.8) | Det här var en felfri version. | 6.4.0.0+ | - | - | 8 | 12 juni 2018 |
| [2.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.6) | Den här versionen innehåller förbättringar under huven, felkorrigeringar och små förbättringar som stöd för att vända bilder i [Bildkomponent.](/help/components/image.md) | 6.4.0.0+ | - | - | 8 | 11 april 2018 |
| [2.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.4) | Den här versionen fokuserade mest på förbättringar under huven, felkorrigeringar och några mindre förbättringar av [Bildkomponent,](/help/components/image.md) [Sidkomponent,](/help/components/page.md) och [Innehållsfragmentkomponent.](/help/components/content-fragment-component.md) | 6.4.0.0+ | - | - | 8 | 7 mars 2018 |
| [2.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.0) | I den här versionen presenterades [Navigeringskomponent,](/help/components/navigation.md) [Språknavigeringskomponent,](/help/components/language-navigation.md) och [Snabbsökningskomponent](/help/components/quick-search.md) och implementera [Formatsystem](/help/get-started/authoring.md#component-styling) för alla komponenter. | 6.4.0.0+ | - | - | 8 | 16 januari 2018 |
| [1.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.1.0) | Den här versionen implementerar JSON-export för alla komponenter och introducerar [Innehållsfragmentkomponent.](/help/components/content-fragment-component.md) | 6.4.0.0+ | - | - | 8 | 10 oktober 2017 |
| [1.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.6) | Den här versionen innehåller flera korrigeringar för [Bildkomponent.](/help/components/image.md) | 6.4.0.0+ | - | - | 8 | 4 augusti 2017 |
| [1.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.4) | Den här versionen lägger till korrigeringar för [Sidkomponent,](/help/components/page.md) [Bildkomponent,](/help/components/image.md) och olika globala korrigeringar och förbättringar. | 6.4.0.0+ | - | - | 8 | 26 april 2017 |
| [1.0.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.all-1.0.2) | Den här versionen innehåller korrigeringar för animerade GIF-bilder i [Bildkomponent.](/help/components/image.md) | 6.4.0.0+ | - | - | 7 | 22 mars 2017 |
| [1.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.0) | Ursprunglig version av kärnkomponenter. | 6.4.0.0+ | - | - | 7 | 20 mars 2017 |

>[!NOTE]
>
>(*) Sedan version 2.11.0, `org.apache.sling.models.impl` version 1.4.12 eller senare krävs (på grund av [SLING-8781](https://issues.apache.org/jira/browse/SLING-8781)). Detta kommer att anges för AEM 6.4 och 6.5 i ett framtida Service Pack. Fram till dess ingår Sling Models-paketet i `core.wcm.components.all` paket.

>[!TIP]
>
>Precis som med AEM rekommenderar Adobe att utvecklare använder [senaste versionen och versioner av de viktigaste komponenterna](https://github.com/adobe/aem-core-wcm-components/releases/latest) som är kompatibel med den version av AEM som de körs för att dra nytta av de senaste korrigeringarna och funktionerna.

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
| **[Dolt formulär](components/forms/form-hidden.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
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
| **[Experience Fragment](components/experience-fragment.md)** |  |  |  |  |  |  |  |  | v1 | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Bädda in](components/embed.md)** |  |  |  |  |  |  |  |  |  | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Förloppsindikator](components/progress-bar.md)** |  |  |  |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 |
| **[PDF Viewer](components/pdf-viewer.md)** |  |  |  |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 |
| **[Innehållsförteckning](components/tableofcontents.md)** |  |  |  |  |  |  |  |  |  |  |  |  |  | v1 | v1 |

## Versioner och releaser {#versions-and-releases}

Kärnkomponenter distribueras via GitHub. Detta gör att Adobe snabbare kan lägga till funktioner i komponenterna och även göra det möjligt för communityanvändare utanför AEM.

Core-komponenterna är tillgängliga med definierade AEM som de är kompatibla med. Detta innebär att en AEM kan ha stöd för flera versioner eller versioner av de centrala komponenterna.

### Versioner {#versions}

Den största upprepningen av kärnkomponenterna är **versioner**. Varje komponent har en version. Versioner markeras med **v** läggs till med ett positivt heltal som inte är noll, till exempel v1 och v2. Versionerna ökas endast för ändringar som inte är bakåtkompatibla, vilket vanligtvis är fallet när nya funktioner införs.

Utvecklare och administratörer kan känna igen versioner av kärnkomponenterna med ett antal i sina resurstypssökvägar och i de fullständiga Java-klassnamnen för sina implementeringar. Versionsnumret representerar en huvudversion som definieras av [riktlinjer för semantisk versionshantering](https://semver.org/).

Mer information om grundkomponentversionerna finns i [utvecklardokumentation för kärnkomponenterna](developing/guidelines.md).

### Utgåvor {#releases}

Kärnkomponenterna görs tillgängliga via **releaser** och [representerar de faktiska publicerade artefakter som finns på GitHu.](https://github.com/adobe/aem-core-wcm-components/releases) Releaser anges med ett decimaltal i formatet `X.Y.Z` och samla ihop alla kärnkomponenter i ett och samma paket.

* **Större releaser** innehåller helt nya komponenter, förbättringar av befintliga versioner av komponenter samt standardfelkorrigeringar. Detta representeras av en ökning i `X` -komponenten i versionsnumret.
* **Mindre releaser** introducerar nya komponenter, nya funktioner i befintliga versioner av komponenter samt felkorrigeringar. Detta representeras av en ökning i `Y` -komponenten i versionsnumret.
* **Patch releases** innehåller bara felkorrigeringar. Detta representeras av en ökning i `Z` -komponenten i versionsnumret.

>[!NOTE]
>
>Releaser kan innehålla flera versioner av samma komponent.
>
>Samma version av en komponent kan visas i flera versioner.

## Stöd för kärnkomponenter {#core-components-support}

Core Components är en integrerad del av AEM och stöds enligt samma villkor som om de levererades som en del av QuickStart.

I likhet med andra produktfunktioner är den allmänna regeln om produktlivslängd:

* Komponenterna meddelas först att bli borttagna innan de tas bort
* Först tas de bort från AEM efter meddelandet.

Detta ger kunderna minst en releasecykel att gå över till den nya versionen av komponenten innan supporten upphör.

Versionen för varje komponent anger tydligt vilka AEM som stöds. När stödet upphör för en version av AEM gör det även stödet för kärnkomponenterna för den versionen av AEM.

Mer information om stöd för komponentanpassningar finns i [Anpassa kärnkomponenter](developing/customizing.md) sidan med de relevanta Core Components-versionerna.

## Stöd för Foundation Component {#foundation-component-support}

Adobe-utvecklingsbetoningen har flyttats till kärnkomponenterna och nya funktioner kommer att läggas till även i fortsättningen.

[Nästan alla Foundation-komponenter har ersatts med AEM 6.5](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/siteandpage/default-components-foundation.html) och endast större felkorrigeringar kommer att övervägas för de Foundation Components som fortsätter.
