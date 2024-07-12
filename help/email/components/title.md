---
title: E-posttitelkomponent
description: E-posttitelkomponenten är en avsnittsrubrikkomponent för dina e-postmeddelanden som innehåller redigering på plats.
role: Architect, Developer, Admin, User
exl-id: f65b6973-bb36-406f-bbea-f85a23f5340b
source-git-commit: 3abc29e0c186a84f079d5938b8b716f4c7378d65
workflow-type: tm+mt
source-wordcount: '593'
ht-degree: 0%

---


# E-posttitelkomponent {#email-title-component}

E-posttitelkomponenten är en avsnittsrubrikkomponent för dina e-postmeddelanden som innehåller redigering på plats.

## Användning {#usage}

E-posttitelkomponenten är avsedd att användas som rubrik eller rubrik för ett avsnitt i ett e-postmeddelande.

* De tillgängliga rubriknivåerna kan definieras av mallskaparen i dialogrutan [Design.](#design-dialog)
* Innehållsförfattaren kan välja mellan tillgängliga rubriknivåer i dialogrutan [Redigera.](#edit-dialog)

För att underlätta redigeringen av rubriktexten är det också enkelt att redigera texten på plats.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av E-posttitelkomponenten är v1, som introducerades i och med version x av e-postkärnkomponenterna i oktober 2022, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | Kompatibel | - |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Core Email Components Versions](/help/versions.md).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Title Component [finns på GitHub](https://adobe.com/go/aem_cmp_tech_email_title_v1).

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).

## Dialogrutan Redigera {#edit-dialog}

I redigeringsdialogrutan kan innehållsförfattaren definiera titeltexten och välja rubriknivå.

* **Rubrik** - Om den är tom används sidtiteln
   * Klicka på Campaign-ikonen för att öppna dialogrutan [Välj Adobe Campaign-variabel](/help/email/campaign-variables.md) och infoga dynamiskt innehåll från Adobe Campaign.
* **Typ / Storlek** - Definierar rubriknivån för titeln
* **Länk** - Definierar innehållet som titeln ska länka till. Det kan vara en sökväg till en innehållssida, en extern URL eller en sidankarpunkt.
   * Klicka på Campaign-ikonen för att öppna dialogrutan [Välj Adobe Campaign-variabel](/help/email/campaign-variables.md) och infoga dynamiskt innehåll från Adobe Campaign.
* **ID** - Med det här alternativet kan du kontrollera den unika identifieraren för komponenten i HTML.
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka CSS.

![Redigeringsdialogrutan för e-posttitelkomponenten](/help/email/assets/email-title-edit.png)

Du kan även använda redigeraren på plats för att redigera texten i titelkomponenten.

![Redigering på plats av e-posttitelkomponent](/help/email/assets/email-title-edit-inline.png)

### Fliken Format {#styles-tab-edit}

E-posttitelkomponenten stöder AEM [Style System.](/help/get-started/authoring.md#component-styling)

Använd listrutan för att välja de format som du vill använda på komponenten. Markeringar som görs i redigeringsdialogrutan har samma effekt som de som väljs i komponentverktygsfältet.

Format måste konfigureras för den här komponenten i [designdialogrutan](#design-dialog) för att den nedrullningsbara menyn ska vara tillgänglig.

![Fliken Format i redigeringsdialogrutan för titelkomponent](/help/email/assets/email-title-edit-styles.png)

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera den standardrubriknivå som titelkomponenter ska ha när de skapas av innehållsförfattarna.

### Fliken Storlekar {#sizes-tab}

![Utformningsdialogrutan för titelkomponenten](/help/email/assets/email-title-design.png)

* **Tillåtna typer/storlekar för författare** - Aktivera eller inaktivera rubriktyper som är tillgängliga för innehållsförfattare när de använder e-posttitelkomponenten.
* **Standardtyp/Standardstorlek** - Definiera den rubriktyp som automatiskt tilldelas när en innehållsförfattare lägger till e-posttitelkomponenten på en sida.
* **Inaktivera länk** - Inaktivera stöd för länkar i e-posttitelkomponenten så att innehållsförfattare inte kan länka från titlar.

### Fliken Format {#styles-tab}

E-posttitelkomponenten stöder AEM [Style System](/help/get-started/authoring.md#component-styling).
