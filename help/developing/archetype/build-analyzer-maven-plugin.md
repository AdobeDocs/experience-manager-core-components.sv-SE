---
title: AEM som Cloud Service-SDK Build Analyzer Maven Plugin
description: Dokumentation för det lokala plugin-programmet Maven build analyzer
feature: Kärnkomponenter, AEM projekttyp
role: Architect, Developer, Administrator
exl-id: de26b310-a294-42d6-a0db-91f6036a328c
source-git-commit: de1bb63dc965e6674652bc3e61b515f8f045c6bc
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 4%

---

# AEM som Cloud Service-SDK Build Analyzer Maven Plugin {#maven-analyzer-plugin}

AEM som Cloud Service-SDK Build Analyzer Maven Plugin analyserar strukturen för de olika innehållspaketprojekten.

Se [Maven Plugin-dokumentationen](https://github.com/adobe/aemanalyser-maven-plugin/blob/main/aemanalyser-maven-plugin/README.md) för mer information om hur du tar med den i ett AEM maven-projekt.

>[!NOTE]
>
>Vi rekommenderar att du uppdaterar ditt Maven-projekt så att det refererar till den senaste versionen av plugin-programmet som finns i Maven Central-databasen på följande plats: https://repo1.maven.org/maven2/com/adobe/aem/aemanalyser-maven-plugin/

Plugin-programmet använder den senaste tillgängliga SDK:n i stället för den som konfigurerats i projektet.

Nedan finns en tabell som beskriver de analysatorer som körs som en del av det här steget. <!-- Note that some are executed in the local SDK, while others are only executed during the Cloud Manager pipeline deployment. -->

| Modul | Funktion, exempel och felsökning | Lokal SDK | Cloud Manager |
|---|---|---|---|
| `api-regions-exportsimports` | Kontrollerar om alla OSGI-paket har sina Import-Package-deklarationer tillgodosedda av exportpaketdeklarationen för andra inkluderade paket i Maven-projektet. Ett fel skulle se ut så här: <p> </p> `[ERROR] org.acme:mybundle:0.0.1-SNAPSHOT: Bundle org.acme:mybundle:0.0.1-SNAPSHOT is importing package(s) org.acme.foo in start level 20 but no bundle is exporting these for that start level.`<p> </p>Om du vill felsöka kontrollerar du om paketet som innehåller paketet ingår i distributionen eller också tittar du i manifestet för paketet som du förväntar dig att exportera för att avgöra om fel namn eller version användes. | Ja | Ja |
| `requirements-capabilities` | Kontrollerar om alla kravdeklarationer som gjorts i OSGI-paket uppfylls av kapacitetsdeklarationerna för andra paket som ingår i Maven-projektet. Ett fel skulle se ut så här: <p> </p> `[ERROR] org.acme:mybundle:0.0.1-SNAPSHOT: Artifact org.acme:mybundle:0.0.1-SNAPSHOT requires org.foo.bar in start level 20 but no artifact is providing a matching capability in this start level.`<p> </p> Om du vill felsöka kan du titta i det manifest i paketet som du förväntade dig ska deklarera en funktion för att avgöra varför den saknas, eller kontrollera i manifestet för det paket som kräver det för att se att kraven i det är korrekta. | Ja | Ja |
| `bundle-content` | Ger en varning om ett paket innehåller ursprungligt innehåll som anges med Sling-Initial-Content, vilket är problematiskt i AEM som en grupperad Cloud Service-miljö. Varningen ser ut så här: <p> </p> `[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Found initial content : [/]` <p> </p>Information om hur du felsöker konvertering av det ursprungliga innehållet till poinit-satser finns i Referenshandbok. | Ja | Ja |
| `bundle-resources` | Ger en varning om ett paket innehåller resurser som har angetts med huvudet Sling-Bundle-Resources, vilket är problematiskt i AEM som en Cloud Service i grupperad miljö. Varningen ser ut så här:<p> </p> `[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Found bundle resources : [/libs/sling/explorer!/resources/explorer]`<p> </p> Information om hur du felsöker konvertering av resurser till repoinit-satser finns i [Repoinit Documentation](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html?lang=en#repo-init). | Ja | Ja |
| `api-regions`<p> </p>`api-regions-check-order`<p> </p>`api-regions-dependencies`<p> </p>`api-regions-duplicates` | Dessa analytiker kontrollerar viss information om [innehållspaketet till modellkonverteringsprocessen](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html?lang=en#deploying) som skapar artefakter som överensstämmer med Sling-funktionsmodellen. Alla fel ska rapporteras till Adobe kundsupport. | Ja | Ja |
| `api-regions-crossfeature-dups` | Verifierar att kundens OSGI-paket inte har exportpaketdeklarationer som åsidosätter AEM som Cloud Servicens publika API<p> </p>`[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Package overlap found between region global and bundle org.acme:mybundle:0.0.1.SNAPSHOT which comes from feature: [org.acme:myproject.analyse:slingosgifeature:0.0.1-SNAPSHOT]. Both export package: com.day.util`<p> </p>Sluta exportera ett paket som är en del av det AEM offentliga API:t för att åtgärda problemet. | Ja | Ja |
| `repoinit` | Kontrollerar syntaxen för alla ompekande avsnitt | Ja | Ja |
| `bundle-nativecode` | Verifierar att OSGI-paket inte installerar systemspecifik kod. | Ja | Ja |
| `configuration-api` | Validerar viktiga OSGi-konfigurationer. <p> </p> `Configuration org.apache.felix.webconsole.internal.servlet.OsgiManager: Configuration is not allowed (com.mysite:mysite.all:1.0.0-SNAPSHOT\|com.mysite:mysite.ui.config:1.0.0-SNAPSHOT)` | Ja | Ja |
| `region-deprecated-api` | Kontrollerar om [api](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/deprecated-apis.html) används som föråldrat <p> </p>`[WARNING] com.mysite:mysite.core:1.0.0-SNAPSHOT: Usage of deprecated package found : org.apache.sling.settings : Avoid these features at runtime: run modes, file system access (com.mysite:mysite.all:1.0.0-SNAPSHOT)` | Ja | Ja |

