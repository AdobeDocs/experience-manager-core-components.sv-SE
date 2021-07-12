---
title: Button-komponent
description: Med komponenten Core Component Button kan du skapa och visa en knapp.
role: Architect, Developer, Admin, User
exl-id: e17efd1d-90d4-497a-9e7d-45934d81bc28
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 1%

---

# Button-komponent{#button-component}

Komponenten Core Component Button gör det möjligt att konfigurera och visa ett knappobjekt på en sida.

## Användning {#usage}

Komponenten Core Component Button gör att du kan inkludera en knapp på en sida.

* Knappens egenskaper kan väljas i [konfigurationsdialogrutan](#configure-dialog).
* Format för Button-komponenten kan definieras i [designdialogrutan](#design-dialog).

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Button-komponenten är v1, som introducerades i version 2.5.0 av Core-komponenterna i juni 2019, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Kompatibel | Kompatibel | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill visa Button-komponenten och exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_button).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Button-komponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_button_v1).

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen till Core Components developer](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera knappen och hur den ska fungera och visas för en besökare på sidan.

### Fliken Egenskaper {#properties-tab}

![Fliken Egenskaper i redigeringsdialogrutan för Button-komponenten](/help/assets/button-edit-properties.png)

* **Text**  - Den text som ska visas på knappen
* **Länk**  - Länka till en innehållssida i AEM, en extern resurs eller ett ankare
   * Använd dialogrutan **Markering** för att välja en sökväg i AEM.
* **Ikon**  - Identifierare för att visa en ikon i knappen
* **ID**  - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i  [datalagret](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

### Fliken Tillgänglighet {#accessibility-tab}

![Fliken Tillgänglighet i redigeringsdialogrutan för Button-komponenten](/help/assets/button-edit-accessibility.png)

På fliken **Accessibility** kan värden anges för [ARIA accessibility](https://www.w3.org/WAI/standards-guidelines/aria/)-etiketter för komponenten.

* **Etikett**  - Värdet för ett ARIA-etikettattribut för komponenten

## Designdialogruta {#design-dialog}

### Fliken Format {#styles-tab}

Button-komponenten stöder AEM [Style System](/help/get-started/authoring.md#component-styling).

## Adobe-klientdatalager {#data-layer}

Button-komponenten stöder [Adobe-klientdatalagret.](/help/developing/data-layer/overview.md)
