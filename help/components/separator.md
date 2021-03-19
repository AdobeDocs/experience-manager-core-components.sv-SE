---
title: Avgränsarkomponent
description: Avgränsarkomponenten skapar en brytning mellan komponenter på en sida
role: Arkitekt, utvecklare, administratör, affärsansvarig
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 2%

---


# Avgränsarkomponent {#separator-component}

Komponenten Core Component Separator visar en vågrät linje för att separera innehåll.

## Användning {#usage}

Med avgränsningskomponenten kan innehållsförfattaren enkelt skapa en vågrät linje som en brytning mellan innehållet för att bättre organisera informationen på en sida.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Separator Component är v1, som introducerades i version 2.3.0 av Core Components i februari 2019, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|---|
| v1 | Kompatibel | Kompatibel | Kompatibel |

## Exempelkomponentutdata {#sample-component-output}

Om du vill visa Separator-komponenten och se exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_separator).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om avgränsningskomponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_separator_v1).

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen till Core Components developer](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

![Dialogrutan Redigera avgränsningskomponent](/help/assets/separator-edit.png)

* **ID**  - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i  [datalagret](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

## Designdialog {#design-dialog}

I designdialogrutan kan mallskaparen definiera de format som används för avgränsningskomponenten.

### Fliken Format {#styles-tab}

Separator-komponenten stöder AEM [Style System](/help/get-started/authoring.md#component-styling).
