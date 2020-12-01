---
title: Kärnmodul för AEM projekttyp
description: Kärnmodul för AEM projekttyp
translation-type: tm+mt
source-git-commit: 6f7166c46940ed451721e0760d565d58efe412ab
workflow-type: tm+mt
source-wordcount: '159'
ht-degree: 0%

---


# Kärnmodul för AEM projekttyp {#core-module}

Kärnmodellen (`<src-directory>/<project>/core`) innehåller all Java-kod som behövs för implementeringen. Modulen paketerar all Java-kod och distribuerar den till AEM som en OSGi Bundle.

Plugin-programmet Maven Bundle som definieras i `<src-directory>/<project>/core/pom.xml` ansvarar för att kompilera Java-koden till ett OSGi-paket som kan identifieras av AEM OSGi-behållare. Observera att det här är platsen för Sling Models definieras.

Även om det är ovanligt att kärnpaketet måste driftsättas oberoende av modulen ui.apps i miljöer på den översta nivån, är det bra att driftsätta kärnpaketet direkt under lokal utveckling/testning. Med Maven Sling-pluginen kan kärnpaketet distribueras för att AEM direkt utnyttja `autoInstallBundle`-profilen som definieras i den överordnade POM](/help/developing/archetype/using.md#parent-pom).[

```
mvn -PautoInstallBundle clean install
```

När det är klart ska du kunna se Bundles Console på `http://<host>:<port>/system/console/bundles`.
