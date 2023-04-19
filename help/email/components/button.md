---
title: E-postknappkomponent
description: Med komponenten E-postknapp kan du konfigurera och visa ett knappobjekt i innehållet.
role: Architect, Developer, Admin, User
exl-id: b144e8d1-1097-475d-b2eb-3353c176afb9
source-git-commit: 3abc29e0c186a84f079d5938b8b716f4c7378d65
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# E-postknappkomponent {#email-button-component}

Med komponenten E-postknapp kan du konfigurera och visa ett knappobjekt i innehållet.

## Användning {#usage}

Med komponenten E-postknapp kan du inkludera en knapp i innehållet, klickbar av innehållsläsaren, som länkar till ytterligare resurser.

* Knappens egenskaper kan markeras i [dialogrutan konfigurera.](#configure-dialog)
* Format för e-postknappskomponenten kan definieras i [designdialog.](#design-dialog)

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av e-postknappskomponenten är v1, som introducerades med version x av e-postkärnkomponenterna i oktober 2022, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | Kompatibel | - |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [E-postkärnkomponentversioner.](/help/email/versions.md)

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om e-postknappskomponenten [finns på GitHub.](https://adobe.com/go/aem_cmp_tech_email_button_v1)

Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentens utvecklare.](/help/developing/overview.md)

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera knappen och hur den fungerar och visas för en läsare av ditt innehåll.

### Fliken Egenskaper {#properties-tab}

![Fliken Egenskaper i redigeringsdialogrutan för Button-komponenten](/help/email/assets/email-button-edit-properties.png)

* **Text** - Den text som ska visas på knappen
   * Klicka på Campaign-ikonen för att öppna [Välj Adobe Campaign-variabel](/help/email/campaign-variables.md) för att infoga dynamiskt innehåll från Adobe Campaign.
* **Länk** - Länka till en innehållssida i AEM, en extern resurs eller ett ankare
   * Använd **Dialogrutan Markering** för att välja en bana i AEM.
   * Klicka på Campaign-ikonen för att öppna [Välj Adobe Campaign-variabel](/help/email/campaign-variables.md) för att infoga dynamiskt innehåll från Adobe Campaign.
* **Ikon** - Identifierare för att visa en ikon i knappen
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML.
   * Om du inte anger något värde genereras ett unikt ID automatiskt och du hittar det genom att kontrollera innehållet.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka CSS.
* **Öppna länk på ny flik** - Om det här alternativet är markerat öppnas länken på en ny webbläsarflik.

### Fliken Tillgänglighet {#accessibility-tab}

![Fliken Tillgänglighet i redigeringsdialogrutan för Button-komponenten](/help/email/assets/email-button-edit-accessibility.png)

På **Tillgänglighet** -tabb kan värden anges för [Tillgänglighet för ARIA](https://www.w3.org/WAI/standards-guidelines/aria/) -etiketter för komponenten.

* **Etikett** - Värdet på ett ARIA-etikettattribut för komponenten

### Fliken Format {#styles-tab-edit}

E-postknappkomponenten stöder AEM [Formatsystem.](/help/get-started/authoring.md#component-styling).

Använd listrutan för att välja de format som du vill använda på komponenten. Markeringar som görs i redigeringsdialogrutan har samma effekt som de som väljs i komponentverktygsfältet.

Format måste konfigureras för den här komponenten i [designdialogruta](#design-dialog) för att fliken ska vara tillgänglig.

## Designdialogruta {#design-dialog}

### Fliken Format {#styles-tab}

E-postknappkomponenten stöder AEM [Formatsystem](/help/get-started/authoring.md#component-styling).
