---
title: Komponent för dolt formulär
description: Komponenten Core Component Form Hidden gör det möjligt att visa ett dolt fält.
role: Architect, Developer, Admin, User
exl-id: 0364cd3b-3c09-46db-9392-a67e3f9ea7a5
source-git-commit: 6fbc781db555bc6abaed1d122a9a8756e3d53222
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 1%

---

# Komponent för dolt formulär{#form-hidden-component}

Komponenten Core Component Form Hidden gör det möjligt att visa ett dolt fält.

## Användning {#usage}

Med den dolda komponenten för kärnkomponentformulär kan du skapa dolda fält som skickar information om den aktuella sidan tillbaka till AEM och som ska användas tillsammans med [formulärbehållarkomponenten](form-container.md).

Fältegenskaperna kan definieras av innehållsredigeraren i dialogrutan [Konfigurera](form-hidden.md).

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Form Hidden Component är v2, som introducerades i version 2.0.0 av Core Components i januari 2018 och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponenterna är kompatibla med samt länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|--- |--- |--- |---|---|
| v2 | Kompatibel med <br>[version 2.17.4](/help/versions.md) och tidigare | Kompatibel | Kompatibel | Kompatibel |
| [v1](/help/components/v1/form-hidden-v1.md) | Kompatibel | Kompatibel | - | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill visa Form Hidden-komponenten och se exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_form_hidden).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om den dolda formulärkomponenten [ finns på GitHub](https://adobe.com/go/aem_cmp_tech_form_hidden_v2).

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera parametrarna för det dolda fältet.

![Dialogrutan för dold formulärredigering](/help/assets/form-hidden-edit.png)

* **Namn** - Namnet på fältet som skickas med formulärdata
* **Värde** - Fältets värde, som skickas med formulärdata
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [datalagret](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

Eftersom komponenten Formulär-dold normalt inte har några synliga attribut visar komponentens platshållare i redigeraren fältvärdena **Namn** och **Värde** om de har tilldelats för att hjälpa författaren att identifiera rätt Form Hidden-komponent.

![Exempel på dold formulärkomponent](/help/assets/form-hidden-example.png)

## Designdialogruta {#design-dialog}

### Fliken Format {#styles-tab}

Komponenten Form Hidden stöder AEM [Style System](/help/get-started/authoring.md#component-styling).
