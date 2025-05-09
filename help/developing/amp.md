---
title: AMP-stöd för kärnkomponenterna
description: Kärnkomponenterna har stöd för AMP - accelererade mobilsidor
role: Architect, Developer, Admin
exl-id: 1fd9b6b5-0e4d-48c7-8faa-42e0d4a6bbd0
source-git-commit: 2ac16b15718128feefbe903e92f276b16fe96f69
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 0%

---

# AMP-stöd för kärnkomponenterna {#amp-support}

Från och med [version 2.11.0](/help/versions.md) av kärnkomponenterna stöds [AMP - accelererade mobilsidor](https://developers.google.com/amp) fullt ut.

Det här dokumentet ger en översikt över hur AMP stöds och hur du aktiverar det för dina webbplatser. Fullständig teknisk information finns dock i dokumentationen för [GitHub-utvecklaren.](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)

## Vad är AMP? {#what-is-amp}

Accelerated Mobile Pages eller AMP är ett ramverk med öppen källkod som ursprungligen utformats av Google för att optimera sidor för mobilsurfning. AMP-sidor läser vanligtvis in mycket snabbare än standardwebbsidor, vilket ger bättre mobilupplevelser.

## AMP i kärnkomponenterna {#amp-in-core-components}

Stöd för AMP i kärnkomponenterna är [fullt konfigurerbart.](#enabling-amp) AMP-versioner av sidor kan hanteras exklusivt, tillsammans med HTML-standardversionerna, eller inte alls.

Core Components använder `amp` som en Sling-väljare för att återge en AMP-sida. `example.html` skulle till exempel återge den normala sidan och `example.amp.html` skulle vara AMP-versionen.

Enskilda projekt kan avgöra om de ska utnyttja AMP eller inte. Eftersom AMP- och HTML-standardsidor kan levereras parallellt kan ett projekt välja att använda AMP endast på vissa sidor i projektet.

## Komma igång med AMP-stöd i ditt projekt {#getting-started}

AMP-stödet ger stor flexibilitet, men för att komma igång snabbt krävs bara några få enkla steg:

1. Installera AMP-supporttillägget om det behövs.
   * För AEM as a Cloud Service-projekt är tillägget automatiskt tillgängligt med kärnkomponenterna och ingen installation behövs.
   * För anläggningsprojekt och AMS-projekt måste tillägget vara explicit installerat när du installerar Core Components.
1. När AMP-tillägget har installerats måste komponentförfattaren helt enkelt peka komponentens supertyper mot dem i tillägget.
1. [Aktivera stöd för AMP](#enabling-amp) på mallnivå eller på enskilda sidor.
1. [Distribuera infogad CSS](#css-requirements) efter behov.

### Aktivera AMP för sidor {#enabling-amp}

Om du vill aktivera AMP för en sida måste **AMP-läget** väljas i [Sidprincipen.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=sv-SE#editing-a-template-page-policy-template-author-developer)

![Alternativ för AMP-sidprincip](/help/assets/amp-policy.png)

* **Ingen AMP** - Sidan levereras endast som HTML som standard.
* **Parade AMP** - Sidan levereras som både AMP och HTML.
* **Endast AMP** - Sidan levereras endast som AMP.

AMP-inställningarna för en sida kan också åsidosättas i [Sidegenskaper](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html?lang=sv-SE) för en enskild sida.

![Sidegenskaper för AMP](/help/assets/amp-page-properties.png)

* **Ärv från sidmall** - Det här är standardvärdet, vilket gör att inställningen kan hämtas från sidmallens princip.
* **Ingen AMP** - Sidan levereras endast som HTML som standard.
* **Parade AMP** - Sidan levereras som både AMP och HTML.
* **Endast AMP** - Sidan levereras endast som AMP.

### CSS-krav {#css-requirements}

När du använder AMP med kärnkomponenterna är den största skillnaden att AMP kräver att alla [CSS är infogade](including-clientlibs.md#inlining) i elementet `<head>` samt optimerade.

Som stöd för detta används en anpassad sidkomponent, som bara läser in den AMP-specifika CSS:en för komponenter som finns på sidan.

>[!NOTE]
>
>På grund av begränsningar i AMP-design stöder inte Adobe användning av det responsiva rutnätet med AMP-versionen av din sida.

Mer information om krav och teknisk information finns i dokumentationen för [GitHub-utvecklaren.](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)
