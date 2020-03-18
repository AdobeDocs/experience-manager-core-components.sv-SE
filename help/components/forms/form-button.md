---
title: Komponent för formulärknapp
description: Komponenten Core Component Form Hidden gör det möjligt att inkludera ett dolt fält i ett formulär.
translation-type: tm+mt
source-git-commit: 95c0621f5423bfa515fe5e8b693e127ea56b4ae0

---


# Komponent för formulärknapp {#form-button-component}

Med komponenten Core Component Form Button Component (Knappkomponent för kärnkomponent) kan du inkludera en knapp som utlöser en åtgärd på en sida.

## Användning {#usage}

Komponenten Core Component Form Button gör det möjligt att skapa knappfält, ofta för att utlösa att formuläret skickas och är avsedd att användas tillsammans med komponenten [](form-container.md)Form Container.

Knappegenskaperna kan definieras av innehållsredigeraren i [konfigurationsdialogrutan](#configure-dialog).

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Form Button Component är v2, som introducerades i version 2.0.0 av Core Components i januari 2018 och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponentversionerna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |--- |---|
| v2 | Kompatibel | Kompatibel | Kompatibel | Kompatibel |
| [v1](/help/components/v1/form-button-v1.md) | Kompatibel | Kompatibel | Kompatibel | - |

Mer information om Core Component-versioner och -versioner finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill visa Form Button-komponenten och se exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_form_button).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Form Button-komponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_form_button_v2).

Mer information om hur du utvecklar kärnkomponenter finns i dokumentationen till [Core Components Developer](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera knappens parametrar.

### Fliken Egenskaper {#properties-tab}

![](/help/assets/screen_shot_2018-01-12at120433.png)

* **Typ**

   * **Knapp**
   * **Skicka**

* **Titel** - Den text som visas på knappen

   * Om inget anges används knapptypen som standard

* **Namn** - Namnet på knappen som skickas med formulärdata
* **Värde** - Värdet på knappen som skickas med formulärdata

## Designdialogruta {#design-dialog}

### Fliken Format {#styles-tab}

Komponenten Form Button har stöd för AEM [Style System](/help/get-started/authoring.md#component-styling).
