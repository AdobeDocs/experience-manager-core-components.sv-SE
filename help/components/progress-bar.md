---
title: Progress Bar-komponent
description: Förloppsindikatorkomponenten visar förloppet mot ett mål
role: Architect, Developer, Admin, User
exl-id: 47afc5a6-ac57-4b6c-92c4-015ca956a20b
source-git-commit: dd30def59a8f037864da875ef4c831b11f766e57
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 1%

---


# Progress Bar-komponent {#progress-bar-component}

Komponenten Core Component Progress Bar representerar visuellt förloppet mot ett mål.

{{traditional-aem}}

## Användning {#usage}

Med Progress Bar-komponenten kan innehållsförfattaren enkelt skapa en förloppsindikator genom att definiera en procentandel av slutförandet, vilket ger en intuitiv visuell visning av förloppet mot ett mål.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Progress Bar-komponenten är v1, som introducerades i version 2.9.0 av Core Components i maj 2020, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponenterna är kompatibla med samt länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|---|---|---|---|---|
| v1 | Kompatibel med <br>[version 2.17.4](/help/versions.md) och tidigare | Kompatibel | Kompatibel | Kompatibel |

## Exempel på komponentutdata {#sample-component-output}

Om du vill visa Progress Bar-komponenten och exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_progressbar).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Progress Bar-komponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_progress_v1).

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

![Förloppsindikatorkomponentens redigeringsdialogruta](/help/assets/progress-bar-edit.png)

* **Slutförande** - förloppet representerat av en procentandel
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [datalagret](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera de format som ska användas för Progress Bar-komponenten.

### Fliken Format {#styles-tab}

Förloppsindikatorkomponenten stöder AEM [Style System](/help/get-started/authoring.md#component-styling).

## Adobe Client Data Layer {#data-layer}

Förloppsindikatorkomponenten stöder [Adobe-klientdatalagret.](/help/developing/data-layer/overview.md)
