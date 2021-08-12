---
title: Introduktion till kärnkomponenter
description: 'Core Components ger robusta och utbyggbara baskomponenter som bygger på den senaste tekniken och bästa praxis. '
role: Architect, Developer, Admin, User
exl-id: d294db22-4cb0-48a4-9366-03fda5b8bb8e
source-git-commit: cc8c3275bf251b4c390ee66588f34bac7c0ec218
workflow-type: tm+mt
source-wordcount: '936'
ht-degree: 3%

---

# Introduktion till kärnkomponenter{#core-components-introduction}

I Adobe Experience Manager är komponenter de strukturella element som utgör innehållet på de sidor som skapas. Komponenter har alltid varit en grundläggande del av AEM och gjort det enkelt men kraftfullt att skapa sidor för författaren och utveckla komponenter flexibelt och utbyggbart för utvecklaren.

De centrala komponenterna är en uppsättning standardiserade WCM-komponenter (Web Content Management) för AEM som snabbar upp utvecklingstiden och minskar underhållskostnaderna för dina webbplatser.

## Resurser {#resources}

* **[Komponentbibliotek:](https://www.adobe.com/go/aem_cmp_library)** En samling exempel som visar komponenterna i deras olika konfigurationer.
* **Komponentdokumentation (det här dokumentet):** För utvecklare och författare, med information om varje komponent.
* **[Core Components GitHub Repository:](https://github.com/adobe/aem-core-wcm-components)** För utvecklarinformation om varje komponent och nedladdning av projekt.
* Kom igång:
   * **[Lyckades med kärnkomponenterna:](/help/developing/success.md)** Riktlinjer som ska övervägas långt före starten av projekt som ska använda kärnkomponenterna.
   * **[WKND-självstudiekurs:](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)** En tvådagars självstudiekurs för att skapa en ny webbplats.
   * **[Självstudiekurs vid Summit:](https://expleague.azureedge.net/labs/L767/index.html)** En självstudiekurs på två timmar för att skapa en ny webbplats (från en labblista på US Summit 2019).
   * **[Gems Webinar:](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)** En guidad genomgång av Core Components (inspelad i december 2018).

## Funktioner {#features}

|  |  |
|---|---|
| Produktionsklart | Core Components är 28 robusta komponenter som är väl testade, allmänt använda och som fungerar bra. |
| Molnklar | Vare sig de är på [AEM som en Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html), på [Adobes hanterade tjänster](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams) eller på plats fungerar de bara. |
| Mångsidig | Komponenterna representerar generiska begrepp som författarna kan använda för att sätta ihop nästan vilken layout som helst. |
| Konfigurerbar | [innehållsprinciper](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/components-templates/templates.html#content-policies) på mallnivå definierar vilka funktioner sidförfattarna får använda eller inte. |
| Spårbar | Integreringen [Adobe Client Data Layer ger dig möjlighet att spåra alla aspekter av besökarupplevelsen.](/help/developing/data-layer/overview.md) |
| Tillgänglig | De är kompatibla med [WCAG 2.1-standarden](https://www.w3.org/TR/WCAG21/), har ARIA-etiketter och stöder tangentbordsnavigering ([kända fel](https://github.com/adobe/aem-core-wcm-components/issues?utf8= ✓&amp;q=is%3Aissue+is%3Aopen+accessibility+in%3Atitle)). |
| SEO-vänlig | HTML-utdata är semantiska och innehåller [schema.org](https://schema.org) mikrodataanteckningar. |
| WebApp-Ready | Med [strömlinjeformade JSON-utdata](https://docs.adobe.com/content/help/en/experience-manager-learn/foundation/development/develop-sling-model-exporter.html) kan klientsidan renderas, fortfarande med möjligheten [kontextredigering](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html). |
| Stöd för AMP | Komponenterna har inbyggt [stöd för AMP-standarden,](/help/developing/amp.md) som snabbar upp mobilupplevelserna. |
| Design Kit | Med ett [gränssnittspaket för Adobe XD](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/AEM-CoreComponents-UI-Kit.xd) kan designers skapa trådramar som de sedan kan [formatera efter behov](https://github.com/adobe/aem-guides-wknd/releases/download/aem-guides-wknd-0.0.2/AEM_UI-kit-WKND.xd). |
| Temaperbar | Komponenterna implementerar [Style System](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/components-templates/style-system.html) och koden följer [BEM CSS-konventioner](http://getbem.com/). |
| Anpassningsbar | Flera mönster gör det möjligt att [enkelt anpassa](developing/customizing.md), från att justera HTML till avancerad återanvändning av funktioner. |
| Versionshantering | Med versionsprincipen [Versionshantering](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-policies) säkerställs att kärnkomponenterna inte bryter din plats när du förbättrar saker som kan påverka dig. |
| Lokaliserbart | Med smart referensupplösning kan vissa komponenter hitta och [återge motsvarande lokaliserat innehåll automatiskt](get-started/localization.md). |
| Öppna källkod | Om något inte är som det ska, [bidra med dina förbättringar!](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) |

## Komponenterna {#the-components}

Den aktuella versionen av Core Components innehåller följande komponenter.

### Mallkomponenter {#template-components}

* [Sidan](components/page.md)
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
>Core Components är inte omedelbart tillgängliga för författare, [utvecklingsteamet måste först integrera dem i din miljö](get-started/using.md). När de är integrerade kan de göras tillgängliga och förkonfigurerade via [mallredigeraren](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html).

>[!NOTE]
>
>Vissa versioner av enskilda kärnkomponenter kanske bara är kompatibla med vissa versioner av AEM.
>
>Mer information finns på den enskilda hjälpsidan (som länkats till i föregående lista) för den specifika komponenten för kompatibilitetsinformation eller i [Core Components Versions](versions.md)-dokumentet.

## Systemkrav {#system-requirements}

| Kärnkomponenter | AEM as a Cloud Service | AEM 6.5 | AEM 6.4 | Java SE | Maven |
|---------|---------|---------|---------|---------|---------|
| [2.17.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.8) | Kontinuerlig | 6.5.6.0+ * | 6.4.8.4+ * | 8, 11 | 3.3.9+ |

>[!NOTE]
>
>(*) Sedan version 2.11.0 krävs `org.apache.sling.models.impl` version 1.4.12 eller senare (på grund av [SLING-8781](https://issues.apache.org/jira/browse/SLING-8781)). Detta kommer att anges för AEM 6.4 och 6.5 i ett framtida Service Pack. Fram till dess ingår Sling Models-paketet i `core.wcm.components.all`-paketet.

Krav från tidigare versioner av Core Component finns i [Core Components Versions](versions.md).

Core-komponenterna kräver [redigerbara mallar](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html) och stöder inte klassiska användargränssnitt eller statiska mallar. Om det behövs kan du titta på [AEM Moderniseringsverktyg](https://opensource.adobe.com/aem-modernize-tools/pages/tools.html) för att uppdatera projektet med dessa moderna AEM funktioner.

Om du vill konfigurera din lokala utvecklingsmiljö går du till [den här översikten för AEM som en Cloud Service-SDK](https://docs.adobe.com/content/help/en/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html) eller det här dokumentet [för äldre versioner av AEM](https://docs.adobe.com/content/help/en/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html).

>[!TIP]
>
>Core Components är automatiskt en del av AEM som en Cloud Service och du har alltid den senaste versionen av Core Components.
>
>Se dokumentet [Använda kärnkomponenter](/help/get-started/using.md) för mer information om hur du kommer igång med kärnkomponenterna både i AEMaaCS och lokalt.
