---
title: Front-End Build för SPA
description: En beskrivning av den inledande processen för React-baserade SPA
translation-type: tm+mt
source-git-commit: 9d737b31efc8c346775ea5296f7599295af07cf1
workflow-type: tm+mt
source-wordcount: '512'
ht-degree: 0%

---


# Front-End Build för React SPA {#frontend-react}

I det här dokumentet förklaras detaljerna för det projekt som skapades när en arkivtyp användes för att skapa ett ensidigt program (SPA) baserat på React-ramverket. Det vill säga när du anger `frontendModule` som `react`.

## Översikt {#overview}

Det här projektet startades med [create-response-app](https://github.com/facebook/create-react-app).

Det här programmet är utformat för att förbruka en webbplats AEM modell. Layouten genereras automatiskt med hjälpkomponenterna från [@adobe/cq-rea-editable-components](https://www.npmjs.com/package/@adobe/cq-react-editable-components)-paketet.

## Skript {#scripts}

I projektkatalogen kan du köra följande kommandon:

### npm start {#npm-start}

```shell
npm start
```

Med det här kommandot körs programmet i utvecklingsläge genom att JSON-modellen proxeras från en lokal AEM som körs på http://localhost:4502. Detta förutsätter att hela projektet har distribuerats till AEM minst en gång (`mvn clean install -PautoInstallPackage` i projektets rot).

När du har kört `npm start` i katalogen [ui.front](uifrontend.md) öppnas din app automatiskt i webbläsaren (på sökvägen `http://localhost:3000/content/<appId>/<country>/<language>/home.html`). Om du gör ändringar läses sidan in igen.

Om du får felmeddelanden relaterade till CORS kan du konfigurera AEM enligt följande:

1. Navigera till Configuration Manager (http://localhost:4502/system/console/configMgr)
1. Öppna konfigurationen för Resursdelningspolicy för korsursprung i Adobe Granite
1. Skapa en ny konfiguration med följande ytterligare värden:
   * Tillåtna ursprungsobjekt: http://localhost:3000
   * Rubriker som stöds: Behörighet
   * Tillåtna metoder: OPTIONS

### npm test {#npm-test}

```shell
npm test
```

Det här kommandot startar testköraren i interaktivt bevakningsläge. Mer information finns i [Reaktionsdokumentationen om att köra test](https://facebook.github.io/create-react-app/docs/running-tests).

### npm run build {#npm-run-build}

```shell
npm run build
```

Med det här kommandot byggs programmet för produktion till byggmappen. Det innehåller Reagera i produktionsläge och optimerar bygget för bästa prestanda. Mer information finns i [Reaktionsdokumentationen om distribution](https://facebook.github.io/create-react-app/docs/deployment).

Dessutom genereras en AEM ClientLib från programmet med [aem-clientlib-generator](https://github.com/wcm-io-frontend/aem-clientlib-generator)-paketet.

## Webbläsarstöd {#browser-support}

Som standard används standardalternativet [BrowserList](https://github.com/browserslist/browserslist) för att identifiera målwebbläsare i det här projektet. Dessutom innehåller det polyfyllningar för moderna språkfunktioner som stöder äldre webbläsare (t.ex. Internet Explorer 11). Om stöd för sådana webbläsare inte krävs kan polyfyllningsberoenden och importer tas bort.

## Koddelning {#code-splitting}

Appen React är konfigurerad att använda [koddelning](https://webpack.js.org/guides/code-splitting) som standard. När du skapar en app för produktion kommer koden att skrivas ut i flera segment:

```shell
$ ls build/static/js
2.5b77f553.chunk.js
2.5b77f553.chunk.js.map
main.cff1a559.chunk.js
main.cff1a559.chunk.js.map
runtime~main.a8a9905a.js
runtime~main.a8a9905a.js.map
```

Att bara läsa in segment när de behövs kan förbättra programmets prestanda avsevärt.

För att den här funktionen ska fungera med AEM måste programmet kunna identifiera vilka JS- och CSS-filer som behöver begäras från den HTML som genereras av AEM. Detta kan du göra med hjälp av nyckeln entrypoints i filen asset-manifest.json. Filen tolkas i clientlib.config.js och bara entrypoint-filerna paketeras i ClientLib. De återstående filerna placeras i ClientLibs resurskatalog och efterfrågas dynamiskt och därför bara laddas när de verkligen behövs.

Mer information om hur AEM ClientLibs används av projektets arkityp finns i den allmänna dokumentationen [ui.front-modulen ](uifrontend.md#clientlibs).
