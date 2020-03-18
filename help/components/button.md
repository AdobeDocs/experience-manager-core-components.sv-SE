---
title: Button-komponent
description: Med komponenten Core Component Button kan du skapa och visa en knapp.
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# Button-komponent{#button-component}

Komponenten Core Component Button gör det möjligt att konfigurera och visa ett knappobjekt på en sida.

## Användning {#usage}

Komponenten Core Component Button gör att du kan inkludera en knapp på en sida.

* Knappens egenskaper kan väljas i [konfigurationsdialogrutan](#configure-dialog).
* Du kan definiera format för Button-komponenten i [designdialogrutan](#design-dialog).

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Button-komponenten är v1, som introducerades i version 2.5.0 av Core-komponenterna i juni 2019, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponentversionerna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|---|
| v1 | Kompatibel | Kompatibel | Kompatibel | Kompatibel |

Mer information om Core Component-versioner och -versioner finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill se exempel på Button-komponenten och dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_button).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Button-komponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_button_v1).

Mer information om hur du utvecklar kärnkomponenter finns i dokumentationen till [Core Components Developer](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera knappen och hur den ska fungera och visas för en besökare på sidan.

### Fliken Egenskaper {#properties-tab}

![](/help/assets/screen-shot-2019-08-29-12.19.32.png)

* **Text** - Den text som ska visas på knappen
* **Länk** - Länka till en innehållssida i AEM, en extern resurs eller ett ankare
   * Använd dialogrutan **** Markering för att välja en bana i AEM.
* **Ikon** - Identifierare för att visa en ikon i knappen

### Fliken Tillgänglighet {#accessibility-tab}

![](/help/assets/screen-shot-2019-08-29-12.19.43.png)

På fliken **Tillgänglighet** kan du ange värden för [ARIA-hjälpmedelsetiketter](https://www.w3.org/WAI/standards-guidelines/aria/) för komponenten.

* **Etikett** - Värdet för ett ARIA-etikettattribut för komponenten

## Designdialogruta {#design-dialog}

### Fliken Format {#styles-tab}

Bildkomponenten stöder AEM [Style System](/help/get-started/authoring.md#component-styling).
