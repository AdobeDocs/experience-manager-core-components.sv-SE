---
title: Titelkomponent
description: Komponenten Core Component Title är en avsnittsrubrikkomponent med redigering på plats.
translation-type: tm+mt
source-git-commit: fe8a121520000ffd56ae3347469590e89121eaf0

---


# Titelkomponent{#title-component}

Komponenten Core Component Title är en avsnittsrubrikkomponent med redigering på plats.

## Användning {#usage}

Titelkomponenten är avsedd att användas som rubrik eller rubrik för ett avsnitt i innehållet. De tillgängliga rubriknivåerna kan definieras av mallskaparen i [designdialogrutan](#design-dialog). Innehållsredigeraren kan välja bland tillgängliga rubriknivåer i [redigeringsdialogrutan](#edit-dialog). För att underlätta redigeringen av rubriktexten är det också enkelt att redigera texten på plats.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Title Component är v2, som introducerades i version 2.0.0 av Core Components i januari 2018, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponentversionerna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|---|---|
| v2 | Kompatibel | Kompatibel | Kompatibel | Kompatibel |
| [v1](v1/title-v1.md) | Kompatibel | Kompatibel | Kompatibel | - |

Mer information om Core Component-versioner och -versioner finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill se både komponenten Title och exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata, går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_title).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Title Component [finns på GitHub](https://adobe.com/go/aem_cmp_tech_title_v2).

Mer information om hur du utvecklar kärnkomponenter finns i dokumentationen till [Core Components Developer](/help/developing/overview.md).

## Dialogrutan Redigera {#edit-dialog}

I redigeringsdialogrutan kan innehållsförfattaren definiera titeltexten och välja rubriknivå.

* **Titel** - Om den är tom används sidans rubrik
* **Typ/storlek** - definierar rubriknivån för titeln
* **Länk** - Definierar innehållet som titeln ska länka till. Det kan vara en sökväg till en innehållssida, en extern URL eller en sidankarpunkt.

![](/help/assets/screenshot_2018-10-19at110055.png)

>[!CAUTION]
>
>Möjligheten att definiera en länk för titeln introducerades i version 2.2.0 av Core Components.

Du kan även använda redigeraren på plats för att redigera texten i titelkomponenten.

![](/help/assets/chlimage_1-37.png)

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera den standardrubriknivå som titelkomponenter ska ha när de skapas av innehållsförfattarna.

### Fliken Storlekar {#sizes-tab}

![](/help/assets/screenshot_2018-10-19at110120.png)

* **Tillåtna typer/storlekar för författare** - Aktivera eller inaktivera rubriktyper som är tillgängliga för innehållsförfattare när de använder titelkomponenten.
* **Standardtyp/storlek**- Definiera den rubriktyp som automatiskt tilldelas när en innehållsförfattare lägger till titelkomponenten på en sida.
* **Inaktivera länk**- Inaktivera stöd för länkar i titelkomponenten för att hindra innehållsförfattare från att länka från titlar.

>[!CAUTION]
>
>Möjligheten att definiera en länk för titeln introducerades i version 2.2.0 av Core Components.

### Fliken Format {#styles-tab}

Title Component har stöd för AEM [Style System](/help/get-started/authoring.md#component-styling).
