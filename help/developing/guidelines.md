---
title: Riktlinjer för komponenter
description: Core Components följer moderna implementeringsmönster som skiljer sig mycket från grundkomponenterna.
role: Arkitekt, utvecklare, administratör
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '1262'
ht-degree: 1%

---


# Riktlinjer för komponenter {#component-guidelines}

[Kärnkomponenterna](overview.md) följer moderna implementeringsmönster som skiljer sig mycket från grundkomponenterna.

På den här sidan förklaras de här mönstren och när du ska använda dem för att skapa egna författarskapande komponenter. Det första avsnittet [Allmänna komponentmönster](#general-component-patterns) gäller alla typer av komponenter, medan det andra avsnittet [Återanvändbara komponentmönster](#reusable-component-patterns) gäller komponenter som är avsedda att återanvändas på platser eller i projekt, till exempel kärnkomponenter.

## Allmänna komponentmönster {#general-component-patterns}

Riktlinjerna i det här avsnittet rekommenderas för alla typer av komponenter, oavsett om komponenten är specifik för ett enskilt projekt eller om komponenten är avsedd att återanvändas i stor omfattning på webbplatser eller i projekt.

### Konfigurerbara komponenter {#configurable-components}

Komponenter kan ha dialogrutor med en mängd olika alternativ. Detta bör utnyttjas för att göra komponenterna flexibla och konfigurerbara och undvika att implementera flera komponenter som i huvudsak är varianter av varandra.

Om en trådram eller design innehåller variationer av liknande element bör dessa variationer vanligtvis inte implementeras som olika komponenter, utan som den enda komponenten med alternativ att välja mellan variationerna.

Om du vill gå ett steg längre och återanvända komponenter mellan platser eller projekt läser du avsnittet [Förkonfigurerbara funktioner](#pre-configurable-capabilities).

### Separation av oro {#separation-of-concerns}

Att hålla logiken (eller modellen) för en komponent åtskild från markeringsmallen (eller vyn) är vanligtvis en bra vana. Det finns flera sätt att uppnå det, men det rekommenderas att du använder [delningsmodeller](https://sling.apache.org/documentation/bundles/models.html) för logiken och [HTML-mallspråk](https://docs.adobe.com/content/help/en/experience-manager-htl/using/overview.html) (HTL) för koden, precis som Core Components också gör.

Sling Models är en uppsättning Java-anteckningar som gör det enkelt att komma åt nödvändiga variabler från POJO:er och därför erbjuder ett enkelt, kraftfullt och effektivt sätt att implementera Java-logik för komponenter.

HTML har utformats för att vara ett säkert och enkelt mallspråk som är anpassat för AEM. Det kan kalla många typer av logik, vilket gör den mycket flexibel.

## Återanvändbara komponentmönster {#reusable-component-patterns}

Riktlinjerna i det här avsnittet kan även användas för alla typer av komponenter, men de passar bäst för komponenter som är avsedda att återanvändas på webbplatser eller i projekt, som till exempel kärnkomponenterna. Dessa riktlinjer kan därför ignoreras för komponenter som bara används på en enda plats eller ett enda projekt.

### Förkonfigurerbara funktioner {#pre-configurable-capabilities}

Förutom redigeringsdialogrutan som används av sidförfattare kan komponenterna även ha en designdialogruta där mallförfattare kan förkonfigurera dem. Med [mallredigeraren](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html) kan du konfigurera alla dessa förkonfigurationer, som kallas för &quot;Principer&quot;.

För att göra komponenterna så återanvändbara som möjligt bör de ha meningsfulla alternativ för förkonfiguration. Detta gör att du kan aktivera eller inaktivera funktioner i komponenterna för att passa de specifika behoven på olika platser.

### Proxykomponentmönster {#proxy-component-pattern}

Eftersom varje innehållsresurs har en `sling:resourceType`-egenskap som refererar till komponenten för att återge den, är det oftast bra att låta dessa egenskaper peka på platsspecifika komponenter, i stället för att peka på komponenter som delas av flera platser. Detta ger större flexibilitet och undviker innehållsomfaktorisering om en webbplats behöver ett annat beteende för en komponent, eftersom den här anpassningen då kan göras på den platsspecifika komponenten och inte påverkar de andra platserna.

Om de projektspecifika komponenterna inte ska duplicera någon kod bör de referera till den delade överordnade komponenten med egenskapen `sling:resourceSuperType`. Dessa projektspecifika komponenter som oftast bara refererar till överordnade komponenter kallas&quot;proxykomponenter&quot;. Proxykomponenter kan vara helt tomma om de helt ärver funktionaliteten, eller så kan de definiera om vissa aspekter av komponenten.

### Komponentversionshantering {#component-versioning}

Komponenterna bör vara helt kompatibla över tid, men ibland krävs ändringar som inte kan hållas kompatibla. En lösning på de motsatta behoven är att införa komponentversionshantering genom att lägga till en siffra i resurstypsökvägen och i de fullständiga Java-klassnamnen för implementeringarna. Det här versionsnumret representerar en huvudversion enligt definitionen i [riktlinjerna för semantisk versionshantering](https://semver.org/), som endast ökas för ändringar som inte är bakåtkompatibla.

Inkompatibla ändringar i följande aspekter av komponenterna resulterar i en ny version av dem:

* Sling Models (i enlighet med riktlinjerna för semantisk versionshantering)
* HTML-skript och mallar
* HTML-kod och CSS-väljare
* JSON-representation
* Dialogrutor

Mer information finns i dokumentet [Versionsprinciper](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-Policies) i GitHub.

Komponentversionshantering skapar en typ av kontrakt som är viktig för uppgraderingar eftersom den klargör när något behöver ändras. Se även avsnittet [Upgrade Compatibility of Customizations](customizing.md#upgrade-compatibility-of-customizations), där det förklaras vilka överväganden olika former av anpassningar kräver för en uppgradering.

För att undvika krånglig innehållsmigrering är det viktigt att aldrig peka direkt på versionskomponenter från innehållsresurser. Som tumregel får inte en `sling:resourceType`-komponent ha något versionsnummer i innehållet, eller om du uppgraderar komponenter måste innehållet omfaktoriseras också. Det bästa sättet att undvika detta är att följa det [Proxykomponentmönster](#proxy-component-pattern) som beskrivs ovan.

### Modellgränssnitt {#model-interfaces}

Det här mönstret handlar om HTML:s `data-sly-use`-instruktion att peka på ett Java-gränssnitt, medan implementeringen av Sling Model också registrerar sig själv för komponentens resurstyp.

I kombination med [Proxy Component Pattern](#proxy-component-pattern) som beskrivs ovan erbjuder den här typen av dubbelbindning följande fina tilläggspunkter:

1. En webbplats kan definiera om implementeringen av en Sling-modell genom att registrera den i proxykomponentens resurstyp, utan att behöva tänka på HTML-filen, som fortfarande kan peka på gränssnittet.
1. En webbplats kan definiera om HTML-koden för en komponent, utan att behöva tänka på vilken implementeringslogik den ska peka på.

## Samla allt {#putting-it-all-together}

Nedan visas en översikt över hela bindningsstrukturen för resurstyper, som i exemplet med kärnkomponenten Title. Det visar hur en platsspecifik proxykomponent kan lösa komponentversionshantering, så att innehållsresursen inte innehåller något versionsnummer. Sedan visas hur komponentens `title.html` [HTML](https://docs.adobe.com/content/help/en/experience-manager-htl/using/overview.html)-fil använder i modellgränssnittet, medan implementeringen binder till den specifika versionen av komponenten via [Sling Model](https://sling.apache.org/documentation/bundles/models.html)-anteckningar.

![Översikt över resursbindning](/help/assets/chlimage_1-32.png)

Nedan finns en annan översikt som inte visar information om implementeringens POJO, men som visar hur associerade [mallar och profiler](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/components-templates/templates.html) refereras.

Egenskapen `cq:allowedTemplates` anger vilka mallar som kan användas för en plats och `cq:template` anger för varje sida vilken mall som är associerad. Varje mall består av följande tre delar:

* **struktur**  - Innehåller de resurser som ska framtvingas på varje sida för att vara närvarande och som sidförfattaren inte kan ta bort, till exempel sidhuvuds- och sidfotskomponenterna.
* **initial**  - Innehåller det ursprungliga innehåll som ska dupliceras till sidan när den skapas.
* **policies**  - Innehåller för varje komponent mappningen till en princip, som är komponentens förkonfiguration. Med den här mappningen kan profiler återanvändas i olika mallar och därför hanteras centralt.

![Mallar och principöversikt](/help/assets/screen_shot_2018-12-07at093102.png)

## AEM Project Archetype {#aem-project-archetype}

[Med AEM Project ](/help/developing/archetype/overview.md) Archetypectres skapas ett minimalt Adobe Experience Manager-projekt som startpunkt för dina egna projekt, inklusive ett exempel på anpassade HTML-komponenter med SlingModels för logik och korrekt implementering av Core Components med det rekommenderade proxymönstret.

**Läs nästa:**

* [Med Core Components](/help/get-started/using.md)  - kom igång med Core Components i ditt eget projekt.
* [Anpassa kärnkomponenter](customizing.md)  för att lära dig hur du formaterar och anpassar kärnkomponenterna.
