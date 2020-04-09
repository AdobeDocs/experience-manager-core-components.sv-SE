---
title: Sökvägar till framgång med kärnkomponenterna
description: Så här lyckas du när du implementerar ditt projekt med Core Components
translation-type: tm+mt
source-git-commit: c338428a681f652d17bb972fb6a2abf216a338c3

---


# Sökvägar till framgång med kärnkomponenterna {#paths-to-success}

Core Components är kraftfulla, flexibla och enkla att använda och anpassa. Om du följer några riktlinjer som beskrivs i det här dokumentet kommer ditt projekt med kärnkomponenterna att bli framgångsrikt.

## Två sökvägar till framgång {#two-paths}

Det finns två grundläggande strategier för att genomföra de centrala komponenterna, som kan leda till framgång men som har egna kompromisser som måste beaktas på projektbasis.

1. Mappa dina designer till de centrala komponenterna och ta den HTML som de tillhandahåller. eller
1. Om du måste följa redan definierade HTML-standarder behöver du mer arbete och får inte alla fördelarna med kärnkomponenterna.

## Vanliga fallgropar i komponentimplementering {#common-pitfalls}

Två vanliga problem som leder till att projekt inte lyckas med kärnkomponenter är:

* **Slutför designen** - dessa kan till och med vara godkända på C-nivå och skickas vidare till utvecklingsgruppen för att implementeras pixelperfekt utan att behöva bekymra sig om den underliggande tekniken.
* **En företagsomfattande HTML-formatguide** - sådana stödlinjer måste följas för ofta av komponenterna som använder format uppifrån och ned.

I båda fallen är de krav som ställs på komponenterna så täta och specifika att det är svårt att få Core-komponenterna eller komponenter som inte ingår i paketet att uppfylla dem, vilket leder till en enorm utveckling av anpassade komponenter.

## Starta tidigt {#start-early}

I stället för att bara ta hänsyn till kärnkomponenterna i projektets implementeringsfas börjar du redan med kärnkomponenterna under trådrams- och designfasen.

### Använda komponentbiblioteket {#component-library}

Referera till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library) som redan är i designfasen. Core Components är kraftfulla och flexibla och kan ta dig långt som en startpunkt. Lägg bara till anpassade komponenter när det finns ett verkligt affärsbehov som verkligen inte kan uppnås med en Core-komponent.

### Använda UI Kit för Adobe XD {#ui-kit}

Så snart det finns ett bevisat behov av en anpassad komponent kan du utnyttja [UI-paketet för Adobe XD](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/assets/overview/AEM_UI-kit_Wireframe.xd) så att designers kan börja bygga trådramar och designer med Core Components som byggstenar.

## Glöm inte kraftfulla funktioner {#powerful-features}

Funktioner i AEM och Core Components kan vara mycket kraftfulla, men också mycket subtila, och möjligheterna till vissa funktioner kanske inte är direkt uppenbara för en designer.

### Innehållsfragment {#content-fragments}

[Med innehållsfragment](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/content-fragments.html) kan du skapa kanalneutralt innehåll tillsammans med (eventuellt kanalspecifika) variationer. Du kan sedan använda dessa fragment och deras variationer när du redigerar innehållssidorna.

Tillsammans med den uppdaterade JSON-exporteraren kan strukturerade innehållsfragment även användas för att leverera AEM-innehåll via Content Services till andra kanaler än AEM-sidor.

### Upplevelsefragmentmallar {#experience-fragment-templates}

Om en författare vill återanvända delar (ett fragment av en upplevelse) av en sida. Utan [Experience Fragments](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/experience-fragments.html) skulle författaren behöva kopiera och klistra in det fragmentet. Att skapa och underhålla dessa klipp-och-klistra-upplevelser är tidskrävande och leder ofta till användarfel. Upplevelsefragment eliminerar behovet av att kopiera/klistra in.

### Komponenten Embed {#embed-component}

[Med inbäddningskomponenten](/help/components/embed.md) kan du inte bara inkludera externa resurser som YouTube-videoinnehåll, utan även utbyggbart så att det kan rymma innehåll som är specifikt för ett projekts behov.