---
title: AEM Project Archetype
description: En projektmall för AEM
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Administrator
translation-type: tm+mt
source-git-commit: 0e737fc766225e00c6d9f5a4c2240e05b49a9a62
workflow-type: tm+mt
source-wordcount: '1043'
ht-degree: 3%

---


# AEM Project Archetype {#aem-project-archetype}

AEM Project Archetype är en Maven-mall som skapar ett minimalt, metodbaserat Adobe Experience Manager-projekt (AEM) som utgångspunkt för webbplatsen.

>[!TIP]
>
>Den senaste AEM Project Archetype [finns på GitHub](https://github.com/adobe/aem-project-archetype).

## Resurser {#resources}

* **Arketype Documentation (this document):** Översikt över arkitekturen och dess olika moduler.
   * **[Använda arkitypen:](using.md)** mer information om hur du använder arkitypen och de tillgängliga modulerna
   * **[ui.front:](uifrontend.md)** Använda modulen för framände
* Följande självstudiekurser är baserade på denna arketyp:
   * **[WKND-webbplats:](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)** Lär dig hur du startar en ny ny webbplats.
   * **[WKND Single Page App:](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)** Lär dig hur du skapar en React- eller Angular-webbapp som är helt redigerbar i AEM.

## Funktioner {#features}

* **Bästa praxis:** Bootstrap med alla de senaste rekommenderade metoderna från Adobe.
* **Lågkod:** Redigera mallar, skapa innehåll, distribuera CSS och webbplatsen är klar att publiceras.
* **Molnklar:** Om du vill kan du använda  [AEM som en molntjänst för ](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html) att publicera produkten på några dagar och förenkla skalbarhet och underhåll.
* **Dispatcher:** Ett projekt är bara färdigt med en  [Dispatcher-](https://docs.adobe.com/content/help/en/experience-manager-dispatcher/using/dispatcher.html) konfiguration som garanterar hastighet och säkerhet.
* **Flera platser:** Om det behövs genererar arkivtypen innehållsstrukturen för en  [flerspråkig och flerregionsinstallation](https://docs.adobe.com/content/help/en/experience-manager-65/administering/introduction/msm.html).
* **Kärnkomponenter:** Författare kan skapa nästan vilken layout som helst med vår mångsidiga  [uppsättning standardiserade komponenter](/help/introduction.md).
* **Redigerbara mallar:** Sammanställ praktiskt taget alla  [mallar utan kod](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html) och definiera vad författarna får redigera.
* **Responsiv layout:** På mallar eller enskilda sidor  [definierar du hur elementen ska ](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/responsive-layout.html) omformas för definierade brytpunkter.
* **Sidhuvud och sidfot:** Sammanställ och lokalisera dem utan kod med komponenternas [ ](https://docs.adobe.com/content/help/en/experience-manager-core-components/using/get-started/localization.html)lokaliseringsfunktioner.
* **Style System:** Undvik att skapa anpassade komponenter genom att låta författare  [använda olika ](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/style-system.html) format på dem.
* **Front-End Build:** Front-end-utvecklare kan  [skapa AEM ](uifrontend.md#webpack-dev-server) sidor och  [bygga ](uifrontend.md) klientbibliotek med Webpack, TypeScript och SASS.
* **WebApp-Ready:** För webbplatser som använder  [](uifrontend-react.md) Reactor  [Angular](uifrontend-angular.md) använder du  [SPA ](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/headless/spa/developing.html) SDKför att bevara utvecklingen  [i appen](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html).
* **Handel aktiverad:** För projekt som vill integrera  [AEM ](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/commerce/home.html) Handel med handelslösningar som  [](https://magento.com/) Magentousing the  [Commerce Core Components](https://github.com/adobe/aem-core-cif-components).
* **Exempelkod:** Checka ut HelloWorld-komponenten och exempelmodellerna, servletarna, filtren och schemaläggaren.
* **Öppna källa:** Bifoga  [](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) förbättringarna om något inte är som det ska!

## Användning

Om du vill generera ett projekt justerar du följande kommandorad efter dina behov:

```shell
mvn -B archetype:generate \
 -D archetypeGroupId=com.adobe.aem \
 -D archetypeArtifactId=aem-project-archetype \
 -D archetypeVersion=26 \
 -D appTitle="My Site" \
 -D appId="mysite" \
 -D groupId="com.mysite" \
```

* Ange `aemVersion=cloud` för [AEM som en Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html);\
   Ange `aemVersion=6.5.0` för [Adobes hanterade tjänster](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams) eller lokal.
Core Components-beroendet läggs bara till för andra versioner än molnbaserade, eftersom Core Components tillhandahålls OTB för AEM som en Cloud Service.
* Justera `appTitle="My Site"` för att definiera webbplatsens titel och komponentgrupper.
* Justera `appId="mysite"` för att definiera Maven artifactId, komponentens, konfigurations- och innehållsmappens namn samt klientbibliotekens namn.
* Justera `groupId="com.mysite"` för att definiera Maven groupId och Java Source Package.
* Leta upp listan med tillgängliga egenskaper för att se om det finns mer att justera.

## Tillgängliga egenskaper

| Namn | Standard | Beskrivning |
--------------------------|----------------|--------------------
| `appTitle` |  | Programtitel, kommer att användas för webbplatsens titel och komponentgrupper (t.ex. `"My Site"`). |
| `appId` |  | Tekniskt namn, kommer att användas för komponentnamn, konfigurations- och innehållsmappnamn samt klientbiblioteksnamn (t.ex. `"mysite"`). |
| `artifactId` | *`${appId}`* | Base Maven artifact ID (t.ex. `"mysite"`). |
| `groupId` |  | Grupp-ID för Bas Maven-grupp (t.ex. `"com.mysite"`). |
| `package` | *`${groupId}`* | Källpaket för Java (t.ex. `"com.mysite"`). |
| `version` | `1.0-SNAPSHOT` | Projektversion (t.ex. `1.0-SNAPSHOT`). |
| `aemVersion` | `cloud` | AEM (kan vara `cloud` för [AEM som en Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html); eller `6.5.0`, eller `6.4.4` för [Adobes hanterade tjänster](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams) eller lokalt). |
| `sdkVersion` | `latest` | När `aemVersion=cloud` en [SDK](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/developing/aem-as-a-cloud-service-sdk.html)-version kan anges (t.ex. `2020.02.2265.20200217T222518Z-200130`). |
| `includeDispatcherConfig` | `y` | Innehåller en dispatcherkonfiguration för antingen molnet eller AMS/lokalt, beroende på värdet `aemVersion` (kan vara `y` eller `n`). |
| `frontendModule` | `general` | Innehåller en Webpack-modul för klientbibliotek (kan vara `general` eller `none` för vanliga webbplatser). kan vara `angular` eller `react` för ett Single Page-program som implementerar [SPA Editor](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/headless/spa/editor-overview.html)). |
| `language` | `en` | Språkkod (ISO 639-1) för att skapa innehållsstrukturen från (t.ex. `en`, `deu`). |
| `country` | `us` | Landskod (ISO 3166-1) för att skapa innehållsstrukturen från (t.ex. `US`). |
| `singleCountry` | `y` | Innehåller en innehållsstruktur på överordnad (kan vara `y` eller `n`). |
| `includeExamples` | `n` | Innehåller en [exempelplats för komponentbibliotek](https://www.aemcomponents.dev/) (kan vara `y` eller `n`). |
| `includeErrorHandler` | `n` | Innehåller en anpassad 404-svarssida som kommer att vara global för hela instansen (kan vara `y` eller `n`). |
| `includeCommerce` | `n` | Inkluderar [CIF Core Components](https://github.com/adobe/aem-core-cif-components)-beroenden och genererar motsvarande artefakter. |
| `commerceEndpoint` |  | Krävs endast för CIF. Valfri slutpunkt för handelssystemet GraphQL-tjänst som ska användas (t.ex. `https://hostname.com/grapql`). |
| `datalayer` | `y` | Aktivera integrering med [Adobe Client Data Layer](/help/developing/data-layer/overview.md). |
| `amp` | `n` | Aktivera stöd för [AMP](/help/developing/amp.md) för genererade projektmallar. |

## Systemkrav

| Arketyp | AEM as a Cloud Service | AEM 6.5 | AEM 6.4 | Java SE | Maven |
|---------|---------|---------|---------|---------|---------|
| [26](https://github.com/adobe/aem-project-archetype/releases/tag/aem-project-archetype-26) | Kontinuerlig | 6.5.5.0+ | 6.4.8.1+ | 8, 11 | 3.3.9+ |

Konfigurera den lokala utvecklingsmiljön för [AEM som Cloud Service-SDK](https://docs.adobe.com/content/help/en/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html) eller för [äldre versioner av AEM](https://docs.adobe.com/content/help/en/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html).

### Kända fel

När du kör i Windows och genererar dispatcherkonfigurationen bör du köra i en förhöjd kommandotolk eller i Windows-undersystemet för Linux (se [#329](https://github.com/adobe/aem-project-archetype/issues/329)).

När arketypen körs i interaktivt läge (utan parametern `-B`) kan egenskaperna med standardvärden inte ändras, såvida inte den slutliga bekräftelsen stängs, vilket sedan upprepar frågorna genom att egenskaperna med standardvärden inkluderas i frågorna (se
[ARCHETYPE-308](https://issues.apache.org/jira/browse/ARCHETYPE-308) för mer information).

## Ytterligare läsning {#further-reading}

Mer information om hur du använder arkitypen, inklusive dess fördelar, alternativ och hur dess moduler fungerar, finns i [Använda dokumentet för arkitypen.](using.md).
