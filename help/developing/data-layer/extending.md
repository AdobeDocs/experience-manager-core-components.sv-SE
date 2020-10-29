---
title: Utöka datalagret för klienten Adobe
description: Adobe-klientdatalagret kan utökas efter vissa grundläggande mönster
translation-type: tm+mt
source-git-commit: 1ada05d5089ccef95d41d47468776654e397f31d
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 0%

---


# Utöka datalagret för klienten Adobe {#extending-acdl}

Du kan utöka kärnkomponenterna med anpassade dialogrutealternativ som gör att innehållsförfattare kan ange ytterligare information om datalagret.

Om du vill ta med de här fälten i datalagret som tillhandahålls av kärnkomponenterna, måste du utöka komponentmodellen som implementerar sina egna speciella datalagermetoder.

## Exempel: Titelkomponent {#example}

En Core-komponent som [Title-komponenten](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java) utökar [komponenten](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java) som har en `getData` metod som returnerar [`ComponentData`som standard.](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/datalayer/ComponentData.java)

`ComponentData` serialiserar fördefinierade fält som komponenten kan implementera, precis som `getDataLayerLinkUrl` och `getDataLayerTitle` för [`TitleImpl`.](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/internal/models/v1/TitleImpl.java)

Därför kan din anpassade Sling-modell ha en `getData` metod som returnerar ett objekt som utökas `ComponentData` för att returnera fler fält.

Då läggs ett attribut till i HTML-elementet för komponenten med JSON för de data som ska fyllas i i datalagret. `data-cmp-data-layer` Nu kan du implementera skript som lyssnar på dessa data eller relaterade händelser.

>[!TIP]
>
>Om du vill utforska datalagrets flexibilitet ytterligare kan du granska integreringsalternativen, inklusive hur du aktiverar datalagret för dina anpassade komponenter.
