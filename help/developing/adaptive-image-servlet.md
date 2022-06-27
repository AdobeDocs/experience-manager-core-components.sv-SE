---
title: Adaptiv bildserver
description: Lär dig hur Core Components använder Adaptive Image Servlet för bildleverans och hur du kan optimera användningen.
role: Architect, Developer, Admin, User
source-git-commit: 3ff1343ab4ef7a52f910984a0bcd8fc4201441bf
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 0%

---


# Adaptiv bildserver {#adaptive-image-servlet}

Lär dig hur Core Components använder Adaptive Image Servlet för bildleverans och hur du kan optimera användningen.

## Adaptiv bildserver eller webboptimerad bildleverans? {#options}

Image Core Component kan använda två metoder för att leverera bilder.

* Standardinställningen är Adaptiv bildserver.
* [Webboptimerad bildleverans](/help/developing/web-optimized-image-delivery.md) är tillgängligt för AEMaaCS och minskar hämtningsstorleken med i genomsnitt 25 %.

Det här dokumentet beskriver standardservern för adaptiv bildhantering.

## Översikt {#overview}

Som standard använder Image Component (Bildkomponent) Core-komponentens adaptiva bildserver för att leverera bilder. [Adaptiv bildserver](https://github.com/adobe/aem-core-wcm-components/wiki/The-Adaptive-Image-Servlet) ansvarar för bildbehandling och direktuppspelning och kan utnyttjas av utvecklare i [anpassningar av kärnkomponenterna](/help/developing/customizing.md).

## Optimera återgivningsmarkering {#optimizing-rendition-selection}

Den adaptiva bildservern kommer att försöka välja den bästa återgivningen för den önskade bildstorleken och bildtypen. Vi rekommenderar att DAM-återgivningar och tillåtna bildkomponentbredder definieras synkroniserade så att den adaptiva bildservern utför så lite bearbetning som möjligt.

Detta förbättrar prestanda och förhindrar att vissa bilder bearbetas felaktigt av det underliggande bildbehandlingsbiblioteket.

## Använda senast ändrade rubriker {#last-modified}

Villkorliga begäranden via `Last-Modified` -huvudet stöds av Adaptive Image Servlet, men cachelagringen av `Last-Modified` header [måste aktiveras i Dispatcher](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html?lang=en#caching-http-response-headers).

[AEM Project Archetype](/help/developing/archetype/overview.md)Exempelkonfigurationen för Dispatcher innehåller redan den här konfigurationen.
