---
title: Delningskomponent för sociala medier
description: Komponenten för delning via sociala medier i kärnkomponenten är en delningswidget för Facebook och Pinterest.
role: Architect, Developer, Admin, User
exl-id: 8bd53c76-da91-479b-b416-f978682a3d43
source-git-commit: 327c239b02e0aecee878784c918bfa98d960530e
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 1%

---

# Delningskomponent för sociala medier{#social-sharing-component}

Komponenten för delning via sociala medier i kärnkomponenten är en delningswidget för Facebook och Pinterest.

>[!NOTE]
>
>Delningskomponenten för sociala medier har avskrivits med kärnkomponenter [version 2.18.0.](/help/versions.md)

## Användning {#usage}

Delningskomponenten för sociala medier lägger till Facebook- och Pinterest-delningslänkar på sidan. Den ingår ofta i sidhuvuden och sidfötter.

Till skillnad från andra komponenter görs inställningarna för komponenten för delning via sociala medier av mallförfattaren via [Egenskaper för första sidan](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html) och av innehållsförfattaren via [Sidegenskaper](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html).

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av den sociala delningskomponenten är v1, som introducerades i version 1.0.0 av de centrala komponenterna, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds och de AEM versionerna som komponenterna är kompatibla med.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v1 | Kompatibel med<br>[version 2.17.4](/help/versions.md) och tidigare | Kompatibel, borttagen | Kompatibel, borttagen |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Huvudkomponentversioner](/help/versions.md).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om delningskomponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_sharing_v1).

Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Dialogrutan Redigera {#edit-dialog}

![Redigeringsdialogrutan för delningskomponenten](/help/assets/sharing-edit.png)

* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [Datalager](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

Eftersom delning kräver särskilda sidhuvuden måste delning vara aktiverat på sidnivå. För innehållsförfattaren är därför ytterligare redigeringsalternativ för delningskomponenten tillgängliga via fliken Delning på [sidegenskaper](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html).

## Designdialogruta {#design-dialog}

Eftersom delning kräver särskilda sidhuvuden måste delning vara aktiverat på sidnivå. Därför är designalternativen för delningskomponenten tillgängliga för mallskaparen via [egenskaper för inledande sida](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html).
