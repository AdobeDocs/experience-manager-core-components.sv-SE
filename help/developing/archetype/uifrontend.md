---
title: AEM Project Archetype Front-End Build
description: En projektmall för AEM-baserade program
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# ui.frontModule för AEM Project Archetype {#uifrontend-module}

AEM Project Archetype innehåller en dedikerad front-end-konstruktionsmekanism som bygger på WebPack som tillval. Modulen ui.front blir därmed den centrala platsen för alla projektets frontresurser, inklusive JavaScript- och CSS-filer. Om du vill utnyttja den här användbara och flexibla funktionen till fullo är det viktigt att du förstår hur frontendutvecklingen passar in i ett AEM-projekt.

## AEM Projects och Front-End Development {#aem-and-front-end-development}

I betydligt förenklade termer kan man tänka sig att AEM-projekt består av två separata men relaterade delar:

* Bakgrundsutveckling som driver logiken i AEM och skapar Java-bibliotek, OSGi-tjänster osv.
* Framtidsutveckling som driver presentationen och beteendet på den slutliga webbplatsen och skapar JavaScript- och CSS-bibliotek

Eftersom dessa två utvecklingsprocesser är inriktade på olika delar av projektet kan både back-end och front-end-utveckling ske parallellt.

![arbetsflödesdiagram för frontend](/help/assets/front-end-flow.png)

Alla resulterande projekt måste dock använda resultatet från båda dessa utvecklingssatsningar, dvs. både back end och front end.

När du kör `npm run dev` startas frontendkonstruktionsprocessen som samlar de JavaScript- och CSS-filer som lagras i modulen ui.front och skapar två minifierade klientbibliotek eller ClientLibs som anropas `clientlib-site` och `clientlib-dependencies` placerar dem i modulen ui.apps. ClientLibs kan distribueras till AEM och gör att du kan lagra din klientkod i databasen.

När hela AEM-projekts arketyp körs med `mvn clean install -PautoInstallPackage` alla projektartefakter, inklusive ClientLibs, skickas sedan till AEM-instansen.

