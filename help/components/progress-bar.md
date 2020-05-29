---
title: Progress Bar-komponent
description: Förloppsindikatorkomponenten visar förloppet mot ett mål
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 2%

---


# Progress Bar-komponent {#progress-bar-component}

Komponenten Core Component Progress Bar representerar visuellt förloppet mot ett mål.

## Användning {#usage}

Med Progress Bar-komponenten kan innehållsförfattaren enkelt skapa en förloppsindikator genom att definiera en procentandel av slutförandet, vilket ger en intuitiv visuell visning av förloppet mot ett mål.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Progress Bar-komponenten är v1, som introducerades i version 2.9.0 av Core Components i maj 2020, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponentversionerna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|---|
| v1 | Kompatibel | Kompatibel | Kompatibel |

## Exempel på komponentutdata {#sample-component-output}

Om du vill visa Progress Bar-komponenten och se exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_progress).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Progress Bar-komponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_progress_v1).

Mer information om hur du utvecklar kärnkomponenter finns i dokumentationen till [Core Components Developer](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

![Förloppsindikatorkomponentens redigeringsdialogruta](/help/assets/progress-bar-edit.png)

* **Slutförd** - förloppet i procent
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [datalagret](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera de format som ska användas för Progress Bar-komponenten.

### Fliken Format {#styles-tab}

Komponenten Progress Bar har stöd för AEM [Style System](/help/get-started/authoring.md#component-styling).
