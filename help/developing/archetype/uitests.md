---
title: ui.tests Module of AEM Project Archetype
description: Så här använder du AEM projektarkitekturens gränssnittstester
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: eb3c9b34-f10e-410f-bcf3-34f94f124c7c
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 0%

---

# ui.tests Module of the AEM Project Archetype {#uitests-module}

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

Efter körningen finns rapporter och loggar i `target/reports` mapp.

## Ytterligare alternativ {#additional-options}

Gränssnittstester kan köras med många olika alternativ, bland annat för headless-testning mot en lokal webbläsare och som en Docker-bild. Se [README.md-fil för modulen ui.tests](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/ui.tests) för ytterligare information.
