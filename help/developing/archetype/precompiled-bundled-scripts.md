---
title: Förkompilerade paketerade skript
description: Lär dig hur du distribuerar komponentskript via OSGi-paket till Adobe Experience Manager Cloud Service.
exl-id: 3edc388f-01b2-45cc-bd56-f22e5a5a8624
source-git-commit: 767f83fbad11a108aab25be2b77759af3c08b864
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 0%

---

# Förkompilerade paketerade skript

AEM as a Cloud Service stöder driftsättningen av [`ui.apps`](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html#code-packages-%2F-osgi-bundles) som förkompilerade, paketerade skript. Detta gör att utvecklare kan förkompilera sina skript vid byggtillfället och paketera dem som OSGi-paket.

## Fördelarna med att distribuera förkompilerade skript via OSGi-paket

Distribuera skript som förkompilerade skript har följande fördelar:

+ när skript kompileras vid byggtillfället kan utvecklare upptäcka fel tidigt i utvecklingsprocessen
+ Java API-skriptberoenden definieras explicit via `Import-Package` och `Export-Package` källrubriker
+ arv (via `sling:resourceSuperType`) och delegering till andra resurstyper (via HTML `data-sly-resource` blockelement eller via `sling:include` JSP-tagg) kan till exempel mappas via paketets metadata
+ versionshantering av resurstyper kan tillämpas på ungefär samma sätt som Java API:er

## Förkompilering och paketerad import

The [`htl-maven-plugin`](https://sling.apache.org/components/htl-maven-plugin/index.html) kan validera syntaxen för HTML-skript, men den kan också användas för att överföra HTML-skript till Java-klasser. Dessa läggs sedan till i Maven-projektets `generated-sources` och plockas upp av `maven-compiler-plugin`.

The [`bnd-maven-plugin`](https://github.com/bndtools/bnd/tree/master/maven/bnd-maven-plugin) kan läggas till för att generera OSGi-paketets metadata för Java API-import.

## Arv och delegering

OSGi-ramverket är ett kraftfullt sätt att definiera [Krav och funktioner](https://docs.osgi.org/specification/osgi.core/7.0.0/framework.module.html#framework.module.dependencies) att uttrycka kontrakt mellan olika komponenter. Dessa beskrivs via metadata och används vid körning. Paketerade skript använder den här funktionen för att uttrycka både deras arvsrelationer (`sling:resourceSuperType`) och delegering (inklusive andra resurstyper i återgivningsprocessen).

The `bnd` plugin-program från [scriptingbundle-maven-plugin](https://sling.apache.org/components/scriptingbundle-maven-plugin/bnd.html) kan användas för att extrahera de krav och funktioner som motsvarar skript i [`ui.apps`](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html#code-packages-%2F-osgi-bundles) innehållspaket.

## Stöd för AEM Project Archetype

Från och med version 31 är [AEM Project Archetype](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/developing/archetype/using.html) kan användas för att ställa in ett AEM as a Cloud Service projekt på rätt sätt så att förkompilerade skript används. Dessutom konfigurerar AEM Project Archetype [AEM as a Cloud Service SDK Build Analyzer Maven Plugin](/help/developing/archetype/build-analyzer-maven-plugin.md) för att validera både Java-paketnivån och skriptnivåberoenden.
