---
title: ui.apps-modulen för AEM Project Archetype
description: ui.apps-modulen för AEM Project Archetype
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: fc63a19a-3253-44ee-96e2-bb5544c2235b
source-git-commit: 19bceb1d8ba07c70798f2e7203db957d3e8b3d03
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 0%

---

# ui.apps-modulen för AEM Project Archetype {#uiapps-module}

Ui.apps maven module (`<src-directory>/<project>/ui.apps`) innehåller all återgivningskod som behövs för den underliggande webbplatsen `/apps`. Detta inkluderar CSS/JS som lagras i ett AEM som kallas [clientlibs.](uifrontend.md#clientlibs) Detta inkluderar även HTML-skript för återgivning av dynamiska HTML. Du kan tänka dig modulen ui.apps som en karta till strukturen i JCR men i ett format som kan lagras i ett filsystem och användas för källkontroll.

Plugin-programmet Apache Jackrabbit FileVault Package används för att kompilera innehållet i modulen ui.apps till ett AEM paket som kan distribueras till AEM. De globala konfigurationerna för plugin-programmet definieras i den överordnade filen pom.xml.

## Överordnad POM {#parent-pom}

[Överordnad POM](/help/developing/archetype/using.md#parent-pom) (`<src>/<project>/pom.xml`) innehåller `<plugin>` -avsnitt som definierar olika konfigurationer för de plugin-program som används i projektet. Detta innehåller en konfiguration för `filterSource` för Jackrabbit FileVault Package Plugin. The `filterSource` pekar på platsen för `filter.xml` som används för att definiera jcr-sökvägarna som ingår i paketet.

Förutom Jackrabbit FileVault Package Plugin är en definition av innehållspaketets plugin som används för att sedan överföra paketet till AEM. Observera att variabler för `aem.host`, `aem.port`, `vault.user`och `vault.password` används som motsvarar de globala egenskaper som definieras i samma överordnade POM.

## ui.apps/pom.xml {#uiapps-pom}

Observera att paketen core.wcm.components.all och core.wcm.components.examples ingår som ett underpaket. Detta distribuerar Core Components-paketet tillsammans med WKND-koden varje gång.

core.wcm.components.all och core.wcm.components.examples ingår som beroenden i beroendelistan. Som en god praxis utelämnas versioner för beroenden här och hanteras i [överordnad PDF-fil](/help/developing/archetype/using.md#core-components).

## filter.xml {#filter}

The `filter.xml` filen för modulen ui.apps finns på `<src>/<project>/ui.apps/src/main/content/META-INF/vault/filter.xml` och innehåller sökvägarna som ska inkluderas och installeras med paketet ui.apps.
