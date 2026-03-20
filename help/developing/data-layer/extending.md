---
title: Utöka Adobe klientdatalager
description: Adobe-klientdatalagret kan utökas efter vissa grundläggande mönster
feature: Core Components, Adobe Client Data Layer
role: Developer, Admin
exl-id: f3d5555b-4f08-49de-ab0f-dc0fb04aadf8
source-git-commit: 7ba1374bd64686c2e7ac44398d77fb187ff60949
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 0%

---

# Utöka Adobe klientdatalager {#extending-acdl}

Du kan utöka kärnkomponenterna med anpassade dialogrutealternativ som gör att innehållsförfattare kan ange ytterligare information om datalagret.

Om du vill ta med de här fälten i datalagret som tillhandahålls av kärnkomponenterna, måste du utöka komponentmodellen som implementerar sina egna speciella datalagermetoder.

## Exempel: Rubrikkomponent {#example}

En kärnkomponent som [Title-komponenten](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java) utökar [Component](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java) som har en `getData` -metod som som returnerar [`ComponentData` som standard.](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/datalayer/ComponentData.java)

`ComponentData` serialiserar fördefinierade fält som din komponent kan implementera, som `getDataLayerLinkUrl` och `getDataLayerTitle` för [`TitleImpl`.](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/internal/models/v1/TitleImpl.java)

Därför kan din anpassade Sling-modell ha en `getData`-metod som returnerar ett objekt som utökar `ComponentData` för att returnera fler fält.

Då läggs ett `data-cmp-data-layer`-attribut till i HTML-elementet för komponenten med JSON för data som ska fyllas i i datalagret. Nu kan du implementera skript som lyssnar på dessa data eller relaterade händelser.

>[!TIP]
>
>Om du vill utforska datalagrets flexibilitet ytterligare kan du granska integreringsalternativen, inklusive hur du aktiverar datalagret för dina anpassade komponenter.
