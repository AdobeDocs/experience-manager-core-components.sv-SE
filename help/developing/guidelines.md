---
title: Riktlinjer för komponenter
description: Core Components följer moderna implementeringsmönster som skiljer sig mycket från grundkomponenterna.
role: Architect, Developer, Admin
exl-id: e8c58fa5-c991-433c-8d38-575dacfc3433
source-git-commit: ee18626280f74a51a799f16d6bf3f5b0be9cd6b9
workflow-type: tm+mt
source-wordcount: '1227'
ht-degree: 0%

---

# Riktlinjer för komponenter {#component-guidelines}

[Kärnkomponenterna](overview.md) följer moderna implementeringsmönster som skiljer sig mycket från grundkomponenterna.

På den här sidan förklaras de här mönstren och när du ska använda dem för att skapa egna författarskapande komponenter. Det första avsnittet [Allmänna komponentmönster](#general-component-patterns) gäller alla typer av komponenter, medan det andra avsnittet [Återanvändbara komponentmönster](#reusable-component-patterns) gäller komponenter som är avsedda att återanvändas på platser eller i projekt, till exempel kärnkomponenter.

## Allmänna komponentmönster {#general-component-patterns}

Riktlinjerna i det här avsnittet rekommenderas för alla typer av komponenter, oavsett om komponenten är specifik för ett enskilt projekt eller om komponenten är avsedd att återanvändas i stor omfattning på webbplatser eller i projekt.

### Konfigurerbara komponenter {#configurable-components}

Komponenter kan ha dialogrutor med en mängd olika alternativ. Detta bör utnyttjas för att göra komponenterna flexibla och konfigurerbara och undvika att implementera flera komponenter som i huvudsak är varianter av varandra.

Om en trådram eller design innehåller variationer av liknande element bör dessa variationer vanligtvis inte implementeras som olika komponenter, utan som den enda komponenten med alternativ att välja mellan variationerna.

Om du vill gå ett steg längre och återanvända komponenter mellan webbplatser eller projekt läser du avsnittet [Förkonfigurerbara funktioner](#pre-configurable-capabilities).

### Separation av oro {#separation-of-concerns}

Att hålla logiken (eller modellen) för en komponent åtskild från markeringsmallen (eller vyn) är vanligtvis en bra vana. Det finns flera sätt att uppnå det, men det rekommenderas att du använder [segmentmodeller](https://sling.apache.org/documentation/bundles/models.html) för logiken och [HTML-mallspråk](https://experienceleague.adobe.com/docs/experience-manager-htl/using/overview.html?lang=sv-SE) (HTL) för koden, precis som med kärnkomponenterna.

Sling Models är en uppsättning Java-anteckningar som gör det enkelt att komma åt nödvändiga variabler från POJO:er och därför erbjuder ett enkelt, kraftfullt och effektivt sätt att implementera Java-logik för komponenter.

HTML har utformats för att vara ett säkert och enkelt mallspråk som är anpassat för AEM. Det kan kalla många typer av logik, vilket gör den mycket flexibel.

## Återanvändbara komponentmönster {#reusable-component-patterns}

Riktlinjerna i det här avsnittet kan även användas för alla typer av komponenter, men de passar bäst för komponenter som är avsedda att återanvändas på webbplatser eller i projekt, som till exempel kärnkomponenterna. Dessa riktlinjer kan därför ignoreras för komponenter som bara används på en enda plats eller ett enda projekt.

### Förkonfigurerbara funktioner {#pre-configurable-capabilities}

Förutom redigeringsdialogrutan som används av sidförfattare kan komponenterna även ha en designdialogruta där mallförfattare kan förkonfigurera dem. Med [mallredigeraren](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=sv-SE) kan du konfigurera alla dessa förkonfigurationer, som kallas för principer.

För att göra komponenterna så återanvändbara som möjligt bör de ha meningsfulla alternativ för förkonfiguration. Detta gör att du kan aktivera eller inaktivera funktioner i komponenterna för att passa de specifika behoven på olika platser.

### Proxykomponentmönster {#proxy-component-pattern}

Eftersom varje innehållsresurs har en `sling:resourceType`-egenskap som refererar till komponenten för att återge den, är det oftast bra att låta dessa egenskaper peka på platsspecifika komponenter, i stället för att peka på komponenter som delas av flera platser. Detta ger större flexibilitet och undviker innehållsomfaktorisering om en webbplats behöver ett annat beteende för en komponent, eftersom den här anpassningen då kan göras på den platsspecifika komponenten och inte påverkar de andra platserna.

Om de projektspecifika komponenterna inte ska duplicera någon kod bör de referera till den delade överordnade komponenten med egenskapen `sling:resourceSuperType`. Dessa projektspecifika komponenter som oftast bara refererar till överordnade komponenter kallas&quot;proxykomponenter&quot;. Proxykomponenter kan vara helt tomma om de helt ärver funktionaliteten, eller så kan de definiera om vissa aspekter av komponenten.

>[!TIP]
>
>Mer information om hur du skapar proxykomponenter finns i [Använda kärnkomponenter](/help/get-started/using.md#create-proxy-components).

### Komponentversionshantering {#component-versioning}

Komponenterna bör vara helt kompatibla över tid, men ibland krävs ändringar som inte kan hållas kompatibla. En lösning på de motsatta behoven är att införa komponentversionshantering genom att lägga till en siffra i resurstypsökvägen och i de fullständiga Java-klassnamnen för implementeringarna. Det här versionsnumret representerar en huvudversion enligt definitionen i [riktlinjerna för semantisk versionshantering](https://semver.org/), som endast ökas för ändringar som inte är bakåtkompatibla.

Inkompatibla ändringar i följande aspekter av komponenterna resulterar i en ny version av dem:

* Sling Models (i enlighet med riktlinjerna för semantisk versionshantering)
* HTML-skript och mallar
* HTML Markup och CSS-väljare
* JSON-representation
* Dialogrutor

Mer information finns i dokumentet [Versionsprinciper](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-Policies) i GitHub.

Komponentversionshantering skapar en typ av kontrakt som är viktig för uppgraderingar eftersom den klargör när något behöver ändras. Se även avsnittet [Kompatibilitet för uppgradering av anpassningar](customizing.md#upgrade-compatibility-of-customizations), där det förklaras vilka överväganden olika former av anpassningar kräver för en uppgradering.

För att undvika krånglig innehållsmigrering är det viktigt att aldrig peka direkt på versionskomponenter från innehållsresurser. Som tumregel får en/ett `sling:resourceType` av innehållet aldrig ha något versionsnummer, annars måste innehållet omfaktoriseras om för att kunna uppgradera komponenter. Det bästa sättet att undvika detta är att följa [Proxykomponentmönstret](#proxy-component-pattern) som beskrivs ovan.

### Modellgränssnitt {#model-interfaces}

Det här mönstret handlar om HTML:s `data-sly-use`-instruktion att peka på ett Java-gränssnitt, medan implementeringen av Sling-modellen också registrerar sig för komponentens resurstyp.

I kombination med det [Proxy-komponentmönster](#proxy-component-pattern) som beskrivs ovan erbjuder den här typen av dubbelbindning följande fina tilläggspunkter:

1. En webbplats kan definiera om implementeringen av en Sling-modell genom att registrera den i proxykomponentens resurstyp, utan att behöva tänka på HTML-filen, som fortfarande kan peka på gränssnittet.
1. En webbplats kan definiera om HTML-koden för en komponent, utan att behöva tänka på vilken implementeringslogik den ska peka på.

## Sammanställ allt {#putting-it-all-together}

Nedan visas en översikt över hela bindningsstrukturen för resurstyper, som i exemplet med kärnkomponenten Title. Det visar hur en platsspecifik proxykomponent kan lösa komponentversionshantering, så att innehållsresursen inte innehåller något versionsnummer. Sedan visas hur komponentens `title.html` [HTL](https://experienceleague.adobe.com/docs/experience-manager-htl/using/overview.html?lang=sv-SE) -fil använder i modellgränssnittet, medan implementeringen binder till den specifika versionen av komponenten via [Sling Model](https://sling.apache.org/documentation/bundles/models.html) -anteckningar.

![Resursbindningsöversikt](/help/assets/chlimage_1-32.png)

Nedan finns en annan översikt som inte visar information om implementeringens POJO, men som visar hur de associerade [mallarna och profilerna](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/full-stack/components-templates/templates.html?lang=sv-SE) refereras.

Egenskapen `cq:allowedTemplates` anger vilka mallar som kan användas för en plats och `cq:template` anger för varje sida vilken mall som är associerad. Varje mall består av följande tre delar:

* **struktur** - Innehåller resurser som kommer att tvingas att finnas på varje sida och som sidförfattaren inte kommer att kunna ta bort, till exempel sidhuvuds- och sidfotskomponenterna.
* **initial** - Innehåller det ursprungliga innehåll som ska dupliceras till sidan när den skapas.
* **profiler** - Innehåller för varje komponent mappningen till en princip, som är komponentens förkonfiguration. Med den här mappningen kan profiler återanvändas i olika mallar och därför hanteras centralt.

![Mallar och principöversikt](/help/assets/screen_shot_2018-12-07at093102.png)

## AEM Project Archettype {#aem-project-archetype}

[AEM Project Archetype](/help/developing/archetype/overview.md) skapar ett minimalt Adobe Experience Manager-projekt som startpunkt för dina egna projekt, inklusive ett exempel på anpassade HTML-komponenter med SlingModels för logik och korrekt implementering av Core Components med det rekommenderade proxymönstret.

**Läs nästa:**

* [Använda kärnkomponenter](/help/get-started/using.md) - Kom igång med Core Components i ditt eget projekt.
* [Anpassa kärnkomponenter](customizing.md) - för att lära dig hur du formaterar och anpassar kärnkomponenterna.
