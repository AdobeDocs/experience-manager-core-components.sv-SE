---
title: Huvudkomponentversioner
description: Kärnkomponenter publiceras som releaser som kan innehålla mer än en version av samma kärnkomponenter. I det här dokumentet förklaras vilka versioner som är tillgängliga och hur man förstår kompatibiliteten med Core Components och AEM.
translation-type: tm+mt
source-git-commit: 6c0dcfbe4af6aeb3bfa69bdbb43edaab273207be

---


# Huvudkomponentversioner {#core-components-versions}

Den aktuella versionen av kärnkomponenterna är 2.8.0 och är kompatibel med [AEM som molntjänst](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html) och [lokala AEM](https://docs.adobe.com/content/help/en/experience-manager-65/user-guide/home.html) -installationer. Den släpptes i december 2019 som en viktig uppdatering till version 2.0.0. I version 2.0.0 introducerades nya komponenter tillsammans med v2-uppdateringar av befintliga komponenter.

## Versionshistorik och kompatibilitet {#release-history-and-compatibility}

Core Components släpptes först med AEM 6.3 och är utformade för att vara flexibla och kompatibla med alla AEM-versioner som stöds. På grund av detta kan en version av komponenterna innehålla flera versioner av samma komponent.

I följande tabeller visas kompatibiliteten för de versioner av kärnkomponenterna som ingår i releaserna.

### Versionshistorik och krav {#release-history-requirements}

Följande tabell, vars innehåll är [tillgängligt på GitHub med fullständig versionsinformation](https://github.com/adobe/aem-core-wcm-components/releases), ger en översikt över de olika versionerna av Core Components och deras kompatibilitet med AEM- och Java-versioner.

| Frigör | Beskrivning | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service | Java | Releasedatum |
|---|---|---|---|---|---|---|---|
| [2.8.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.8.0) | Den här versionen fokuserar på korrigeringar med små förbättringar. | 6.3.3.4+ | 6.4.4.0+ | 6.5.0.0+ | Kontinuerlig | 8, 11 | 5 december 2019 |
| [2.7.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.7.0) | I den här versionen introducerades den nya inbäddningskomponenten | 6.3.3.4+ | 6.4.4.0+ | 6.5.0.0+ | Kontinuerlig | 8, 11 | 25 september 2019 |
| [2.6.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.6.0) | I den här versionen introducerades den nya Experience Fragment-komponenten | 6.3.3.4+ | 6.4.4.0+ | 6.5.0.0+ | Kontinuerlig | 8, 11 | 6 september 2019 |
| [2.5.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.5.0) | I den här versionen introducerades de nya komponenterna Accordion, Button, Container och Download. | 6.3.3.0+ | 6.4.2.0+ | 6.5.0.0+ | Kontinuerlig | 8, 11 | 25 juni 2019 |
| [2.4.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.4.0) | I den här versionen introducerades List-komponenten för innehållsfragment | 6.3.3.0+ | 6.4.2.0+ | 6.5.0.0+ | Kontinuerlig | 8, 11 | 7 maj 2019 |
| [2.3.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.2) | Den här versionen fokuserar på förbättringar av komponentbiblioteket, men innehåller även vissa funktionsförbättringar för Separator-komponenten | 6.3.3.0+ | 6.4.2.0+ | 6.5.0.0+ | Kontinuerlig | 8 | 14 mars 2019 |
| [2.3.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.0) | I den här versionen fokuserades både komponentbiblioteket och den nya separationskomponenten, men den innehåller också vissa funktionsförbättringar för bildkomponenten | 6.3.3.0+ | 6.4.2.0+ | - | - | 8 | 11 februari 2019 |
| [2.2.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.2) | Den här versionen fokuserar främst på felkorrigeringar, men innehåller även vissa funktionsförbättringar för Carousel-komponenten | 6.3.3.0+ | 6.4.2.0+ | - | - | 8 | 27 november 2018 |
| [2.2.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.0) | Flikar och Carousel-komponenter introducerades, förbättringar av bild-, sid- och titelkomponenter samt förbättrad spårning | 6.3.3.0+ | 6.4.2.0+ | - | - | 8 | 16 oktober 2018 |
| [2.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.1.0) | Teaser Component (Teaser Component) introducerades, Image Component-förbättringar och flera felkorrigeringar | 6.3.3.0+ | 6.4.2.0+ | - | - | 8 | 13 juli 2018 |
| [2.0.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.8) | Bugfix-release | 6.3.2.0+ | 6.4.0.0+ | - | - | 8 | 12 juni 2018 |
| [2.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.6) | Ytterligare förbättringar under huven, felkorrigeringar och små förbättringar som stöd för att vända bilder. | 6.3.2.0+ | 6.4.0.0+ | - | - | 8 | 11 april 2018 |
| [2.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.4) | De flesta förbättringar under huven, felkorrigeringar och vissa mindre förbättringar av komponenterna Bild, Sida och Innehållsfragment | 6.3.2.0+ | 6.4.0.0+ | - | - | 8 | 7 mars 2018 |
| [2.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.0) | Komponenterna för navigering, språknavigering och snabbsökning har lagts till. Formatsystem implementerat för alla komponenter. | 6.3.2.0+ | 6.4.0.0+ | - | - | 8 | 16 januari 2018 |
| [1.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.1.0) | Implementering av JSON-export för alla komponenter, introduktion av komponenten Content Fragment | 6.3.1.0 | 6.4.0.0+ | - | - | 8 | 10 oktober 2017 |
| [1.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.6) | Flera korrigeringar för bildkomponenten | 6.3.0.0+ | 6.4.0.0+ | - | - | 8 | 4 augusti 2017 |
| [1.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.4) | Korrigeringar av sidkomponent, bildkomponent, olika globala korrigeringar och förbättringar | 6.3.0.0+ | 6.4.0.0+ | - | - | 8 | 26 april 2017 |
| [1.0.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.all-1.0.2) | Korrigeringar för animerade GIF-bilder i bildkomponenten | 6.3.0.0+ | 6.4.0.0+ | - | - | 7 | 22 mars 2017 |
| [1.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.0) | Ursprunglig version av kärnkomponenter | 6.3.0.0+ | 6.4.0.0+ | - | - | 7 | 20 mars 2017 |

>[!NOTE]
>
>Precis som med AEM rekommenderar Adobe att utvecklare använder den [senaste versionen och de versioner av kärnkomponenterna](https://github.com/adobe/aem-core-wcm-components/releases/latest) som är kompatibla med den version av AEM som de kör för att dra nytta av de senaste korrigeringarna och funktionerna.

### Komponentversioner och releaser {#component-versions-and-releases}

Tabellen nedan visar vilka versioner av vilka komponenter som ingår i vilka versioner av kärnkomponenterna släpps.

|  | Version 1.0.0 - 1.0.6 | Version 1.1.0 | Version 2.0.0 - 2.0.8 | Version 2.1.0 | Version 2.2.0-2.2.0 | Version 2.3.0-2.3.2 | Version 2.4.0 | Version 2.5.0 | Version 2.6.0 | Version 2.7.0+ |
|---|---|---|---|---|---|---|---|---|---|---|
| **[Sida](components/page.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Titel](components/title.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Bild](components/image.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Lista](components/list.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Breadcrumb](components/breadcrumb.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Delning av sociala medier](components/sharing.md)** | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Formulärbehållare](components/forms/form-container.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Formulärtext](components/forms/form-text.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Formuläralternativ](components/forms/form-options.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Dolt formulär](components/forms/form-hidden.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Formulärknapp](components/forms/form-button.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[Innehållsfragment](components/content-fragment-component.md)** |  | Sandbox | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Navigering](components/navigation.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Språknavigering](components/language-navigation.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Snabbsökning](components/quick-search.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Teaser](components/teaser.md)** |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Tabbar](components/tabs.md)** |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Carousel](components/carousel.md)** |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Avgränsare](components/separator.md)** |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 |
| **[Innehållsfragmentlista](components/content-fragment-list.md)** |  |  |  |  |  |  | v1 | v1 | v1 | v1 |
| **[Dragspel](components/accordion.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 |
| **[Knapp](components/button.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 |
| **[Behållare](components/container.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 |
| **[Hämta](components/download.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 |
| **[Experience Fragment](components/experience-fragment.md)** |  |  |  |  |  |  |  |  | v1 | v1 |
| **[Bädda in](components/embed.md)** |  |  |  |  |  |  |  |  |  | v1 |

## Versioner och releaser {#versions-and-releases}

Kärnkomponenter distribueras via GitHub. På så sätt kan Adobe snabbare lägga till funktioner i komponenterna och även ge möjlighet till communityfeedback utanför AEM-releasecykeln.

De viktigaste komponenterna är tillgängliga med definierade AEM-versioner som de är kompatibla med. Det innebär att en AEM-version kan ha stöd för flera versioner eller versioner av de centrala komponenterna. Detta ger större flexibilitet än tidigare Foundation Components, som var knutna till en viss version av AEM.

### Versioner {#versions}

Huvudupprepningen av kärnkomponenterna är **versionerna**. Varje komponent har en version. Versioner markeras med **v** med ett positivt heltal som inte är noll, till exempel v1 och v2. Versionerna ökas endast för ändringar som inte är bakåtkompatibla, vilket vanligtvis är fallet när nya funktioner införs.

Utvecklare och administratörer kan känna igen versioner av kärnkomponenterna med ett antal i sina resurstypssökvägar och i de fullständiga Java-klassnamnen för sina implementeringar. Det här versionsnumret representerar en huvudversion enligt riktlinjerna för [semantisk versionshantering](https://semver.org/).

Mer information om grundkomponentversionerna finns i [utvecklardokumentationen för kärnkomponenterna](developing/guidelines.md).

### Utgåvor {#releases}

Kärnkomponenterna görs tillgängliga via **releaser** och [representerar de faktiska publicerade artefakterna som finns på GitHub](https://github.com/adobe/aem-core-wcm-components/releases). Releaser anges med ett decimaltal i formatet X.Y.Z och samlar ihop alla kärnkomponenter som ett slutproduktspaket.

* **Större releaser** kan innehålla nya versioner av befintliga komponenter tillsammans med helt nya komponenter samt standardfelkorrigeringar. Detta representeras av en ökning i X-komponenten i versionsnumret.
* **Viktiga versioner** kan innehålla nya funktioner för befintliga versioner av komponenter tillsammans med felkorrigeringar. Detta representeras av en ökning i Y-komponenten i versionsnumret.
* **Mindre versioner** innehåller bara felkorrigeringar. Detta representeras av en ökning i Z-komponenten i versionsnumret.

>[!NOTE]
>
>Releaser kan innehålla flera versioner av samma komponent.
>
>Samma version av en komponent kan visas i flera versioner.

## Stöd för kärnkomponenter {#core-components-support}

Core Components är en integrerad del av AEM och stöds i befintligt skick, på samma villkor som om de levererades som en del av QuickStart.

I likhet med andra produktfunktioner är den allmänna regeln om produktlivslängd:

* Komponenterna meddelas först att bli borttagna innan de tas bort
* Som tidigast tas de bort från AEM-versionen efter meddelandet.

Detta ger kunderna minst en releasecykel att gå över till den nya versionen av komponenten innan supporten upphör.

Versionen för varje komponent anger tydligt vilka AEM-versioner som stöds. När supporten upphör för en version av AEM gör även stödet för Core Components för den versionen av AEM det.

Mer information om stöd för komponentanpassningar finns på sidan [Anpassa kärnkomponenter](developing/customizing.md) i den relevanta Core Components-versionen.

## Stöd för Foundation Component {#foundation-component-support}

Eftersom Foundation Components har legat till grund för så mycket projektutveckling över många versioner kommer de att fortsätta att stödjas inom överskådlig framtid.

Men Adobes utvecklingstänkande har flyttats till kärnkomponenterna och nya funktioner kommer att läggas till i dem, medan [nästan alla grundkomponenterna har ersatts med AEM 6.5](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/siteandpage/default-components-foundation.html) och endast felkorrigeringar kommer att göras för grundkomponenterna i framtiden.
