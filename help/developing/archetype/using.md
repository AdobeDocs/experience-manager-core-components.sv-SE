---
title: Använda den AEM projekttypen
description: Lär dig använda den AEM projektarkitekturen för att skapa ett minimalt, metodbaserat Adobe Experience Manager-projekt som utgångspunkt för dina egna AEM.
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: a3978d8b-4904-42aa-9ee2-9c1f884327bb
source-git-commit: bd92a5d1884056ca7b44ea28e5817d8bde10a4d9
workflow-type: tm+mt
source-wordcount: '1092'
ht-degree: 0%

---


# Använda den AEM projekttypen {#using-the-archetype}

I det här dokumentet beskrivs hur du kan använda den AEM projektarkitekturen för att skapa ett minimalt, metodbaserat Adobe Experience Manager-projekt som utgångspunkt för dina egna AEM.

Det fokuserar på allmänna användningsmönster och vad arkitypen gör för dig. Detaljerade byggalternativ och tekniska anvisningar finns i dokumentationen i arkivtypens GitHub-databas.

>[!TIP]
>
>Den senaste AEM Project Archetype och tillhörande teknisk dokumentation [finns på GitHub.](https://github.com/adobe/aem-project-archetype)

## Komma igång {#getting-started}

Projektets arkityp gör det enkelt att komma igång med AEM. Du kan utföra de första stegen med arkitypen på flera olika sätt.

* **WKND - självstudiekurs** - En bra introduktion till hur du utvecklar AEM, inklusive hur du utnyttjar arkitekturen, finns i [Komma igång med AEM Sites - WKND självstudiekurs](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html) för ett praktiskt exempel som visar hur du använder arkitypen för att implementera ett enkelt projekt.
* **Självstudiekurs om WKND-händelser** - Om du är särskilt intresserad av utveckling av SPA på AEM ska du ta en titt på [WKND Events, självstudiekurs.](https://helpx.adobe.com/experience-manager/kt/sites/using/getting-started-spa-wknd-tutorial-develop.html)
* **Börja på egen hand!** - Du kan enkelt ladda ned [aktuell projekttyp tillgänglig på GitHub](https://github.com/adobe/aem-project-archetype) och skapa ditt första projekt själv.

## Använda arkitekturen {#how-to-use-the-archetype}

Det första steget med att använda arkitypen är att skapa ett projekt som genererar [modulerna](#what-you-get) i en lokal filstruktur. Som en del av projektgenereringen kan du definiera ett antal egenskaper för ditt projekt, till exempel projektnamn, version, och aktivera olika alternativ.

>[!TIP]
>
>När du skapar en arkityp genereras även en serie Viktigt-filer som ger dig den tekniska informationen och hur modulerna används som [nedan.](#what-you-get)

Genom att bygga projektet med Maven skapas artefakter (paket och OSGi-paket) som kan distribueras till AEM. Ytterligare Maven-kommandon och profiler kan användas för att distribuera projektartefakter till en AEM instans.

## Vad du får med arkitekturen {#what-you-get}

Arkitypen består av moduler, som alla skapas automatiskt när du använder typen architype.

* **[kärna](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/core)** är ett Java-paket som innehåller alla kärnfunktioner som OSGi-tjänster, avlyssnare och schemaläggare, samt komponentrelaterad Java-kod som servrar och efterfrågningsfilter.
* **[it.tests](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/it.tests)** är Java-baserade integreringstester.
* **[ui.apps](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.apps)** innehåller `/apps` och `/etc` delar av projektet, t.ex. JS- och CSS-klienter, komponenter och mallar.
* **[ui.content](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.content)** innehåller exempelinnehåll med hjälp av komponenterna från modulen ui.apps.
* **[ui.config](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.config)** innehåller runmode-specifika OSGi-konfigurationer för projektet.
* **[ui.front.general](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.frontend.general)** innehåller de artefakter som krävs för att använda den allmänna Webpack-baserade frontendmodulen (valfritt).
* **[ui.front.response](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.frontend.react)** **(valfritt)** innehåller de artefakter som krävs när du använder arkivtypen för att skapa ett SPA som baseras på React (valfritt, beror på build-parametrar).
* **[ui.front.angular](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.frontend.angular)** **(valfritt)** innehåller de artefakter som krävs när du använder arraytypen för att skapa ett SPA baserat på Angular (valfritt, beror på byggparametrar).
* **[ui.tests](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.tests)** innehåller selenbaserade UI-tester.
* **[alla](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/all)** är ett enda innehållspaket som bäddar in alla kompilerade moduler (paket och innehållspaket) inklusive eventuella leverantörsberoenden.
* **[dispatcher.ams](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/dispatcher.ams)** innehåller grundläggande konfigurationer för AMS/på-plats-projekt (valfritt, beror på build-parametrar).
* **[dispatcher.cloud](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/dispatcher.cloud)** innehåller grundläggande konfigurationer för AEMaaCS-projekt (valfritt, beror på build-parametrar).

![Ordna innehållspaket](/help/assets/content-package-organization.png)

Modulerna för den arkityp som representeras i Maven distribueras till AEM som innehållspaket som representerar programmet, innehållet och nödvändiga OSGi-paket.

## Överordnad POM {#parent-pom}

The `pom.xml` i projektets rot (`<src-directory>/<project>/pom.xml`) kallas överordnad POM och driver projektets struktur samt hanterar beroenden och vissa globala egenskaper för projektet.

### Egenskaper för globala projekt {#global-properties}

The `<properties>` i den överordnade POM-strukturen definieras flera globala egenskaper som är viktiga för distributionen av ditt projekt på en AEM instans, som användarnamn/lösenord, värdnamn/port osv.

Dessa egenskaper är konfigurerade för att distribueras till en lokal AEM, eftersom detta är den vanligaste versionen som utvecklare kommer att göra. Observera att det finns egenskaper att distribuera till en författarinstans samt en publiceringsinstans. Det är också här som inloggningsuppgifterna ställs in för att autentiseras med AEM. Standardvärdet `admin:admin` autentiseringsuppgifter används.

Dessa egenskaper är konfigurerade så att de kan åsidosättas vid distribution till miljöer på högre nivå. På så sätt behöver inte POM-filerna ändras, utan variabler som `aem.host` och `sling.password` kan åsidosättas via kommandoradsargument:

```shell
mvn -PautoInstallPackage clean install -Daem.host=production.hostname -Dsling.password=productionpasswd
```

### Modulstruktur {#module-structure}

The `<modules>` i överordnad POM definieras de moduler som projektet ska bygga. Som standard byggs projektet [de standardmoduler som tidigare definierats.](#what-you-get) Fler moduler kan alltid läggas till när ett projekt utvecklas.

### Beroenden {#dependencies}

The `<dependencyManagement>` i överordnad POM definieras alla beroenden och versioner av API:er som används i projektet. Versioner ska hanteras i den överordnade POM. Undermoduler bör inte innehålla någon versionsinformation.

#### Uber-Jar {#uber-jar}

Ett av nyckelberoendena är [AEM Java API Jar.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-as-a-cloud-service-sdk.html) Detta inkluderar alla AEM API:er med bara en enda beroendepost för AEM.

>[!NOTE]
>
>Som en god vana bör du uppdatera användarversionen så att den matchar målversionen av AEM. Om du t.ex. tänker driftsätta till AEM 6.5 ska du uppdatera versionen till 6.5.X, där `X` är det senaste Service Pack-paketet.

#### Kärnkomponenter {#core-components}

Arketypen utnyttjar förstås [Kärnkomponenter.](/help/introduction.md) För att kunna utnyttja kärnkomponenterna i alla installationer är det därför en god vana att inkludera dem i Maven-projektet.

core.wcm.components.examples är en uppsättning exempelsidor som illustrerar exempel på kärnkomponenterna. Ett tips är att när du distribuerar ett projekt för produktion bör du ta bort beroendet och delpaketinkluderingen.

>[!NOTE]
>
>Core Components och arkitype underhålls som separata GitHub-projekt och därmed skiljer sig deras versioner.
>
>För varje release av arkitypen används den senaste versionen av de kärnkomponenter som är tillgängliga när den släpps. Du kanske vill uppdatera beroendet av kärnkomponenterna manuellt.

## Testning {#testing}

Det finns tre testnivåer i projektet och eftersom de är olika typer av tester utförs de på olika sätt eller på olika platser.

* **[Enhetstester](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/core)** - Klassisk enhetstestning av koden i paketet
* **[Integrationstester](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/it.tests)** - Integrationstester på serversidan som kör enhetsliknande tester i AEM-miljön, dvs. på den AEM servern
* **[UI-tester](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.tests)** - Selenbaserade test på webbläsarsidan som kontrollerar webbläsarsidans beteende
