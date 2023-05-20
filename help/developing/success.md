---
title: Sökvägar till framgång med kärnkomponenterna
description: Så här lyckas du när du implementerar ditt projekt med Core Components
role: Architect, Developer, Admin, User
exl-id: 1ea8cd1c-8435-4ded-82dc-5a7896c53e0c
source-git-commit: 888719359f9a1d1c9dccff97fb639b332f2be54c
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 0%

---

# Sökvägar till framgång med kärnkomponenterna {#paths-to-success}

Core Components är kraftfulla, flexibla och enkla att använda och anpassa. Om du följer några riktlinjer som beskrivs i det här dokumentet kommer ditt projekt med kärnkomponenterna att bli framgångsrikt.

## Två sökvägar till framgång {#two-paths}

Det finns två grundläggande strategier för att genomföra de centrala komponenterna, som kan leda till framgång men som har egna kompromisser som måste beaktas på projektbasis.

1. Kartlägg dina designer med kärnkomponenterna och ta HTML som de tillhandahåller. eller
1. Om ni måste följa de redan definierade HTML-standarderna behöver ni mer arbete och inte alla fördelarna med kärnkomponenterna.

## Vanliga fallgropar i komponentimplementering {#common-pitfalls}

Två vanliga problem som leder till att projekt inte lyckas med kärnkomponenter är:

* **Slutför design** - Dessa kan till och med godkännas på C-nivå och överlämnas till utvecklingsteamet som ska implementeras pixelperfekt utan att bekymra sig om den underliggande tekniken.
* **En företagsomfattande HTML-guide** - Sådana stödlinjer måste följas alltför ofta av komponenter som använder format uppifrån och ned.

I båda fallen är de krav som ställs på komponenterna så täta och specifika att det är svårt att få Core-komponenterna eller komponenter som inte ingår i paketet att uppfylla dem, vilket leder till en enorm utveckling av anpassade komponenter.

## Starta tidigt {#start-early}

I stället för att bara ta hänsyn till kärnkomponenterna i projektets implementeringsfas börjar du redan med kärnkomponenterna under trådrams- och designfasen.

### Använda komponentbiblioteket {#component-library}

Referera till [Komponentbibliotek](https://adobe.com/go/aem_cmp_library) redan i designfasen. Core Components är kraftfulla och flexibla och kan ta dig långt som en startpunkt. Lägg bara till anpassade komponenter när det finns ett verkligt affärsbehov som verkligen inte kan uppnås med en Core-komponent.

### Använda UI Kit för Adobe XD {#ui-kit}

Så snart det finns ett bevisat behov av en anpassad komponent kan du använda [UI-kit för Adobe XD](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/AEM-CoreComponents-UI-Kit.xd)  så att formgivarna kan börja bygga trådramar och designer med kärnkomponenterna som byggstenar.

## Glöm inte kraftfulla funktioner {#powerful-features}

Funktioner för AEM och grundkomponenterna kan vara mycket kraftfulla, men också mycket subtila, och möjligheterna till vissa funktioner kanske inte är direkt uppenbara för en designer.

### Innehållsfragment {#content-fragments}

[Innehållsfragment](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/content-fragments.html) gör att du kan skapa kanalneutralt innehåll tillsammans med (eventuellt kanalspecifika) variationer. Du kan sedan använda dessa fragment och deras variationer när du redigerar innehållssidorna.

Tillsammans med den uppdaterade JSON-exporteraren kan strukturerade innehållsfragment även användas för att leverera AEM innehåll via Content Services till andra kanaler än AEM.

### Upplevelsefragmentmallar {#experience-fragment-templates}

Om en författare vill återanvända delar (ett fragment av en upplevelse) av en sida. Utan [Experience Fragments,](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/experience-fragments.html) författaren måste kopiera och klistra in det fragmentet. Att skapa och underhålla dessa klipp-och-klistra-upplevelser är tidskrävande och leder ofta till användarfel. Upplevelsefragment eliminerar behovet av att kopiera/klistra in.

### Komponenten Embed {#embed-component}

[Komponenten Embed](/help/components/embed.md) gör det inte bara möjligt att inkludera externa resurser som YouTube videoinnehåll, utan även att göra det möjligt för det att rymma innehåll som är specifikt för ett projekts behov.
