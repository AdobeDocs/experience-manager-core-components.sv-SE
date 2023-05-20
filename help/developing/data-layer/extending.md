---
title: Utöka datalagret för klienten Adobe
description: Adobe-klientdatalagret kan utökas efter vissa grundläggande mönster
feature: Core Components, Adobe Client Data Layer
role: Architect, Developer, Admin
exl-id: f3d5555b-4f08-49de-ab0f-dc0fb04aadf8
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 0%

---

# Utöka datalagret för klienten Adobe {#extending-acdl}

Du kan utöka kärnkomponenterna med anpassade dialogrutealternativ som gör att innehållsförfattare kan ange ytterligare information om datalagret.

Om du vill ta med de här fälten i datalagret som tillhandahålls av kärnkomponenterna, måste du utöka komponentmodellen som implementerar sina egna speciella datalagermetoder.

## Exempel: Titelkomponent {#example}

En kärnkomponent som [Titelkomponent](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java) extends [Komponent](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java) som har `getData` metod som returnerar som standard [`ComponentData`.](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/datalayer/ComponentData.java)

`ComponentData` serialiserar fördefinierade fält som komponenten kan implementera, som `getDataLayerLinkUrl` och `getDataLayerTitle` för [`TitleImpl`.](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/internal/models/v1/TitleImpl.java)

Därför kan din anpassade Sling-modell ha en `getData` metod som returnerar ett objekt som utökas `ComponentData` för att returnera fler fält.

Om du gör det lägger du till en `data-cmp-data-layer` -attributet till elementet HTML i komponenten med JSON för de data som ska fyllas i till datalagret. Nu kan du implementera skript som lyssnar på dessa data eller relaterade händelser.

>[!TIP]
>
>Om du vill utforska datalagrets flexibilitet ytterligare kan du granska integreringsalternativen, inklusive hur du aktiverar datalagret för dina anpassade komponenter.
