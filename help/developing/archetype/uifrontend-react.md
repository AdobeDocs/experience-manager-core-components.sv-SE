---
title: Front-End Build för SPA
description: En beskrivning av den inledande processen för React-baserade SPA
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: dd8ef13a-9686-47a9-b6af-e486ff10c4d8
source-git-commit: 0eea0cd65063c739e5b405b0380b73962a858e48
workflow-type: tm+mt
source-wordcount: '512'
ht-degree: 0%

---

# Front-End Build för SPA {#frontend-react}

I det här dokumentet förklaras detaljerna för det projekt som skapades när en arkivtyp användes för att skapa ett ensidigt program (SPA) baserat på React-ramverket. När du ställer in `frontendModule` alternativ till `react`.

## Översikt {#overview}

Det här projektet startades med [create-rea-app](https://github.com/facebook/create-react-app).

Det här programmet är utformat för att förbruka en webbplats AEM modell. Layouten genereras automatiskt med hjälpkomponenterna från [@adobe/cq-rea-editable-components](https://www.npmjs.com/package/@adobe/aem-react-editable-components) paket.

## Skript {#scripts}

I projektkatalogen kan du köra följande kommandon:

### npm start {#npm-start}

```shell
npm start
```

Med det här kommandot körs programmet i utvecklingsläge genom att JSON-modellen proxeras från en lokal AEM som körs på http://localhost:4502. Detta förutsätter att hela projektet har distribuerats till AEM minst en gång (`mvn clean install -PautoInstallPackage` i projektets rot).

Efter körning `npm start` i [ui.front](uifrontend.md) öppnas din app automatiskt i webbläsaren (på sökvägen `http://localhost:3000/content/<appId>/<country>/<language>/home.html`). Om du gör ändringar läses sidan in igen.

Om du får felmeddelanden relaterade till CORS kan du konfigurera AEM enligt följande:

1. Navigera till Configuration Manager (http://localhost:4502/system/console/configMgr)
1. Öppna konfigurationen för Resursdelningspolicy för korsursprung i Adobe Granite
1. Skapa en ny konfiguration med följande ytterligare värden:
   * Tillåtna ursprungsobjekt: http://localhost:3000
   * Rubriker som stöds: Behörighet
   * Tillåtna metoder: OPTIONS

### npm-provning {#npm-test}

```shell
npm test
```

Det här kommandot startar testköraren i interaktivt bevakningsläge. Se [Reagera på dokumentation om testkörning](https://facebook.github.io/create-react-app/docs/running-tests) för mer information.

### npm run build {#npm-run-build}

```shell
npm run build
```

Med det här kommandot byggs programmet för produktion till byggmappen. Det innehåller Reagera i produktionsläge och optimerar bygget för bästa prestanda. Se [Reagera på dokumentation om distribution](https://facebook.github.io/create-react-app/docs/deployment) för mer information.

Dessutom genereras en AEM ClientLib från programmet med [aem-clientlib-generator](https://github.com/wcm-io-frontend/aem-clientlib-generator) paket.

## Webbläsarstöd {#browser-support}

Som standard används [Webbläsarlista](https://github.com/browserslist/browserslist)Standardalternativet för att identifiera målwebbläsare. Dessutom innehåller det polyfyllningar för moderna språkfunktioner som stöder äldre webbläsare (t.ex. Internet Explorer 11). Om stöd för sådana webbläsare inte krävs kan polyfyllningsberoenden och importer tas bort.

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

För att den här funktionen ska fungera med AEM måste programmet kunna identifiera vilka JS- och CSS-filer som behöver begäras från HTML som genereras av AEM. Detta kan du göra med hjälp av nyckeln entrypoints i filen asset-manifest.json. Filen tolkas i clientlib.config.js och bara entrypoint-filerna paketeras i ClientLib. De återstående filerna placeras i ClientLibs resurskatalog och efterfrågas dynamiskt och därför bara laddas när de verkligen behövs.

Se det allmänna [ui.frontModuldokumentation](uifrontend.md#clientlibs) om du vill ha mer information om hur AEM ClientLibs används av projektets arkityp.
