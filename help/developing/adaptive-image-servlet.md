---
title: Adaptiv bildserver
description: Lär dig hur Core Components använder Adaptive Image Servlet för bildleverans och hur du kan optimera användningen.
role: Architect, Developer, Admin, User
exl-id: d9199d51-6f09-4000-9525-afc30474437e
source-git-commit: 3f6e40c4dbfbd1287213d9d16d96183d24f2ad0a
workflow-type: tm+mt
source-wordcount: '456'
ht-degree: 0%

---

# Adaptiv bildserver {#adaptive-image-servlet}

Lär dig hur Core Components använder Adaptive Image Servlet för bildleverans och hur du kan optimera användningen.

>[!WARNING]
>
>Av prestandaskäl rekommenderar vi att du lagrar bilder i DAM och använder webboptimerad bildleverans.
>
>Lagring av bilder direkt under komponentnoden är avsedd för tillfällig användning. Det utnyttjar inte DAM-renderingarna för att minska bearbetningen i Adaptive Image Servlet och ger inga prestandafördelar vid webboptimerad bildleverans, vilket kan leda till prestandaproblem.

## Adaptiv bildserver eller webboptimerad bildleverans? {#options}

Image Core Component kan använda två metoder för att leverera bilder.

* Standardinställningen är Adaptiv bildserver.
* [Webboptimerad bildleverans](/help/developing/web-optimized-image-delivery.md) är tillgänglig för AEMaaCS och minskar hämtningsstorleken med i genomsnitt 25 %.

Det här dokumentet beskriver standardservern för adaptiv bildhantering.

## Ökning {#overview}

Som standard använder Image Component (Bildkomponent) Core-komponentens Adaptive Image Servlet för att leverera bilder. [Den adaptiva bildservern ](https://github.com/adobe/aem-core-wcm-components/wiki/The-Adaptive-Image-Servlet) ansvarar för bildbearbetning och direktuppspelning och kan utnyttjas av utvecklare i deras [anpassningar av kärnkomponenterna](/help/developing/customizing.md).

## Återgivningsmarkering {#rendition-selection}

Den adaptiva bildservern väljer automatiskt den rendering som passar bäst för visning baserat på storleken på den behållare som den visas i. Processen för att välja återgivning är följande.

1. Adaptive Image Servlet granskar alla tillgängliga återgivningar av bildresursen.
1. Endast de som har samma MIME/Type för den ursprungliga refererade resursen markeras.
   * Om den ursprungliga resursen till exempel är en PNG-fil kommer endast PNG-renderingar att användas.
1. Av dessa återgivningar beaktas dimensionerna och de jämförs med storleken på behållaren som bilden ska visas i.
1. Om återgivningen är >= behållarstorleken läggs den till i en lista över möjliga återgivningar.
1. Om återgivningen är &lt; behållarstorleken ignoreras den.
1. Dessa kriterier säkerställer att återgivningen inte skalas upp, vilket skulle påverka bildkvaliteten.
1. Den adaptiva bildservern väljer sedan den rendering som har den minsta filstorleken från listan över kandidater.

## Optimera återgivningsmarkering {#optimizing-rendition-selection}

Den adaptiva bildservern kommer att försöka välja den bästa återgivningen för den önskade bildstorleken och bildtypen. Vi rekommenderar att DAM-återgivningar och tillåtna bildkomponentbredder definieras synkroniserade så att den adaptiva bildservern utför så lite bearbetning som möjligt.

Detta förbättrar prestanda och förhindrar att vissa bilder bearbetas felaktigt av det underliggande bildbearbetningsbiblioteket.

## Använda senast ändrade rubriker {#last-modified}

Villkorliga begäranden via `Last-Modified`-huvudet stöds av Adaptive Image Server, men cachelagringen av `Last-Modified` header [ måste aktiveras i Dispatcher](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html?lang=en#caching-http-response-headers).

[Dispatcher-exempelkonfigurationen för AEM Project Archetype](/help/developing/archetype/overview.md) innehåller redan den här konfigurationen.
