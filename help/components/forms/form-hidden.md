---
title: Komponent för dolt formulär
description: Komponenten Core Component Form Hidden gör det möjligt att visa ett dolt fält.
translation-type: tm+mt
source-git-commit: 95c0621f5423bfa515fe5e8b693e127ea56b4ae0

---


# Komponent för dolt formulär{#form-hidden-component}

Komponenten Core Component Form Hidden gör det möjligt att visa ett dolt fält.

## Användning {#usage}

Med den dolda komponenten för kärnkomponentformulär kan du skapa dolda fält som skickar information om den aktuella sidan tillbaka till AEM och som ska användas tillsammans med [formulärbehållarkomponenten](form-container.md).

Fältegenskaperna kan definieras av innehållsredigeraren i [konfigurationsdialogrutan](form-hidden.md).

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Form Hidden Component är v2, som introducerades i version 2.0.0 av Core Components i januari 2018 och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponentversionerna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |--- |---|
| v2 | Kompatibel | Kompatibel | Kompatibel | Kompatibel |
| [v1](/help/components/v1/form-hidden-v1.md) | Kompatibel | Kompatibel | Kompatibel | - |

Mer information om Core Component-versioner och -versioner finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill visa Form Hidden Component (Komponenten är dold) och se exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_form_hidden).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Form Hidden Component [finns på GitHub](https://adobe.com/go/aem_cmp_tech_form_hidden_v2).

Mer information om hur du utvecklar kärnkomponenter finns i dokumentationen till [Core Components Developer](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera parametrarna för det dolda fältet.

![](/help/assets/chlimage_1-26.png)

* **Namn** Namnet på fältet som skickas med formulärdata
* **Värde** Fältets värde, som skickas med formulärdata
* **Identifierare** Identifieraren ska vara unik på sidan och kan användas för att binda skript till det här formulärfältet

Eftersom komponenten Formulär-dold normalt inte har några synliga attribut visar komponentens platshållare i redigeraren fältvärdena **Namn** och **Värde** om de har tilldelats för att hjälpa författaren att identifiera rätt formulärets dolda komponent.

![](/help/assets/screenshot_2018-10-19at094927.png)

## Designdialogruta {#design-dialog}

Det finns ingen designdialogruta för komponenten Formulär-dold.
