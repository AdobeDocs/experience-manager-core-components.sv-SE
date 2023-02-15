---
title: AEM Project Archetype
description: En projektmall för AEM
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 58994726-9b65-4035-9d45-60b745d577bb
source-git-commit: 0d004c90e789f23ff9e121fbd8ae11df9c9748b2
workflow-type: tm+mt
source-wordcount: '1192'
ht-degree: 1%

---

# AEM Project Archetype {#aem-project-archetype}

AEM Project Archetype är en Maven-mall som skapar ett minimalt, metodbaserat Adobe Experience Manager-projekt (AEM) som utgångspunkt för webbplatsen.

>[!TIP]
>
>Den senaste AEM Project Archetype [finns på GitHub.](https://github.com/adobe/aem-project-archetype)

## Resurser {#resources}

* **Arketype Documentation (this document):** Översikt över arkitekturen och dess olika moduler.
   * **[Använda Archetype:](using.md)** Mer information om hur du använder arkitypen och tillgängliga moduler
   * **[ui.front:](uifrontend.md)** Så här använder du modulen för frontendbygge
* **Följande självstudiekurser är baserade på denna arketyp:**
   * **[WKND-plats:](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)** Lär dig hur du skapar en ny webbplats.
   * **[WKND Single Page App:](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)** Lär dig hur du skapar en React- eller Angular-webbapp som är helt redigerbar i AEM.

## Funktioner {#features}

* **God praxis:** Bootstrap er sajt med alla de senaste Adobe rekommenderade metoderna.
* **Lågkod:** Redigera mallarna, skapa innehåll, distribuera CSS så är sajten klar att publiceras.
* **Molnklart:** Använd [AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html) att publicera på bara några dagar och förenkla skalbarhet och underhåll.
* **Dispatcher:** Ett projekt är bara färdigt med en [Dispatcher-konfiguration](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/dispatcher.html) som garanterar hastighet och säkerhet.
* **Flera platser:** Vid behov genereras innehållsstrukturen för en [flerspråkig och flerregionsinstallation](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/msm/overview.html).
* **Kärnkomponenter:** Författare kan skapa nästan vilken layout som helst med vår mångsidiga [uppsättning standardiserade komponenter](/help/introduction.md).
* **Redigerbara mallar:** Sammanställ praktiskt taget alla [mall utan kod](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html)och definiera vad författarna får redigera.
* **Responsiv layout:** På mallar eller enskilda sidor [definiera hur elementen flödar om](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/get-started/localization.html) för definierade brytpunkter.
* **Sidhuvud och sidfot:** Sammanställ och lokalisera dem utan kod med [komponenternas lokaliseringsfunktioner](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/get-started/localization.html).
* **Formatsystem:** Undvik att bygga anpassade komponenter genom att tillåta författare att [använda olika format](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/project-archetype/style-system.html) till dem.
* **Front-End Build:** Utvecklare kan [AEM](uifrontend.md#webpack-dev-server) och [skapa klientbibliotek](uifrontend.md) med Webpack, TypeScript och SASS.
* **WebApp-Ready:** För webbplatser som använder [Reagera](uifrontend-react.md) eller [Angular](uifrontend-angular.md), använder du [SPA SDK](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/hybrid/developing.html) för att behålla [kontextredigering av appen](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html).
* **Handel aktiverad:** För projekt som vill integreras [AEM](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/home.html) med e-handelslösningar som [Magento](https://magento.com/) med [Kärnkomponenter i Commerce](https://github.com/adobe/aem-core-cif-components).
* **Exempelkod:** Checka ut HelloWorld-komponenten och exempelmodellerna, servletarna, filtren och schemaläggaren.
* **Öppen källa:** Om något inte är som det ska, [contribute](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) förbättringar!

## Användning {#usage}

Om du vill generera ett projekt justerar du följande kommandorad efter dina behov:

```shell
mvn -B org.apache.maven.plugins:maven-archetype-plugin:3.2.1:generate \
 -D archetypeGroupId=com.adobe.aem \
 -D archetypeArtifactId=aem-project-archetype \
 -D archetypeVersion=XX \
 -D appTitle="My Site" \
 -D appId="mysite" \
 -D groupId="com.mysite" \
```

* Ersätt `XX` med de senaste [versionsnummer för arkivtyp.](#requirements)
* Ange `aemVersion=cloud` for [AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html);\
   Ange `aemVersion=6.5.0` for [Adobes hanterade tjänster](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams)eller lokalt.
Core Components-beroendet läggs bara till för andra versioner än molnbaserade, eftersom Core Components tillhandahålls OTB för AEM as a Cloud Service.
* Justera `appTitle="My Site"` för att definiera webbplatsens titel och komponentgrupper.
* Justera `appId="mysite"` för att definiera Maven artifactId, komponentens, konfigurations- och innehållsmappens namn samt klientbibliotekens namn.
* Justera `groupId="com.mysite"` för att definiera Maven groupId och Java Source Package.
* Leta upp listan med tillgängliga egenskaper för att se om det finns mer att justera.

## Tillgängliga egenskaper {#available-properties}

| Namn | Standard | Beskrivning |
|---------------------------|----------------|--------------------|
| `appTitle` |  | Programtitel, kommer att användas för webbplatsens titel och komponentgrupper (t.ex. `"My Site"`). |
| `appId` |  | Tekniskt namn, kommer att användas för komponentnamn, konfigurations- och innehållsmappnamn samt klientbiblioteksnamn (t.ex. `"mysite"`). |
| `artifactId` | *`${appId}`* | Base Maven artifact ID (t.ex. `"mysite"`). |
| `groupId` |  | Grupp-ID för Bas Maven-grupp (t.ex. `"com.mysite"`). Värdet måste vara en [giltigt namn på Java-paket.](https://docs.oracle.com/javase/specs/jls/se6/html/packages.html#7.7) |
| `package` | *`${groupId}`* | Källpaket för Java (t.ex. `"com.mysite"`). |
| `version` | `1.0-SNAPSHOT` | Projektversion (t.ex. `1.0-SNAPSHOT`). |
| `aemVersion` | `cloud` | AEM (kan `cloud` for [AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html); eller `6.5.0`, eller `6.4.4` for [Adobes hanterade tjänster](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams) eller på plats). |
| `sdkVersion` | `latest` | När `aemVersion=cloud` en [SDK](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-as-a-cloud-service-sdk.html) kan anges (t.ex. `2020.02.2265.20200217T222518Z-200130`). |
| `includeDispatcherConfig` | `y` | Innehåller en dispatcherkonfiguration för antingen molnet eller AMS/lokal, beroende på värdet för `aemVersion` (kan `y` eller `n`). |
| `frontendModule` | `general` | Innehåller en Webpack-modul för klientbibliotek (kan `general` eller `none` för vanliga webbplatser, kan `angular` eller `react` för en Single Page-app som implementerar [SPA](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/hybrid/editor-overview.html)). |
| `language` | `en` | Språkkod (ISO 639-1) för att skapa innehållsstrukturen från (t.ex. `en`, `deu`). |
| `country` | `us` | Landskod (ISO 3166-1) för att skapa innehållsstrukturen från (t.ex. `US`). |
| `singleCountry` | `y` | Innehåller en struktur för överordnad innehåll (kan vara `y`, eller `n`). |
| `includeExamples` | `n` | Innehåller en [Komponentbibliotek](https://www.aemcomponents.dev/) exempelwebbplats (kan `y`, eller `n`). |
| `includeErrorHandler` | `n` | Innehåller en anpassad 404-svarssida som är global till hela instansen (kan `y` eller `n`). |
| `includeCommerce` | `n` | Inkluderar [CIF-kärnkomponenter](https://github.com/adobe/aem-core-cif-components) beroenden och genererar motsvarande artefakter. |
| `commerceEndpoint` |  | Krävs endast för CIF. Valfri slutpunkt för e-handelssystemets GraphQL-tjänst som ska användas (t.ex. `https://hostname.com/grapql`). |
| `includeFormscommunications` | `n` | Inkluderar [Forms Core Components](https://github.com/adobe/aem-core-forms-components) beroenden, mallar, formulärdatamodeller, teman och genererar motsvarande artefakter för Forms Communications-program. |
| `includeFormsenrollment` | `n` | Inkluderar [Forms Core Components](https://github.com/adobe/aem-core-forms-components) beroenden, mallar, formulärdatamodeller, teman och genererar motsvarande artefakter för Forms Enrollment-program. |
| `sdkFormsVersion` | `latest` | När `aemVersion=cloud` och en av `includeFormsenrollment=y` eller `includeFormscommunications=y`kan en Forms SDK-version anges (t.ex. `2020.12.17.02`). |
| `datalayer` | `y` | Aktivera integrering med [Adobe-klientdatalager](/help/developing/data-layer/overview.md). |
| `amp` | `n` | Aktivera [AMP](/help/developing/amp.md) stöd för genererade projektmallar. |
| `enableDynamicMedia` | `n` | Aktiverar basen för DynamicMedia-komponenter i projektpolicyinställningar och aktiverar Dynamic Media-funktioner i huvudbildkomponentens policy. |
| `enableSSR` | `n` | Möjlighet att aktivera SSR för front-end-projektet |
| `precompiledScripts` | `n` | Alternativ till [förkompilera](/help/developing/archetype/precompiled-bundled-scripts.md) serverskript från `ui.apps` och bifoga dem till bygget som en sekundär paketartefakt i `ui.apps` projekt. `aemVersion` ska anges till `cloud`. |
| `includeFormsheadless` | `n` | Inkluderar [Forms Core Components](https://github.com/adobe/aem-core-forms-components) beroenden, `ui.frontend.react.forms.af`och utan störande artefakter. |

## Systemkrav {#requirements}

| Arketyp | AEM as a Cloud Service | AEM 6.5 | Java SE | Maven |
|---------|---------|---------|---------|---------|
| [40](https://github.com/adobe/aem-project-archetype/releases/tag/aem-project-archetype-40) | Kontinuerlig | 6.5.7.0+ | 8, 11 | 3.3.9+ |

Konfigurera den lokala utvecklingsmiljön för [AEM as a Cloud Service SDK](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html) eller för [äldre versioner av AEM](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html).

### Kända fel {#known-issues}

När du kör i Windows och genererar dispatcherkonfigurationen bör du köra i en förhöjd kommandotolk eller i Windows-undersystemet för Linux (se [#329](https://github.com/adobe/aem-project-archetype/issues/329)).

När arketypen körs i interaktivt läge (utan `-B` parameter) kan egenskaperna med standardvärden inte ändras, såvida inte den slutliga bekräftelsen avvisas, som sedan upprepar frågorna genom att inkludera egenskaperna med standardvärden i frågorna (se
[ARCHETYPE-308](https://issues.apache.org/jira/browse/ARCHETYPE-308) för mer information).

Du kan inte använda den här arkitypen i Eclipse när du startar ett nytt projekt med `File -> New -> Maven Project` sedan genereringsskriptet `archetype-post-generate.groovy` kommer inte att köras på grund av [Eclipse-problem.](https://bugs.eclipse.org/bugs/show_bug.cgi?id=514993) Du kan komma runt problemet genom att använda ovanstående kommandorad och sedan använda den i Eclipse `File -> Import -> Existing Maven Project`.

## Ytterligare läsning {#further-reading}

Mer information om hur du använder arkitypen, inklusive dess fördelar, alternativ och hur dess moduler fungerar, finns i [Använda Arketype-dokumentet.](using.md)
