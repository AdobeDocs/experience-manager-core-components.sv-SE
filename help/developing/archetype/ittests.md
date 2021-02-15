---
title: it.tests Module of AEM Project Archetype
description: Så här använder du AEM Project Archetype Integration Tests
translation-type: tm+mt
source-git-commit: 9d737b31efc8c346775ea5296f7599295af07cf1
workflow-type: tm+mt
source-wordcount: '75'
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
