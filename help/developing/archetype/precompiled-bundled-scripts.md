---
title: Förkompilerade paketerade skript
description: Lär dig hur du distribuerar komponentskript via OSGi-paket till Adobe Experience Manager Cloud Service.
source-git-commit: 56464decc8d6ae3cef68d62bfe459bceda0539ef
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 0%

---

# Förkompilerade paketerade skript

AEM som en Cloud Service har stöd för distribution av [`ui.apps`](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html#code-packages-%2F-osgi-bundles)-komponentskripten som förkompilerade paketerade skript. Detta gör att utvecklare kan förkompilera sina skript vid byggtillfället och paketera dem som OSGi-paket.

## Fördelarna med att distribuera förkompilerade skript via OSGi-paket

Distribuera skript som förkompilerade skript har följande fördelar:

+ när skript kompileras vid byggtillfället kan utvecklare upptäcka fel tidigt i utvecklingsprocessen
+ Java API-skriptberoenden definieras explicit via `Import-Package`- och `Export-Package`-paketrubrikerna
+ arv (via `sling:resourceSuperType`) och delegering till andra resurstyper (via till exempel HTL:s `data-sly-resource`-blockelement eller via JSP-taggen `sling:include`) kan mappas via paketets metadata
+ versionshantering av resurstyper kan tillämpas på ungefär samma sätt som Java API:er

## Förkompilering och paketerad import

[`htl-maven-plugin`](https://sling.apache.org/components/htl-maven-plugin/index.html) kan validera syntaxen för HTML-skript, men den kan också användas för att överföra HTML-skript till Java-klasser. Dessa läggs sedan till i Maven-projektets `generated-sources`-mapp och hämtas upp av `maven-compiler-plugin`.

[`bnd-maven-plugin`](https://github.com/bndtools/bnd/tree/master/maven/bnd-maven-plugin) kan läggas till för att generera OSGi-paketets metadata för Java API-import.

## Arv och delegering

OSGi-ramverket är ett kraftfullt sätt att definiera [krav och funktioner](https://docs.osgi.org/specification/osgi.core/7.0.0/framework.module.html#framework.module.dependencies) för att uttrycka kontrakt mellan olika komponenter. Dessa beskrivs via metadata och används vid körning. Paketerade skript använder den här funktionen för att uttrycka både arvsrelationer (`sling:resourceSuperType`) och delegering (inklusive andra resurstyper i återgivningsprocessen).

Plugin-programmet `bnd` från [scriptingbundle-maven-plugin](https://sling.apache.org/components/scriptingbundle-maven-plugin/bnd.html)-projektet kan användas för att extrahera de krav och funktioner som motsvarar de skript som finns i [`ui.apps`](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html#code-packages-%2F-osgi-bundles)-innehållspaketet.

## Stöd för AEM Project Archetype

Från och med version 31 kan du använda [AEM Project Archetype](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/developing/archetype/using.html) för att konfigurera en AEM som ett Cloud Service-projekt för att använda förkompilerade, paketerade skript. Dessutom konfigurerar AEM Project Archetype [AEM som en Cloud Service-SDK Build Analyzer Maven Plugin](/help/developing/archetype/build-analyzer-maven-plugin.md) för att validera både Java-paketnivån och beroenden på skriptnivå.