>[!TIP]
>Läs mer om ClientLibs i [AEM-utvecklingsdokumentationen](https://docs.adobe.com/content/help/en/experience-manager-65/developing/introduction/clientlibs.html) och [hur ui.front-modulen använder dem nedan](#clientlib-generation).

## ClientLibs Overview {#clientlibs}

Framtend-modulen är tillgänglig med en [AEM ClientLib](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/clientlibs.html). När NPM-byggskriptet körs skapas appen och paketet aem-clientlib-generator tar det resulterande byggresultatet och omvandlar det till en sådan ClientLib.

En ClientLib består av följande filer och kataloger:

* `css/`: CSS-filer som kan begäras i HTML
* `css.txt`: Anger ordning och namn på filer i AEM så `css/` att de kan sammanfogas
* `js/`: JavaScript-filer som kan begäras i HTML
* `js.txt` Anger ordning och namn på filer i AEM så `js/` att de kan sammanfogas
* `resources/`: Källmappningar, kodsegment som inte är ingångspunkter (till följd av koddelning), statiska resurser (t.ex. ikoner) osv.

## Möjliga arbetsflöden för utveckling i gränssnittet {#possible-workflows}

Framtidsmodulen är ett användbart och mycket flexibelt verktyg, men har ingen särskild åsikt om hur den ska användas. Nedan följer två exempel på *möjlig* användning, men dina individuella projektbehov kan styra andra användningsmodeller.

### Använda Statisk utvecklingsserver för Webpack {#using-webpack}

Med Webpack kan du utforma och utveckla baserat på statiska utdata från AEM-webbsidor i modulen ui.front.

1. Förhandsgranska sidan i AEM med förhandsgranskningsläget eller skicka `wcmmode=disabled` i URL:en
1. Visa sidans källa och spara som statisk HTML i modulen ui.front
1. [Starta webbpaketet](#webpack-dev-server) och börja formatera och generera nödvändigt JavaScript och CSS
1. Kör `npm run dev` för att generera ClientLibs

I det här flödet kan en AEM-utvecklare utföra steg ett och två och skicka den statiska HTML-koden till den frontutvecklare som utvecklar baserat på AEM HTML-utdata.

>[!TIP]
>
>Man skulle också kunna utnyttja [komponentbiblioteket](https://adobe.com/go/aem_cmp_library) för att hämta exempel från varje komponents markeringar för att arbeta på komponentnivå i stället för på sidnivå.

### Använda Storybook {#using-storybook}

Med [Storybook](https://storybook.js.org) kan du utföra mer atomiskt framend-arbete. Även om Storybook inte ingår i AEM Project Archetype kan du installera den och lagra dina Storybook-artefakter i modulen ui.front. När de är klara för testning i AEM kan de distribueras som ClientLibs genom att köras `npm run dev`.

>[!NOTE]
>
>[Storybook](https://storybook.js.org) ingår inte i AEM Project Archetype. Om du väljer att använda den måste du installera den separat.

### Bestämma markeringen {#determining-markup}

Oavsett vilket utvecklingsarbetsflöde ni bestämmer er för att implementera för projektet måste backend-utvecklarna och front end-utvecklarna först komma överens om koden. Vanligtvis definierar AEM koden, som tillhandahålls av kärnkomponenterna. [Detta kan dock anpassas vid behov](/help/developing/customizing.md#customizing-the-markup).

## Modulen ui.front {#ui-frontend-module}

AEM Project Archetype innehåller en dedikerad frontendkonstruktionsmekanism som bygger på Webpack med följande funktioner.

* Fullt stöd för TypeScript, ES6 och ES5 (med tillämpliga Webpack-wrappers)
* TypeScript- och JavaScript-linting med en TSLint-regeluppsättning
* ES5-utdata, för äldre webbläsare
* Globbing
   * Du behöver inte lägga till import överallt
   * Alla JS- och CSS-filer kan nu läggas till i varje komponent.
      * Bästa praxis är under `/clientlib/js`, `/clientlib/css`eller `/clientlib/scss`
   * Inga `.content.xml` eller `js.txt`/`css.txt` filer behövs eftersom allt körs via Webpack.
   * Globen hämtar alla JS-filer under `/component/` mappen.
      * Med Webpack kan CSS-/SCSS-filer kedjas i via JS-filer.
      * De dras in genom de två ingångspunkterna `sites.js` och `vendors.js`.
   * Den enda fil som används av AEM är utdatafilerna `site.js` och `site.css` i `/clientlib-site` samt `dependencies.js` och `dependencies.css` i `/clientlib-dependencies`
* Chunks
   * Main (site js/css)
   * Leverantörer (beroenden js/css)
* Fullt stöd för Sass/Scss (Sass kompileras till CSS via Webpack)
* Statisk webbpaketsutvecklingsserver med inbyggd proxy till en lokal instans av AEM

>[!NOTE]
>
>Mer teknisk information om modulen ui.front finns i [dokumentationen om GitHub](https://github.com/adobe/aem-project-archetype/blob/master/src/main/archetype/ui.frontend.general/README.md).

## Installation {#installation}

1. Installera [NodeJS](https://nodejs.org/en/download/) (v10+) globalt. Detta installerar även npm.
1. Navigera till ui.front i ditt projekt och kör `npm install`.

>[!NOTE]
>
>Du måste ha [kört arkivtypen](overview.md) med alternativet `-DoptionIncludeFrontendModule=y` att fylla mappen ui.front.

## Användning {#usage}

Följande nPM-skript driver arbetsflödet framåt:

* `npm run dev` - fullständigt bygge med JS-optimering inaktiverad (trädskakning osv.) och källmappningar aktiverade och CSS-optimering inaktiverad.
* `npm run prod` - fullständigt bygge med JS-optimering aktiverad (trädskakning osv.), källmappningar inaktiverade och CSS-optimering aktiverad.
* `npm run start` - Startar en statisk webbpaketsutvecklingsserver för lokal utveckling med minimalt beroende av AEM.

## Output {#output}

Modulen ui.front kompilerar koden under `ui.frontend/src` mappen och matar ut kompilerad CSS och JS samt eventuella resurser under en mapp med namnet `ui.frontend/dist`.

* **Plats** - `site.js`, `site.css` och en `resources/` mapp för layoutberoende bilder och teckensnitt skapas i en mapp `dist/`på klienten.
* **Beroenden** - `dependencies.js` och `dependencies.css` skapas i en `dist/clientlib-dependencies` mapp.

### JavaScript {#javascript}

* Optimering - För produktionsbyggen tas alla JS som inte används eller anropas bort.

### CSS {#css}

* Automatisk korrigering - Alla CSS körs via ett prefix och alla egenskaper som kräver prefix läggs automatiskt till i CSS.
* Optimering - I efterhand körs all CSS via en optimerare (cssnano) som normaliserar den enligt följande standardregler:
   * Minskar CSS-beräkningsuttrycket där det är möjligt och säkerställer både webbläsarkompatibilitet och compressionConverts mellan likvärdiga värden för längd, tid och vinkel. Observera att längdvärden som standard inte konverteras.
   * Tar bort kommentarer i och runt regler, väljare och deklarationer
   * Tar bort dubblerade regler, regler och deklarationer
      * Observera att detta bara fungerar för exakta dubbletter.
   * Tar bort tomma regler, mediefrågor och regler med tomma väljare eftersom de inte påverkar utdata
   * Sammanfogar intilliggande regler efter väljare och överlappande egenskaps-/värdepar
   * Ser till att det bara finns en enda @charset i CSS-filen och flyttar den högst upp i dokumentet
   * Ersätter det inledande CSS-nyckelordet med det faktiska värdet när resultatet blir mindre
   * Komprimerar infogade SVG-definitioner med SVGO
* Rensning - Innehåller explicit rensning av CSS-, JS- och Map-filer vid behov.
* Källmappning - endast utvecklingsbygge

>[!NOTE]
>Det första byggalternativet använder konfigureringsfiler för enbart dev och endast prod, som delar en gemensam konfigurationsfil. På så sätt kan utvecklings- och produktionsinställningarna ändras oberoende av varandra.

### Generering av klientbibliotek {#clientlib-generation}

Byggningsprocessen för modulen ui.front utnyttjar plugin-programmet [aem-clientlib-generator](https://www.npmjs.com/package/aem-clientlib-generator) för att flytta kompilerad CSS, JS och eventuella resurser till modulen ui.apps. Konfigurationen för aem-clientlib-generator definieras i `clientlib.config.js`. Följande klientbibliotek genereras:

* **clientlib-site** - `ui.apps/src/main/content/jcr_root/apps/<app>/clientlibs/clientlib-site`
* **clientlib-beroenden** - `ui.apps/src/main/content/jcr_root/apps/<app>/clientlibs/clientlib-dependencies`

### Inkludera klientbibliotek på sidor {#clientlib-inclusion}

`clientlib-site` och `clientlib-dependencies` kategorier inkluderas på sidor via [sidprincipskonfigurationen](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/templates/page-templates-editable.html#template-definitions) som en del av standardmallen. Om du vill visa profilen redigerar du **Innehållssidmall > Sidinformation > Sidprofil**.

Klientbibliotek på webbplatssidan inkluderas slutligen på följande sätt:

```
<HTML>
    <head>
        <link rel="stylesheet" href="clientlib-base.css" type="text/css">
        <script type="text/javascript" src="clientlib-dependencies.js"></script>
        <link rel="stylesheet" href="clientlib-dependencies.css" type="text/css">
        <link rel="stylesheet" href="clientlib-site.css" type="text/css">
    </head>
    <body>
        ....
        <script type="text/javascript" src="clientlib-site.js"></script>
        <script type="text/javascript" src="clientlib-base.js"></script>
    </body>
</HTML>
```

Ovanstående tillägg kan förstås ändras genom att man uppdaterar sidprofilen och/eller ändrar kategorierna och inbäddningsegenskaperna för respektive klientbibliotek.

### Statisk webbpaketsutvecklingsserver {#webpack-dev-server}

I modulen ui.front ingår en webpack-dev-server som tillhandahåller direktladdning för snabb frontutveckling utanför AEM. Installationen utnyttjar pluginmodulen html-webpack-plugin för att automatiskt mata in CSS och JS som kompilerats från modulen ui.front i en statisk HTML-mall.

#### Viktiga filer {#important-files}

* `ui.frontend/webpack.dev.js`
   * Detta innehåller konfigurationen för webbpack-dev-server och pekar på html-mallen som ska användas.
   * Den innehåller också en proxykonfiguration för en AEM-instans som körs på localhost:4502.
* `ui.frontend/src/main/webpack/static/index.html`
   * Det här är den statiska HTML-kod som servern ska köras mot.
   * På så sätt kan utvecklare göra CSS-/JS-ändringar och omedelbart se hur de återspeglas i koden.
   * Det antas att koden som placeras i den här filen korrekt återger den kod som genereras av AEM-komponenterna.
   * Markeringar i den här filen synkroniseras inte automatiskt med AEM-komponentkod.
   * Den här filen innehåller även referenser till klientbibliotek som lagras i AEM, t.ex. Core Component CSS och Responsive Grid CSS.
   * Webbpaketets utvecklingsserver är konfigurerad för att proxyvisa dessa CSS/JS-inkluderingar från en lokal AEM-instans som körs baserat på konfigurationen som finns i `ui.frontend/webpack.dev.js`.

#### Använda {#using-webpack-server}

1. Kör kommandot i projektets rot `mvn -PautoInstallSinglePackage clean install` för att installera hela projektet till en AEM-instans som körs i `localhost:4502`.
1. Navigera i `ui.frontend` mappen.
1. Kör följande kommando `npm run start` för att starta webbpaketets dev-server. När programmet har startats bör det öppna en webbläsare (`localhost:8080` eller nästa tillgängliga port).

Nu kan du ändra CSS-, JS-, SCSS- och TS-filer och se ändringarna direkt på webbpaketets dev-server.