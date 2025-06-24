---
title: E-postknappkomponent
description: Med komponenten E-postknapp kan du konfigurera och visa ett knappobjekt i ditt innehåll.
role: Architect, Developer, Admin, User
exl-id: b144e8d1-1097-475d-b2eb-3353c176afb9
index: false
source-git-commit: eb77567dc32cccb81a9fc131493d11fb55b7e93b
workflow-type: tm+mt
source-wordcount: '517'
ht-degree: 0%

---


# E-postknappkomponent {#email-button-component}

Med komponenten E-postknapp kan du konfigurera och visa ett knappobjekt i ditt innehåll.

## Användning {#usage}

Med komponenten E-postknapp kan du inkludera en knapp i innehållet, klickbar av innehållsläsaren, som länkar till ytterligare resurser.

* Knappens egenskaper kan väljas i dialogrutan [Konfigurera.](#configure-dialog)
* Format för e-postknappskomponenten kan definieras i dialogrutan [design.](#design-dialog)

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av e-postknappskomponenten är v1, som introducerades med version x av e-postkärnkomponenterna i oktober 2022, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponenterna är kompatibla med samt länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|---|---|---|---|
| v1 | Kompatibel | - | - |

Mer information om Core Component-versioner och -versioner finns i dokumentet [Email Core Components Versions.](/help/email/versions.md)

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om e-postknappkomponenten [finns på GitHub.](https://adobe.com/go/aem_cmp_tech_email_button_v1)

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen till utvecklaren av kärnkomponenter.](/help/developing/overview.md)

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera knappen och hur den fungerar och visas för en läsare av ditt innehåll.

### Fliken Egenskaper {#properties-tab}

![Fliken Egenskaper i redigeringsdialogrutan för knappkomponenten](/help/email/assets/email-button-edit-properties.png)

* **Text** - Den text som ska visas på knappen
   * Klicka på Campaign-ikonen för att öppna dialogrutan [Välj Adobe Campaign-variabel](/help/email/campaign-variables.md) och infoga dynamiskt innehåll från Adobe Campaign.
* **Länk** - Länka till en innehållssida i AEM, en extern resurs eller ett ankare
   * Använd dialogrutan **Markering** för att välja en sökväg i AEM.
   * Klicka på Campaign-ikonen för att öppna dialogrutan [Välj Adobe Campaign-variabel](/help/email/campaign-variables.md) och infoga dynamiskt innehåll från Adobe Campaign.
* **Ikon** - Identifierare för att visa en ikon i knappen
* **ID** - Det här alternativet tillåter kontroll av den unika identifieraren för komponenten i HTML.
   * Om du inte anger något värde genereras ett unikt ID automatiskt och du hittar det genom att kontrollera innehållet.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka CSS.
* **Öppna länk på ny flik** - Om det här alternativet är markerat öppnas länken på en ny flik i webbläsaren.

### Fliken Tillgänglighet {#accessibility-tab}

![Fliken Tillgänglighet i redigeringsdialogrutan för Button-komponenten](/help/email/assets/email-button-edit-accessibility.png)

På fliken **Hjälpmedel** kan värden anges för [ARIA-hjälpmedelsetiketter](https://www.w3.org/WAI/standards-guidelines/aria/) för komponenten.

* **Etikett** - Värdet för ett ARIA-etikettattribut för komponenten

### Fliken Format {#styles-tab-edit}

Knappkomponenten E-post stöder AEM [Style System.](/help/get-started/authoring.md#component-styling).

Använd listrutan för att välja de format som du vill använda på komponenten. Markeringar som görs i redigeringsdialogrutan har samma effekt som de som väljs i komponentverktygsfältet.

Format måste konfigureras för den här komponenten i [designdialogrutan](#design-dialog) för att fliken ska vara tillgänglig.

## Designdialogruta {#design-dialog}

### Fliken Format {#styles-tab}

Knappkomponenten E-post stöder AEM [Style System](/help/get-started/authoring.md#component-styling).
