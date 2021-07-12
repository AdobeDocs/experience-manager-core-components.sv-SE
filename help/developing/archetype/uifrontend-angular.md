---
title: Front-End Build för Angular SPA
description: En beskrivning av utvecklingsprocessen för Angular-baserade SPA
feature: Kärnkomponenter, AEM projekttyp
role: Architect, Developer, Admin
exl-id: 5726e29d-081c-42bb-bf4e-2852043b21d6
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 0%

---

# Front-End Build för Angular SPA {#frontend-angular}

I det här dokumentet beskrivs detaljerna för det projekt som skapas när du använder en arkivtyp för att skapa ett enda SPA baserat på ramverket för Angular. Det vill säga när du anger `frontendModule` som `angular`.

## Översikt {#overview}

Det här projektet startades med [Angular-CLI](https://github.com/angular/angular-cli).

Det här programmet är utformat för att förbruka en webbplats AEM modell. Layouten genereras automatiskt med hjälpkomponenterna från [@adobe/cq-angular-editable-components](https://www.npmjs.com/package/@adobe/cq-angular-editable-components)-paketet.

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

Detta kommando startar Karma test runner. Mer information finns i [dokumentationen till Angularna om hur du kör test](https://angular.io/guide/testing).

### npm run test:debug {#npm-run-test-debug}

```shell
npm run test:debug
```

Det här kommandot startar Karma-testkörningen i interaktivt bevakningsläge.

### npm run build {#npm-run-build}

```shell
npm run build
```

Med det här kommandot byggs programmet för produktion till byggmappen. Det paketerar Angular i produktionsläge och optimerar bygget för bästa prestanda. Mer information finns i [Angularnas dokumentation om distribution](https://angular.io/guide/deployment).

Dessutom genereras en AEM ClientLib från programmet med [aem-clientlib-generator](https://github.com/wcm-io-frontend/aem-clientlib-generator)-paketet.

Mer information om hur AEM ClientLibs används av projektets arkityp finns i den allmänna dokumentationen [ui.front-modulen ](uifrontend.md#clientlibs).

## Webbläsarstöd {#browser-support}

Som standard används standardalternativet [BrowserList](https://github.com/browserslist/browserslist) för att identifiera målwebbläsare i det här projektet. Dessutom innehåller det polyfyllningar för moderna språkfunktioner som stöder äldre webbläsare (t.ex. Internet Explorer 11). Om stöd för sådana webbläsare inte krävs kan polyfyllningsberoenden och importer tas bort.
