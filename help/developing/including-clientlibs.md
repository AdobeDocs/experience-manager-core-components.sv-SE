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

* Klientlibs för **platsen** tillhandahåller det minimala funktionsbeteendet för komponenterna som ska tillämpas på platsen.
   * De fungerar som en startpunkt för att snabba upp projekt, och implementeringar uppmuntras att utöka och [anpassa dem](/help/developing/customizing.md) för att få önskat utseende och önskad funktionalitet.
* Klientlibs för **redigeraren** används i redigeringsdialogrutan för att säkerställa den förväntade funktionen och utseendet.
* Klientlibs **editorch** används på webbplatsen när den läses in i redigeringsläge.
   * De innehåller JavaScript-kod som körs på händelser som triggas av redigerare, vilket underlättar initieringen av dynamiska funktioner.
* Vissa komponenter kan ha särskilda ytterligare klienten som är utformade för användning i vissa situationer, till exempel när de används tillsammans med [Dynamic Media](/help/components/image.md#dynamic-media).

## Inkluderar klientbibliotek {#including}

Det finns flera olika sätt att inkludera [klientbibliotek](/help/developing/archetype/front-end.md#clientlibs) beroende på ditt användningssätt. Följande är exempel med exempel på [HTML-fragment](https://experienceleague.adobe.com/docs/experience-manager-htl/using/overview.html) för varje.

### Rekommenderad standardanvändning {#recommended-default-usage}

Om du inte har tid att undersöka vad som är bäst i din situation kan du inkludera dina klientbibliotek genom att placera följande HTML-rader i sidelementet `head`:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories='wknd.base', defer=true}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

Detta inkluderar både CSS och JS på sidan `head`, men om du lägger till attributet `defer` i JS `script` -inkluderingarna så att webbläsarna väntar på att DOM ska vara klar innan skripten körs och därför optimerar sidans inläsningshastighet.

### Grundläggande användning {#basic-usage}

Grundläggande syntax för att inkludera både JS och CSS i en klientbibliotekskategori, som genererar alla motsvarande CSS `link`-element och/eller JS `script` -element, är följande:

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

### Endast CSS eller JS {#css-js-only}

Ofta vill man montera CSS-elementet i elementet `head`, och JS-elementet inkluderar precis före stängningen av elementet `body`.

I `head` använder du `cssIncludes` om du bara vill inkludera CSS, och inte JS:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.cssIncludes @ context="unsafe"}
</sly>
```

Använd `jsIncludes` före stängningen av `body` om du bara vill inkludera JS, och inte CSS:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsIncludes @ context="unsafe"}
</sly>
```

### Attribut {#attributes}

Om du vill använda attribut på de genererade CSS `link`-elementen och/eller JS `script` -elementen kan du ange ett antal parametrar:

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

* `media`: sträng-JS `script`-attribut som kan skickas till `jsAndCssIncludes` och `jsIncludes`:
* `async`: boolesk
* `defer`: boolesk
* `onload`: sträng
* `crossorigin`: sträng

### Inledande {#inlining}

I vissa fall, antingen för optimering eller för e-post eller [AMP](amp.md), kan det krävas att du infogar CSS eller JS i utdata från HTML.

Om du vill infoga CSS kan `cssInline` användas. I så fall måste du skriva det omgivande `style`-elementet:

```html
<style type="text/css"
    data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.cssInline @ context="unsafe"}
</style>
```

På samma sätt kan `jsInline` användas för att infoga JS, vilket innebär att du måste skriva det omgivande `script`-elementet:

```html
<script type="text/javascript"
    data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsInline @ context="unsafe"}
</script>
```

### Läsa in sammanhangsberoende CSS och JavaScript {#context-aware-loading}

Sidkomponenten [Page](/help/components/page.md) stöder även inläsning av utvecklardefinierade sammanhangsberoende CSS-, JavaScript- eller meta-taggar.

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
