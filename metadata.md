---
product: Adobe Experience Manager
description: Dokumentation för Adobe Experience Manager Core Components
git-repo: https://git.corp.adobe.com/AdobeDocs/experience-manager-core-components.sv-SE
index: y
solution-title: Lär dig mer och support för AEM
solution-hub-url: https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/home.html
getting-started-title: Komma igång med utveckling för AEM
getting-started-url: https://docs.adobe.com/content/help/en/experience-manager-cloud-service/core-concepts/home.html
tutorials-title: AEM Tutorials
tutorials-url: https://docs.adobe.com/content/help/en/experience-manager-learn/cloud-service/overview.html
translation-type: tm+mt
source-git-commit: f109463f1942349c300600acf6b94f268e8aa60e
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 16%

---


# Metadata för intern användning

Metadata i GitHub-redigeringssystemet är hierarkiska och definieras så här i ökande prioritetsnivåer.

1. metadata.md
1. TillC
1. Artikel

Metadata som definieras i filen metadata.md gäller för hela repon, men kan åsidosättas på ToC- och artikelnivå. Alla åsidosättningar av metadata bör göras på lägsta möjliga nivå.

Metadata i filen experience-manager-core-components.en repo är det minsta nödvändiga.

metadata.md

* `product`
* `git-repo`
* `index: y`
* `solution-title`
* `solution-hub-url`
* `getting-started-title`
* `getting-started-url`
* `tutorials-title`
* `tutorials-url`

ToCS

* `sub-product`
* `user-guide-title`

Artikel

* `title`
* `description`
* `index: n` (endast för tidigare versioner av komponenter)

Mer information om metadata finns i den interna redigeringsguiden för [.](https://docs.adobe.com/help/en/collaborative-doc-instructions/collaboration-guide/markdown/metadata.html#solution-metadata)
