---
product: adobe experience manager
solution: Experience Manager Sites
type: Documentation
description: Dokumentation för Adobe Experience Manager Core Components
git-repo: https://git.corp.adobe.com/AdobeDocs/experience-manager-core-components.sv-SE
index: y
translation-type: tm+mt
source-git-commit: 290423c39b925ea8cf4077f31a76ecf01167f344
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 0%

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
