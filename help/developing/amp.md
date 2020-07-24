---
title: AMP-stöd för kärnkomponenterna
description: Kärnkomponenterna har stöd för AMP - accelererade mobilsidor
translation-type: tm+mt
source-git-commit: 905096d909d4fbf624152ba3b5cbc1d80637245f
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 0%

---


# AMP-stöd för kärnkomponenterna {#amp-support}

Från och med [version 2.11.0](/help/versions.md) av kärnkomponenterna stöds [AMP - Accelererade mobilsidor](https://developers.google.com/amp) - fullt ut.

Det här dokumentet ger en översikt över hur AMP stöds och hur du aktiverar det för dina webbplatser. Fullständig teknisk information finns dock i dokumentationen för [GitHub-utvecklaren.](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)

## Vad är AMP? {#what-is-amp}

Accelerated Mobile Pages eller AMP är ett ramverk med öppen källkod som ursprungligen designats av Google för att optimera sidor för mobilsurfning. AMP-sidor läser vanligtvis in mycket snabbare än standardwebbsidor, vilket ger bättre mobilupplevelser.

## AMP i kärnkomponenterna {#amp-in-core-components}

Stöd för AMP i Core Components är [fullt konfigurerbart.](#enabling-amp) AMP-versioner av sidor kan hanteras exklusivt, tillsammans med HTML-standardversionerna, eller inte alls.

Core Components använder `amp` som Sling-väljare för att återge en AMP-sida. Det `example.html` skulle till exempel återge den normala sidan och `example.amp.html` vara AMP-versionen.

### Krav {#requirements}

När du använder AMP med kärnkomponenterna är den största skillnaden att AMP kräver att alla CSS är inbäddade i `<head>` elementet samt optimerade.

Som stöd för detta används en anpassad sidkomponent, som bara läser in den AMP-specifika CSS:en för komponenter som finns på sidan.

Mer information om krav och teknisk information finns i dokumentationen för [GitHub-utvecklaren.](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)

### Använda AMP i kärnkomponenterna {#using-amp}

Enskilda projekt kan avgöra om de ska utnyttja AMP eller inte. Eftersom AMP- och standard-HTML-sidor kan levereras parallellt kan ett projekt välja att använda AMP endast på vissa sidor i projektet.

### Installerar stöd för AMP {#installing-amp}

Eftersom AMP är valfritt levereras det som ett tillägg till kärnkomponenterna.

* För AEM som Cloud Service-projekt är tillägget automatiskt tillgängligt.
* För anläggningsprojekt och AMS-projekt måste tillägget vara explicit installerat när du installerar Core Components.

När tillägget har installerats måste komponentförfattaren helt enkelt peka komponentens supertyper mot dem i tillägget.

### Aktivera AMP för sidor {#enabling-amp}

Om du vill aktivera AMP för en sida måste **AMP-läget** väljas i [Sidprofil.](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/siteandpage/templates.html#editingatemplatepagepolicies)

![Alternativ för AMP-sidprofil](/help/assets/amp-policy.png)

* **Ingen AMP** - Sidan levereras endast som standard-HTML.
* **Parade AMP** - Sidan levereras som både AMP och HTML.
* **Endast** AMP - Sidan levereras endast som AMP.

AMP-inställningarna för en sida kan också åsidosättas i [Sidegenskaper](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/authoring/editing-page-properties.html) för en enskild sida.

![Egenskaper för AMP-sida](/help/assets/amp-page-properties.png)

* **Ärv från sidmall** - Det här är standardvärdet, som gör att inställningen kan hämtas från sidmallens princip.
* **Ingen AMP** - Sidan levereras endast som standard-HTML.
* **Parade AMP** - Sidan levereras som både AMP och HTML.
* **Endast** AMP - Sidan levereras endast som AMP.
