---
title: Delningskomponent för sociala medier
description: Den centrala komponenten för delning via sociala medier är en widget för delning via Facebook och Pinterest.
translation-type: tm+mt
source-git-commit: 4813748bcfa83ce7c73e81d4e4d445ecc8215d26
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 1%

---


# Delningskomponent för sociala medier{#social-sharing-component}

Den centrala komponenten för delning via sociala medier är en widget för delning via Facebook och Pinterest.

## Användning {#usage}

Delningskomponenten för sociala medier lägger till länkar för delning av Facebook och Pinterest på sidan. Det ingår ofta i sidhuvuden och sidfötter.

Till skillnad från andra komponenter görs inställningarna för komponenten för delning via sociala medier av mallskaparen via [Egenskaper för första sidan](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html) och av innehållsförfattaren via [Sidegenskaper](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html).

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av den sociala delningskomponenten är v1, som introducerades i version 1.0.0 av de centrala komponenterna, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds och de AEM versionerna som komponenterna är kompatibla med.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v1 | Kompatibel | Kompatibel | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempelkomponentutdata {#sample-component-output}

Om du vill se komponenterna för social delning och exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_sharing).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om delningskomponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_sharing_v1).

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen till Core Components developer](/help/developing/overview.md).

## Redigera dialogruta {#edit-dialog}

![Redigeringsdialogrutan för delningskomponenten](/help/assets/sharing-edit.png)

* **ID**  - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i  [datalagret](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

Eftersom delning kräver särskilda sidhuvuden måste delning vara aktiverat på sidnivå. Därför är ytterligare redigeringsalternativ för delningskomponenten tillgängliga på delningsfliken i [sidegenskaperna](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html) för innehållsförfattaren.

## Designdialog {#design-dialog}

Eftersom delning kräver särskilda sidhuvuden måste delning vara aktiverat på sidnivå. Därför är designalternativen för delningskomponenten tillgängliga för mallskaparen via de [inledande sidegenskaperna](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html).
