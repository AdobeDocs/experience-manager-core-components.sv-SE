---
title: Utöka datalagret för klienten Adobe
description: Adobe-klientdatalagret kan utökas efter vissa grundläggande mönster
feature: Kärnkomponenter, Adobe-klientdatalager
role: Arkitekt, utvecklare, administratör
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 0%

---


# Utöka datalagret för klienten i Adobe {#extending-acdl}

Du kan utöka kärnkomponenterna med anpassade dialogrutealternativ som gör att innehållsförfattare kan ange ytterligare information om datalagret.

Om du vill ta med de här fälten i datalagret som tillhandahålls av kärnkomponenterna, måste du utöka komponentmodellen som implementerar sina egna speciella datalagermetoder.

## Exempel: Titelkomponent {#example}

En kärnkomponent som [Title-komponenten](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java) utökar [komponenten](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java) som har en `getData`-metod som returnerar [`ComponentData` som standard.](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/datalayer/ComponentData.java)

`ComponentData` serialiserar fördefinierade fält som din komponent kan implementera, precis som  `getDataLayerLinkUrl` och  `getDataLayerTitle` för  [`TitleImpl`.](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/internal/models/v1/TitleImpl.java)

Därför kan din anpassade Sling-modell ha en `getData`-metod som returnerar ett objekt som utökar `ComponentData` för att returnera fler fält.

Då läggs ett `data-cmp-data-layer`-attribut till i HTML-elementet för komponenten med JSON för data som ska fyllas i i datalagret. Nu kan du implementera skript som lyssnar på dessa data eller relaterade händelser.

>[!TIP]
>
>Om du vill utforska datalagrets flexibilitet ytterligare kan du granska integreringsalternativen, inklusive hur du aktiverar datalagret för dina anpassade komponenter.
