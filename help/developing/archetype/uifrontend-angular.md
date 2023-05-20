---
title: Front-End Build för Angular SPA
description: En beskrivning av utvecklingsprocessen för Angular-baserade SPA
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 5726e29d-081c-42bb-bf4e-2852043b21d6
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 0%

---

# Front-End Build för Angular SPA {#frontend-angular}

I det här dokumentet förklaras detaljerna för det projekt som skapas när du använder en arkivtyp för att skapa ett enda SPA baserat på ramverket för Angular. När du ställer in `frontendModule` alternativ till `angular`.

## Översikt {#overview}

Det här projektet startades med [Angular CLI](https://github.com/angular/angular-cli).

Det här programmet är utformat för att förbruka en webbplats AEM modell. Layouten genereras automatiskt med hjälpkomponenterna från [@adobe/cq-angular-editable-components](https://www.npmjs.com/package/@adobe/cq-angular-editable-components) paket.

## Skript {#scripts}

I projektkatalogen kan du köra följande kommandon.

### npm start {#npm-start}

```
npm start
```

Med det här kommandot körs programmet i utvecklingsläge genom att JSON-modellen proxeras från en lokal AEM som körs på http://localhost:4502. Detta förutsätter att hela projektet har distribuerats till AEM minst en gång (`mvn clean install -PautoInstallPackage` i projektets rot).

När npm har startats i katalogen ui.front öppnas appen automatiskt i webbläsaren (på sökvägen http://localhost:4200/content/${appId}/${country}/${language}/home.html). Om du gör ändringar läses sidan in igen.

Om du får felmeddelanden relaterade till CORS kan du konfigurera AEM enligt följande:

1. Navigera till Configuration Manager (http://localhost:4502/system/console/configMgr)
1. Öppna konfigurationen för Resursdelningspolicy för korsursprung i Adobe Granite
1. Skapa en ny konfiguration med följande ytterligare värden:
   * Tillåtna ursprungsobjekt: http://localhost:4200
   * Rubriker som stöds: Behörighet
   * Tillåtna metoder: OPTIONS

### npm-provning {#npm-test}

```shell
npm test
```

Detta kommando startar Karma test runner. Se [Angular om testkörning](https://angular.io/guide/testing) för mer information.

### npm run test:debug {#npm-run-test-debug}

```shell
npm run test:debug
```

Det här kommandot startar Karma-testkörningen i interaktivt bevakningsläge.

### npm run build {#npm-run-build}

```shell
npm run build
```

Med det här kommandot byggs programmet för produktion till byggmappen. Det paketerar Angular i produktionsläge och optimerar bygget för bästa prestanda. Se [Angular om distribution](https://angular.io/guide/deployment) för mer information.

Dessutom genereras en AEM ClientLib från programmet med [aem-clientlib-generator](https://github.com/wcm-io-frontend/aem-clientlib-generator) paket.

Se det allmänna [ui.frontModuldokumentation](uifrontend.md#clientlibs) om du vill ha mer information om hur AEM ClientLibs används av projektets arkityp.

## Webbläsarstöd {#browser-support}

Som standard används [Webbläsarlista](https://github.com/browserslist/browserslist)Standardalternativet för att identifiera målwebbläsare. Dessutom innehåller det polyfyllningar för moderna språkfunktioner som stöder äldre webbläsare (t.ex. Internet Explorer 11). Om stöd för sådana webbläsare inte krävs kan polyfyllningsberoenden och importer tas bort.
