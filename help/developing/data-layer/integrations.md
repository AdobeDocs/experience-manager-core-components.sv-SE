---
title: Integreringar och Adobe Client Data Layer
description: Lär dig hur Adobe Client Data Layer kan integreras med dina anpassade komponenter och hur integreringar med Adobe Analytics och Adobe Target kan hjälpa dig att få insikter om din webbplats
translation-type: tm+mt
source-git-commit: ea7a0e08ea1b769b400fce275c8ce7e0db6f9407
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 0%

---


# Integrering med Adobe Client Data Layer {#integrations}

Adobe Client Data Layer minskar arbetet med att instrumentera webbplatser genom att tillhandahålla en standardiserad metod för att visa och få tillgång till alla typer av data för alla typer av skript.

Adobe Client Data Layer kan integreras med era anpassade komponenter och integreringar med Adobe Analytics och Adobe Target för att ge er insikter om er webbplats.

## Aktivera datalagret för anpassade komponenter {#enabling-custom-components}

Så här lägger du automatiskt till en anpassad komponent i datalagret:

1. Definiera egenskaperna för den anpassade komponentmodellen som behöver spåras.
1. Lägg till `data-cmp-data-layer` attributet i den anpassade komponentens HTML-kod. T.ex. `data-cmp-data-layer="${mycomponent.data.json}"`.

Om du automatiskt vill att datalagret ska utlösa en `cmp:click` händelse varje gång du klickar på ett visst element i den anpassade komponenten, lägger du till `data-cmp-clickable` attributet i elementet som ska spåras i den anpassade komponentens HTML-kod.

Attributet kan efterfrågas på klientsidan för att kontrollera om datalagret är aktiverat. `data-cmp-data-layer-enabled`

>[!TIP]
>
>Mer teknisk information om integreringen av Adobe Client Data Layer med Core Components och om hur du aktiverar datalagret för dina anpassade komponenter finns i [`DATA_LAYER_INTEGRATION.md`](https://github.com/adobe/aem-core-wcm-components/blob/master/DATA_LAYER_INTEGRATION.md) filen i Core Components-databasen.

## Integrera med Adobe Analytics och Adobe Target {#analytics-target}

Tillsammans med Adobe Analytics och Adobe Target är Adobe Client Data Layer grunden till ett mycket kraftfullt och flexibelt verktyg för att få insikter i era digitala upplevelser. Följande självstudiekurser leder dig genom exempelintegreringar.

### Samla in siddata med Adobe Analytics {#collect-page-data}

Lär dig använda de inbyggda funktionerna i Adobe Client Data Layer med AEM Core Components för att samla in data om en sida i Adobe Experience Manager Sites. Experience Platform Launch och Adobe Analytics kommer att användas för att skapa regler för att skicka siddata till Adobe Analytics.

[Se självstudiekursen här.](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/integrations/analytics/collect-data-analytics.html)

### Spåra komponenter som klickats med Adobe Analytics {#track-clicked-components}

Använd det händelsestyrda Adobe Client Data Layer med AEM Core Components för att spåra klick på specifika komponenter på en Adobe Experience Manager-plats. Lär dig hur du använder regler i Experience Platform Launch för att lyssna efter klickhändelser, filtrera efter komponent och skicka data till en Adobe Analytics med en spårlänkssignal.

[Se självstudiekursen här.](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/integrations/analytics/track-clicked-component.html)
