---
title: Titelkomponent
description: Komponenten Core Component Title är en avsnittsrubrikkomponent med redigering på plats.
role: Architect, Developer, Admin, User
exl-id: 393af72c-549f-4609-afb0-2712f827b549
source-git-commit: dd30def59a8f037864da875ef4c831b11f766e57
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 0%

---


# Titelkomponent{#title-component}

Komponenten Core Component Title är en avsnittsrubrikkomponent med redigering på plats.

{{traditional-aem}}

## Användning {#usage}

Titelkomponenten är avsedd att användas som rubrik eller rubrik för ett avsnitt i innehållet. De tillgängliga rubriknivåerna kan definieras av mallskaparen i [designdialogrutan](#design-dialog). Innehållsredigeraren kan välja bland tillgängliga rubriknivåer i dialogrutan [Redigera](#edit-dialog). För att underlätta redigeringen av rubriktexten är det också enkelt att redigera texten på plats.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Title Component är v3, som introducerades i version 2.18.0 av Core Components i februari 2022, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponenterna är kompatibla med samt länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|---|---|---|---|---|
| v3 | - | Kompatibel | Kompatibel | Kompatibel |
| [v2](v2/title.md) | Kompatibel | Kompatibel | - | Kompatibel |
| [v1](v1/title-v1.md) | Kompatibel | Kompatibel | - | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill se både Title Component (Rubrik-komponenten) och exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [Component Library](https://adobe.com/go/aem_cmp_library_title).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Title Component [finns på GitHub](https://adobe.com/go/aem_cmp_tech_title_v3).

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).

## Dialogrutan Redigera {#edit-dialog}

I redigeringsdialogrutan kan innehållsförfattaren definiera titeltexten och välja rubriknivå.

* **Rubrik** - Om den är tom används sidtiteln
* **Typ / Storlek** - Definierar rubriknivån för titeln
* **Länk** - Definierar innehållet som titeln ska länka till. Det kan vara en sökväg till en innehållssida, en extern URL eller en sidankarpunkt.
* **Öppna länk på ny flik** - När det här alternativet är markerat öppnas länken på en ny flik i webbläsaren.
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [datalagret](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

![Redigeringsdialogrutan för titelkomponent](/help/assets/title-edit.png)

Du kan även använda redigeraren på plats för att redigera texten i titelkomponenten.

![Redigering på plats av titelkomponent](/help/assets/title-edit-inline.png)

### Fliken Format {#styles-tab-edit}

Title Component har stöd för AEM [Style System.](/help/get-started/authoring.md#component-styling).

Använd listrutan för att välja de format som du vill använda på komponenten. Markeringar som görs i redigeringsdialogrutan har samma effekt som de som väljs i komponentverktygsfältet.

Format måste konfigureras för den här komponenten i [designdialogrutan](#design-dialog) för att den nedrullningsbara menyn ska vara tillgänglig.

![Fliken Format i redigeringsdialogrutan för titelkomponent](/help/assets/title-edit-styles.png)

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera den standardrubriknivå som titelkomponenter ska ha när de skapas av innehållsförfattarna.

### Fliken Storlekar {#sizes-tab}

![Utformningsdialogrutan för titelkomponenten](/help/assets/title-design.png)

* **Tillåtna typer/storlekar för författare** - Aktivera eller inaktivera rubriktyper som är tillgängliga för innehållsförfattare när de använder titelkomponenten.
* **Standardtyp/Standardstorlek**- Definiera den rubriktyp som automatiskt tilldelas när en innehållsförfattare lägger till titelkomponenten på en sida.
* **Inaktivera länk**- Inaktivera stöd för länkar i titelkomponenten så att innehållsförfattare inte kan länka från titlar.

### Fliken Format {#styles-tab}

Title Component har stöd för AEM [Style System](/help/get-started/authoring.md#component-styling).

## Adobe Client Data Layer {#data-layer}

Titelkomponenten stöder [Adobe-klientdatalagret.](/help/developing/data-layer/overview.md)
