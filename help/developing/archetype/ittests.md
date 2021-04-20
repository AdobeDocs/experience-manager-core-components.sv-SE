---
title: it.tests Module of AEM Project Archetype
description: Så här använder du AEM Project Archetype Integration Tests
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Administrator
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '83'
ht-degree: 0%

---


# it.tests Module of the AEM Project Archetype {#ittests-module}

Det finns tre testnivåer i projektet:

* [Enhetstester](core.md#unit-tests)
* Integrationstester
* [UI-tester](uitests.md)

I den här artikeln beskrivs de integrationstester som är tillgängliga som en del av modulen it.tests.

## Kör integreringstester {#running-tests}

Integrationstesterna på serversidan gör att enhetstester kan köras i AEM-miljön, dvs. på den AEM servern. Testa genom att köra:

```
mvn clean verify -PintegrationTests
```
