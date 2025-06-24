---
title: Utveckla kärnkomponenter
description: Med Core Components får du robusta och utbyggbara baskomponenter med funktionsrika funktioner, kontinuerlig leverans, versionshantering av komponenter, modern implementering, tunn markering och JSON-export av innehåll.
role: Architect, Developer, Admin
exl-id: 0f79cac1-a3b0-487e-90be-0bd8263d3912
source-git-commit: 5994133947ff697f7c866fe61598c58e37e77008
workflow-type: tm+mt
source-wordcount: '1130'
ht-degree: 2%

---

# Utveckla kärnkomponenter {#developing-core-components}

Med Core Components får du robusta och utbyggbara baskomponenter med funktionsrika funktioner, kontinuerlig leverans, versionshantering av komponenter, modern implementering, tunn markering och JSON-export av innehåll.

{{traditional-aem}}

## Så här lyckas du med kärnkomponenterna {#how-to-succeed}

Core Components är kraftfulla, flexibla och enkla att använda och anpassa. [Om du följer några viktiga riktlinjer](success.md) ser du till att ditt projekt med kärnkomponenterna fungerar som det ska.

## Migrera till kärnkomponenterna

Alla nya projekt ska implementeras med kärnkomponenter. Befintliga projekt har dock oftast omfattande implementeringar av Foundation Components.

### Migrerar från Foundation Components {#from-foundation}

En större insats i ett befintligt projekt (till exempel en omprofilering eller en övergripande omfaktorisering) ger ofta möjlighet att migrera till kärnkomponenterna. För att underlätta migreringen har Adobe tillhandahållit ett antal migreringsverktyg för att uppmuntra användningen av kärnkomponenterna och den senaste AEM-tekniken.

