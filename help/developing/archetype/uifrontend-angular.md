---
title: Front-End Build för vinkelräta SPA
description: En beskrivning av den inledande byggprocessen för vinkelbaserade SPA-projekt
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# Front-End Build för vinkelräta SPA {#frontend-angular}

I det här dokumentet förklaras detaljerna för det projekt som skapades när du använde arkitypen för att skapa ett SPA-program (single page application) baserat på vinkelramverket. Det vill säga när du ställer in `frontendModule` alternativet på `angular`.

## Översikt {#overview}

Detta projekt startades med [Angular CLI](https://github.com/angular/angular-cli).

Det här programmet är utformat för att använda en webbplats AEM-modell. Layouten genereras automatiskt med hjälpkomponenterna från paketet [@adobe/cq-angular-editable-components](https://www.npmjs.com/package/@adobe/cq-angular-editable-components) .

## Skript {#scripts}

I projektkatalogen kan du köra följande kommandon.

### npm start {#npm-start}

```
npm start
```

Med det här kommandot körs programmet i utvecklingsläge genom att JSON-modellen proxeras från en lokal AEM-instans som körs på http://localhost:4502. Detta förutsätter att hela projektet har distribuerats till AEM minst en gång (`mvn clean install -PautoInstallPackage` i projektets rot).

När npm har startats i katalogen ui.front öppnas appen automatiskt i webbläsaren (på sökvägen http://localhost:4200/content/${appId}/${country}/${language}/home.html). Om du gör ändringar läses sidan in igen.

Om du får felmeddelanden relaterade till CORS kanske du vill konfigurera AEM enligt följande:

1. Navigera till Configuration Manager (http://localhost:4502/system/console/configMgr)
1. Öppna konfigurationen för&quot;Adobe Granite Cross-Origin Resource Sharing Policy&quot;
1. Skapa en ny konfiguration med följande ytterligare värden:
   * Tillåtna ursprungsobjekt: http://localhost:4200
   * Rubriker som stöds: Behörighet
   * Tillåtna metoder: ALTERNATIV

### npm-provning {#npm-test}

```
npm test
```

Detta kommando startar Karma test runner. Mer information finns i [vinkeldokumentationen om hur du kör tester](https://angular.io/guide/testing) .

### npm run test:debug {#npm-run-test-debug}

```
npm run test:debug
```

Det här kommandot startar Karma-testkörningen i interaktivt bevakningsläge.

### npm run build {#npm-run-build}

```
npm run build
```

Med det här kommandot byggs programmet för produktion till byggmappen. Det paketerar Angular i produktionsläge och optimerar bygget för bästa prestanda. Mer information finns i [vinkeldokumentationen om distribution](https://angular.io/guide/deployment) .

Dessutom genereras en AEM ClientLib från appen med hjälp av paketet [aem-clientlib-generator](https://github.com/wcm-io-frontend/aem-clientlib-generator) .

Mer information om hur AEM ClientLibs används av projekttypen finns i den allmänna dokumentationen [för modulen](uifrontend.md#clientlibs) ui.front.

## Webbläsarstöd {#browser-support}

Som standard använder det här projektet standardalternativet för [webbläsarlistor](https://github.com/browserslist/browserslist)för att identifiera målwebbläsare. Dessutom innehåller det polyfyllningar för moderna språkfunktioner som stöder äldre webbläsare (t.ex. Internet Explorer 11). Om stöd för sådana webbläsare inte krävs kan polyfyllningsberoenden och importer tas bort.
