---
title: Huvudkomponentversioner
description: Kärnkomponenter publiceras som releaser som kan innehålla mer än en version av samma kärnkomponenter. I det här dokumentet förklaras vad som är releaser och versioner och hur man förstår kompatibiliteten med kärnkomponenter och AEM.
role: Architect, Developer, Admin, User
exl-id: 7d4dbe46-4013-4217-b815-cdb1462072c6
source-git-commit: 5271174f5c325a9793dc155c763054752c7308b8
workflow-type: tm+mt
source-wordcount: '2275'
ht-degree: 11%

---

# Huvudkomponentversioner {#core-components-versions}

Den aktuella versionen av Core Components är 2.17.8 och är kompatibel med [AEM som en Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html) och [lokala AEM](https://docs.adobe.com/content/help/en/experience-manager-65/user-guide/home.html)-installationer.

## Versionshistorik och kompatibilitet {#release-history-and-compatibility}

Core Components är utformade för att vara flexibla och kompatibla med alla AEM som stöds. På grund av detta kan en version av komponenterna innehålla flera versioner av samma komponent.

I följande tabeller visas kompatibiliteten för de versioner av kärnkomponenterna som ingår i releaserna.

### Versionshistorik och krav {#release-history-requirements}

Följande tabell, vars innehåll är [tillgängligt på GitHub med fullständig versionsinformation](https://github.com/adobe/aem-core-wcm-components/releases), ger en översikt över versionerna av kärnkomponenterna och deras kompatibilitet med AEM och Java-versioner.

| Frigör | Beskrivning | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service | Java | Releasedatum |
|---|---|---|---|---|---|---|
| [2.17.10](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.10) | Den här korrigeringen förbättrar [List](/help/components/list.md) och [Navigation](/help/components/navigation.md)-komponenterna för att visa den externa URL:en för omdirigeringsmål, aktiverar sidbildsarv för [Teaser](/help/components/teaser.md)-komponenten och innehåller ytterligare felkorrigeringar. | 6.4.8.4+ * | 6.5.6.0+ * | Kontinuerlig | 8, 11 | 31 augusti 2021 |
| [2.17.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.8) | Den här korrigeringsversionen Det här är en korrigeringsversion som åtgärdar en inkompatibel ändring bakåt som introducerades tidigare. | 6.4.8.4+ * | 6.5.6.0+ * | Kontinuerlig | 8, 11 | 2 augusti 2021 |
| [2.17.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.6) | Den här korrigeringsversionen har stöd för webbplatskartor för sidor och innehåller olika tillgänglighetsförbättringar. | 6.4.8.4+ * | 6.5.6.0+ * | Kontinuerlig | 8, 11 | 29 juli 2021 |
| [2.17.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.2) | Den här korrigeringsversionen innehåller en korrigering för [datalagret](/help/developing/data-layer/overview.md) som inte fungerar med AEMaaCS. | 6.4.8.4+ * | 6.5.6.0+ * | Kontinuerlig | 8, 11 | 8 juli 2021 |
| [2.17.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.0) | Den här versionen innehåller tekniska förhandsvisningar av många nya komponentversioner med stöd för länkhanterarfunktioner samt en teknisk förhandsvisning av en aktuell bildfunktion för [sidkomponenten.](/help/components/page.md) Flera felkorrigeringar ingår också. | 6.4.8.4+ * | 6.5.6.0+ * | Kontinuerlig | 8, 11 | 16 juni 2021 |
| [2.16.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.16.4) | Det här är en korrigeringsversion som åtgärdar ett problem med den nya länkhanteraren. | 6.4.8.1+ * | 6.5.5.0+ * | Kontinuerlig | 8, 11 | 19 maj 2021 |
| [2.16.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.16.2) | Det här var en korrigeringsrelease som huvudsakligen åtgärdade ett problem med den nya länkhanteraren och lade till en förbättring som stöder flersidiga program för [PWA.](/help/components/page.md#pwa-support) | 6.4.8.1+ * | 6.5.5.0+ * | Kontinuerlig | 8, 11 | 15 maj 2021 |
| [2.16.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.16.0) | Den här versionen fokuserar på tillgänglighetsförbättringar och introducerar en ny länkhanterare för befintliga komponenter. | 6.4.8.1+ * | 6.5.5.0+ * | Kontinuerlig | 8, 11 | 22 april 2021 |
| [2.15.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.15.2) | Det här var en korrigeringsrelease som huvudsakligen åtgärdar problem med [bakåtkompatibilitet för datalager](/help/developing/data-layer/overview.md) och IT-tester misslyckades i vissa situationer. | 6.4.8.1+ * | 6.5.5.0+ * | Kontinuerlig | 8, 11 | 16 mars 2021 |
| [2.15.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.15.0) | Den här versionen innehåller stöd för [progressiva webbprogram (PWA) i Page Component](/help/components/page.md#pwa-support) och stöder version 2.0.0 i [datalagret Adobe.](/help/developing/data-layer/overview.md) | 6.4.8.1+ * | 6.5.5.0+ * | Kontinuerlig | 8, 11 | 23 februari 2021 |
| [2.14.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.14.0) | Den här versionen innehåller nya alternativ för [Embed Component](/help/components/embed.md) och introducerar Brand Slug på [sidnivå](/help/components/page.md) samt åtgärdar många problem. | 6.4.8.1+ * | 6.5.5.0+ * | Kontinuerlig | 8, 11 | 9 februari 2021 |
| [2.13.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.13.2) | Det här var en patch som åtgärdade ett problem med RTE när den användes i AEMaaCS | 6.4.8.1+ * | 6.5.5.0+ * | Kontinuerlig | 8, 11 | 16 december 2020 |
| [2.13.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.13.0) | Den här versionen innehåller nya Dynamic Media-funktioner för [Image Component.](/help/components/image.md) | 6.4.8.1+ * | 6.5.5.0+ * | Kontinuerlig | 8, 11 | 4 december 2020 |
| [2.12.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.2) | Det här var en patch-version för 2.12.0 med smärre korrigeringar. | 6.4.8.1+ * | 6.5.5.0+ * | Kontinuerlig | 8, 11 | 11 november 2020 |
| [2.12.1](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.1) | Det här var en korrigeringsversion för 2.12.0 som åtgärdar ett större fel i [Image Component.](/help/components/image.md) | 6.4.8.1+ * | 6.5.5.0+ * | Kontinuerlig | 8, 11 | 5 november 2020 |
| [2.12.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.0) | I den här versionen introducerades [en ny formulärhanterare för POST;](/help/components/forms/form-container.md#post-data) möjlighet att inkludera anpassade CSS-, Javascript- och metadata [taggar via kontextmedveten konfiguration;](/help/developing/including-clientlibs.md#context-aware-loading) och ett `DataLayerBuilder`-verktyg för att [förenkla integreringen av datalager i anpassade komponenter.](/help/developing/data-layer/integrations.md#enabling-custom-components) | 6.4.8.1+ * | 6.5.5.0+ * | Kontinuerlig | 8, 11 | 29 oktober 2020 |
| [2.11.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.11.0) | I den här versionen introducerades stöd för [AMP.](/help/developing/amp.md) | 6.4.8.1+ * | 6.5.5.0+ * | Kontinuerlig | 8, 11 | 20 juli 2020 |
| [2.10.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.10.0) | I den här versionen introducerades komponenten [PDF Viewer.](/help/components/pdf-viewer.md) | 6.4.8.1+ | 6.5.5.0+ | Kontinuerlig | 8, 11 | 17 juni 2020 |
| [2.9.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.9.0) | Den här versionen aktiverade integrering med [Adobe Client Data Layer](/help/developing/data-layer/overview.md) och introducerade komponenten [Progress Bar.](/help/components/progress-bar.md) | 6.4.8.0+ | 6.5.4.0+ | Kontinuerlig | 8, 11 | 29 maj 2020 |
| [2.8.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.8.0) | Den här versionen fokuserar på korrigeringar med små förbättringar. | 6.4.4.0+ | 6.5.0.0+ | Kontinuerlig | 8, 11 | 5 december 2019 |
| [2.7.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.7.0) | I den här versionen introducerades den nya [inbäddningskomponenten.](/help/components/embed.md) | 6.4.4.0+ | 6.5.0.0+ | Kontinuerlig | 8, 11 | 25 september 2019 |
| [2.6.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.6.0) | I den här versionen introducerades den nya [Experience Fragment-komponenten.](/help/components/experience-fragment.md) | 6.4.4.0+ | 6.5.0.0+ | Kontinuerlig | 8, 11 | 6 september 2019 |
| [2.5.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.5.0) | I den här versionen introducerades den nya [dragspelspanelen,](/help/components/accordion.md) [Knapp,](/help/components/button.md) [behållare,](/help/components/container.md) och [hämtningskomponenter.](/help/components/download.md) | 6.4.2.0+ | 6.5.0.0+ | Kontinuerlig | 8, 11 | 25 juni 2019 |
| [2.4.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.4.0) | I den här versionen introducerades [listkomponenten för innehållsfragment.](/help/components/content-fragment-list.md) | 6.4.2.0+ | 6.5.0.0+ | Kontinuerlig | 8, 11 | 7 maj 2019 |
| [2.3.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.2) | Den här versionen fokuserade på förbättringar av [komponentbiblioteket,](https://aemcomponents.dev), men innehåller också vissa funktionsförbättringar för [avgränsningskomponenten.](/help/components/separator.md) | 6.4.2.0+ | 6.5.0.0+ | Kontinuerlig | 8 | 14 mars 2019 |
| [2.3.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.0) | Den här versionen fokuserade på [komponentbiblioteket](https://aemcomponents.dev) och introducerade den nya [avgränsningskomponenten,](/help/components/separator.md), men innehåller också vissa funktionsförbättringar för [bildkomponenten.](/help/components/image.md) | 6.4.2.0+ | - | - | 8 | 11 februari 2019 |
| [2.2.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.2) | Den här versionen fokuserade främst på felkorrigeringar, men innehåller också vissa funktionsförbättringar för [Carousel-komponenten.](/help/components/carousel.md) | 6.4.2.0+ | - | - | 8 | 27 november 2018 |
| [2.2.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.0) | I den här versionen introducerades komponenten [Tabbar](/help/components/tabs.md) och [Carousel-komponenten](/help/components/carousel.md) samt förbättringar av [Image-komponenten](/help/components/image.md) [Page Component,](/help/components/page.md) och [Title Component](/help/components/title.md) och förbättrad spårning. | 6.4.2.0+ | - | - | 8 | 16 oktober 2018 |
| [2.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.1.0) | I den här versionen introducerades [Teaser Component](/help/components/teaser.md) tillsammans med förbättringar av [Image Component](/help/components/image.md) och flera felkorrigeringar. | 6.4.2.0+ | - | - | 8 | 13 juli 2018 |
| [2.0.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.8) | Det här var en felfri version. | 6.4.0.0+ | - | - | 8 | 12 juni 2018 |
| [2.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.6) | Den här versionen innehåller förbättringar under huven, felkorrigeringar och små förbättringar, inklusive stöd för bildvändning i [Image Component.](/help/components/image.md) | 6.4.0.0+ | - | - | 8 | 11 april 2018 |
| [2.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.4) | Den här versionen fokuserade mest på förbättringar under huven, felkorrigeringar och några mindre förbättringar av [Image Component,](/help/components/image.md) [Page Component,](/help/components/page.md) och [Content Fragment Component.](/help/components/content-fragment-component.md) | 6.4.0.0+ | - | - | 8 | 7 mars 2018 |
| [2.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.0) | I den här versionen introducerades [navigeringskomponenten,](/help/components/navigation.md) [språknavigeringskomponenten,](/help/components/language-navigation.md) och [snabbsökskomponenten](/help/components/quick-search.md) och [formatsystemet](/help/get-started/authoring.md#component-styling) för alla komponenter. | 6.4.0.0+ | - | - | 8 | 16 januari 2018 |
| [1.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.1.0) | Den här versionen implementerar JSON-export för alla komponenter och introducerar komponenten [Content Fragment.](/help/components/content-fragment-component.md) | 6.4.0.0+ | - | - | 8 | 10 oktober 2017 |
| [1.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.6) | Den här versionen lägger till flera korrigeringar för [Image Component.](/help/components/image.md) | 6.4.0.0+ | - | - | 8 | 4 augusti 2017 |
| [1.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.4) | Den här versionen lägger till korrigeringar för [sidkomponenten,](/help/components/page.md) [Image Component,](/help/components/image.md) och olika globala korrigeringar och förbättringar. | 6.4.0.0+ | - | - | 8 | 26 april 2017 |
| [1.0.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.all-1.0.2) | Den här versionen lägger till korrigeringar för animerade GIF-bilder i [Bildkomponent.](/help/components/image.md) | 6.4.0.0+ | - | - | 7 | 22 mars 2017 |
| [1.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.0) | Ursprunglig version av kärnkomponenter. | 6.4.0.0+ | - | - | 7 | 20 mars 2017 |

>[!NOTE]
>
>(*) Sedan version 2.11.0 krävs `org.apache.sling.models.impl` version 1.4.12 eller senare (på grund av [SLING-8781](https://issues.apache.org/jira/browse/SLING-8781)). Detta kommer att anges för AEM 6.4 och 6.5 i ett framtida Service Pack. Fram till dess ingår Sling Models-paketet i `core.wcm.components.all`-paketet.

>[!TIP]
>
>Precis som med AEM rekommenderar Adobe att utvecklare använder den [senaste versionen av de kärnkomponenter](https://github.com/adobe/aem-core-wcm-components/releases/latest) som är tillgängliga och kompatibla med den version av AEM som de kör för att dra nytta av de senaste korrigeringarna och funktionerna.

### Komponentversioner och releaser {#component-versions-and-releases}

Tabellen nedan visar vilka versioner av vilka komponenter som ingår i vilka versioner av kärnkomponenterna släpps.

|  | Version 1.0.0 - 1.0.6 | Version 1.1.0 | Version 2.0.0 - 2.0.8 | Version 2.1.0 | Version 2.2.0-2.2.0 | Version 2.3.0-2.3.2 | Version 2.4.0 | Version 2.5.0 | Version 2.6.0 | Version 2.7.0-2.8.0 | Version 2.9.0+ |
|---|---|---|---|---|---|---|---|---|---|---|---|
| **[Sida](components/page.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Titel](components/title.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Bild](components/image.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Lista](components/list.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Breadcrumb](components/breadcrumb.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Delning av sociala medier](components/sharing.md)** | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Formulärbehållare](components/forms/form-container.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Formulärtext](components/forms/form-text.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Formuläralternativ](components/forms/form-options.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Dolt formulär](components/forms/form-hidden.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Formulärknapp](components/forms/form-button.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Innehållsfragment](components/content-fragment-component.md)** |  | Sandbox | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1, v2 | v1, v2 |
| **[Navigering](components/navigation.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Språknavigering](components/language-navigation.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Snabbsökning](components/quick-search.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Teaser](components/teaser.md)** |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Tabbar](components/tabs.md)** |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Carousel](components/carousel.md)** |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Avgränsare](components/separator.md)** |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Innehållsfragmentlista](components/content-fragment-list.md)** |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 |
| **[Dragspel](components/accordion.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 |
| **[Knapp](components/button.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 |
| **[Behållare](components/container.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 |
| **[Hämta](components/download.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 |
| **[Experience Fragment](components/experience-fragment.md)** |  |  |  |  |  |  |  |  | v1 | v1 | v1 |
| **[Bädda in](components/embed.md)** |  |  |  |  |  |  |  |  |  | v1 | v1 |
| **[Förloppsindikator](components/progress-bar.md)** |  |  |  |  |  |  |  |  |  |  | v1 |
| **[PDF Viewer](components/pdf-viewer.md)** |  |  |  |  |  |  |  |  |  |  | v1 |

## Versioner och releaser {#versions-and-releases}

Kärnkomponenter distribueras via GitHub. Detta gör att Adobe snabbare kan lägga till funktioner i komponenterna och även göra det möjligt för communityanvändare utanför AEM.

Core-komponenterna är tillgängliga med definierade AEM som de är kompatibla med. Detta innebär att en AEM kan ha stöd för flera versioner eller versioner av de centrala komponenterna. Detta ger större flexibilitet än tidigare Foundation Components, som var knutna till en viss version av AEM.

### Versioner {#versions}

Huvudupprepningen av kärnkomponenterna är **versionerna**. Varje komponent har en version. Versioner anges med **v** som tillägg med ett positivt heltal som inte är noll, till exempel v1 och v2. Versionerna ökas endast för ändringar som inte är bakåtkompatibla, vilket vanligtvis är fallet när nya funktioner införs.

Utvecklare och administratörer kan känna igen versioner av kärnkomponenterna med ett antal i sina resurstypssökvägar och i de fullständiga Java-klassnamnen för sina implementeringar. Detta versionsnummer representerar en huvudversion enligt definitionen i [riktlinjerna för semantisk versionshantering](https://semver.org/).

Mer information om grundkomponentversionerna finns i [utvecklardokumentationen för grundkomponenterna](developing/guidelines.md).

### Utgåvor {#releases}

Kärnkomponenterna är tillgängliga via **releaser** och [representerar de faktiska publicerade artefakterna som är tillgängliga på GitHub](https://github.com/adobe/aem-core-wcm-components/releases). Releaser anges med ett decimaltal i formatet X.Y.Z och samlar ihop alla kärnkomponenter som ett slutproduktspaket.

* **I större** versioner kan nya versioner av befintliga komponenter introduceras tillsammans med helt nya komponenter samt vanliga felkorrigeringar. Detta representeras av en ökning i X-komponenten i versionsnumret.
* **Viktiga releaser** kan innehålla nya funktioner för befintliga versioner av komponenter tillsammans med felkorrigeringar. Detta representeras av en ökning i Y-komponenten i versionsnumret.
* **Mindre** releaser innehåller bara felkorrigeringar. Detta representeras av en ökning i Z-komponenten i versionsnumret.

>[!NOTE]
>
>Releaser kan innehålla flera versioner av samma komponent.
>
>Samma version av en komponent kan visas i flera versioner.

## Stöd för kärnkomponenter {#core-components-support}

Kärnkomponenter är en integrerad del av AEM och stöds som de är, på samma villkor som om de levererades som en del av QuickStart.

I likhet med andra produktfunktioner är den allmänna regeln om produktlivslängd:

* Komponenterna meddelas först att bli borttagna innan de tas bort
* Först tas de bort från AEM efter meddelandet.

Detta ger kunderna minst en releasecykel att gå över till den nya versionen av komponenten innan supporten upphör.

Versionen för varje komponent anger tydligt vilka AEM som stöds. När stödet upphör för en version av AEM gör det även stödet för kärnkomponenterna för den versionen av AEM.

Mer information om stöd för komponentanpassningar finns på sidan [Anpassa kärnkomponenter](developing/customizing.md) i den relevanta Core Components Version.

## Stöd för Foundation Component {#foundation-component-support}

Adobe-utvecklingsbetoningen har flyttats till kärnkomponenterna och nya funktioner kommer att läggas till även i fortsättningen.

[Nästan alla Foundation-komponenter har ersatts med AEM 6.5](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/siteandpage/default-components-foundation.html) och endast större felkorrigeringar kommer att övervägas för Foundation Components som fortsätter.
