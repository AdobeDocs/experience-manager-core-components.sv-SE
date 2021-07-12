---
title: ui.apps-modulen för AEM Project Archetype
description: ui.apps-modulen för AEM Project Archetype
feature: Kärnkomponenter, AEM projekttyp
role: Architect, Developer, Admin
exl-id: fc63a19a-3253-44ee-96e2-bb5544c2235b
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 0%

---

# ui.apps-modulen för AEM Project Archetype {#uiapps-module}

Modulen ui.apps maven (`<src-directory>/<project>/ui.apps`) innehåller all återgivningskod som behövs för webbplatsen under `/apps`. Detta inkluderar CSS/JS som lagras i ett AEM som heter [clientlibs.](uifrontend.md#clientlibs) Detta inkluderar även HTML-skript för återgivning av dynamisk HTML. Du kan tänka dig modulen ui.apps som en karta till strukturen i JCR men i ett format som kan lagras i ett filsystem och användas för källkontroll.

Plugin-programmet Apache Jackrabbit FileVault Package används för att kompilera innehållet i modulen ui.apps till ett AEM paket som kan distribueras till AEM. De globala konfigurationerna för plugin-programmet definieras i den överordnade filen pom.xml.

## Överordnad POM {#parent-pom}

[Den överordnade POM](/help/developing/archetype/using.md#parent-pom) (`<src>/<project>/pom.xml`) innehåller  `<plugin>` avsnitt som definierar olika konfigurationer för de plugin-program som används i projektet. Detta inkluderar en konfiguration för `filterSource` för Jackrabbit FileVault Package Plugin. `filterSource` pekar på platsen för den `filter.xml`-fil som används för att definiera jcr-sökvägarna som ingår i paketet.

Förutom Jackrabbit FileVault Package Plugin är en definition av innehållspaketets plugin som används för att sedan överföra paketet till AEM. Observera att variabler för `aem.host`, `aem.port`, `vault.user` och `vault.password` används som motsvarar de globala egenskaper som definierats i samma överordnade POM.

## ui.apps/pom.xml {#uiapps-pom}

Ui.apps pom (`<src>/<project>/ui.apps/pom.xml`) innehåller `embedded`-taggar för `filevault-package-maven-plugin`. `embedded`-taggarna inkluderar det kompilerade kärnpaketet som en del av ui.apps-paketet och var det ska installeras.

Observera att paketen core.wcm.components.all och core.wcm.components.examples ingår som ett underpaket. Detta distribuerar Core Components-paketet tillsammans med WKND-koden varje gång.

core.wcm.components.all och core.wcm.components.examples ingår som beroenden i beroendelistan. Som en god praxis utelämnas versioner för beroenden här och hanteras i den [överordnade PDF-filen](/help/developing/archetype/using.md#core-components).

## filter.xml {#filter}

Filen `filter.xml` för modulen ui.apps finns på `<src>/<project>/ui.apps/src/main/content/META-INF/vault/filter.xml` och innehåller sökvägarna som ska inkluderas och installeras med paketet ui.apps.
