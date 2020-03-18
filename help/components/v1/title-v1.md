---
title: Titelkomponent (v1)
description: Komponenten Core Component Title är en avsnittsrubrikkomponent med redigering på plats.
index: n
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# Titelkomponent (v1) {#title-component-v}

Komponenten Core Component Title är en avsnittsrubrikkomponent med redigering på plats.

## Användning {#usage}

Titelkomponenten är avsedd att användas som rubrik eller rubrik för ett avsnitt i innehållet.

De tillgängliga rubriknivåerna kan definieras av mallskaparen i [designdialogrutan](#design-dialog). Innehållsredigeraren kan välja bland tillgängliga rubriknivåer i [redigeringsdialogrutan](#edit-dialog). För att underlätta redigeringen av rubriktexten är det också enkelt att redigera texten på plats.

## Version och kompatibilitet {#version-and-compatibility}

I det här dokumentet beskrivs v1 i Title Component, som ursprungligen introducerades i version 1.0.0 av Core Components med AEM 6.3.

I följande tabell visas kompatibiliteten för v1 för komponenten Title.

| AEM-version | Titelkomponent v1 |
|--- |--- |
| 6.3 | Kompatibel |
| 6.4 | Kompatibel |

>[!CAUTION]
>
>Det här dokumentet beskriver version 1 av komponenten Title.
>
>Mer information om den aktuella versionen av komponenten Title finns i [dokumentet Title Component](/help/components/title.md) (Rubrikkomponent).

## Exempel på komponentutdata {#sample-component-output}

Följande är ett exempel från [We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

### Skärmbild {#screenshot}

![](/help/assets/chlimage_1-36.png)

### HTML {#html}

```
<div class="cmp cmp-title aem-GridColumn aem-GridColumn--default--12">
     <h2>Welcome! This is our finest equipment!</h2>
</div>
```

### JSON {#json}

```
"title": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              ":type": "weretail/components/content/title",
              "jcr:title": "Welcome! This is our finest equipment!",
              "type": "h2"
            }
```

>[!NOTE]
>
>JSON-export från Core Components kräver version 1.1.0 av Core Components. Mer information finns i [kompatibilitetsinformationen för Core Components v1](/help/versions.md) .

## Dialogrutan Redigera {#edit-dialog}

I redigeringsdialogrutan kan innehållsförfattaren definiera titeltexten och välja rubriknivå.

>[!NOTE]
>
>Om du anger ett tomt värde för titeln visas sidans titel.

![](/help/assets/chlimage_1-91.png)

Du kan även använda redigeraren på plats för att redigera texten i titelkomponenten.

![](/help/assets/chlimage_1-37.png)

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera den standardrubriknivå som titelkomponenter ska ha när de skapas av innehållsförfattarna.

![](/help/assets/chlimage_1-92.png)

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Title Component [finns på GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/title/v1/title).

Hela kärnkomponentprojektet kan laddas ned från GitHub.

Mer information om hur du utvecklar kärnkomponenter finns i dokumentationen till [Core Components Developer](/help/developing/overview.md).
