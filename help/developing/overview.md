---
title: Utveckla kärnkomponenter
description: Med Core Components får du robusta och utbyggbara baskomponenter med funktionsrika funktioner, kontinuerlig leverans, versionshantering av komponenter, modern implementering, tunn markering och JSON-export av innehåll.
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# Utveckla kärnkomponenter {#developing-core-components}

## Översikt {#overview}

Core Components ger robusta och utbyggbara baskomponenter, och deras högdagrar är:

* Funktioner
   * [Flexibla konfigurationsalternativ](/help/get-started/authoring.md) för många användningsområden
   * [Förkonfigurerbara funktioner](/help/get-started/authoring.md#pre-configuring-core-components) för att definiera vilka funktioner som är tillgängliga för sidförfattare
* Kontinuerlig leverans
   * Vanliga förbättringar av stegvisa funktioner
   * Tillgänglighet för [källkoden på GitHub](https://github.com/adobe/aem-core-wcm-components) så att utvecklarcommunityn kan ge feedback och bidra
   * Installation via ett [separat släppt innehållspaket](https://github.com/adobe/aem-core-wcm-components/releases) för komponentuppgraderingar som kan göras oberoende av AEM-uppgraderingar
* [Komponentversionshantering](guidelines.md#component-versioning)
   * [Säkerställ kompatibiliteten i en version](#upgrade-of-core-components), men låt komponenterna utvecklas
   * Tillåt att flera versioner av en komponent finns samtidigt i samma miljö
* Modern implementering
   * Markering definierad i [HTML-mallspråk](https://docs.adobe.com/content/help/en/experience-manager-htl/using/overview.html) (HTL)
   * Innehållsmodelllogik som implementerats med [Sling Models](https://sling.apache.org/documentation/bundles/models.html)
* Lean-markering
   * Efter [BEM-notation (Block Element Modifier](https://getbem.com/) ) från och med version 2.0.0
      * Förhandsversionen följer [namngivningskonventionerna för Bootstrap](https://getbootstrap.com/css/)
   * Byggt på riktlinjer för [tillgänglighet](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html)
   * Kan användas för responsiva och mobila webbplatser
* Möjlighet att serialisera som JSON i innehållsmodellen för headless CMS-användningsfall
* Tillgänglig
   * Överensstämmer med standarden [WCAG 2.0 AA](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html)

>[!CAUTION]
>
>Core Components require AEM 6.3 or later and Java 8 and require the use [editable templates](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)
>
>Kärnkomponenter fungerar inte med det klassiska användargränssnittet och inte heller med statiska mallar.

## Översikt över Gems-session {#gems-session-overview}

En introduktion till kärnkomponenterna, de funktioner de erbjuder och hur de används i AEM finns i AEM Gems Session [AEM Core Components.](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)

[Gems on Adobe Experience Manager](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/aem-index.html) är en serie tekniska djupdykningar som levereras av Adobes experter. Den här serien kompletterar produktdokumentationen och alla andra tekniska kanaler, så att utvecklarna kan komma i kontakt med varandra och gå djupare på ett visst ämne.

## WKND Developer Tutorial {#wknd-developer-tutorial}

Kom igång med att utveckla AEM-webbplatser med kärnkomponenter genom att följa [den här stegvisa självstudiekursen.](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)

## AEM Project Archetype {#aem-project-archetype}

[AEM Project Archetype](/help/developing/archetype/overview.md) skapar ett minimalt Adobe Experience Manager-projekt som startpunkt för dina egna projekt, inklusive ett exempel på anpassade HTML-komponenter med SlingModels för en logisk och korrekt implementering av Core Components med det rekommenderade proxymönstret.

## Levereras via GitHub {#delivered-over-github}

Core-komponenterna utvecklas i och levereras via GitHub.

KOD PÅ GITHUB

Koden för den här sidan finns på GitHub

* [Öppna aem-core-wcm-components-projekt på GitHub](https://github.com/adobe/aem-core-wcm-components)
* Hämta projektet som [en ZIP-fil](https://github.com/adobe/aem-core-wcm-components/archive/master.zip)

På dokumentationssidan [Använda kärnkomponenter](/help/get-started/using.md) finns mer information om hur du kommer igång med att använda dem i ditt projekt.

Med Core Components på GitHub kan du göra regelbundna uppdateringar och lyssna på feedback från AEM-utvecklarcommunityn. Detta bör även hjälpa kunder och partners att följa liknande mönster när de skapar anpassade komponenter.

>[!NOTE]
>
>Om du vill hålla dig uppdaterad om de senaste ändringarna av kärnkomponenterna kan du titta på [Core Components-databasen](https://github.com/adobe/aem-core-wcm-components) på GitHub.

## Komponentbibliotek

Ta en titt på [komponentbiblioteket](https://adobe.com/go/aem_cmp_library), som visar den aktuella versionen av kärnkomponenterna och ger exempel på hur de används.

### Kärnkomponenter som är färdiga {#out-of-the-box}

Kärnkomponenterna installeras eventuellt inte automatiskt beroende på hur du kör AEM.

#### AEM as a Cloud Service {#aem-cloud-service}

Även om kärnkomponenterna är helt kompatibla med [AEM som molntjänst](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html)måste kärnkomponenterna installeras manuellt och inte vara tillgängliga direkt.

#### AEM On-Premise {#on-premise}

I lokala installationer är kärnkomponenterna synliga i QuickStart när exempelinnehållet finns, eftersom de används av [webbbutikens referenswebbplats](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html) . När du kör i produktion (i `nosamplecontent` körläge, utan att ha provinnehåll aktiverat) kommer kärnkomponenterna inte längre att finnas och måste installeras på AEM-instansen.

>[!NOTE]
>
>I produktionsmiljöer på plats kör du alltid QuickStart i `nosamplecontent` körläge. Om du vill använda kärnkomponenterna i `nosamplecontent` runmode följer du anvisningarna på dokumentationssidan [Använda kärnkomponenter](/help/get-started/using.md) .

## Teknisk kapacitet {#technical-capabilities}

Följande tabell ger en översikt över skillnaderna mellan kärnkomponenter och grundkomponenter.

Mer information om deras redigeringsfunktioner och alternativ för att förkonfigurera dem [finns på redigeringssidan om dem](/help/get-started/authoring.md).

| **Funktion** | **Kärnkomponent** | **Foundation Component** |
|-----|---|---|
| Logikimplementering | Java POJOs with [Sling Models](https://sling.apache.org/documentation/bundles/models.html) annotations | JSP-kod |
| Markeringsdefinition | [HTML-mallssyntax](https://docs.adobe.com/content/help/en/experience-manager-htl/using/overview.html) (HTL) | JSP-kod |
| XSS-sanering | Automatiserad av HTML | Mest manuella |
| Namnge CSS-klasser | Standardiserad namnkonvention baserad på BEM-notation ( [Block Element Modifier](https://getbem.com/) ) (från och med version 2.0.0) | Anpassade scheman |
| Dialogdefinition | [Korall 3](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/reference-materials/coral-ui/coralui3/index.html) | Coral 2 + Classic UI |
| JSON-utdata | [Sling Models Exporter med Jackson-serialisering](https://sling.apache.org/documentation/bundles/models.html#exporter-framework-since-130) | Default Sling-server |
| Versionshantering | [För modellen och HTML](guidelines.md) | Inget |
| Testning | Enhetstester + integrationstester | Integrationstester |
| Leverans | [Via offentlig GitHub](https://github.com/adobe/aem-core-wcm-components) | Via QuickStart |
| Licens | [Apache-licens](https://www.apache.org/licenses/LICENSE-2.0) | Adobes egna |
| Bidrag | Via pull-begäran | Inte möjligt |
| Tillgänglighet | Fullt kompatibel med [WCAG 2.0 AA-standarden](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html | Endast delvis kompatibelt med [WCAG 2.0 AA-standarden](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html) |

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
| [Delning av sociala medier](https://adobe.com/go/aem_cmp_tech_sharing_v1) | Widgeten för delning av Facebook och Pinterest | `-` |
| [Formulärbehållare](https://adobe.com/go/aem_cmp_tech_form_container_v2) | Styckesystem för responsiva formulär | `/libs/foundation/components/form/start /libs/foundation/components/form/end` |
| [Formulärtext](https://adobe.com/go/aem_cmp_tech_form_text_v2) | Textinmatningsfält | `/libs/foundation/components/form/text /libs/foundation/components/form/password` |
| [Formuläralternativ](https://adobe.com/go/aem_cmp_tech_form_options_v2) | Indatafält för flera alternativ | `/libs/foundation/components/form/checkbox /libs/foundation/components/form/radio /libs/foundation/components/form/dropdown` |
| [Dolt formulär](https://adobe.com/go/aem_cmp_tech_form_hidden_v2) | Dolt indatafält | `/libs/foundation/components/form/hidden` |
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
| [Experience Fragment](https://adobe.com/go/aem_cmp_tech_xf_v1) | Lägga till ett upplevelsefragment på en sida | `/libs/cq/experience-fragments/editor/components/experiencefragment` |
| [Bädda in](https://adobe.com/go/aem_cmp_tech_embed_v1) | Bädda in en extern resurs på en sida | - |

### Kommande komponenter {#upcoming-components}

En översikt över den kommande Core Component-vägkartan finns i [projektets wiki på GitHub](https://github.com/adobe/aem-core-wcm-components/wiki/home).

## Uppgradering av kärnkomponenter {#upgrade-of-core-components}

En fördel med versionskomponenter är att det går att separera migreringen till en ny AEM-version från migreringen till nya komponentversioner. Om det finns nya komponentversioner är det också möjligt att migrera varje komponent individuellt till den nya versionen.

Migreringar till en ny AEM-version påverkar inte hur Core Components fungerar, förutsatt att deras versioner även stöder den nya AEM-versionen som migreras till. Anpassningar som görs i kärnkomponenterna bör inte heller påverkas, så länge de inte använder API:er som har [tagits bort](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/release-notes/deprecated-removed-features.html)eller tagits bort.

Migreringar till nya versioner av kärnkomponenterna kommer inte heller att påverka hur komponenten fungerar, men nya funktioner kan introduceras för sidförfattare, vilket kan kräva viss konfiguration av en mallredigerare om standardbeteendet inte önskas. Anpassningar kan dock behöva anpassas. Mer information finns på sidan [Anpassa kärnkomponenter](customizing.md#upgrade-compatibility-of-customizations) .

## När ska kärnkomponenterna användas? {#when-to-use-the-core-components}

Eftersom kärnkomponenterna är helt nya och ger flera fördelar rekommenderar vi att nya AEM-projekt använder dem. För befintliga projekt bör en migrering ingå i en större projektinsats, till exempel en omprofilering eller en övergripande omfaktorisering.

Därför ger Adobe följande rekommendationer:

* **Nya projekt** Nya projekt ska alltid försöka använda kärnkomponenter. Om kärnkomponenter inte kan användas direkt eller [utökas](customizing.md) för att uppfylla projektkraven skapar du en anpassad komponent enligt komponentarkitekturen som anges i kärnkomponenterna. Undvik att använda [grundkomponenterna](#foundation-component-support), om inte annat är möjligt.
* **Befintliga projektrekommendationer** fortsätter att använda [grundkomponenterna](#foundation-component-support), såvida inte en omfaktorisering planeras för en plats eller komponent.\
   Eftersom de används i mycket stor utsträckning av de flesta befintliga projekt [kommer grundkomponenterna att fortsätta att stödjas.](#foundation-component-support)
* **Nya anpassade komponenter** utvärderas om en befintlig [kärnkomponent kan anpassas](customizing.md).\
   I annat fall rekommenderar vi att du skapar en ny anpassad komponent enligt riktlinjerna [för](guidelines.md)komponenter.
* **Befintliga anpassade komponenter** Om dina komponenter fungerar som de ska bör du behålla dem som de är.\
   Om inte, se&quot;Nya anpassade komponenter&quot; ovan.

## Migrera till kärnkomponenterna

Alla nya projekt ska implementeras med kärnkomponenter. Befintliga projekt har dock oftast omfattande implementeringar av Foundation Components.

En större insats i ett befintligt projekt (till exempel en omprofilering eller en övergripande omfaktorisering) ger ofta möjlighet att migrera till kärnkomponenterna. För att underlätta migreringen har Adobe tillhandahållit ett antal migreringsverktyg för att uppmuntra användningen av kärnkomponenterna och den senaste AEM-tekniken.

[Med AEM Modernization Tools](http://opensource.adobe.com/aem-modernize-tools/) blir det enkelt att konvertera

* Statiska mallar till redigerbara mallar
* Utforma konfigurationer enligt policyer
* Foundation Components to Core Components
* Klassiskt användargränssnitt till pekaktiverat användargränssnitt

Mer information om hur dessa verktyg används [finns i dokumentationen](http://opensource.adobe.com/aem-modernize-tools/)till dem.

>[!NOTE]
>
>AEM Modernize Tools är en community-åtgärd som inte stöds eller garanteras av Adobe.

## Stöd för kärnkomponenter {#core-component-support}

Core Components är en integrerad del av AEM och stöds i befintligt skick, på samma villkor som om de levererades som en del av QuickStart.

Liksom andra AEM-funktioner är den allmänna regeln: Komponenter tillkännages först som borttagna och den tidigaste borttagningen för följande AEM-version. Det ger kunderna minst en releasecykel att gå över till den nya versionen av komponenten innan stödet släpps.

Versionen för varje komponent anger tydligt vilka AEM-versioner som stöds. När supporten upphör för en version av AEM gör även stödet för Core Components för den versionen av AEM det.

Mer information om stöd för komponentanpassningar finns på sidan [Anpassa kärnkomponenter](customizing.md) .

## Stöd för Foundation Component {#foundation-component-support}

Eftersom grundkomponenterna har legat till grund för så mycket projektutveckling över många AEM-versioner kommer de att fortsätta stödjas inom överskådlig framtid.

Men Adobes utvecklingstänkande har flyttats till kärnkomponenterna och nya funktioner kommer att läggas till i dem, medan [nästan alla grundkomponenterna har ersatts med AEM 6.5](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/siteandpage/default-components-foundation.html) och endast felkorrigeringar kommer att göras för grundkomponenterna i framtiden.

**Läs nästa:**

* [Använda kärnkomponenter](/help/get-started/using.md) - Kom igång med Core Components i ditt eget projekt.
* [Komponentriktlinjer](guidelines.md) - för att lära dig implementeringsmönstren för kärnkomponenterna.