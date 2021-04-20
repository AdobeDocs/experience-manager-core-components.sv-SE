---
title: Använda den AEM projekttypen
description: Detaljerade användningsinstruktioner för AEM Project Archetype
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Administrator
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '2072'
ht-degree: 0%

---


# AEM Project Archetype {#aem-project-archetype}

AEM Project Archetype skapar ett minimalt, metodbaserat Adobe Experience Manager-projekt som utgångspunkt för dina egna AEM. De egenskaper som måste anges när du använder den här typen av arkivtyp gör att du kan ange namn för alla delar av projektet samt styra vissa valfria funktioner.

## Varför ska du använda arkitypen {#why-use-the-archetype}?

Med den AEM Project Archetype-tekniken kan du skapa ett AEM projekt med bästa praxis och bara några få tangenttryckningar. Genom att använda arkivtypen kommer alla delar redan att vara på plats, så även om det resulterande projektet är minimalt, implementerar det redan alla [nyckelfunktioner](#what-you-get) i AEM så att allt du behöver göra är att bygga ovanpå och utöka.

Det finns förstås många element som ingår i ett framgångsrikt AEM, men det är en bra grund att använda den AEM Project Archetype-typen och rekommenderas starkt för alla AEM projekt.

## Komma igång {#getting-started}

Projektets arkityp gör det enkelt att komma igång med AEM. Du kan utföra dina första steg på flera olika sätt.

* WKND-självstudiekurs - En bra introduktion till hur du utvecklar AEM, inklusive hur du utnyttjar typen av arkiv, finns i [Komma igång med AEM Sites - WKND-självstudiekurs](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html) för ett praktiskt exempel som visar hur du använder arkitypen för att implementera ett enkelt projekt.
* Självstudiekurs om WKND-händelser - Om du är särskilt intresserad av att utveckla ett enda program (SPA) på AEM ska du titta på den dedikerade självstudiekursen [WKND Events](https://helpx.adobe.com/experience-manager/kt/sites/using/getting-started-spa-wknd-tutorial-develop.html).
* Ladda ned och börja själv! - Du kan enkelt hämta den aktuella projekttypen som finns på GitHub och skapa ditt första projekt genom att [följa de enkla stegen nedan](#how-to-use-the-archetype).

## Vad du får med arkitekturen {#what-you-get}

Den AEM arkitekturen består av moduler:

* **[kärna](core.md)**: är ett Java-paket som innehåller alla kärnfunktioner som OSGi-tjänster, avlyssnare och schemaläggare, samt komponentrelaterad Java-kod som servrar och efterfrågningsfilter.
* **[it.tests](ittests.md)**: är Java-baserade integreringstester.
* **[ui.apps](uiapps.md)**: innehåller projektets innehåll  `/apps` och  `/etc` delar, dvs. JS- och CSS-klientlibs, komponenter och mallar.
* **[ui.content](uicontent.md)**: innehåller exempelinnehåll med hjälp av komponenterna från modulen ui.apps.
* **ui.config**: innehåller runmode-specifika OSGi-konfigurationer för projektet.
* **[ui.front.general](uifrontend.md)**:  **(valfritt)** innehåller de artefakter som krävs för att använda den allmänna Webpack-baserade front-end-modulen.
* **[ui.front.response](uifrontend-react.md)**:  **(valfritt)** innehåller de artefakter som krävs när du använder arkivtypen för att skapa ett SPA baserat på Reagera.
* **[ui.front.angular](uifrontend-angular.md)**:  **(valfritt)** innehåller de artefakter som krävs när du använder en arkivtyp för att skapa ett SPA baserat på Angular.
* **[ui.tests](uitests.md)**: innehåller selenbaserade UI-tester.
* **alla**: är ett enda innehållspaket som bäddar in alla kompilerade moduler (paket och innehållspaket) inklusive eventuella leverantörsberoenden.
* **analysera**: kör en analys av projektet, som ger ytterligare validering för att distribuera till AEM som en Cloud Service.

![](/help/assets/archetype-structure.png)

Modulerna AEM Archetype som representeras i Maven distribueras till AEM som innehållspaket som representerar programmet, innehållet och nödvändiga OSGi-paket.

## Använda arkitekturen {#how-to-use-the-archetype}

Om du vill använda arkitypen måste du först skapa ett projekt som genererar modulerna i en lokal filstruktur som [som tidigare beskrivits](#what-you-get). Som en del av projektgenereringen kan du definiera ett antal egenskaper för projektet, till exempel projektnamn, version.

Genom att bygga projektet med Maven skapas artefakter (paket och OSGi-paket) som kan distribueras till AEM. Ytterligare Maven-kommandon och profiler kan användas för att distribuera projektartefakter till en AEM instans.

### Skapa ett projekt {#create-project}

För att komma igång behöver du bara använda tillägget [AEM Eclipse](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developer-tools/eclipse.html) och följa guiden Nytt projekt och välja **AEM Sample Multi-Module Project** för att använda en släppt version av typen.

Naturligtvis kan du också anropa Maven direkt.

```shell
mvn -B archetype:generate \
 -D archetypeGroupId=com.adobe.aem \
 -D archetypeArtifactId=aem-project-archetype \
 -D archetypeVersion=XX \
 -D aemVersion=cloud \
 -D appTitle="My Site" \
 -D appId="mysite" \
 -D groupId="com.mysite" \
 -D frontendModule=general \
 -D includeExamples=n
```

* Ange `XX` som [versionsnummer](https://github.com/adobe/aem-project-archetype/blob/master/VERSIONS.md) för den senaste AEM Project Archetype.
* Ange `aemVersion=cloud` för [AEM som en Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html);\
   Ange `aemVersion=6.5.0` för [Adobes hanterade tjänster](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams) eller lokal.
Core Components-beroendet läggs bara till för andra versioner än molnbaserade, eftersom Core Components tillhandahålls OTB för AEM som ett moln
Tjänst.
* Justera `appTitle="My Site"` för att definiera webbplatsens titel och komponentgrupper.
* Justera `appId="mysite"` för att definiera Maven artifactId, komponentens, konfigurations- och innehållsmappens namn samt klientbibliotekens namn.
* Justera `groupId="com.mysite"` för att definiera Maven groupId och Java Source Package.
* Leta upp listan med tillgängliga egenskaper för att se om det finns mer att justera.

>[!NOTE]
>
>Det är bäst att lägga till profilen `adobe-public` i din Maven `settings.xml`-fil för att automatiskt lägga till repo.adobe.com i maven build-processen.
>
>Ett exempel på POM [finns här](https://helpx.adobe.com/experience-manager/kb/SetUpTheAdobeMavenRepository.html).

### Egenskaper {#properties}

Följande egenskaper är tillgängliga när du skapar ett projekt med hjälp av typen architype.

| Namn | Standard | Beskrivning |
--------------------------|----------------|--------------------
| `appTitle` |  | Programtitel, kommer att användas för webbplatsens titel och komponentgrupper (t.ex. `"My Site"`). |
| `appId` |  | Tekniskt namn, kommer att användas för komponentnamn, konfigurations- och innehållsmappnamn samt klientbiblioteksnamn (t.ex. `"mysite"`). |
| `artifactId` | *`${appId}`* | Base Maven artifact ID (t.ex. `"mysite"`). |
| `groupId` |  | Grupp-ID för Bas Maven-grupp (t.ex. `"com.mysite"`). |
| `package` | *`${groupId}`* | Källpaket för Java (t.ex. `"com.mysite"`). |
| `version` | `1.0-SNAPSHOT` | Projektversion (t.ex. `1.0-SNAPSHOT`). |
| `aemVersion` | `6.5.0` | AEM (kan vara `cloud` för [AEM som en Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html); eller `6.5.0`, eller `6.4.4` för [Adobes hanterade tjänster](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams) eller lokalt). |
| `sdkVersion` | `latest` | När `aemVersion=cloud` en [SDK](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/developing/aem-as-a-cloud-service-sdk.html)-version kan anges (t.ex. `2020.02.2265.20200217T222518Z-200130`). |
| `includeDispatcherConfig` | `y` | Innehåller en dispatcherkonfiguration för antingen molnet eller AMS/lokalt, beroende på värdet `aemVersion` (kan vara `y` eller `n`). |
| `frontendModule` | `none` | Innehåller en Webpack-modul för klientbibliotek (kan vara `general` eller `none` för vanliga webbplatser). kan vara `angular` eller `react` för ett Single Page-program som implementerar [SPA Editor](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/headless/spa/introduction.html)). |
| `languageCountry` | `en_us` | Språk- och landskod för att skapa innehållsstrukturen från (t.ex. `en_us`). |
| `singleCountry` | `y` | Innehåller en innehållsstruktur på överordnad (kan vara `y` eller `n`). |
| `includeExamples` | `y` | Innehåller en [exempelplats för komponentbibliotek](https://www.aemcomponents.dev/) (kan vara `y` eller `n`). |
| `includeErrorHandler` | `n` | Innehåller en anpassad 404-svarssida som kommer att vara global för hela instansen (kan vara `y` eller `n`). |

>[!NOTE]
>
> Om arkitypen körs i interaktivt läge första gången går det inte att ändra egenskaper med standardvärden (mer information finns i [ARCHETYPE-308](https://issues.apache.org/jira/browse/ARCHETYPE-308)). Värdet kan ändras när egenskapsbekräftelsen i slutet nekas och enkäten upprepas, eller genom att parametern skickas i kommandoraden (t.ex. `-DoptionIncludeExamples=n`).

>[!NOTE]
>
>När du kör i Windows och genererar dispatcherkonfigurationen bör du köra i en förhöjd kommandotolk eller i Windows-undersystemet för Linux (se [utgåva 329](https://github.com/adobe/aem-project-archetype/issues/329)).

### Profiler {#profiles}

Det genererade maven-projektet stöder olika distributionsprofiler när `mvn install` körs.

| Profil-ID | Beskrivning |
--------------------------|------------------------------
| `autoInstallBundle` | Installera kärnpaketet med maven-sling-plugin-programmet i felix-konsolen |
| `autoInstallPackage` | Installera innehållspaketet ui.content och ui.apps med content-package-maven-plugin i pakethanteraren för att skapa standardförfattarinstansen på localhost, port 4502. Värdnamn och port kan ändras med de användardefinierade egenskaperna `aem.host` och `aem.port`. |
| `autoInstallPackagePublish` | Installera innehållspaketet ui.content och ui.apps med content-package-maven-plugin i pakethanteraren om du vill använda standardpubliceringsinstansen på localhost, port 4503. Värdnamn och port kan ändras med de användardefinierade egenskaperna `aem.host` och `aem.port`. |
| `autoInstallSinglePackage` | Installera `all`-innehållspaketet med content-package-maven-plugin i pakethanteraren till standardförfattarinstansen på localhost, port 4502. Värdnamn och port kan ändras med de användardefinierade egenskaperna `aem.host` och `aem.port`. |
| `autoInstallSinglePackagePublish` | Installera `all`-innehållspaketet med content-package-maven-plugin i pakethanteraren om du vill använda standardpubliceringsinstansen på localhost, port 4503. Värdnamn och port kan ändras med de användardefinierade egenskaperna `aem.host` och `aem.port`. |
| `integrationTests` | Kör de angivna integrationstesterna på AEM-instansen (endast för `verify`-fasen) |

### Bygger och installerar {#building-and-installing}

Om du vill skapa alla moduler som körs i projektets rotkatalog använder du följande Maven-kommando.

```shell
mvn clean install
```

Om du har en AEM som körs kan du skapa och paketera hela projektet och distribuera det till AEM med följande Maven-kommando.

```shell
mvn clean install -PautoInstallPackage
```

Kör det här kommandot om du vill distribuera den till en publiceringsinstans.

```shell
mvn clean install -PautoInstallPackagePublish
```

Om du vill distribuera till en publiceringsinstans kör du det här kommandot.

```shell
mvn clean install -PautoInstallPackage -Daem.port=4503
```

Eller kör det här kommandot om du bara vill distribuera paketet till författaren.

```shell
mvn clean install -PautoInstallBundle
```

## Överordnad POM {#parent-pom}

`pom.xml` i projektets rot (`<src-directory>/<project>/pom.xml`) kallas överordnad POM och driver projektets struktur samt hanterar beroenden och vissa globala egenskaper för projektet.

### Globala projektegenskaper {#global-properties}

Avsnittet `<properties>` i den överordnade POM definierar flera globala egenskaper som är viktiga för distributionen av ditt projekt på en AEM instans som användarnamn/lösenord, värdnamn/port osv.

Dessa egenskaper är konfigurerade för att distribueras till en lokal AEM, eftersom detta är den vanligaste versionen som utvecklare kommer att göra. Observera att det finns egenskaper att distribuera till en författarinstans samt en publiceringsinstans. Det är också här som inloggningsuppgifterna ställs in för att autentiseras med AEM. Standardautentiseringsuppgifterna för admin:admin används.

Dessa egenskaper är konfigurerade så att de kan åsidosättas vid distribution till miljöer på högre nivå. På så sätt behöver inte POM-filerna ändras, men variabler som `aem.host` och `sling.password` kan åsidosättas via kommandoradsargument:

```shell
mvn -PautoInstallPackage clean install -Daem.host=production.hostname -Dsling.password=productionpasswd
```

### Modulstruktur {#module-structure}

Avsnittet `<modules>` i den överordnade POM definierar modulerna som projektet ska bygga. Som standard skapar projektet [standardmoduler som tidigare definierats](#what-you-get): core, ui.apps, ui.content, ui.tests och it.launcher. Fler moduler kan alltid läggas till när ett projekt utvecklas.

### Beroenden {#dependencies}

Avsnittet `<dependencyManagement>` i den överordnade POM definierar alla beroenden och versioner av API:er som används i projektet. Versioner ska hanteras i den överordnade POM. Undermoduler som core och ui.apps ska inte innehålla någon versionsinformation.

#### Uber-Jar {#uber-jar}

Ett av nyckelberoendena är [AEM uber-jar](https://docs.adobe.com/content/help/en/experience-manager-65/developing/devtools/ht-projects-maven.html#ExperienceManagerAPIDependencies). Detta inkluderar alla AEM API:er med bara en enda beroendepost för AEM.

>[!NOTE]
>
>Som en god vana bör du uppdatera användarversionen så att den matchar målversionen av AEM. Om du t.ex. tänker distribuera till AEM 6.4 bör du uppdatera versionen till 6.4.0.

#### Kärnkomponenter {#core-components}

Den AEM projekttypen utnyttjar förstås kärnkomponenterna.

Core Components installeras automatiskt i AEM i standardkörningsläget och används av WKND-exempelwebbplatsen. I ett [produktionsläge](https://docs.adobe.com/content/help/en/experience-manager-65/administering/security/production-ready.html) (`nosamplecontent`) är kärnkomponenterna inte tillgängliga.

För att kunna utnyttja kärnkomponenterna i alla installationer är det därför en god vana att inkludera dem i Maven-projektet.

>[!NOTE]
>
>Varje release av de centrala komponenterna följs vanligtvis av en release av den AEM Project Archetype så att den senaste arkitypen använder den senaste versionen av de centrala komponenterna.
>
>En ny version av typen kan dock inte följa direkt efter en ny version av Core Components, så du kanske vill uppdatera beroendet av Core Components till den senaste versionen.

>[!NOTE]
>
>core.wcm.components.examples är en uppsättning exempelsidor som illustrerar exempel på kärnkomponenterna. Ett tips är att när du distribuerar ett projekt för produktion bör du ta bort beroendet och delpaketinkluderingen.

## Testning {#testing}

Det finns tre testnivåer i projektet och eftersom de är olika typer av tester utförs de på olika sätt eller på olika platser.

* Enhetstest i kärnan: Detta visar klassiska enhetstestningar av koden i paketet. Testa genom att köra:
   * `mvn clean test`
* Integrationstester på serversidan: Dessa kör enhetsliknande tester i AEM-miljön, dvs. på AEM. Testa genom att köra:
   * `mvn clean verify -PintegrationTests`
* Hobbes.js-tester på klientsidan: Detta är JavaScript-baserade webbläsarbaserade tester som verifierar webbläsarsidans beteende. Så här testar du:
   1. Läs in AEM i webbläsaren på samma sätt som du skapar en sida.
   1. Öppna sidan i [Utvecklarläge](https://docs.adobe.com/content/help/en/experience-manager-65/developing/components/developer-mode.html)
   1. Öppna den vänstra panelen och växla till fliken **Test**.
   1. Hitta de genererade **MyName-testerna** och kör dem.

## Nästa steg {#next-steps}

Så du har byggt och installerat AEM Project Archetype. Vad händer nu? Arkitypen är liten, men består av många exempel på kraftfulla AEM som konfigurerats enligt rekommenderade metoder. Här visas hur du kan utnyttja dessa funktioner i ditt projekt. För alla projekt du troligtvis behöver:

* [Anpassa komponenterna genom att utöka de befintliga komponenterna](/help/developing/customizing.md)
* [Lägg till ytterligare mallar](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)
* [Anpassa lokaliseringsstrukturen](https://docs.adobe.com/content/help/en/experience-manager-65/administering/introduction/tc-prep.html)
* [Läs mer om modulen för bygge](uifrontend.md)
