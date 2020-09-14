---
title: AEM Project Archetype
description: En projektmall för AEM
translation-type: tm+mt
source-git-commit: ed8c4609683d8e43ebc6859694ff7b9578fb07ff
workflow-type: tm+mt
source-wordcount: '989'
ht-degree: 3%

---


# AEM Project Archetype {#aem-project-archetype}

AEM Project Archetype är en Maven-mall som skapar ett minimalt, metodbaserat Adobe Experience Manager-projekt (AEM) som utgångspunkt för webbplatsen.

>[!TIP]
>
>Den senaste AEM Project Archetype [finns på GitHub](https://github.com/adobe/aem-project-archetype).

## Resurser {#resources}

* **Arketype Documentation (this document):** Översikt över arkitekturen och dess olika moduler.
   * **[Använda Archetype:](using.md)** Mer information om hur du använder arkitypen och tillgängliga moduler
   * **[ui.front:](uifrontend.md)** Så här använder du modulen för frontendbygge
* Följande självstudiekurser är baserade på denna arketyp:
   * **[WKND-plats:](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)** Lär dig hur du skapar en ny webbplats.
   * **[WKND Single Page App:](https://helpx.adobe.com/experience-manager/kt/sites/using/getting-started-spa-wknd-tutorial-develop.html)** Lär dig hur du skapar en React- eller Angular-webbapp som är helt redigerbar i AEM.

## Funktioner {#features}

* **God praxis:** Bootstrap er sajt med alla de senaste Adobe rekommenderade metoderna.
* **Lågkod:** Redigera mallarna, skapa innehåll, distribuera CSS så är sajten klar att publiceras.
* **Molnklart:** Om du vill kan du använda [AEM som en Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html) för att publicera på några dagar och förenkla skalbarhet och underhåll.
* **Dispatcher:** Ett projekt är bara färdigt med en [Dispatcher-konfiguration](https://docs.adobe.com/content/help/en/experience-manager-dispatcher/using/dispatcher.html) som garanterar hastighet och säkerhet.
* **Flera platser:** Vid behov genererar arkitypen innehållsstrukturen för en [flerspråkig och flerregionsinstallation](https://docs.adobe.com/content/help/en/experience-manager-65/administering/introduction/msm.html).
* **Kärnkomponenter:** Författare kan skapa nästan vilken layout som helst med vår mångsidiga [uppsättning standardiserade komponenter](/help/introduction.md).
* **Redigerbara mallar:** Sammanställ praktiskt taget alla [mallar utan kod](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html)och definiera vad författarna får redigera.
* **Responsiv layout:** På mallar eller enskilda sidor [definierar du hur elementen flödar](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/siteandpage/responsive-layout.html) om för de definierade brytpunkterna.
* **Sidhuvud och sidfot:** Sammanställ och lokalisera dem utan kod med komponenternas [](https://docs.adobe.com/content/help/en/experience-manager-core-components/using/get-started/localization.html)lokaliseringsfunktioner.
* **Formatsystem:** Undvik att bygga anpassade komponenter genom att låta författarna [använda olika format](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/style-system.html) på dem.
* **Front-End Build:** Front-end-utvecklare kan [skapa AEM sidor](uifrontend.md#webpack-dev-server) och [bygga klientbibliotek](uifrontend.md) med Webpack, TypeScript och SASS.
* **WebApp-Ready:** För webbplatser som använder [React](uifrontend-react.md) eller [Angular](uifrontend-angular.md)använder du [SPA SDK](https://docs.adobe.com/content/help/en/experience-manager-64/developing/headless/spas/spa-architecture.html) för att bevara utvecklingen [i appen](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html).
* **Exempelkod:** Kolla in komponenten HelloWorld och exempelmodellerna, serveleterna, filtren och schemaläggaren.
* **Öppen källa:** Om något inte är som det ska [du bidra](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) till förbättringarna!

## Användning

Om du vill generera ett projekt justerar du följande kommandorad efter dina behov:

```
mvn -B archetype:generate \
 -D archetypeGroupId=com.adobe.granite.archetypes \
 -D archetypeArtifactId=aem-project-archetype \
 -D archetypeVersion=23 \
 -D aemVersion=cloud \
 -D appTitle="My Site" \
 -D appId="mysite" \
 -D groupId="com.mysite" \
 -D frontendModule=general \
 -D includeExamples=n
```

* Set `aemVersion=cloud` for [AEM as a Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html);\
   Ange `aemVersion=6.5.0` för [Adobes hanterade tjänster](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams)eller lokalt.
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
| `aemVersion` | `6.5.0` | Målversion AEM (kan vara `cloud` för [AEM som Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html)). eller `6.5.0`, `6.4.4`eller `6.3.3` för [Adobes hanterade tjänster](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams) eller lokalt). |
| `sdkVersion` | `latest` | När `aemVersion=cloud` en [SDK](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/developing/aem-as-a-cloud-service-sdk.html) -version kan anges (t.ex. `2020.02.2265.20200217T222518Z-200130`). |
| `includeDispatcherConfig` | `y` | Innehåller en dispatcherkonfiguration för antingen molnet eller AMS/lokal, beroende på värdet för `aemVersion` (kan vara `y` eller `n`). |
| `frontendModule` | `none` | Innehåller en Webpack-modul för klientbibliotek (kan finnas `general` eller `none` för vanliga webbplatser). kan vara `angular` eller `react` för ett Single Page-program som implementerar [SPA-redigeraren](https://docs.adobe.com/content/help/en/experience-manager-65/developing/headless/spas/spa-overview.html)). |
| `languageCountry` | `en_us` | Språk- och landskod för att skapa innehållsstrukturen från (t.ex. `en_us`). |
| `singleCountry` | `y` | Innehåller en innehållsstruktur på överordnad (kan vara `y`eller `n`). |
| `includeExamples` | `y` | Innehåller en exempelplats för [komponentbibliotek](https://www.aemcomponents.dev/) (kan vara `y`eller `n`). |
| `includeErrorHandler` | `n` | Innehåller en anpassad 404-svarssida som kommer att vara global för hela instansen (kan vara `y` eller `n`). |
| `includeCommerce` | `n` | Inkluderar [CIF Core Components](https://github.com/adobe/aem-core-cif-components) -beroenden och genererar motsvarande artefakter. |
| `commerceEndpoint` |  | Krävs endast för CIF. Valfri slutpunkt för handelssystemet GraphQL-tjänst som ska användas (t.ex. `https://hostname.com/grapql`). |
| `datalayer` | `y` | Aktivera integrering med [Adobe Client Data Layer](/help/developing/data-layer/overview.md). |
| `amp` | `n` | Aktivera [AMP](/help/developing/amp.md) -stöd för genererade projektmallar. |

## Systemkrav

| Arketyp | AEM as a Cloud Service | AEM 6.5 | AEM 6.4 | Java SE | Maven |
---------|---------|---------|---------|---------|---------|---------
| [24](https://github.com/adobe/aem-project-archetype/releases/tag/aem-project-archetype-24) | Kontinuerlig | 6.5.5.0+ | 6.4.8.1+ | 8, 11 | 3.3.9+ |

Konfigurera den lokala utvecklingsmiljön för [AEM som Cloud Service-SDK](https://docs.adobe.com/content/help/en/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html) eller för [äldre versioner av AEM](https://docs.adobe.com/content/help/en/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html).

### Kända fel

När du kör i Windows och genererar dispatcherkonfigurationen bör du köra i en förhöjd kommandotolk eller i Windows-undersystemet för Linux (se [#329](https://github.com/adobe/aem-project-archetype/issues/329)).

När du kör typen architype i interaktivt läge (utan parametern `-B` ) kan egenskaperna med standardvärden inte ändras, såvida inte den slutliga bekräftelsen stängs, som sedan upprepar frågorna genom att inkludera egenskaperna med standardvärden i frågorna (mer information finns[i ARCHETYPE-308](https://issues.apache.org/jira/browse/ARCHETYPE-308) ).

## Ytterligare läsning {#further-reading}

Mer information om hur du använder arkitypen, inklusive dess fördelar, alternativ och hur dess moduler fungerar, finns i dokumentet [Använda arkitypen.](using.md)
