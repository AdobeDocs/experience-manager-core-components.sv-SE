---
title: Inkluderar klientbibliotek
description: Det finns flera olika sätt att inkludera klientbibliotek beroende på hur du använder dem.
translation-type: tm+mt
source-git-commit: 24f718be2ba66113eda970c213c6ce4baec51752
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 3%

---


# Inkluderar klientbibliotek {#including-client-libraries}

Det finns flera olika sätt att inkludera [klientbibliotek](/help/developing/archetype/uifrontend.md#clientlibs) beroende på hur du använder dem. Det här dokumentet innehåller exempel och exempel på [HTML-kodfragment](https://docs.adobe.com/content/help/en/experience-manager-htl/using/overview.html) för varje.

## Rekommenderad standardanvändning {#recommended-default-usage}

Om du inte har tid att ta reda på vad som är bäst i din situation kan du inkludera dina klientbibliotek genom att placera följande HTML-rader i sidelementet `head` :

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories='wknd.base', defer=true}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

Detta inkluderar både CSS och JS på sidan, `head`men om du lägger till `defer` attributet i JS- `script` inkluderingen, så att webbläsarna väntar på att DOM ska vara klar innan skripten körs och därmed optimerar sidans inläsningshastighet.

## Grundläggande användning {#basic-usage}

Grundsyntaxen för att inkludera både JS och CSS i en klientbibliotekskategori, som genererar alla motsvarande CSS- `link` element och/eller JS- `script` element, är följande:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

Om du vill göra samma sak för flera klientbibliotekskategorier samtidigt kan en array med strängar skickas till `categories` parametern:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories=['wknd.base', 'cq.foundation']}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

## Endast CSS eller JS {#css-js-only}

Ofta vill man placera CSS-inkluderingarna i HTML- `head` elementet, och JS-elementet inkluderar precis innan `body` elementet stängs.
&#x200B;
Om du bara vill ta med CSS `head`i , och inte JS, använder du `cssIncludes`:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.cssIncludes @ context="unsafe"}
</sly>
```

Innan du stänger ska du `body` använda `jsIncludes`:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsIncludes @ context="unsafe"}
</sly>
```

## Attribut {#attributes}

Om du vill använda attribut på de genererade CSS- `link` elementen och/eller JS- `script` elementen kan du ange ett antal parametrar:

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

CSS- `link` attribut som kan skickas till `jsAndCssIncludes` och `cssIncludes`:

* `media`: sträng &#x200B; JS- `script` attribut som kan skickas till `jsAndCssIncludes` och `jsIncludes`:

* `async`: boolean
* `defer`: boolean
* `onload`: string
* `crossorigin`: string

## Inledande {#inlining}

I vissa fall, antingen för optimering eller för e-post eller [AMP,](amp.md) kan det vara nödvändigt att infoga CSS eller JS i HTML-utdata.
&#x200B;
Om du vill infoga CSS:en kan `cssInline` användas. I så fall måste du skriva det omgivande `style` elementet:

```html
<style type="text/css"
    data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.cssInline @ context="unsafe"}
</style>
```

Om du vill infoga JS-elementet kan du också använda `jsInline` . I så fall måste du skriva det omgivande `script` elementet:

```html
<script type="text/javascript"
    data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsInline @ context="unsafe"}
</script>
```