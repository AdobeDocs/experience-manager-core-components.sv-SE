---
title: Introduktion till kärnkomponenter
description: 'Core Components ger robusta och utbyggbara baskomponenter som bygger på den senaste tekniken och bästa praxis. '
translation-type: tm+mt
source-git-commit: 2926c51c2ab97b50b9ec4942cd5415c15a1411b6
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Introduktion till kärnkomponenter{#core-components-introduction}

I Adobe Experience Manager är komponenter de strukturella element som utgör innehållet på de sidor som skapas. Komponenter har alltid varit en grundläggande del av AEM och gjort det enkelt men kraftfullt att skapa sidor för författaren och utveckla komponenter flexibelt och utbyggbart för utvecklaren.

De centrala komponenterna är en uppsättning standardiserade WCM-komponenter (Web Content Management) för AEM som snabbar upp utvecklingstiden och minskar underhållskostnaderna för dina webbplatser.

## Resurser {#resources}

* **[Komponentbibliotek:](https://www.adobe.com/go/aem_cmp_library)** En samling exempel som visar komponenterna i deras olika konfigurationer.
* **Komponentdokumentation (det här dokumentet):** För utvecklare och författare, med information om varje komponent.
* **[Core Components GitHub Repository:](https://github.com/adobe/aem-core-wcm-components)** Om du vill ha information om varje komponent och nedladdning av projekt får du information om utvecklare.
* Kom igång:
   * **[Lyckades med kärnkomponenterna:](/help/developing/success.md)** Riktlinjer som ska övervägas långt före början av projekt som ska använda kärnkomponenterna.
   * **[WKND - självstudiekurs:](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)** En tvådagars självstudiekurs för att skapa en ny webbplats.
   * **[Självstudiekurs:](https://expleague.azureedge.net/labs/L767/index.html)** En tvåtimmars självstudiekurs för att skapa en ny webbplats (från en labbutekurs på US Summit 2019).
   * **[Gems Webinar:](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)** En guidad demo av kärnkomponenterna (inspelad i december 2018).

## Funktioner {#features}

|  |  |
|---|---|
| Produktionsklart | Core Components är 28 robusta komponenter som är väl testade, allmänt använda och som fungerar bra. |
| Molnklar | Vare sig det gäller [AEM som Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html), [Adobes hanterade tjänster](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams)eller på plats fungerar de bara. |
| Mångsidig | Komponenterna representerar generiska begrepp som författarna kan använda för att sätta ihop nästan vilken layout som helst. |
| Konfigurerbar | Principer för [innehåll på mallnivå](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/components-templates/templates.html#content-policies) definierar vilka funktioner sidförfattarna får använda eller inte använda. |
| Spårbar | Integreringen [av](/help/developing/data-layer/overview.md) Adobe Client Data Layer möjliggör spårning av alla aspekter av besökarupplevelsen. |
| Tillgänglig | De uppfyller [WCAG 2.1-standarden](https://www.w3.org/TR/WCAG21/), tillhandahåller ARIA-etiketter och stöder tangentbordsnavigering ([kända fel](https://github.com/adobe/aem-core-wcm-components/issues?utf8= ✓&amp;q=is%3Aissue+is%3Aopen+accessibility+in%3Atitle)). |
| SEO-vänlig | HTML-utdata är semantiska och innehåller [schema.org](https://schema.org) -mikrodataanteckningar. |
| WebApp-Ready | Den [strömlinjeformade JSON-utdata](https://docs.adobe.com/content/help/en/experience-manager-learn/foundation/development/develop-sling-model-exporter.html) möjliggör rendering på klientsidan, fortfarande med möjlighet till [kontextredigering](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html). |
| Stöd för AMP | Komponenterna har inbyggt [stöd för AMP-standarden,](/help/developing/amp.md) vilket snabbar upp era mobilupplevelser. |
| Design Kit | Med ett [gränssnittspaket för Adobe XD](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/assets/overview/AEM_UI-kit_Wireframe.xd) kan designers skapa trådramar som de sedan kan [formatera efter behov](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/assets/overview/AEM_UI-kit_WKND.xd). |
| Temaperbar | Komponenterna implementerar [Style System](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/components-templates/style-system.html)och koden följer [BEM CSS-konventioner](http://getbem.com/). |
| Anpassningsbar | Flera mönster gör det [enkelt att anpassa](developing/customizing.md), från att justera HTML till avancerad återanvändning av funktioner. |
| Versionshantering | Versionsprincipen [](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-policies) säkerställer att kärnkomponenterna inte bryter din webbplats när du förbättrar saker som kan påverka dig. |
| Lokaliserbart | Med smart referensupplösning kan vissa komponenter hitta och [återge motsvarande lokaliserat innehåll automatiskt](get-started/localization.md). |
| Öppna källkod | Om något inte är som det ska, [bidrar du till förbättringarna!](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) |

## Komponenterna {#the-components}

Den aktuella versionen av Core Components innehåller följande komponenter.

### Mallkomponenter {#template-components}

* [Sida](components/page.md)
* [Navigering](components/navigation.md)
* [Språknavigering](components/language-navigation.md)
* [Breadcrumb](components/breadcrumb.md)
* [Snabbsökning](components/quick-search.md)

### Sidredigeringskomponenter {#page-authoring-components}

* [Titel](components/title.md)
* [Text](components/text.md)
* [Bild](components/image.md)
* [Knapp](components/button.md)
* [Teaser](components/teaser.md)
* [Hämta](components/download.md)
* [Lista](components/list.md)
* [Experience Fragment](components/experience-fragment.md)
* [Innehållsfragment](components/content-fragment-component.md)
* [Innehållsfragmentlista](components/content-fragment-list.md)
* [Bädda in](components/embed.md)
* [Delning av sociala medier](components/sharing.md)
* [Avgränsare](components/separator.md)
* [Förloppsindikator](components/progress-bar.md)
* [PDF Viewer](components/pdf-viewer.md)

### Behållarkomponenter {#container-components}

* [Behållare](components/container.md)
* [Carousel](components/carousel.md)
* [Tabbar](components/tabs.md)
* [Dragspel](components/accordion.md)

### Formulärkomponenter {#form-components}

* [Formulärbehållare](components/forms/form-container.md)
* [Formulärtext](components/forms/form-text.md)
* [Formuläralternativ](components/forms/form-options.md)
* [Dolt formulär](components/forms/form-hidden.md)
* [Formulärknapp](components/forms/form-button.md)

>[!NOTE]
>
>De centrala komponenterna är inte direkt tillgängliga för författare, [utvecklingsteamet måste först integrera dem i din miljö](get-started/using.md). När de är integrerade kan de göras tillgängliga och förkonfigurerade via [mallredigeraren](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html).

>[!NOTE]
>
>Vissa versioner av enskilda kärnkomponenter kanske bara är kompatibla med vissa versioner av AEM.
>
>Mer information finns på den enskilda hjälpsidan (som länkats till i föregående lista) för den specifika komponenten. Du kan även läsa mer i dokumentet [Core Components Versions](versions.md) .

## Systemkrav {#system-requirements}

| Kärnkomponenter | AEM as a Cloud Service | AEM 6.5 | AEM 6.4 | Java SE | Maven |
|---------|---------|---------|---------|---------|---------|
| [2.11.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.11.0) | Kontinuerlig | 6.5.5.0+ | 6.4.8.1+ | 8, 11 | 3.3.9+ |

Krav från tidigare versioner av Core Component finns i [Core Components Versions](versions.md).

Core-komponenterna kräver [redigerbara mallar](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html) och stöder inte klassiska användargränssnitt eller statiska mallar. Om det behövs kan du kolla in [AEM Moderniseringsverktyg](https://opensource.adobe.com/aem-modernize-tools/pages/tools.html) för att uppdatera projektet med dessa moderna AEM funktioner.

Om du vill konfigurera en lokal utvecklingsmiljö kan du kontrollera [den här översikten för AEM som en Cloud Service-SDK](https://docs.adobe.com/content/help/en/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html) eller det här dokumentet [för äldre versioner av AEM](https://docs.adobe.com/content/help/en/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html).
