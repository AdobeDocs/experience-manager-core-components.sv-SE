---
title: E-posttitelkomponent
description: E-posttitelkomponenten är en avsnittsrubrikkomponent för dina e-postmeddelanden som innehåller redigering på plats.
role: Architect, Developer, Admin, User
hidefromtoc: true
index: false
source-git-commit: 8bebe3ca036557f3f7c6b8ec0e65d6d104d5ffae
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 1%

---


# E-posttitelkomponent {#email-title-component}

E-posttitelkomponenten är en avsnittsrubrikkomponent för dina e-postmeddelanden som innehåller redigering på plats.

## Användning {#usage}

E-posttitelkomponenten är avsedd att användas som rubrik eller rubrik för ett avsnitt i ett e-postmeddelande.

* De tillgängliga rubriknivåerna kan definieras av mallskaparen i [designdialog.](#design-dialog)
* Innehållsförfattaren kan välja bland tillgängliga rubriknivåer i [redigeringsdialogruta.](#edit-dialog)

För att underlätta redigeringen av rubriktexten är det också enkelt att redigera texten på plats.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av E-posttitelkomponenten är v1, som introducerades i och med version x av e-postkärnkomponenterna i oktober 2022, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | Kompatibel | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Huvudversioner av e-postkomponenter](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill se både komponenten Title och exempel på dess konfigurationsalternativ samt HTML och JSON-utdata går du till [Komponentbibliotek.](https://adobe.com/go/aem_cmp_library_email_title)

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Title Component [finns på GitHub](https://adobe.com/go/aem_cmp_tech_email_title_v1).

Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Dialogrutan Redigera {#edit-dialog}

I redigeringsdialogrutan kan innehållsförfattaren definiera titeltexten och välja rubriknivå.

* **Titel** - Om den är tom används sidans rubrik
   * Klicka på Campaign-ikonen för att öppna [Välj Adobe Campaign-variabel](/help/email/campaign-variables.md) för att infoga dynamiskt innehåll från Adobe Campaign.
* **Typ / Storlek** - Definierar rubriknivån för titeln
* **Länk** - Definierar innehållet som titeln ska länka till. Det kan vara en sökväg till en innehållssida, en extern URL eller en sidankarpunkt.
   * Klicka på Campaign-ikonen för att öppna [Välj Adobe Campaign-variabel](/help/email/campaign-variables.md) för att infoga dynamiskt innehåll från Adobe Campaign.
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML.
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka CSS.

![Redigeringsdialogruta för e-posttitelkomponent](/help/email/assets/email-title-edit.png)

Du kan även använda redigeraren på plats för att redigera texten i titelkomponenten.

![In-place editing of Email Title Component](/help/email/assets/email-title-edit-inline.png)

### Fliken Format {#styles-tab-edit}

E-posttitelkomponenten stöder AEM [Formatsystem.](/help/get-started/authoring.md#component-styling)

Använd listrutan för att välja de format som du vill använda på komponenten. Markeringar som görs i redigeringsdialogrutan har samma effekt som de som väljs i komponentverktygsfältet.

Format måste konfigureras för den här komponenten i [designdialogruta](#design-dialog) för att den nedrullningsbara menyn ska vara tillgänglig.

![Fliken Stilar i redigeringsdialogrutan för komponenten Titel](/help/email/assets/email-title-edit-styles.png)

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera den standardrubriknivå som titelkomponenter ska ha när de skapas av innehållsförfattarna.

### Fliken Storlekar {#sizes-tab}

![Title Components&#39;&#39;s design dialog](/help/email/assets/email-title-design.png)

* **Tillåtna typer/storlekar för författare** - Aktivera eller inaktivera rubriktyper som är tillgängliga för innehållsförfattare när de använder e-posttitelkomponenten.
* **Standardtyp/storlek** - Definiera den rubriktyp som automatiskt tilldelas när en innehållsförfattare lägger till e-posttitelkomponenten på en sida.
* **Inaktivera länk** - Inaktivera stöd för länkar i e-posttitelkomponenten så att innehållsförfattare inte kan länka från titlar.

### Fliken Format {#styles-tab}

E-posttitelkomponenten stöder AEM [Formatsystem](/help/get-started/authoring.md#component-styling).