[Med AEM moderniseringsverktyg](https://opensource.adobe.com/aem-modernize-tools/) kan du enkelt konvertera:

* Statiska mallar till redigerbara mallar
* Designkonfigurationer till policyer
* Foundation-komponenter till Core-komponenter
* Klassiskt användargränssnitt till pekaktiverat användargränssnitt 

Mer information om hur dessa verktyg används finns i [dokumentationen för dem](https://opensource.adobe.com/aem-modernize-tools/).

>[!NOTE]
>
>AEM Modernize Tools är en community-åtgärd som inte stöds eller garanteras av Adobe.

## Migrering via Move to AEM as a Cloud Service {#via-aemaacs}

Eftersom AEM as a Cloud Service har den senaste versionen av Core Components automatiskt måste du ta bort alla beroenden till Core Components i din `pom.xml`-projektfil när du flyttar från en lokal AEM-installation.

Proxykomponenterna fungerar fortfarande som de gjorde tidigare eftersom   utkast pekar på den nödvändiga supertypen och den överordnade textbanan har versionen i den. På så sätt kan du bara ta bort beroendet och få Core Components att fungera i AEMaaCS på samma sätt som lokalt.

Precis som andra AEMaaCS-projekt måste du också lägga in ett beroende i AEM SDK jar. Detta är inte specifikt för kärnkomponenterna, men krävs.

```xml
<dependency>
   <groupId>com.adobe.aem</groupId>
   <artifactId>aem-sdk-api</artifactId>
</dependency>
```

Mer information om AEMaaCS-projekt finns i dokumentet [AEM Project Structure](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html?lang=sv-SE).

## Stöd för kärnkomponenter {#core-component-support}

Core Components är en integrerad del av AEM och stöds som det är, på samma villkor som om de levererades som en del av QuickStart.

Precis som för andra AEM-produktfunktioner är den allmänna regeln: Komponenter tillkännages först som inaktuella och den tidigaste borttagningen för följande AEM-version. Det ger kunderna minst en releasecykel att gå över till den nya versionen av komponenten innan stödet släpps.

Versionen för varje komponent anger tydligt vilka AEM-versioner som stöds. När supporten för en version av AEM upphör, gör det också stödet för Core Components för den versionen av AEM.

Mer information om stöd för komponentanpassningar finns på sidan [Anpassa kärnkomponenter](customizing.md).


## Teknisk kapacitet {#technical-capabilities}

Följande tabell ger en översikt över skillnaderna mellan kärnkomponenter och grundkomponenter.

Mer information om deras redigeringsfunktioner och alternativ för att förkonfigurera dem finns på [redigeringssidan om dem](/help/get-started/authoring.md).

| **Funktion** | **Kärnkomponent** | **Foundation Component** |
|-----|---|---|
| Logic implementation | Java-POJO med [delningsmodeller](https://sling.apache.org/documentation/bundles/models.html) anteckningar | JSP-kod |
| Markeringsdefinition | [Syntax för HTML-mallspråk](https://experienceleague.adobe.com/docs/experience-manager-htl/using/overview.html?lang=sv-SE) (HTML) | JSP-kod |
| XSS-sanering | Automatiserad av HTML | Mest manuella |
| Namnge CSS-klasser | Standardiserad namnkonvention baserad på [Blockelementets modifierare](https://getbem.com/) (BEM)-notation (från och med version 2.0.0) | Anpassade scheman |
| Dialogdefinition | [Korall 3](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/reference-materials/coral-ui/coralui3/index.html) | Coral 2 + Classic UI |
| JSON-utdata | [Sling Models Exporter med Jackson-serialisering](https://sling.apache.org/documentation/bundles/models.html#exporter-framework-since-130) | Default Sling-server |
| Versioner | [För modellen och HTML](guidelines.md) | Ingen |
| Testning | Enhetstester + integrationstester | Integrationstester |
| Leverans | [Via offentlig GitHub](https://github.com/adobe/aem-core-wcm-components) | Via QuickStart |
| Licens | [Apache-licens](https://www.apache.org/licenses/LICENSE-2.0) | Adobe |
| Bidrag | Via pull-begäran | Inte möjligt |
| Tillgänglighet | Fullt kompatibel med [WCAG 2.0 AA-standarden](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html?lang=sv-SE) | Endast delvis kompatibel med [WCAG 2.0 AA-standarden](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html?lang=sv-SE) |

## Komponentlista {#component-list}

I följande tabell visas de tillgängliga kärnkomponenterna, som länkar till deras API, och vilka grundläggande komponenter de ersätter.

| Kärnkomponent | Beskrivning | Ersatt Foundation-komponent(er) |
|---|---|---|
| [Sida](https://adobe.com/go/aem_cmp_tech_page_v2) | Responsiv sida som arbetar med mallredigerare | `/libs/foundation/components/page /libs/wcm/foundation/components/page` |
| [Breadcrumb](https://adobe.com/go/aem_cmp_tech_breadcrumb_v2) | Navigering i sidhierarki | `/libs/foundation/components/breadcrumb` |
| [Titel](https://adobe.com/go/aem_cmp_tech_title_v2) | H1-H6-titel | `/libs/foundation/components/title /libs/wcm/foundation/components/title` |
| [Text](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/text/v2/text) | RTF | `/libs/foundation/components/text /libs/foundation/components/table /libs/wcm/foundation/components/text` |
| [Bild](https://adobe.com/go/aem_cmp_tech_image_v2) | Smart och lat inläsning av optimal återgivningsstorlek | `/libs/foundation/components/image /libs/foundation/components/adaptiveimage /libs/foundation/components/logo /libs/foundation/components/mobileimage  /libs/foundation/components/mobilelogo /libs/wcm/foundation/components/image` |
| [Lista](https://adobe.com/go/aem_cmp_tech_list_v2) | Lista över sidor | `/libs/foundation/components/list /libs/foundation/components/mobilelist /libs/wcm/foundation/components/list` |
| [Delning av sociala medier](https://adobe.com/go/aem_cmp_tech_sharing_v1) | Delningswidgeten Facebook och Pinterest | `-` |
| [Formulärbehållare](https://adobe.com/go/aem_cmp_tech_form_container_v2) | Styckesystem för responsiva formulär | `/libs/foundation/components/form/start /libs/foundation/components/form/end` |
| [Formulärtext](https://adobe.com/go/aem_cmp_tech_form_text_v2) | Textinmatningsfält | `/libs/foundation/components/form/text /libs/foundation/components/form/password` |
| [Formuläralternativ](https://adobe.com/go/aem_cmp_tech_form_options_v2) | Indatafält för flera alternativ | `/libs/foundation/components/form/checkbox /libs/foundation/components/form/radio /libs/foundation/components/form/dropdown` |
| [Formuläret dolt](https://adobe.com/go/aem_cmp_tech_form_hidden_v2) | Dolt indatafält | `/libs/foundation/components/form/hidden` |
| [Formulärknapp](https://adobe.com/go/aem_cmp_tech_form_button_v2) | Skicka eller anpassa knapp | `/libs/foundation/components/form/submit` |
| [Navigering](https://adobe.com/go/aem_cmp_tech_navigation_v1) | En webbplatsnavigeringskomponent som listar den kapslade sidhierarkin | `/libs/foundation/components/topnav /libs/foundation/components/mobiletopnav` |
| [Språknavigering](https://adobe.com/go/aem_cmp_tech_langnav_v1) | En språk- och landsväljare som listar den globala språkstrukturen | `-` |
| [Snabbsökning](https://adobe.com/go/aem_cmp_tech_search_v1) | En sökkomponent som visar resultaten som förslag på plats i en nedrullningsbar meny | `/libs/foundation/components/search` |
| [Teaser](https://adobe.com/go/aem_cmp_tech_teaser_v1) | Gör det möjligt för innehållsförfattaren att enkelt skapa ett suddgummi för ytterligare innehåll med hjälp av en bild, en titel eller formaterad text och länka till ytterligare innehåll eller andra åtgärder | `-` |
| [Tabbar](https://adobe.com/go/aem_cmp_tech_tabs_v1) | Låter innehållsförfattaren organisera sidinnehåll på flera flikar | `-` |
| [Carousel](https://adobe.com/go/aem_cmp_tech_carousel_v1) | Låter innehållsförfattaren ordna innehållet i en roterande karusell med bilder | `/libs/foundation/components/carousel` |
| [Innehållsfragment](https://adobe.com/go/aem_cmp_tech_cf_v1) | Tillåter visning av ett innehållsfragment | `-` |
| [Innehållsfragmentlista](https://adobe.com/go/aem_cmp_tech_cflist_v1) | Gör att en lista med innehållsfragment kan visas | `-` |
| [Avgränsare](https://adobe.com/go/aem_cmp_tech_separator_v1) | Delar upp innehållet på en sida | `-` |
| [Dragspel](https://adobe.com/go/aem_cmp_tech_accordion_v1) | Ordna innehållspaneler i ett komprimerbart dragspel | `-` |
| [Behållare](https://adobe.com/go/aem_cmp_tech_container_v1) | Ordna komponenter i en behållare | `-` |
| [Knapp](https://adobe.com/go/aem_cmp_tech_button_v1) | Skapa en knapp på en sida | `-` |
| [Hämta](https://adobe.com/go/aem_cmp_tech_download_v1) | Lägga till en hämtningsbar resurs på en sida | `-` |
| [Upplevelsefragment](https://adobe.com/go/aem_cmp_tech_xf_v1) | Lägga till ett upplevelsefragment på en sida | `/libs/cq/experience-fragments/editor/components/experiencefragment` |
| [Bädda in](https://adobe.com/go/aem_cmp_tech_embed_v1) | Bädda in en extern resurs på en sida | - |
| [Förloppsindikator](https://adobe.com/go/aem_cmp_tech_progress_v1) | Ge en visuell representation av framstegen mot ett mål | - |
| [PDF Viewer](https://adobe.com/go/aem_cmp_tech_pdfviewer_v1) | Presenterar ett PDF-dokument på en sida | - |

## Uppgradering av kärnkomponenter {#upgrade-of-core-components}

En fördel med versionskomponenter är att det går att separera migreringen till en ny AEM-version från migreringen till nya komponentversioner. Om det finns nya komponentversioner är det också möjligt att migrera varje komponent individuellt till den nya versionen.

Migreringar till en ny AEM-version påverkar inte hur Core Components fungerar, förutsatt att deras versioner även stöder den nya AEM-versionen som migreras till. Anpassningar som görs för kärnkomponenterna ska inte heller påverkas, så länge de inte använder API:er som har [tagits bort eller tagits bort](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/deprecated-removed-features.html?lang=sv-SE).

Migreringar till nya versioner av kärnkomponenterna kommer inte heller att påverka hur komponenten fungerar, men nya funktioner kan introduceras för sidförfattare, vilket kan kräva viss konfiguration av en mallredigerare om standardbeteendet inte önskas. Anpassningar kan dock behöva anpassas. Mer information finns på sidan [Anpassa kärnkomponenter](customizing.md#upgrade-compatibility-of-customizations).
