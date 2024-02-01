---
title: Klientbibliotek och kärnkomponenter
description: Core Components har ett antal klientbibliotek och ger möjlighet att inkludera egna.
role: Architect, Developer, Admin
exl-id: 84e7c178-247b-42a2-99bf-6d1699ecee14
source-git-commit: d39fe0084522f67664203a026340b23d325c1883
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 0%

---


# Klientbibliotek och kärnkomponenter {#client-libraries}

Core Components har ett antal klientbibliotek och ger möjlighet att inkludera egna.

## Tillhandahållna klientbibliotek {#provided}

Core Components innehåller följande klientbibliotek som är färdiga.

* The **webbplats** clientlibs ger det minimala funktionsbeteendet hos de komponenter som ska användas på platsen.
   * De fungerar som en startpunkt för att snabba upp projekt, och implementeringarna uppmuntras att utöka och [anpassa dem](/help/developing/customizing.md) för att uppnå önskat utseende och önskad funktionalitet.
* The **redigerare** clientlibs används i redigeringsdialogrutan för att säkerställa dess förväntade funktioner och utseende.
* The **editorkrok** Klientlibs används på platsen när den läses in i redigeringsläge.
   * De innehåller JavaScript-kod som körs på händelser som utlöses av redigerare, vilket underlättar initieringen av dynamiska funktioner.
* Vissa komponenter kan ha särskilda extra klientlibs som är utformade för användning i särskilda situationer, som när de används tillsammans med [Dynamic Media](/help/components/image.md#dynamic-media) till exempel.

## Inkluderar klientbibliotek {#including}

Det finns flera olika sätt att inkludera [klientbibliotek](/help/developing/archetype/front-end.md#clientlibs) beroende på ditt användningssätt. Följande är exempel med exempel [HTML-kodfragment](https://experienceleague.adobe.com/docs/experience-manager-htl/using/overview.html) for each.

### Rekommenderad standardanvändning {#recommended-default-usage}

Om du inte har tid att undersöka vad som är bäst i din situation kan du inkludera dina klientbibliotek genom att placera följande HTML-rader på sidan `head` element:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories='wknd.base', defer=true}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

Detta inkluderar både CSS och JS på sidan `head`, men lägger till `defer` attribut till din JS `script` inkluderar, så att webbläsarna väntar på att DOM ska vara klar innan skripten körs och därför optimerar sidans inläsningshastighet.

### Grundläggande användning {#basic-usage}

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

### Endast CSS eller JS {#css-js-only}

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

### Attribut {#attributes}

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

### Inledande {#inlining}

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

### Läsa in sammanhangsberoende CSS och JavaScript {#context-aware-loading}

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
