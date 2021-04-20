---
title: ui.tests Module of AEM Project Archetype
description: Så här använder du AEM projektarkitekturens gränssnittstester
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Administrator
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 0%

---


# ui.tests-modulen för AEM Project Archetype {#uitests-module}

Det finns tre testnivåer i projektet:

* [Enhetstester](core.md#unit-tests)
* [Integrationstester](ittests.md)
* UI-tester

I den här artikeln beskrivs de UI-tester som är tillgängliga som en del av modulen ui.tests.

## Kör gränssnittstester {#running-tests}

Testa genom att köra:

```shell
mvn verify -Pui-tests-local-execution
```

Efter körningen är rapporter och loggar tillgängliga i mappen `target/reports`.

## Ytterligare alternativ {#additional-options}

Gränssnittstester kan köras med många olika alternativ, bland annat för headless-testning mot en lokal webbläsare och som en Docker-bild. Mer information finns i filen [README.md i modulen ui.tests](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/ui.tests).
