---
title: Introduktion till kärnkomponenter
description: Få lösningar på problem med kärnkomponenterna och låt andra skapa element i AEM.
role: Architect, Developer, Admin, User
exl-id: d294db22-4cb0-48a4-9366-03fda5b8bb8e
source-git-commit: 9064b357476128525c428b33bdb49fbe68138890
workflow-type: tm+mt
source-wordcount: '928'
ht-degree: 2%

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
   * **[WKND - självstudiekurs:](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)** En tvådagars självstudiekurs för att skapa en ny webbplats.
   * **[Självstudiekurs:](https://expleague.azureedge.net/labs/L767/index.html)** En tvåtimmars självstudiekurs för att skapa en ny webbplats (från en labbutekurs på US Summit 2019).
   * **[Gems Webinar:](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)** En guidad demo av kärnkomponenterna (inspelad i december 2018).

## Funktioner {#features}

|  |  |
|---|---|
| Produktionsklart | Core Components är 30 robusta komponenter som är väl testade, allmänt använda och som fungerar bra. |
| Molnklar | Om [AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html), på [Adobes hanterade tjänster](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams)eller lokalt fungerar de bara. |
| Mångsidig | Komponenterna representerar generiska begrepp som författarna kan använda för att sätta ihop nästan vilken layout som helst. |
| Konfigurerbar | Mallnivå [innehållsprinciper](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/full-stack/components-templates/templates.html#content-policies) Ange vilka funktioner som sidförfattarna får använda eller inte får använda. |
| Spårbar | The [Integrering av Adobe Client Data Layer](/help/developing/data-layer/overview.md) gör det möjligt att spåra alla aspekter av besökarupplevelsen. |
| Tillgänglig | De följer [WCAG 2.1-standard](https://www.w3.org/TR/WCAG21/), har ARIA-etiketter och stöd för tangentbordsnavigering ([kända problem](https://github.com/adobe/aem-core-wcm-components/issues?utf8=✓&amp;q=is%3Aissue+is%3Aopen+accessibility+in%3Atitle)). |
| SEO-vänlig | Utdata från HTML är semantiska och ger [schema.org](https://schema.org) mikrodataanteckningar. |
| WebApp-Ready | The [strömlinjeformade JSON-utdata](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/development/develop-sling-model-exporter.html) tillåter rendering på klientsidan, fortfarande med möjlighet att [kontextredigering](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html). |
| Stöd för AMP | Komponenterna har inbyggda [stöd för AMP-standarden,](/help/developing/amp.md) för mobilupplevelser. |
| Design Kit | A [UI-kit för Adobe XD](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/AEM-CoreComponents-UI-Kit.xd) ger designers möjlighet att skapa trådramar som de sedan kan [format efter behov](https://github.com/adobe/aem-guides-wknd/releases/download/aem-guides-wknd-0.0.2/AEM_UI-kit-WKND.xd). |
| Temaperbar | Komponenterna implementerar [Formatsystem](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/style-system.html)och koden följer [BEM CSS-konventioner](http://getbem.com/). |
| Anpassningsbar | Flera mönster tillåts [enkel anpassning](developing/customizing.md), från justering av HTML till avancerad funktionalitet, återanvändning. |
| Versionshantering | The [versionsprincip](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-policies) säkerställer att kärnkomponenterna inte bryter din plats när du förbättrar saker som kan påverka dig. |
| Lokaliserbart | Med smart referensupplösning kan vissa komponenter hitta och [återge motsvarande lokaliserat innehåll automatiskt](get-started/localization.md). |
| Öppna källkod | Om något inte är som det ska, [bidra till förbättringar!](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) |

## Komponenterna {#the-components}

Den aktuella versionen av Core Components innehåller följande komponenter.

### Mallkomponenter {#template-components}

* [Sidan](components/page.md)
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
* [Hämta](components/download.md)
* [Lista](components/list.md)
* [Experience Fragment](components/experience-fragment.md)
* [Innehållsfragment](components/content-fragment-component.md)
* [Innehållsfragmentlista](components/content-fragment-list.md)
* [Bädda in](components/embed.md)
* [Delning av sociala medier](components/sharing.md) (borttagen)
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
>Kärnkomponenter är inte omedelbart tillgängliga för författare, [Utvecklingsteamet måste först integrera dem i din miljö](get-started/using.md). När de är integrerade kan de göras tillgängliga och förkonfigurerade via [mallredigerare](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html).

>[!NOTE]
>
>Vissa versioner av enskilda kärnkomponenter kanske bara är kompatibla med vissa versioner av AEM.
>
>Se den enskilda hjälpsidan (som är länkad till i föregående lista) för den specifika komponenten för kompatibilitetsinformation eller för att referera till [Huvudkomponentversioner](versions.md) för mer information.

## Systemkrav {#system-requirements}

| Core Components Release | AEM as a Cloud Service | AEM 6.5 | Java SE-version | Maven Version |
|---------|---------|---------|---------|---------|
| [2.21.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.21.0) | Kontinuerlig | 6.5.13.0+ * | 8, 11 | 3.3.9+ |

>[!NOTE]
>
>(*) Sedan version 2.11.0, `org.apache.sling.models.impl` version 1.4.12 eller senare krävs (på grund av [SLING-8781](https://issues.apache.org/jira/browse/SLING-8781)). Detta kommer att anges för AEM 6.4 och 6.5 i ett framtida Service Pack. Fram till dess ingår Sling Models-paketet i `core.wcm.components.all` paket.

Krav från tidigare versioner av Core Component finns i [Huvudkomponentversioner](versions.md).

Kärnkomponenterna kräver användning av [redigerbara mallar](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html) och har inte stöd för klassiska användargränssnitt eller statiska mallar. Om det behövs kan du kolla in [AEM](https://opensource.adobe.com/aem-modernize-tools/pages/tools.html) för att uppdatera projektet med dessa moderna AEM.

Om du vill konfigurera din lokala utvecklingsmiljö går du till [den här översikten för AEM as a Cloud Service SDK](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html) eller det här dokumentet [för äldre versioner av AEM](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html).

>[!TIP]
>
>Core Components är automatiskt en del av AEM as a Cloud Service och du har alltid den senaste versionen av Core Components.
>
>Se [Använda kärnkomponenter](/help/get-started/using.md) om du vill ha mer information om hur du kommer igång med kärnkomponenterna både i AEMaaCS och lokalt.
