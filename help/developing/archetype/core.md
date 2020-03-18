---
title: Kärnmodul för AEM-projektarkitypen
description: Kärnmodul för AEM-projektarkitypen
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# Kärnmodul för AEM-projektarkitypen {#core-module}

Kärnmodellen (`<src-directory>/<project>/core`) innehåller all Java-kod som behövs för implementeringen. Modulen paketerar all Java-kod och distribuerar den till AEM-instansen som ett OSGi Bundle.

Plugin-programmet Maven Bundle som definieras i `<src-directory>/<project>/core/pom.xml` är ansvarigt för att kompilera Java-koden till ett OSGi-paket som kan identifieras av AEM:s OSGi-behållare. Observera att det här är platsen för Sling Models definieras.

Även om det är ovanligt att kärnpaketet måste driftsättas oberoende av modulen ui.apps i miljöer på den översta nivån, är det bra att driftsätta kärnpaketet direkt under lokal utveckling/testning. Med Maven Sling-pluginen kan kärnpaketet distribueras till AEM direkt med hjälp av den `autoInstallBundle` profil som definieras i den [överordnade POM](overview.md#parent-pom).

```
mvn -PautoInstallBundle clean install
```

När det är klart ska du kunna se Bundles Console på `http://<host>:<port>/system/console/bundles`.
