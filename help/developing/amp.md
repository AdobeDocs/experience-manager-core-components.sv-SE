---
title: AMP-stöd för kärnkomponenterna
description: Kärnkomponenterna har stöd för AMP - accelererade mobilsidor
role: Architect, Developer, Administrator
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 0%

---


# AMP-stöd för kärnkomponenterna {#amp-support}

Från och med [version 2.11.0](/help/versions.md) av kärnkomponenterna stöds [AMP - Accelererade mobilsidor](https://developers.google.com/amp) fullt ut.

Det här dokumentet ger en översikt över hur AMP stöds och hur du aktiverar det för dina webbplatser. Fullständig teknisk information finns dock i dokumentationen för [GitHub-utvecklaren.](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)

## Vad är AMP? {#what-is-amp}

Accelerated Mobile Pages eller AMP är ett ramverk med öppen källkod som ursprungligen designats av Google för att optimera sidor för mobilsurfning. AMP-sidor läser vanligtvis in mycket snabbare än standardwebbsidor, vilket ger bättre mobilupplevelser.

## AMP i kärnkomponenterna {#amp-in-core-components}

Stöd för AMP i Core Components är [fullt konfigurerbart.](#enabling-amp) AMP-versioner av sidor kan hanteras exklusivt, tillsammans med HTML-standardversionerna, eller inte alls.

Core Components använder `amp` som en Sling-väljare för att återge en AMP-sida. `example.html` skulle till exempel återge den normala sidan och `example.amp.html` skulle vara AMP-versionen.

Enskilda projekt kan avgöra om de ska utnyttja AMP eller inte. Eftersom AMP- och standard-HTML-sidor kan levereras parallellt kan ett projekt välja att använda AMP endast på vissa sidor i projektet.

## Komma igång med AMP-stöd i ditt projekt {#getting-started}

AMP-stödet ger stor flexibilitet, men för att komma igång snabbt krävs bara några få enkla steg:

1. Installera AMP-supporttillägget om det behövs.
   * För AEM som Cloud Service-projekt är tillägget automatiskt tillgängligt med kärnkomponenterna och ingen installation behövs.
   * För anläggningsprojekt och AMS-projekt måste tillägget vara explicit installerat när du installerar Core Components.
1. När AMP-tillägget har installerats måste komponentförfattaren helt enkelt peka komponentens supertyper mot dem i tillägget.
1. [Aktivera AMP-](#enabling-amp) stöd på mallnivå eller på enskilda sidor.
1. [Distribuera infogad ](#css-requirements) CSS efter behov.

### Aktivera AMP för sidor {#enabling-amp}

Om du vill aktivera AMP för en sida måste du välja **AMP-läge** i [sidprincipen.](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html#editing-a-template-page-policy-template-author-developer)

![Alternativ för AMP-sidprofil](/help/assets/amp-policy.png)

* **Ingen AMP**  - Sidan levereras endast som standard-HTML.
* **Parade AMP**  - Sidan levereras som både AMP och HTML.
* **Endast**  AMP - Sidan levereras endast som AMP.

AMP-inställningarna för en sida kan också åsidosättas i [Sidegenskaper](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html) för en enskild sida.

![Egenskaper för AMP-sida](/help/assets/amp-page-properties.png)

* **Ärv från sidmall**  - Det här är standardvärdet, som gör att inställningen kan hämtas från sidmallens princip.
* **Ingen AMP**  - Sidan levereras endast som standard-HTML.
* **Parade AMP**  - Sidan levereras som både AMP och HTML.
* **Endast**  AMP - Sidan levereras endast som AMP.

### CSS-krav {#css-requirements}

När du använder AMP med Core Components är den största skillnaden att AMP kräver att alla [CSS är infogade](including-clientlibs.md#inlining) i `<head>`-elementet samt optimerade.

Som stöd för detta används en anpassad sidkomponent, som bara läser in den AMP-specifika CSS:en för komponenter som finns på sidan.

>[!NOTE]
>
>På grund av begränsningar i AMP-design stöder inte Adobe användning av det responsiva rutnätet med AMP-versionen av din sida.

Mer information om krav och teknisk information finns i dokumentationen för [GitHub-utvecklaren.](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)
