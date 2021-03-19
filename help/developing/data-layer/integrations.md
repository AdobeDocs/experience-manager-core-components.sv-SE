---
title: Integreringar och Adobe Client Data Layer
description: Lär dig hur Adobe Client Data Layer kan integreras med dina anpassade komponenter och hur integreringar med Adobe Analytics och Adobe Target kan hjälpa dig att få insikter om din webbplats
feature: Kärnkomponenter, Adobe-klientdatalager
role: Arkitekt, utvecklare, administratör
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 0%

---


# Integrering med Adobe-klientdatalagret {#integrations}

Adobe Client Data Layer minskar arbetet med att instrumentera webbplatser genom att tillhandahålla en standardiserad metod för att visa och få tillgång till alla typer av data för alla typer av skript.

Adobe Client Data Layer kan integreras med era anpassade komponenter och integreringar med Adobe Analytics och Adobe Target för att ge er insikter om er webbplats.

## Aktivera datalagret för anpassade komponenter {#enabling-custom-components}

Så här lägger du automatiskt till en anpassad komponent i datalagret:

1. Definiera egenskaperna för den anpassade komponentmodellen som behöver spåras.
1. Lägg till attributet `data-cmp-data-layer` i den anpassade komponentens HTML-kod. T.ex. `data-cmp-data-layer="${mycomponent.data.json}"`.

Om du automatiskt vill att datalagret ska utlösa en `cmp:click`-händelse varje gång någon klickar på ett visst element i den anpassade komponenten, lägger du till attributet `data-cmp-clickable` till elementet som ska spåras i den anpassade komponentens HTML.

Attributet `data-cmp-data-layer-enabled` kan efterfrågas på klientsidan för att kontrollera om datalagret är aktiverat.

>[!TIP]
>
>Mer teknisk information om integreringen av Adobe Client Data Layer med Core Components och om hur du aktiverar datalagret för dina anpassade komponenter finns i filen [`DATA_LAYER_INTEGRATION.md`](https://github.com/adobe/aem-core-wcm-components/blob/master/DATA_LAYER_INTEGRATION.md) i Core Components-databasen.

## Integrera med Adobe Analytics och Adobe Target {#analytics-target}

Tillsammans med Adobe Analytics och Adobe Target är Adobe Client Data Layer grunden till ett mycket kraftfullt och flexibelt verktyg för att få insikter i era digitala upplevelser. Följande självstudiekurser leder dig genom exempelintegreringar.

### Samla in siddata med Adobe Analytics {#collect-page-data}

Lär dig använda de inbyggda funktionerna i Adobe Client Data Layer med AEM Core Components för att samla in data om en sida i Adobe Experience Manager Sites. Experience Platform Launch och Adobe Analytics kommer att användas för att skapa regler för att skicka siddata till Adobe Analytics.

[Se självstudiekursen här.](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/integrations/analytics/collect-data-analytics.html)

### Spåra komponenter som klickats med Adobe Analytics {#track-clicked-components}

Använd det händelsestyrda Adobe Client Data Layer med AEM Core Components för att spåra klick på specifika komponenter på en Adobe Experience Manager-plats. Lär dig hur du använder regler i Experience Platform Launch för att lyssna efter klickhändelser, filtrera efter komponent och skicka data till en Adobe Analytics med en spårlänkssignal.

[Se självstudiekursen här.](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/integrations/analytics/track-clicked-component.html)
