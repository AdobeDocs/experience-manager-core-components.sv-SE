---
title: Titelkomponent
description: Komponenten Core Component Title är en avsnittsrubrikkomponent med redigering på plats.
translation-type: tm+mt
source-git-commit: 4813748bcfa83ce7c73e81d4e4d445ecc8215d26
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 1%

---


# Titelkomponent{#title-component}

Komponenten Core Component Title är en avsnittsrubrikkomponent med redigering på plats.

## Användning {#usage}

Titelkomponenten är avsedd att användas som rubrik eller rubrik för ett avsnitt i innehållet. De tillgängliga rubriknivåerna kan definieras av mallskaparen i [designdialogrutan](#design-dialog). Innehållsredigeraren kan välja bland tillgängliga rubriknivåer i [redigeringsdialogrutan](#edit-dialog). För att underlätta redigeringen av rubriktexten är det också enkelt att redigera texten på plats.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Title Component är v2, som introducerades i version 2.0.0 av Core Components i januari 2018, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|---|
| v2 | Kompatibel | Kompatibel | Kompatibel |
| [v1](v1/title-v1.md) | Kompatibel | Kompatibel | - |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempelkomponentutdata {#sample-component-output}

Om du vill visa både komponenten Title och exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_title).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Title Component [finns på GitHub](https://adobe.com/go/aem_cmp_tech_title_v2).

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen till Core Components developer](/help/developing/overview.md).

## Redigera dialogruta {#edit-dialog}

I redigeringsdialogrutan kan innehållsförfattaren definiera titeltexten och välja rubriknivå.

* **Titel**  - Om den är tom används sidans rubrik
* **Typ/storlek**  - Anger rubriknivån för titeln
* **Länk**  - Definierar innehållet som titeln ska länka till. Det kan vara en sökväg till en innehållssida, en extern URL eller en sidankarpunkt.
* **ID**  - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i  [datalagret](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

![Redigeringsdialogrutan för titelkomponent](/help/assets/title-edit.png)

>[!NOTE]
>
>Möjligheten att definiera en länk för titeln introducerades i version 2.2.0 av Core Components.

Du kan även använda redigeraren på plats för att redigera texten i titelkomponenten.

![In-place editing of Title Component](/help/assets/title-edit-inline.png)

## Designdialog {#design-dialog}

I designdialogrutan kan mallskaparen definiera den standardrubriknivå som titelkomponenter ska ha när de skapas av innehållsförfattarna.

### Fliken Storlekar {#sizes-tab}

![Title Components&#39;&#39;s design dialog](/help/assets/title-design.png)

* **Tillåtna typer/storlekar för författare**  - Aktivera eller inaktivera rubriktyper som är tillgängliga för innehållsförfattare när de använder titelkomponenten.
* **Standardtyp/storlek** - Definiera den rubriktyp som automatiskt tilldelas när en innehållsförfattare lägger till titelkomponenten på en sida.
* **Inaktivera länk** - Inaktivera stöd för länkar i titelkomponenten för att hindra innehållsförfattare från att länka från titlar.

>[!NOTE]
>
>Möjligheten att definiera en länk för titeln introducerades i version 2.2.0 av Core Components.

### Fliken Format {#styles-tab}

Title Component har stöd för AEM [Style System](/help/get-started/authoring.md#component-styling).
