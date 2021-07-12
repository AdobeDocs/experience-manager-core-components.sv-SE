---
title: it.tests Module of AEM Project Archetype
description: Så här använder du AEM Project Archetype Integration Tests
feature: Kärnkomponenter, AEM projekttyp
role: Architect, Developer, Admin
exl-id: 0abc0265-3a3f-4323-97e6-3af0c62299ef
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 0%

---

# it.tests Module of the AEM Project Archettype {#ittests-module}

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
