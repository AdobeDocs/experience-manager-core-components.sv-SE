---
title: ui.tests Module of AEM Project Archetype
description: Så här använder du AEM JUnit Tests för projektarkitektur
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 0%

---


# ui.tests-modulen för AEM Project Archetype {#uitests-module}

Det finns tre testnivåer i projektet:

## Enhetstester {#unit-tests}

Enhetstestet i [kärnmodulen](core.md) visar klassiska enhetstestningar av koden i paketet. Testa genom att köra:

```
mvn clean test
```

## Integrationstester {#integration-tests}

Integrationstesterna på serversidan gör att enhetstester kan köras i AEM-miljön, dvs. på den AEM servern. Testa genom att köra:

```
mvn clean verify -PintegrationTests
```

## Klientsidtester {#client-side-tests}

`client-side Hobbes.js`-testerna är JavaScript-baserade webbläsarbaserade tester som verifierar webbläsarsidans beteende.

När du visar en AEM som du vill testa i webbläsaren öppnar du sidan i **Utvecklarläge** genom att öppna den vänstra panelen och växlar till fliken **Tester** och söker efter de **MyName Tests** som har skapats och kör dem.
