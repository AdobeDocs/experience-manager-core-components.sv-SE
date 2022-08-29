---
title: Button-komponent
description: Med komponenten Core Component Button kan du skapa och visa en knapp.
role: Architect, Developer, Admin, User
exl-id: e17efd1d-90d4-497a-9e7d-45934d81bc28
source-git-commit: 327c239b02e0aecee878784c918bfa98d960530e
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 1%

---

# Button-komponent{#button-component}

Komponenten Core Component Button gör det möjligt att konfigurera och visa ett knappobjekt på en sida.

## Användning {#usage}

Komponenten Core Component Button gör att du kan inkludera en knapp på en sida.

* Knappens egenskaper kan markeras i [konfigurera dialogruta](#configure-dialog).
* Format för Button-komponenten kan definieras i [designdialogruta](#design-dialog).

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Button-komponenten är v2, som introducerades i version 2.18.0 av Core-komponenterna i februari 2022, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v2 | - | Kompatibel | Kompatibel |
| [v1](v1/button.md) | Kompatibel | Kompatibel | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Huvudkomponentversioner](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill se exempel på Button-komponenten och dess konfigurationsalternativ samt HTML och JSON-utdata går du till [Komponentbibliotek](https://adobe.com/go/aem_cmp_library_button).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Button-komponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_button_v2).

Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera knappen och hur den ska fungera och visas för en besökare på sidan.

### Fliken Egenskaper {#properties-tab}

![Fliken Egenskaper i redigeringsdialogrutan för Button-komponenten](/help/assets/button-edit-properties.png)

* **Text** - Den text som ska visas på knappen
* **Länk** - Länka till en innehållssida i AEM, en extern resurs eller ett ankare
   * Använd **Dialogrutan Markering** för att välja en bana i AEM.
* **Öppna länk på ny flik** - Om det här alternativet är markerat öppnas länken på en ny webbläsarflik.
* **Ikon** - Identifierare för att visa en ikon i knappen
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [Datalager](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

### Fliken Tillgänglighet {#accessibility-tab}

![Fliken Tillgänglighet i redigeringsdialogrutan för Button-komponenten](/help/assets/button-edit-accessibility.png)

På **Tillgänglighet** -tabb kan värden anges för [Tillgänglighet för ARIA](https://www.w3.org/WAI/standards-guidelines/aria/) -etiketter för komponenten.

* **Etikett** - Värdet på ett ARIA-etikettattribut för komponenten

### Fliken Format {#styles-tab-edit}

![Fliken Stilar i redigeringsdialogrutan för Button-komponenten](/help/assets/button-edit-styles.png)

Button-komponenten stöder AEM [Formatsystem.](/help/get-started/authoring.md#component-styling).

Använd listrutan för att välja de format som du vill använda på komponenten. Markeringar som görs i redigeringsdialogrutan har samma effekt som de som väljs i komponentverktygsfältet.

Format måste konfigureras för den här komponenten i [designdialogruta](#design-dialog) för att den nedrullningsbara menyn ska vara tillgänglig.

## Designdialogruta {#design-dialog}

### Fliken Format {#styles-tab}

Button-komponenten stöder AEM [Formatsystem](/help/get-started/authoring.md#component-styling).

## Adobe-klientdatalager {#data-layer}

Button-komponenten har stöd för [Adobe Client Data Layer.](/help/developing/data-layer/overview.md)
