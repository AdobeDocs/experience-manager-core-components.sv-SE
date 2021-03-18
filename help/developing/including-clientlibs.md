---
title: Inkluderar klientbibliotek
description: Det finns flera olika sätt att inkludera klientbibliotek beroende på hur du använder dem.
role: Arkitekt, utvecklare, administratör
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 2%

---


# Inkluderar klientbibliotek {#including-client-libraries}

Det finns flera olika sätt att inkludera [klientbibliotek](/help/developing/archetype/uifrontend.md#clientlibs) beroende på ditt användningssätt. Det här dokumentet innehåller exempel och exempel på [HTML-kodfragment](https://docs.adobe.com/content/help/en/experience-manager-htl/using/overview.html) för varje.

## Rekommenderad standardanvändning {#recommended-default-usage}

Om du inte har tid att undersöka vad som är bäst i din situation kan du inkludera dina klientbibliotek genom att placera följande HTML-rader i elementet `head` på sidan:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories='wknd.base', defer=true}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

Detta inkluderar både CSS och JS på sidan `head`, men om du lägger till attributet `defer` i dina JS `script`-inkluderingar så att webbläsarna väntar på att DOM ska vara klart innan skripten körs och därför optimerar sidans inläsningshastighet.

## Grundläggande användning {#basic-usage}

Grundläggande syntax för att inkludera både JS och CSS för en klientbibliotekskategori, som genererar alla motsvarande CSS `link`-element och/eller JS `script`-element, är följande:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

Om du vill göra samma sak för flera klientbibliotekskategorier samtidigt kan en array med strängar skickas till parametern `categories`:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories=['wknd.base', 'cq.foundation']}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

## Endast CSS eller JS {#css-js-only}

Ofta vill man placera CSS-inkluderingarna i HTML-elementet `head`, och JS-elementet inkluderar precis före stängningen av `body`-elementet.

Använd `cssIncludes` om du bara vill inkludera CSS, och inte JS, i `head`:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.cssIncludes @ context="unsafe"}
</sly>
```

Använd `jsIncludes` före `body`-stängningen om du bara vill ta med JS, och inte CSS:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsIncludes @ context="unsafe"}
</sly>
```

## Attribut {#attributes}

Om du vill använda attribut på de genererade CSS `link`-elementen och/eller JS `script`-elementen kan du ange ett antal parametrar:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories='wknd.base',
    media='print',
    async=true,
    defer=true,
    onload='console.log(\'loaded: \' + this.src)',
    crossorigin='anonymous'}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

CSS `link`-attribut som kan skickas till `jsAndCssIncludes` och `cssIncludes`:

* `media`: JS-strängattribut  `script` som kan skickas till  `jsAndCssIncludes` och  `jsIncludes`:
* `async`: boolean
* `defer`: boolesk
* `onload`: string
* `crossorigin`: string

## Infogar {#inlining}

I vissa fall, antingen för optimering eller för e-post eller [AMP,](amp.md), kan det krävas att infoga CSS eller JS i HTML-utdata.

Om du vill infoga CSS kan du använda `cssInline` och då måste du skriva det omgivande `style`-elementet:

```html
<style type="text/css"
    data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.cssInline @ context="unsafe"}
</style>
```

Om du vill infoga JS-elementet kan du använda `jsInline`. I så fall måste du skriva det omgivande `script`-elementet:

```html
<script type="text/javascript"
    data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsInline @ context="unsafe"}
</script>
```

## Läser in sammanhangsberoende CSS och JavaScript {#context-aware-loading}

[Sidkomponenten](/help/components/page.md) stöder även inläsning av utvecklardefinierade sammanhangsberoende CSS-, JavaScript- eller meta-taggar.

Detta görs genom att skapa en [kontextmedveten resurs](context-aware-configs.md) för `com.adobe.cq.wcm.core.components.config.HtmlPageItemsConfig` med följande struktur:

```text
com.adobe.cq.wcm.core.components.config.HtmlPageItemsConfig
    - prefixPath="/some/path"
    + item01
        - element=["link"|"script"|"meta"]
        - location=["header"|"footer"]
        + attributes
            - attributeName01="attributeValue01"
            - attributeName02="attributeValue02"
            ...
    + item02
        ...
    ...
```

[Mer information finns i den tekniska dokumentationen för sidkomponenten.](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/page/v2/page#loading-of-context-aware-cssjs)
