---
title: AEM as a Cloud Service SDK Build Analyzer Maven Plugin
description: Dokumentation för det lokala plugin-programmet Maven build analyzer
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: de26b310-a294-42d6-a0db-91f6036a328c
source-git-commit: 554be9539428cd75462a38fc45f1bece04baf066
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 0%

---

# AEM as a Cloud Service SDK Build Analyzer Maven Plugin {#maven-analyzer-plugin}

AEM as a Cloud Service SDK Build Analyzer Maven Plugin analyserar strukturen för de olika innehållspaketprojekten.

I [Maven Plugin-dokumentationen](https://github.com/adobe/aemanalyser-maven-plugin/blob/main/aemanalyser-maven-plugin/README.md) finns information om hur du inkluderar det i ett AEM maven-projekt.

>[!NOTE]
>
>Vi rekommenderar att du uppdaterar ditt Maven-projekt så att det refererar till den senaste versionen av plugin-programmet som finns i [Maven central databas.](https://repo1.maven.org/maven2/com/adobe/aem/aemanalyser-maven-plugin/)

Plugin-programmet använder den senaste tillgängliga SDK:n i stället för den som konfigurerats i projektet.

Nedan finns en tabell som beskriver de analysatorer som körs som en del av det här steget. <!-- Note that some are executed in the local SDK, while others are only executed during the Cloud Manager pipeline deployment. -->

| Modul | Funktion, exempel och felsökning | Lokal SDK | Cloud Manager |
|---|---|---|---|
| `api-regions-exportsimports` | Kontrollerar om alla OSGi-paket har sina Import-Package-deklarationer nöjda med exportpaketdeklarationen för andra inkluderade paket i Maven-projektet. Ett fel skulle se ut så här: <p> </p> `[ERROR] org.acme:mybundle:0.0.1-SNAPSHOT: Bundle org.acme:mybundle:0.0.1-SNAPSHOT is importing package(s) org.acme.foo in start level 20 but no bundle is exporting these for that start level.`<p> </p>Om du vill felsöka kontrollerar du om paketet som innehåller paketet ingår i distributionen eller också tittar du i manifestet för paketet som du förväntar dig att exportera för att avgöra om fel namn eller version användes. | Ja | Ja |
| `bundle-unversioned-packages` | Kontrollerar om OSGi-paket anger en version med en Export-Package-deklaration och ett versionsintervall med en Import-Package-deklaration. Ett fel skulle se ut så här: <p> </p> `[ERROR] org.acme:mybundle:0.0.1-SNAPSHOT: Bundle org.acme:mybundle:0.0.1-SNAPSHOT is exporting package org.acme.foo without a version.`<p> </p>Om du vill felsöka måste du lägga till en `package-info.java` i det paketet och ange vilken version som ska exporteras. | Ja | Ja |
| `requirements-capabilities` | Kontrollerar om alla kravdeklarationer som gjorts i OSGi-paket uppfylls av kapacitetsdeklarationerna för andra paket som ingår i Maven-projektet. Ett fel skulle se ut så här: <p> </p> `[ERROR] org.acme:mybundle:0.0.1-SNAPSHOT: Artifact org.acme:mybundle:0.0.1-SNAPSHOT requires org.foo.bar in start level 20 but no artifact is providing a matching capability in this start level.`<p> </p> Om du vill felsöka kan du titta i det manifest i paketet som du förväntade dig ska deklarera en funktion för att avgöra varför den saknas, eller kontrollera i manifestet för det paket som kräver det för att se att kraven i det är korrekta. | Ja | Ja |
| `bundle-content` | Ger en varning om ett paket innehåller ursprungligt innehåll som anges med Sling-Initial-Content, vilket är problematiskt i AEM as a Cloud Service klustermiljö. Varningen ser ut så här: <p> </p> `[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Found initial content : [/]` <p> </p>Information om hur du felsöker konvertering av det ursprungliga innehållet till poinit-satser finns i Referenshandbok. | Ja | Ja |
| `bundle-resources` | Ger en varning om ett paket innehåller resurser som har angetts med rubriken Sling-Bundle-Resources, vilket är problematiskt i AEM as a Cloud Service klustermiljö. Varningen ser ut så här:<p> </p> `[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Found bundle resources : [/libs/sling/explorer!/resources/explorer]`<p> </p> Information om hur du felsöker konvertering av resurser för att kommentera programsatser finns i [Öppna dokumentation](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html?lang=en#repo-init). | Ja | Ja |
| `api-regions`<p> </p>`api-regions-check-order`<p> </p>`api-regions-dependencies`<p> </p>`api-regions-duplicates` | Dessa analytiker kontrollerar viss information om [innehållspaketet till en modellkonverteringsprocess](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html?lang=en#deploying) som skapar artefakter som överensstämmer med Sling-funktionsmodellen. Alla fel ska rapporteras till Adobe kundsupport. | Ja | Ja |
| `api-regions-crossfeature-dups` | Verifierar att kundens OSGi-paket inte har exportpaketdeklarationer som åsidosätter AEM as a Cloud Service publika API<p> </p>`[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Package overlap found between region global and bundle org.acme:mybundle:0.0.1.SNAPSHOT which comes from feature: [org.acme:myproject.analyse:slingosgifeature:0.0.1-SNAPSHOT]. Both export package: com.day.util`<p> </p>Sluta exportera ett paket som är en del av det AEM offentliga API:t för att åtgärda problemet. | Ja | Ja |
| `repoinit` | Kontrollerar syntaxen för alla ompekande avsnitt | Ja | Ja |
| `bundle-nativecode` | Verifierar att OSGi-paket inte installerar systemspecifik kod. | Ja | Ja |
| `configuration-api` | Validerar viktiga OSGi-konfigurationer. <p> </p> `Configuration org.apache.felix.webconsole.internal.servlet.OsgiManager: Configuration is not allowed (com.mysite:mysite.all:1.0.0-SNAPSHOT\|com.mysite:mysite.ui.config:1.0.0-SNAPSHOT)` | Ja | Ja |
| `region-deprecated-api` | Kontrollerar om [api](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/deprecated-apis.html) som tagits bort används <p> </p>`[WARNING] com.mysite:mysite.core:1.0.0-SNAPSHOT: Usage of deprecated package found : org.apache.sling.settings : Avoid these features at runtime: run modes, file system access (com.mysite:mysite.all:1.0.0-SNAPSHOT)` | Ja | Ja |
| `artifact-rules` | Validerar beroenden som paket och innehållspaket för att förhindra kända problem i artefakter.<p> </p>`[WARNING] [artifact-rules] com.adobe.acs:acs-aem-commons-bundle:5.0.4: Use at least version 5.0.10 (com.mysite:mysite.all:1.0.0-SNAPSHOT)` | Ja | Ja |
| `aem-env-var` | Kontrollerar användningen av env-variabler enligt [variabelnamnguiden](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/configuring-osgi.html#variable-naming)<p> </p>`[ERROR] Configuration org.apache.felix.webconsole.internal.servlet.OsgiManager: Value for property 'port' must not use env vars prefixed with INTERNAL_ or ADOBE_ (com.mysite1:my-site-1.all:1.0.0-SNAPSHOT\|com.mysite1:my-site-1.ui.config:1.0.0-SNAPSHOT)` | Ja | Ja |
| `content-package-validation` | Kör filevault-validerare. Som standard är Jackrabbit-docviewparser aktiverat, vilket kontrollerar om det finns en korrekt formaterad innehållssyntax för XML i paket som ska installeras under distributionen.<p> </p>`[main] WARN org.apache.sling.feature.analyser.task.impl.CheckContentPackages - ValidationViolation: "jackrabbit-docviewparser: Invalid XML found: The reference to entity "se" must end with the ';' delimiter.", filePath=jcr_root/apps/somename/configs/com.adobe.test.Invalid.xml, nodePath=/apps/somename/configs/com.adobe.test.Invalid`<p> </p>Åtgärda problemet genom att kontrollera om det finns XML-problem i filen som analyseraren har namngett. | Ja | Ja |

{style="table-layout:auto"}

## Kända fel

Nedan finns en lista med kända fel när du använder Build Analyzer Maven Plugin.

### Det gick inte att köra Build Analyzer Maven Plugin i Local SDK

När du använder den lokala SDK:n med en Build Analyzer Maven Plugin-version som är lägre än `1.1.2` kan felet nedan uppstå om du kör plugin-programmet. I så fall uppdaterar du projektet till den senaste versionen av plugin-programmet.

```txt
[ERROR] Failed to execute goal com.adobe.aem:aemanalyser-maven-plugin:1.1.0:analyse (default-analyse) on project mysite.analyse: Execution default-analyse of goal com.adobe.aem:aemanalyser-maven-plugin:1.1.0:analyse failed: arraycopy: source index -1 out of bounds for char[65536] -> [Help 1]
```

Om du använde AEM Project Archetype för att konfigurera ditt projekt måste du justera egenskapen i rotmasken `pom.xml` som nedan.

```xml
   ...
   <properties>
      ...
      <aemanalyser.version>1.1.2</aemanalyser.version> <!-- Make sure to use the latest release -->
      ...
   </properties>
```
