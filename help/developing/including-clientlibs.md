---
title: Inkluderar klientbibliotek
description: Det finns flera olika sätt att inkludera klientbibliotek beroende på hur du använder dem.
role: Architect, Developer, Admin
exl-id: 84e7c178-247b-42a2-99bf-6d1699ecee14
source-git-commit: 39a5dee1666fa2645e0579fdfac0400f7fcbdc27
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 0%

---

# Inkluderar klientbibliotek {#including-client-libraries}

Det finns flera olika sätt att inkludera [klientbibliotek](/help/developing/archetype/front-end.md#clientlibs) beroende på ditt användningssätt. Det här dokumentet innehåller exempel och exempel [HTML-kodfragment](https://experienceleague.adobe.com/docs/experience-manager-htl/using/overview.html) for each.

## Rekommenderad standardanvändning {#recommended-default-usage}

Om du inte har tid att undersöka vad som är bäst i din situation kan du inkludera dina klientbibliotek genom att placera följande HTML-rader på sidan `head` element:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories='wknd.base', defer=true}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

Detta inkluderar både CSS och JS på sidan `head`, men lägger till `defer` attribut till din JS `script` inkluderar, så att webbläsarna väntar på att DOM ska vara klar innan skripten körs och därför optimerar sidans inläsningshastighet.

## Grundläggande användning {#basic-usage}

Den grundläggande syntaxen som inkluderar både JS och CSS för en klientbibliotekskategori, som genererar alla motsvarande CSS `link` element och/eller JS `script` -element, enligt följande:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

Om du vill göra samma sak för flera klientbibliotekskategorier samtidigt kan en array med strängar skickas till `categories` parameter:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories=['wknd.base', 'cq.foundation']}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

## Endast CSS eller JS {#css-js-only}

Ofta vill man placera CSS-inkluderingarna i HTML `head` -elementet och JS-elementet innehåller precis före stängningen av `body` -element.

I `head`, som bara innehåller CSS, och inte JS, använder du `cssIncludes`:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.cssIncludes @ context="unsafe"}
</sly>
```

Före `body` closing, to include only the JS, and not the CSS, use `jsIncludes`:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsIncludes @ context="unsafe"}
</sly>
```

## Attribut {#attributes}

Tillämpa attribut på den genererade CSS:en `link` element och/eller JS `script` -element kan du ange ett antal parametrar:

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

CSS `link` attribut som kan skickas till `jsAndCssIncludes` och `cssIncludes`:

* `media`: sträng-JS `script` attribut som kan skickas till `jsAndCssIncludes` och `jsIncludes`:
* `async`: boolesk
* `defer`: boolesk
* `onload`: string
* `crossorigin`: string

## Inledande {#inlining}

I vissa fall, antingen för optimering eller för e-post eller [AMP,](amp.md) det kan krävas att CSS eller JS infogas i utdata från HTML.

Om du vill infoga CSS:en `cssInline` kan användas, och då måste du skriva den omgivande `style` element:

```html
<style type="text/css"
    data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.cssInline @ context="unsafe"}
</style>
```

På samma sätt gäller att om du vill infoga JS, `jsInline` kan användas, och då måste du skriva den omgivande `script` element:

```html
<script type="text/javascript"
    data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsInline @ context="unsafe"}
</script>
```

## Läsa in sammanhangsberoende CSS och JavaScript {#context-aware-loading}

The [Sidkomponent](/help/components/page.md) har även stöd för inläsning av utvecklardefinierade sammanhangsberoende CSS-, JavaScript- eller metataggar.

Detta görs genom att skapa en [kontextmedveten resurs](context-aware-configs.md) for `com.adobe.cq.wcm.core.components.config.HtmlPageItemsConfig` med följande struktur:

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
