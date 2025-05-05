---
title: Förkompilerade paketerade skript
description: Lär dig hur du distribuerar komponentskript via OSGi-paket till Adobe Experience Manager Cloud Service.
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 3edc388f-01b2-45cc-bd56-f22e5a5a8624
source-git-commit: 554be9539428cd75462a38fc45f1bece04baf066
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 0%

---


# Förkompilerade paketerade skript {#precompiled-bundled-scripts}

AEM as a Cloud Service stöder distributionen av [`ui.apps`](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html?lang=sv-SE#code-packages-%2F-osgi-bundles)-komponentskripten som förkompilerade paketerade skript. Detta gör att utvecklare kan förkompilera sina skript vid byggtillfället och paketera dem som OSGi-paket.

## Fördelar med att distribuera förkompilerade skript via OSGi Bundles {#advantages}

Distribuera skript som förkompilerade skript har följande fördelar:

+ Genom att kompilera skript vid byggtillfället kan utvecklare upptäcka fel tidigt i utvecklingsprocessen.
+ Java API-skriptberoenden definieras explicit via `Import-Package` och `Export-Package` bundle headers.
+ Arv (via `sling:resourceSuperType`) och delegering till andra resurstyper (via till exempel HTL:s `data-sly-resource` -blockelement eller via JSP-taggen `sling:include`) kan mappas via paketets metadata.
+ Versionshantering för resurstyper kan tillämpas på ungefär samma sätt som Java API:er.

## Förkompilering och paketimport {#precompilation}

[`htl-maven-plugin`](https://sling.apache.org/components/htl-maven-plugin/index.html) kan validera syntaxen för HTML-skript, men den kan också användas för att överföra HTML-skripten till Java-klasser. Dessa läggs sedan till i Maven-projektets `generated-sources`-mapp och plockas upp av `maven-compiler-plugin`.

[`bnd-maven-plugin`](https://github.com/bndtools/bnd/tree/master/maven/bnd-maven-plugin) kan läggas till för att generera OSGi-paketets metadata för Java API-import.

## Arv och delegering {#inheritance-delegation}

OSGi-ramverket är ett kraftfullt sätt att definiera [krav och funktioner](https://docs.osgi.org/specification/osgi.core/7.0.0/framework.module.html#framework.module.dependencies) för att uttrycka kontrakt mellan olika komponenter. Dessa beskrivs via metadata och används vid körning. Paketerade skript använder den här mekanismen för att uttrycka både arvsrelationer (`sling:resourceSuperType`) och delegering (inklusive andra resurstyper i återgivningsprocessen).

Plugin-programmet `bnd` från projektet [scriptingbundle-maven-plugin](https://sling.apache.org/components/scriptingbundle-maven-plugin/bnd.html) kan användas för att extrahera de krav och funktioner som motsvarar skripten från [`ui.apps`.Innehållspaket ](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html?lang=sv-SE#code-packages-%2F-osgi-bundles)

## Stöd för AEM Project Archetype {#support}

Från och med version 31 kan [AEM Project Archetype](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/developing/archetype/using.html?lang=sv-SE) användas för att konfigurera ett AEM as a Cloud Service-projekt så att det använder förkompilerade paketerade skript.

Dessutom konfigurerar AEM Project Archetype [AEM as a Cloud Service SDK Build Analyzer Maven Plugin](/help/developing/archetype/build-analyzer-maven-plugin.md) för att validera Java-paketnivån samt beroenden på skriptnivå.
