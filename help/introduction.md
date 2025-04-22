---
title: Introduktion till kärnkomponenter
description: Få lösningar på problem med kärnkomponenterna och låt andra skapa element i AEM.
role: Architect, Developer, Admin, User
exl-id: d294db22-4cb0-48a4-9366-03fda5b8bb8e
source-git-commit: 302dc24598f892104b57cab3dd4b507975f90dad
workflow-type: tm+mt
source-wordcount: '811'
ht-degree: 1%

---


# Introduktion till kärnkomponenter{#core-components-introduction}

I Adobe Experience Manager är komponenter de strukturella element som utgör innehållet på de sidor som skapas. Komponenter har alltid varit en grundläggande del av AEM-upplevelsen och gjort det enkelt men kraftfullt att skapa sidor för författaren och utveckla komponenter flexibelt och utbyggbart för utvecklaren.

Core Components är en uppsättning standardiserade WCM-komponenter (Web Content Management) för AEM som snabbar upp utvecklingstiden och minskar underhållskostnaderna för dina webbplatser.

## Resurser {#resources}

* **[Komponentbibliotek:](https://www.adobe.com/go/aem_cmp_library)** En samling exempel som visar komponenterna i deras olika konfigurationer.
* **Komponentdokumentation (det här dokumentet):** För utvecklare och författare, med information om varje komponent.
* **[Core Components GitHub Repository:](https://github.com/adobe/aem-core-wcm-components)** För utvecklarinformation om varje komponent och nedladdning av projekt.
* Kom igång:
   * **[Lyckades med kärnkomponenterna:](/help/developing/success.md)** Riktlinjer som ska övervägas långt före starten av projekt som ska använda kärnkomponenterna.
   * **[WKND-självstudiekurs:](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)** En tvådagars självstudiekurs för att skapa en ny webbplats.
   * **[Summit-självstudiekurs:](https://expleague.azureedge.net/labs/L767/index.html)** En tvåtimmars självstudiekurs för att skapa en ny webbplats (från en labbgrupp på US Summit 2019).
   * **[Gems-webbinarium:](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)** En guidad genomgång av Core Components (inspelad i december 2018).

## Funktioner {#features}

|  |  |
|---|---|
| Produktionsklart | Core Components är 30 robusta WCM-komponenter som är väl testade, allmänt använda och som fungerar bra. |
| Molnklar | Vare sig de är på [AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html), på [Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams) eller på plats fungerar de bara. |
| Mångsidig | Komponenterna representerar generiska begrepp som författarna kan använda för att sätta ihop nästan vilken layout som helst. |
| Konfigurerbar | [Innehållsprinciper](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/full-stack/components-templates/templates.html#content-policies) på mallnivå definierar vilka funktioner sidförfattarna får använda eller inte använda. |
| [Responsiv](responsive.md) | Alla kärnkomponenter är utformade för att vara fullt responsiva och ger en sömlös upplevelse på alla enheter |
| Spårbar | Integreringen av [Adobe Client Data Layer ](/help/developing/data-layer/overview.md) gör att du kan spåra alla aspekter av besökarupplevelsen. |
| Tillgänglig | De är kompatibla med standarden [WCAG 2.1](https://www.w3.org/TR/WCAG21/), har ARIA-etiketter och stöder tangentbordsnavigering ([kända fel](https://github.com/adobe/aem-core-wcm-components/issues?utf8= ✓&amp;q=is%3Aissue+is%3Aopen+accessibility+in%3Atitle)). |
| SEO-vänlig | Utdata från HTML är semantiska och innehåller mikrodatsanteckningar för [schema.org](https://schema.org). |
| WebApp-Ready | Med [strömlinjeformade JSON-utdata](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/development/develop-sling-model-exporter.html) kan klientsidan renderas, men ändå med en möjlighet till [kontextredigering](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html). |
| Stöd för AMP | Komponenterna har inbyggt [stöd för AMP-standarden,](/help/developing/amp.md) som snabbar upp dina mobilupplevelser. |
| Design Kit | Med ett [gränssnittspaket för Adobe XD](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/AEM-CoreComponents-UI-Kit.xd) kan designers skapa trådramar som de sedan kan [formatera efter behov](https://github.com/adobe/aem-guides-wknd/releases/download/aem-guides-wknd-0.0.2/AEM_UI-kit-WKND.xd). |
| Temaperbar | Komponenterna implementerar [Style System](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/style-system.html) och koden följer [BEM CSS-konventioner](https://getbem.com/). |
| Anpassningsbar | Flera mönster tillåter [enkel anpassning](developing/customizing.md), från justering av HTML till avancerad återanvändning av funktioner. |
| Versioner | Versionsprincipen [för ](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-policies) säkerställer att kärnkomponenterna inte bryter din plats när du förbättrar saker som kan påverka dig. |
| Lokaliserbart | Med smart referensupplösning kan vissa komponenter hitta och [återge motsvarande lokaliserat innehåll automatiskt](get-started/localization.md). |
| Öppen källkod | Om något inte är som det ska, [bidrar du med dina förbättringar!](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) |


## WCM-komponenterna {#the-wcm-components}

Den aktuella versionen av Core Components innehåller följande komponenter.

### Mallkomponenter {#template-components}

* [Sida](components/page.md)
* [Navigering](components/navigation.md)
* [Språknavigering](components/language-navigation.md)
* [Breadcrumb](components/breadcrumb.md)
* [Snabbsökning](components/quick-search.md)
* [Innehållsförteckning](components/tableofcontents.md)

### Sidredigeringskomponenter {#page-authoring-components}

* [Titel](components/title.md)
* [Text](components/text.md)
* [Bild](components/image.md)
* [Knapp](components/button.md)
* [Teaser](components/teaser.md)
* [Ladda ned](components/download.md)
* [Lista](components/list.md)
* [Experience Fragment](components/experience-fragment.md)
* [Innehållsfragment](components/content-fragment-component.md)
* [Innehållsfragmentlista](components/content-fragment-list.md)
* [Bädda in](components/embed.md)
* [Delning av sociala medier](components/sharing.md) (borttagen)
* [Avgränsare](components/separator.md)
* [Förloppsfält](components/progress-bar.md)
* [PDF Viewer](components/pdf-viewer.md)

### Behållarkomponenter {#container-components}

* [Behållare](components/container.md)
* [Karusell](components/carousel.md)
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
>Kärnkomponenter är inte omedelbart tillgängliga för författare. Utvecklingsteamet [måste först integrera dem i din miljö](get-started/using.md). När de är integrerade kan de göras tillgängliga och förkonfigurerade via [mallredigeraren](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html).

>[!NOTE]
>
>Vissa versioner av enskilda kärnkomponenter kanske bara är kompatibla med vissa versioner av AEM.
>
>Mer information finns på den enskilda hjälpsidan (som länkats till i föregående lista) för den specifika komponenten för kompatibilitetsinformation, eller i dokumentet [Core Components Versions](versions.md) .

## Systemkrav {#system-requirements}

| Core Components Release | AEM as a Cloud Service | AEM 6.5 LTS | AEM 6.5 | Java SE-version | Maven Version |
|---|---|---|---|---|---|
| [2.28.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.28.0) | Kontinuerlig | 6,5 LTS GA | 6.5.21.0+ | 8, 11 | 3.3.9+ |

Information om kraven från tidigare versioner av Core Component finns i [Core Components Versions](versions.md).

Core-komponenterna kräver att [redigerbara mallar](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html) används och stöder inte klassiska användargränssnitt eller statiska mallar. Om det behövs kan du ta en titt på [AEM Moderniseringsverktyg](https://opensource.adobe.com/aem-modernize-tools/) och uppdatera ditt projekt med dessa moderna AEM-funktioner.

Om du vill konfigurera din lokala utvecklingsmiljö kan du ta en titt på [den här översikten för AEM as a Cloud Service SDK](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html) eller det här dokumentet [för äldre versioner av AEM](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html).

>[!TIP]
>
>Core Components är automatiskt en del av AEM as a Cloud Service och du har alltid den senaste versionen av Core Components.
>
>Se dokumentet [Använda kärnkomponenter](/help/get-started/using.md) för mer information om hur du kommer igång med kärnkomponenterna både i AEMaaCS och lokalt.

## Andra komponenter {#other-components}

Det finns ytterligare komponenter som är tillgängliga för AEM-författare, som bygger på kärnkomponenterna.

* [E-postkärnkomponenterna](/help/email/introduction.md) - Upptäck komponenter som är byggda ovanpå kärnkomponenterna som är särskilt avsedda att användas med Adobe Campaign.
