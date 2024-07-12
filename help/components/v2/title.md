---
title: Titelkomponent (v2)
description: Komponenten Core Component Title är en avsnittsrubrikkomponent med redigering på plats.
role: Architect, Developer, Admin, User
exl-id: f853ec46-19fd-4569-a9d3-5c376d2a2101
source-git-commit: e291d4c1bfd37292d68c236178f9681c4e5ee741
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 0%

---

# Titelkomponent (v2) {#title-component}

Komponenten Core Component Title är en avsnittsrubrikkomponent med redigering på plats.

## Användning {#usage}

Titelkomponenten är avsedd att användas som rubrik eller rubrik för ett avsnitt i innehållet. De tillgängliga rubriknivåerna kan definieras av mallskaparen i [designdialogrutan](#design-dialog). Innehållsredigeraren kan välja bland tillgängliga rubriknivåer i dialogrutan [Redigera](#edit-dialog). För att underlätta redigeringen av rubriktexten är det också enkelt att redigera texten på plats.

## Version och kompatibilitet {#version-and-compatibility}

I det här dokumentet beskrivs v2 av Title Component, som introducerades i version 2.0.0 av Core Components i januari 2018.

>[!CAUTION]
>
>Det här dokumentet beskriver v2 för komponenten Title.
>
>Mer information om den aktuella versionen av komponenten Title finns i dokumentet [Title Component](/help/components/title.md) (Rubrikkomponent).

## Exempel på komponentutdata {#sample-component-output}

Om du vill se både komponenten Title och exempel på dess konfigurationsalternativ samt HTML och JSON-utdata, går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_title).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Title Component [finns på GitHub](https://adobe.com/go/aem_cmp_tech_title_v2).

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).

## Dialogrutan Redigera {#edit-dialog}

I redigeringsdialogrutan kan innehållsförfattaren definiera titeltexten och välja rubriknivå.

* **Rubrik** - Om den är tom används sidtiteln
* **Typ / Storlek** - Definierar rubriknivån för titeln
* **Länk** - Definierar innehållet som titeln ska länka till. Det kan vara en sökväg till en innehållssida, en extern URL eller en sidankarpunkt.
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [datalagret](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

![Redigeringsdialogrutan för titelkomponent](/help/assets/title-edit.png)

>[!NOTE]
>
>Möjligheten att definiera en länk för titeln introducerades i version 2.2.0 av Core Components.

Du kan även använda redigeraren på plats för att redigera texten i titelkomponenten.

![Redigering på plats av titelkomponent](/help/assets/title-edit-inline.png)

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera den standardrubriknivå som titelkomponenter ska ha när de skapas av innehållsförfattarna.

### Fliken Storlekar {#sizes-tab}

![Utformningsdialogrutan för titelkomponenten](/help/assets/title-design.png)

* **Tillåtna typer/storlekar för författare** - Aktivera eller inaktivera rubriktyper som är tillgängliga för innehållsförfattare när de använder titelkomponenten.
* **Standardtyp/Standardstorlek**- Definiera den rubriktyp som automatiskt tilldelas när en innehållsförfattare lägger till titelkomponenten på en sida.
* **Inaktivera länk**- Inaktivera stöd för länkar i titelkomponenten så att innehållsförfattare inte kan länka från titlar.

>[!NOTE]
>
>Möjligheten att definiera en länk för titeln introducerades i version 2.2.0 av Core Components.

### Fliken Format {#styles-tab}

Titelkomponenten stöder AEM [Style System](/help/get-started/authoring.md#component-styling).

## Adobe-klientdatalager {#data-layer}

Titelkomponenten stöder datalagret [Adobe Client.](/help/developing/data-layer/overview.md)
