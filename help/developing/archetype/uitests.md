---
title: ui.tests Module of AEM Project Archetype
description: Så här använder du AEM Project Archetype JUnit Tests
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# ui.tests Module of the AEM Project Archetype {#uitests-module}

Det finns tre testnivåer i projektet:

## Enhetstester {#unit-tests}

Enhetstestet i [kärnmodulen](core.md) visar klassiska enhetstestningar av koden i paketet. Testa genom att köra:

```
mvn clean test
```

## Integrationstester {#integration-tests}

Integrationstesterna på serversidan gör att enhetstester kan köras i AEM-miljön, dvs. på AEM-servern. Testa genom att köra:

```
mvn clean verify -PintegrationTests
```

## Klientsidtester {#client-side-tests}

Testen är JavaScript-baserade `client-side Hobbes.js` webbläsarbaserade tester som verifierar webbläsarsidans beteende.

Om du vill testa en AEM-sida som du vill testa i webbläsaren öppnar du sidan i **utvecklarläge** genom att öppna den vänstra panelen och växlar till fliken **Tester** och söker efter de genererade **MyName-testerna** och kör dem.
