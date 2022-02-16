---
title: Avgränsarkomponent
description: Avgränsarkomponenten skapar en brytning mellan komponenter på en sida
role: Architect, Developer, Admin, User
exl-id: 79f19368-67fa-4864-93f7-2aa801d13fdb
source-git-commit: 9767a3a10cb9a77f385edc0ac3fb00096c0087af
workflow-type: tm+mt
source-wordcount: '308'
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
| v1 | Kompatibel med<br>[version 2.17.4](/help/versions.md) och tidigare | Kompatibel | Kompatibel |

## Exempel på komponentutdata {#sample-component-output}

Om du vill visa Separator-komponenten samt se exempel på dess konfigurationsalternativ samt HTML och JSON-utdata går du till [Komponentbibliotek](https://adobe.com/go/aem_cmp_library_separator).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Separator-komponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_separator_v1).

Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

![Dialogrutan Redigera avgränsningskomponent](/help/assets/separator-edit.png)

* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [Datalager](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera de format som används för avgränsningskomponenten.

### Fliken Format {#styles-tab}

Separator-komponenten stöder AEM [Formatsystem](/help/get-started/authoring.md#component-styling).
