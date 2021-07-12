---
title: Kärnmodul av AEM projekttyp
description: Kärnmodul av AEM projekttyp
feature: Kärnkomponenter, AEM projekttyp
role: Architect, Developer, Admin
exl-id: 49e80d8c-2b41-4c42-b45e-c2e3b4b16a59
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 0%

---

# Kärnmodul av AEM projekttyp {#core-module}

Kärnmodellen (`<src-directory>/<project>/core`) innehåller all Java-kod som behövs för implementeringen. Modulen paketerar all Java-kod och distribuerar den till AEM som en OSGi Bundle.

Plugin-programmet Maven Bundle som definieras i `<src-directory>/<project>/core/pom.xml` ansvarar för att kompilera Java-koden till ett OSGi-paket som kan identifieras av AEM OSGi-behållare. Observera att det här är platsen för Sling Models definieras.

Även om det är ovanligt att kärnpaketet måste driftsättas oberoende av modulen ui.apps i miljöer på den översta nivån, är det bra att driftsätta kärnpaketet direkt under lokal utveckling/testning. Med Maven Sling-pluginen kan kärnpaketet distribueras för att AEM direkt utnyttja `autoInstallBundle`-profilen enligt definitionen i [överordnad POM](/help/developing/archetype/using.md#parent-pom).

```shell
mvn -PautoInstallBundle clean install
```

När det är klart ska du kunna se Bundles Console på `http://<host>:<port>/system/console/bundles`.

##  Enhetstester {#unit-tests}

Enhetstestet i kärnmodulen visar klassiska enhetstestningar av koden i paketet. Testa genom att köra:

```shell
mvn clean test
```
