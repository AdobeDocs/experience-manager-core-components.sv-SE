---
title: Komponent för formulärknapp
description: Komponenten Core Component Form Hidden gör det möjligt att inkludera ett dolt fält i ett formulär.
role: Architect, Developer, Admin, User
exl-id: 1e5cff43-57db-4bfc-b2d2-23307eaf5eb3
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 2%

---

# Komponent för formulärknapp {#form-button-component}

Med komponenten Core Component Form Button Component (Knappkomponent för kärnkomponent) kan du inkludera en knapp som utlöser en åtgärd på en sida.

## Användning {#usage}

Komponenten Core Component Form Button gör det möjligt att skapa knappfält, ofta för att utlösa att formuläret skickas och är avsedd att användas tillsammans med [komponenten Formulärbehållare](form-container.md).

Knappegenskaperna kan definieras av innehållsredigeraren i [konfigurationsdialogrutan](#configure-dialog).

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Form Button Component är v2, som introducerades i version 2.0.0 av Core Components i januari 2018 och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | Kompatibel | Kompatibel | Kompatibel |
| [v1](/help/components/v1/form-button-v1.md) | Kompatibel | Kompatibel | - |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill visa Form Button-komponenten och se exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_form_button).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Form Button-komponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_form_button_v2).

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen till Core Components developer](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera knappens parametrar.

### Fliken Egenskaper {#properties-tab}

![Formulärknappskomponentens redigeringsdialogruta](/help/assets/form-button-edit.png)

* **Typ**

   * **Knapp**
   * **Skicka**

* **Titel**  - Texten som visas på knappen

   * Om inget anges används knapptypen som standard

* **Namn** - Namnet på knappen som skickas med formulärdata
* **Värde**  - Värdet på knappen som skickas in tillsammans med formulärdata

* **ID**  - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i  [datalagret](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

## Designdialogruta {#design-dialog}

### Fliken Format {#styles-tab}

Komponenten Form Button stöder AEM [Style System](/help/get-started/authoring.md#component-styling).
