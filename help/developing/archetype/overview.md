---
title: AEM Project Archetype
description: En projektmall för AEM-baserade program
translation-type: tm+mt
source-git-commit: 6be0028c45ce9f8b36ea278f8e569f3d6a626ae2

---


# AEM Project Archetype {#aem-project-archetype}

AEM Project Archetype skapar ett minimalt, metodbaserat Adobe Experience Manager-projekt som utgångspunkt för dina egna AEM-projekt. De egenskaper som måste anges när du använder den här typen av arkivtyp gör att du kan ange namn för alla delar av projektet samt styra vissa valfria funktioner.

>[!TIP]
>
>Den senaste AEM-projektarkitekturen [finns på GitHub](https://github.com/adobe/aem-project-archetype).

## Funktioner {#features}

Arketypen har ett antal funktioner som är avsedda att vara en bra startpunkt för nya AEM-projekt:

* Engelska och franska sidor med exempelinnehåll
* En innehållsmall som baseras på den redigerbara mallfunktionen med en exempelinnehållsprincip
* Sidkomponent baserad på [AEM Page Core-komponenten](/help/components/page.md)
* Exempel på innehållskomponenter som implementerats med det rekommenderade proxymönstret och en exempel på en anpassad standardkomponent som alla baseras på [AEM Core-komponenter](/help/introduction.md).
* Exempel på [formulärkomponenter](/help/components/forms/form-container.md)
* Konfigurationer för enhetsemulatorer, dra-och-släpp-konfigurationer och internationalisering
* Klientbibliotek som följer BEM-namnkonventioner samt komponentspecifika format
* Exempelpaket med exempelmodeller, servrar, filter och schemaläggare
* Enhet, integrering och klienttester
* Exempel på SPA-implementeringar i React eller Angular (tillval)

## Varför använda Arketype {#why-use-the-archetype}

Med AEM Project Archetype kan du skapa ett AEM-projekt med några få tangenttryckningar. Genom att använda arkivtypen kommer alla delar redan att vara på plats, så även om det färdiga projektet är minimalt, implementerar det redan alla [nyckelfunktioner](#features) i AEM så att allt du behöver göra är att bygga vidare och utvidga.

Det finns förstås många element som ingår i ett framgångsrikt AEM-projekt, men det är en bra grund att använda AEM Project Archetype och vi rekommenderar starkt för alla AEM-projekt.

## Komma igång {#getting-started}

Projektets arkityp gör det enkelt att komma igång med utvecklingen på AEM. Du kan utföra dina första steg på flera olika sätt.

* WKND-självstudiekurs - En bra introduktion till hur du utvecklar med AEM, inklusive hur du utnyttjar typen av arkiv, finns i självstudiekursen [Komma igång med AEM Sites - WKND](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html) , där du får ett praktiskt exempel som visar hur du använder typen av arkiv för att implementera ett enkelt projekt.
* WKND Events-självstudiekurs - Om du är särskilt intresserad av SPA-utveckling (single page application) på AEM, ska du titta på den dedikerade [WKND Events-självstudiekursen](https://helpx.adobe.com/experience-manager/kt/sites/using/getting-started-spa-wknd-tutorial-develop.html).
* Ladda ned och börja själv! - Du kan enkelt hämta den aktuella projekttypen som finns på GitHub och skapa ditt första projekt genom att [följa de enkla stegen nedan](#how-to-use-the-archetype).

## What You Get Using the Archetype {#what-you-get}

AEM-arkitekturen består av moduler:

* **[kärna](core.md)**: är ett Java-paket som innehåller alla kärnfunktioner som OSGi-tjänster, avlyssnare och schemaläggare, samt komponentrelaterad Java-kod som servrar och efterfrågningsfilter.
* **[ui.apps](uiapps.md)**: innehåller`/apps`och`/etc`delar av projektet, dvs. JS- och CSS-klientlibs, komponenter, mallar, runmode-specifika konfigurationer samt Hobbes-tester.
* **[ui.content](uicontent.md)**: innehåller exempelinnehåll med hjälp av komponenterna från modulen ui.apps.
* **[ui.tests](uitests.md)**: är ett Java-paket som innehåller JUnit-tester som körs på serversidan. Paketet ska inte distribueras till produktionen.
* **ui.launcher**: innehåller limkod som distribuerar paketet ui.tests (och beroende paket) till servern och utlöser fjärrexekveringen av JUnit.
* **[ui.front.general](uifrontend.md)**:**(valfritt)**innehåller de artefakter som krävs för att använda den allmänna Webpack-baserade front-end-modulen.
* **[ui.front.response](uifrontend-react.md)**:**(valfritt)**innehåller de artefakter som krävs när du använder arkitypen för att skapa ett SPA-projekt baserat på React.
* **[ui.front.angular](uifrontend-angular.md)**:**(valfritt)**innehåller de artefakter som krävs när du använder en arkityp för att skapa ett SPA-projekt baserat på vinkeln.

![](/help/assets/archetype-structure.png)

Modulerna för AEM Archetype som representeras i Maven distribueras till AEM som innehållspaket som representerar programmet, innehållet och nödvändiga OSGi-paket.

## Krav {#requirements}

Aktuell version av typen architype har följande krav:

* Adobe Experience Manager 6.3.3.0 eller senare (6.4.2 eller senare) när du genererar ett projekt med frontendens vinklar eller Reaktion) eller [AEM som molntjänst](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html)
* Apache Maven (3.3.9 eller senare)
* Adobe Public Maven Repository i dina Maven-inställningar. Mer information finns i den här [kunskapsbasartikeln](https://helpx.adobe.com/experience-manager/kb/SetUpTheAdobeMavenRepository.html).

En lista över vilka AEM-versioner som stöds av tidigare versioner av arketype finns i de [tidigare AEM-versionerna](https://github.com/adobe/aem-project-archetype/blob/master/VERSIONS.md)som stöds.

## Använda arkitekturen {#how-to-use-the-archetype}

Om du vill använda arkitypen måste du först skapa ett projekt som genererar modulerna i en lokal filstruktur som [tidigare beskrivits](#what-you-get). Som en del av projektgenereringen kan du definiera ett antal egenskaper för projektet, till exempel projektnamn, version.

Genom att bygga projektet med Maven skapas artefakter (paket och OSGi-paket) som kan distribueras till AEM. Ytterligare Maven-kommandon och profiler kan användas för att distribuera projektartefakter till en AEM-instans.

### Skapa ett projekt {#create-project}

För att komma igång behöver du bara använda [AEM Eclipse-tillägget](https://docs.adobe.com/content/help/en/experience-manager-65/developing/devtools/aem-eclipse.html) och följa guiden Nytt projekt och välja **AEM Sample Multi-Module Project** för att använda en släppt version av typen.

Naturligtvis kan du också anropa Maven direkt.

```
mvn archetype:generate \
 -DarchetypeGroupId=com.adobe.granite.archetypes \
 -DarchetypeArtifactId=aem-project-archetype \
 -DarchetypeVersion=XX
```

Var `XX` finns [versionsnumret](https://github.com/adobe/aem-project-archetype/blob/master/VERSIONS.md) för den senaste AEM-projektarkitypen.

>[!NOTE]
>
>Det är bäst att lägga till `adobe-public` profilen i Maven- `settings.xml` filen för att automatiskt lägga till repo.adobe.com i maven build-processen.
>
>Här [finns ett exempel på POM](https://helpx.adobe.com/experience-manager/kb/SetUpTheAdobeMavenRepository.html).

### Egenskaper {#properties}

Följande egenskaper är tillgängliga när du skapar ett projekt med hjälp av typen architype.

| Namn | Standard | Beskrivning |
----------------------------|---------|--------------------
| `groupId` |  | Base Maven `groupId` |
| `artifactId` |  | Base Maven ArtifactId |
| `version` |  | Version |
| `package` |  | Java-källpaket |
| `appID` |  | Program-ID som används för komponent-, konfigurations- och innehållsmappar och css-ID:n |
| `appTitle` |  | Programtitel som används för webbplatsens titel och komponentgrupper |
| `aemVersion` | 6.5.0 | AEM-målversion |
| `sdkVersion` |  |
| `languageCountry` | en_us | Språk- och landskod för att skapa den lokaliserade innehållsstrukturen (t.ex. `en_us`) |
| `includeExamples` | y | Inkludera en exempelwebbplats för komponentbibliotek |
| `includeErrorHandler` | n | Inkludera en anpassad 404-svarssida |
| `frontendModule` | inga | Inkludera en särskild frontmodul (en av `none`, [`general`](uifrontend.md), [`angular`](uifrontend-angular.md), [`react`](uifrontend-react.md)) |
| `singleCountry` | y | Skapa en huvudstruktur för språk i exempelinnehåll |
| `includeDispatcherConfig` | n | Definierar om en dispatcherkonfiguration genereras för projektet <br> Set to [`cloud`](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.cloud) när ett projekt för [AEM skapas som en Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html) Set <br> på [`ams`](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams) när ett projekt för Adobe Managed Services skapas |

>[!NOTE]
> Om arkitypen körs i interaktivt läge första gången går det inte att ändra egenskaper med standardvärden (mer information finns i [ARCHETYPE-308](https://issues.apache.org/jira/browse/ARCHETYPE-308) ). Värdet kan ändras när egenskapsbekräftelsen i slutet nekas och enkäten upprepas, eller genom att parametern skickas i kommandoraden (t.ex. `-DoptionIncludeExamples=n`).

>[!NOTE]
>När du kör i Windows och genererar dispatcherkonfigurationen bör du köra i en förhöjd kommandotolk eller i Windows-undersystemet för Linux (se [problem 329](https://github.com/adobe/aem-project-archetype/issues/329)).

### Profiler {#profiles}

Det genererade maven-projektet stöder olika distributionsprofiler när det körs `mvn install`.

| Profil-ID | Beskrivning |
--------------------------|------------------------------
| `autoInstallBundle` | Installera kärnpaketet med maven-sling-plugin-programmet i felix-konsolen |
| `autoInstallPackage` | Installera innehållspaketet ui.content och ui.apps med content-package-maven-plugin i pakethanteraren för att skapa standardförfattarinstansen på localhost, port 4502. Värdnamn och port kan ändras med de `aem.host` - och `aem.port` användardefinierade egenskaperna. |
| `autoInstallPackagePublish` | Installera innehållspaketet ui.content och ui.apps med content-package-maven-plugin i pakethanteraren om du vill använda standardpubliceringsinstansen på localhost, port 4503. Värdnamn och port kan ändras med de `aem.host` - och `aem.port` användardefinierade egenskaperna. |
| `autoInstallSinglePackage` | Installera innehållspaketet med `all` content-package-maven-plugin i pakethanteraren för att skapa standardförfattarinstansen på localhost, port 4502. Värdnamn och port kan ändras med de `aem.host` - och `aem.port` användardefinierade egenskaperna. |
| `autoInstallSinglePackagePublish` | Installera innehållspaketet med `all` content-package-maven-plugin i pakethanteraren för att publicera standardinstansen på localhost, port 4503. Värdnamn och port kan ändras med de `aem.host` - och `aem.port` användardefinierade egenskaperna. |
| `integrationTests` | Kör de medföljande integrationstesterna på AEM-instansen (endast för `verify` fasen) |

### Bygga och installera {#building-and-installing}

Om du vill skapa alla moduler som körs i projektets rotkatalog använder du följande Maven-kommando.

```
mvn clean install
```

Om du har en AEM-instans som körs kan du skapa och paketera hela projektet och distribuera det till AEM med följande Maven-kommando.

```
mvn clean install -PautoInstallPackage
```

Kör det här kommandot om du vill distribuera den till en publiceringsinstans.

```
mvn clean install -PautoInstallPackagePublish
```

Om du vill distribuera till en publiceringsinstans kör du det här kommandot.

```
mvn clean install -PautoInstallPackage -Daem.port=4503
```

Eller kör det här kommandot om du bara vill distribuera paketet till författaren.

```
mvn clean install -PautoInstallBundle
```

## Överordnad POM {#parent-pom}

Det `pom.xml` som ligger till grund för projektet (`<src-directory>/<project>/pom.xml`) kallas överordnad POM och driver projektets struktur samt hanterar beroenden och vissa globala egenskaper för projektet.

### Egenskaper för globala projekt {#global-properties}

Avsnittet i den överordnade POM definierar flera globala egenskaper som är viktiga för distributionen av ditt projekt på en AEM-instans, till exempel användarnamn/lösenord, värdnamn/port. `<properties>`

Dessa egenskaper är konfigurerade för att distribueras till en lokal AEM-instans, eftersom detta är den vanligaste versionen som utvecklare kommer att göra. Observera att det finns egenskaper att distribuera till en författarinstans samt en publiceringsinstans. Det är också här som inloggningsuppgifterna ställs in för att autentiseras med AEM-instansen. Standardautentiseringsuppgifterna för admin:admin används.

Dessa egenskaper är konfigurerade så att de kan åsidosättas vid distribution till miljöer på högre nivå. På så sätt behöver inte POM-filerna ändras, men variabler som `aem.host` och `sling.password` kan åsidosättas via kommandoradsargument:

````
mvn -PautoInstallPackage clean install -Daem.host=production.hostname -Dsling.password=productionpasswd
````

### Modulstruktur {#module-structure}

Avsnittet `<modules>` i den överordnade POM definierar modulerna som projektet ska bygga. Som standard bygger projektet [de standardmoduler som tidigare definierats](#what-you-get): core, ui.apps, ui.content, ui.tests och it.launcher. Fler moduler kan alltid läggas till när ett projekt utvecklas.

### Beroenden {#dependencies}

Avsnittet `<dependencyManagement>` i den överordnade POM definierar alla beroenden och versioner av API:er som används i projektet. Versioner ska hanteras i den överordnade POM. Undermoduler som core och ui.apps ska inte innehålla någon versionsinformation.

#### Uber-Jar {#uber-jar}

Ett av de viktigaste beroendena är [AEM-behållaren](https://docs.adobe.com/content/help/en/experience-manager-65/developing/devtools/ht-projects-maven.html#ExperienceManagerAPIDependencies). Detta inkluderar alla AEM API:er med endast en beroendepost för versionen av AEM.

>[!NOTE]
>
>Som en god vana bör du uppdatera användarversionen så att den matchar målversionen av AEM. Om du t.ex. tänker distribuera till AEM 6.4 bör du uppdatera versionen till 6.4.0.

#### Kärnkomponenter {#core-components}

AEM Project Archetype utnyttjar förstås kärnkomponenterna.

Core Components installeras automatiskt i AEM i standardkörningsläget och används av exempelwebbplatsen We.Retail. I ett [produktionsläge](https://docs.adobe.com/content/help/en/experience-manager-65/administering/security/production-ready.html) (`nosamplecontent`) är kärnkomponenterna inte tillgängliga.

För att kunna utnyttja kärnkomponenterna i alla installationer är det därför en god vana att inkludera dem i Maven-projektet.

>[!NOTE]
>
>Varje release av de centrala komponenterna följs vanligtvis av en release av AEM Project Archetype så att den senaste arkitypen använder den senaste versionen av de centrala komponenterna.
>
>En ny version av typen kan dock inte följa direkt efter en ny version av Core Components, så du kanske vill uppdatera beroendet av Core Components till den senaste versionen.

>[!NOTE]
>
>core.wcm.components.examples är en uppsättning exempelsidor som illustrerar exempel på kärnkomponenterna. Ett tips är att när du distribuerar ett projekt för produktion bör du ta bort beroendet och delpaketinkluderingen.

## Testning {#testing}

Det finns tre testnivåer i projektet och eftersom de är olika typer av tester utförs de på olika sätt eller på olika platser.

* Enhetstest i kärnan: Detta visar klassiska enhetstestningar av koden i paketet. Testa genom att köra:
   * `mvn clean test`
* Integrationstester på serversidan: Dessa kör enhetsliknande tester i AEM-miljön, dvs. på AEM-servern. Testa genom att köra:
   * `mvn clean verify -PintegrationTests`
* Hobbes.js-tester på klientsidan: Detta är JavaScript-baserade webbläsarbaserade tester som verifierar webbläsarsidans beteende. Så här testar du:
   1. Läs in AEM i webbläsaren på samma sätt som du skapar en sida.
   1. Öppna sidan i [utvecklarläget](https://docs.adobe.com/content/help/en/experience-manager-65/developing/components/developer-mode.html)
   1. Öppna den vänstra panelen och växla till fliken **Test** .
   1. Leta reda på de genererade **MyName-testerna** och kör dem.

## Nästa steg {#next-steps}

Så du har byggt och installerat AEM Project Archetype. Vad händer nu? Arkitypen är liten, men består av många exempel på kraftfulla AEM-funktioner som konfigurerats enligt rekommenderade metoder. Här visas hur du kan utnyttja dessa funktioner i ditt projekt. För alla projekt du troligtvis behöver:

* [Anpassa komponenterna genom att utöka de befintliga komponenterna](/help/developing/customizing.md)
* [Lägg till ytterligare mallar](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)
* [Anpassa lokaliseringsstrukturen](https://docs.adobe.com/content/help/en/experience-manager-65/administering/introduction/tc-prep.html)
* [Läs mer om modulen för bygge](uifrontend.md)