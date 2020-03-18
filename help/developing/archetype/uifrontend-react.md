---
title: Front-End Build for React SPAs
description: En beskrivning av den inledande processen för byggprojekt för Reaktionsbaserade SPA-projekt
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# Front-End Build for React SPAs {#frontend-react}

I det här dokumentet förklaras detaljerna för det projekt som skapades när en arraytyp användes för att skapa ett SPA-program (single page application) baserat på React-ramverket. Det vill säga när du ställer in `frontendModule` alternativet på `react`.

## Översikt {#overview}

Det här projektet startades med [create-rea-app](https://github.com/facebook/create-react-app).

Det här programmet är utformat för att använda en webbplats AEM-modell. Layouten genereras automatiskt med hjälpkomponenterna från paketet [@adobe/cq-response-editable-components](https://www.npmjs.com/package/@adobe/cq-react-editable-components) .

## Skript {#scripts}

I projektkatalogen kan du köra följande kommandon:

### npm start {#npm-start}

```
npm start
```

Med det här kommandot körs programmet i utvecklingsläge genom att JSON-modellen proxeras från en lokal AEM-instans som körs på http://localhost:4502. Detta förutsätter att hela projektet har distribuerats till AEM minst en gång (`mvn clean install -PautoInstallPackage` i projektets rot).

När du har kört `npm start` i katalogen [ui.front](uifrontend.md) öppnas appen automatiskt i webbläsaren (på sökvägen `http://localhost:3000/content/<appId>/<country>/<language>/home.html`). Om du gör ändringar läses sidan in igen.

Om du får felmeddelanden relaterade till CORS kanske du vill konfigurera AEM enligt följande:

1. Navigera till Configuration Manager (http://localhost:4502/system/console/configMgr)
1. Öppna konfigurationen för&quot;Adobe Granite Cross-Origin Resource Sharing Policy&quot;
1. Skapa en ny konfiguration med följande ytterligare värden:
   * Tillåtna ursprungsobjekt: http://localhost:3000
   * Rubriker som stöds: Behörighet
   * Tillåtna metoder: ALTERNATIV

### npm-provning {#npm-test}

```
npm test
```

Det här kommandot startar testköraren i interaktivt bevakningsläge. Mer information finns i [Reaktionsdokumentationen om hur du kör tester](https://facebook.github.io/create-react-app/docs/running-tests) .

### npm run build {#npm-run-build}

```
npm run build
```

Med det här kommandot byggs programmet för produktion till byggmappen. Det innehåller Reagera i produktionsläge och optimerar bygget för bästa prestanda. Mer information finns i [React-dokumentationen om distribution](https://facebook.github.io/create-react-app/docs/deployment) .

Dessutom genereras en AEM ClientLib från appen med hjälp av paketet [aem-clientlib-generator](https://github.com/wcm-io-frontend/aem-clientlib-generator) .

## Webbläsarstöd {#browser-support}

Som standard använder det här projektet standardalternativet för [webbläsarlistor](https://github.com/browserslist/browserslist)för att identifiera målwebbläsare. Dessutom innehåller det polyfyllningar för moderna språkfunktioner som stöder äldre webbläsare (t.ex. Internet Explorer 11). Om stöd för sådana webbläsare inte krävs kan polyfyllningsberoenden och importer tas bort.

## Koddelning {#code-splitting}

Appen React är konfigurerad att som standard använda [koddelning](https://webpack.js.org/guides/code-splitting) . När du skapar en app för produktion kommer koden att skrivas ut i flera segment:

```
$ ls build/static/js
2.5b77f553.chunk.js
2.5b77f553.chunk.js.map
main.cff1a559.chunk.js
main.cff1a559.chunk.js.map
runtime~main.a8a9905a.js
runtime~main.a8a9905a.js.map
```

Att bara läsa in segment när de behövs kan förbättra programmets prestanda avsevärt.

För att den här funktionen ska fungera med AEM måste appen kunna identifiera vilka JS- och CSS-filer som behöver begäras från den HTML som genererats av AEM. Detta kan du göra med hjälp av nyckeln entrypoints i filen asset-manifest.json. Filen tolkas i clientlib.config.js och bara entrypoint-filerna paketeras i ClientLib. De återstående filerna placeras i ClientLibs resurskatalog och efterfrågas dynamiskt och därför bara laddas när de verkligen behövs.

Mer information om hur AEM ClientLibs används av projekttypen finns i den allmänna dokumentationen [för modulen](uifrontend.md#clientlibs) ui.front.
