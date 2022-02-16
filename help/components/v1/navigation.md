---
title: Navigeringskomponent (v1)
description: Med Navigation Component (Navigeringskomponent) kan användarna enkelt navigera i en globaliserad platsstruktur.
role: Architect, Developer, Admin, User
source-git-commit: e5251010ca41025eb2bb56b66164ecf4cc0145c8
workflow-type: tm+mt
source-wordcount: '1430'
ht-degree: 0%

---


# Navigeringskomponent (v1) {#navigation-component}

Med Navigation Component (Navigeringskomponent) kan användarna enkelt navigera i en globaliserad platsstruktur.

## Användning {#usage}

Navigeringskomponenten listar ett träd med sidor så att användare på en webbplats enkelt kan navigera i webbplatsstrukturen.

Navigeringskomponenten kan automatiskt identifiera platsens globala struktur och [anpassa automatiskt till en lokaliserad sida.](#localized-site-structure) Dessutom kan den ha stöd för valfri webbplatsstruktur genom att använda [omdirigeringssidor för skuggor](#shadow-structure) för att representera en annan struktur än den som är huvudinnehållsstrukturen.

The [redigeringsdialogruta](#edit-dialog) gör att innehållsförfattaren kan definiera navigeringsrotsidan tillsammans med navigeringsdjupet. The [designdialogruta](#design-dialog) gör att mallskaparen kan definiera standardvärden för navigeringsroten och -djupet.

## Version och kompatibilitet {#version-and-compatibility}

I det här dokumentet beskrivs v1 i Navigation Component, som introducerades i version 2.0.0 av Core Components i januari 2018.

>[!CAUTION]
>
>I det här dokumentet beskrivs v1 för navigeringskomponenten.
>
>Information om den aktuella versionen av navigeringskomponenten finns i [Navigeringskomponent](/help/components/navigation.md) -dokument.

## Lokaliserat stöd för webbplatsstruktur {#localized-site-structure}

Webbplatser finns ofta på flera språk för olika regioner. Vanligtvis innehåller varje lokaliserad sida ett navigeringselement som ingår i sidmallen. Med navigeringskomponenten kan du placera den en gång i en mall för alla sidor på platsen, och den anpassas sedan automatiskt för de enskilda lokaliserade sidorna baserat på den globaliserade webbplatsstrukturen.

* Ett exempel på hur lokaliseringsfunktionen för navigeringskomponenten fungerar finns i [avsnittet nedan](#example-localization).
* Ett exempel på hur lokaliseringsfunktionerna för kärnkomponenterna fungerar tillsammans finns i [Lokaliseringsfunktioner för sidan Core Components](/help/get-started/localization.md).

### Exempel {#example-localization}

Låt oss säga att innehållet ser ut ungefär så här:

```
/content
+-- wknd
   +-- language-masters
      +-- de
         \-- experience
            \-- arctic-surfing-in-lofoten
      +-- en
         \-- experience
            \-- arctic-surfing-in-lofoten
      +-- es
      +-- fr
      \-- it
   +-- us
      +-- en
         \-- experience
            \-- arctic-surfing-in-lofoten
      \-- es
   \-- ch
      +-- de
         \-- experience
            \-- arctic-surfing-in-lofoten
      +-- fr
      \-- it
+-- wknd-events
\-- wknd-shop
```

För platsen WKND vill du förmodligen placera navigeringskomponenten i en sidmall som en del av sidhuvudet. När du är en del av mallen kan du ange **Navigeringsrot** för komponenten till `/content/wknd/language-masters/en` eftersom det är där ditt överordnad innehåll för den webbplatsen börjar. Du kanske också vill ange **Navigeringsstrukturens djup** att `2` eftersom du förmodligen inte vill att hela innehållsträdet ska visas av komponenten, utan snarare de två första nivåerna så att det fungerar som en översikt.

Med **Navigeringsrot** värdet vet Navigation Component att efter `/content/wknd/language-masters/en` som navigeringen börjar med och kan generera navigeringsalternativ genom att repetera platsens struktur två nivåer nedåt (som definieras av **Navigeringsstrukturens djup** värde).

Oavsett vilken lokaliserad sida en användare visar kan navigeringskomponenten hitta motsvarande lokaliserad sida genom att känna till platsen för den aktuella sidan, arbeta bakåt till roten och sedan vidarebefordra till motsvarande sida.

Så om en besökare tittar `/content/ch/de/experience/arctic-surfing-in-lofoten`kan komponenten generera navigeringsstrukturen baserat på `/content/wknd/language-masters/de`. Detsamma gäller om besökaren tittar `/content/us/en/experience/arctic-surfing-in-lofoten`kan komponenten generera navigeringsstrukturen baserat på `/content/wknd/language-masters/en`.

## Stöd för Shadow Site Structure {#shadow-structure}

Ibland är det nödvändigt att skapa en navigeringsmeny för besökaren som skiljer sig från den faktiska platsstrukturen. En kampanj kanske ska lyfta fram visst innehåll på menyn genom att ordna om innehållslistan. Med hjälp av skuggsidor, som helt enkelt omdirigeras till andra innehållssidor, kan navigeringskomponenten generera en godtycklig navigeringsstruktur som behövs.

För att göra detta måste du:

1. Skapa skuggsidor som tomma sidor som representerar den önskade webbplatsstrukturen. Detta kallas ofta för en skuggplatsstruktur.
1. Ange **Omdirigering** värden i sidegenskaperna på dessa sidor så att de pekar på de faktiska innehållssidorna.
1. Ange **Dölj i navigering** i sidegenskaperna för skuggsidorna.
1. Ange **Navigeringsrot** Navigeringskomponentens värde så att det pekar på roten för den nya skuggwebbplatsstrukturen.

Navigeringskomponenten återger sedan menyn baserat på skuggwebbplatsens struktur. Länkarna som återges av komponenten är de faktiska innehållssidorna som skuggsidorna dirigerar om till och inte till själva skuggsidorna. Dessutom visar komponenten namnen på de faktiska sidorna och markerar den aktiva sidan korrekt, även när navigeringen baseras på skuggsidor. Navigeringskomponenten gör skuggsidorna helt genomskinliga för besökaren.

>[!NOTE]
>Skuggsidor gör navigeringsalternativen mycket mer flexibla, men tänk på att det är helt manuellt att behålla strukturen. Om du sorterar om det faktiska webbplatsinnehållet eller lägger till/tar bort innehåll måste du uppdatera skuggstrukturen manuellt efter behov.

>[!NOTE]
>När du återger en skuggwebbplatsstruktur är det bara skuggsidorna som rekursiveras av navigeringslogiken. Logiken ger inte en rekursiv omdirigering av destinationerna.

## Omdirigeringar i navigering {#redirects}

När en sida har ett omdirigeringsmål (oavsett om det pekar på en extern URL eller en annan AEM sida), är det en navigeringskomponent som innehåller länkar till den punkten direkt till URL:en för omdirigeringsmålet.

### Exempel {#redirect-example}

* Skapa en sida A som dirigeras om till sida B.
* Skapa en sida C som dirigeras om till `https://aemcomponents.dev`
* På en sida D infogar du en komponent eller navigeringskomponent som innehåller sidorna A och C
* De länkar som skapas pekar sedan direkt på sidan B och `https://aemcomponents.dev`

## Exempel på komponentutdata {#sample-component-output}

Om du vill visa navigeringskomponenten och se exempel på dess konfigurationsalternativ samt HTML och JSON-utdata går du till [Komponentbibliotek](https://adobe.com/go/aem_cmp_library_navigation).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om navigeringskomponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_navigation_v1).

Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

>[!NOTE]
>
>Från och med Core Components version 2.1.0 stöder Navigation Components [schema.org, mikrodata](https://schema.org).

## Dialogrutan Redigera {#edit-dialog}

I redigeringsdialogrutan kan innehållsförfattaren definiera rotsidan för navigering och navigeringsstrukturens djup.

### Fliken Egenskaper {#properties-tab}

![Egenskaper för redigeringsdialogruta i navigeringskomponenten](/help/assets/navigation-edit-properties.png)

* **Navigeringsrot** - Rotsidan som ska användas för att generera navigeringsträdet.
* **Uteslut rotnivåer** - Ofta ska roten inte tas med i navigeringen. Med det här alternativet kan du ange hur många nivåer upp från roten som du vill utesluta. Till exempel:
   * 0 = visa rotnivån
   * 1 = utelämna rotnivån
   * 2 = exkludera roten och ytterligare 1 nivå upp
   * osv.
* **Samla in alla underordnade sidor** - Samla in alla sidor som är underordnade navigeringsroten.
* **Navigeringsstrukturens djup** - Definierar hur många nivåer i navigeringsträdet som komponenten ska visa i förhållande till navigeringsroten (endast tillgängligt när **Samla in alla underordnade sidor** är inte markerat).
* **Inaktivera skuggning** - Om sidan i hierarkin är en omdirigering visas namnet på omdirigeringssidan i stället för målet. Se [Stöd för Shadow Site Structure](#shadow-structure) för mer information.
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [Datalager](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

### Fliken Tillgänglighet {#accessibility-tab}

![Navigeringskomponentens flik för redigeringsdialogruta för tillgänglighet](/help/assets/navigation-edit-accessibility.png)

På **Tillgänglighet** -tabb kan värden anges för [Tillgänglighet för ARIA](https://www.w3.org/WAI/standards-guidelines/aria/) -etiketter för komponenten.

* **Etikett** - Värdet på ett ARIA-etikettattribut för komponenten

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen ange standardvärden för navigeringsrotsidan och navigeringsdjupet som presenteras för innehållsförfattarna.

### Fliken Egenskaper {#properties-tab-design}

![Designdialogrutan för navigeringskomponenten](/help/assets/navigation-design.png)

* **Navigeringsrot** - Standardvärdet för navigeringsstrukturens rotsida, som kommer att användas för att generera navigeringsträdet och som standard när innehållsförfattaren lägger till komponenten på sidan.
* **Uteslut rotnivåer** - Ofta ska roten inte tas med i navigeringen. Med det här alternativet kan du ange standardvärdet för hur många nivåer uppåt från roten som du vill utesluta. Till exempel:
   * 0 = visa rotnivån
   * 1 = utelämna rotnivån
   * 2 = exkludera roten och ytterligare 1 nivå upp
   * osv.
* **Samla in alla underordnade sidor** - Standardvärdet för alternativet att samla alla sidor som är underordnade navigeringsroten.
* **Navigeringsstrukturens djup** - Standardvärdet för navigeringsstrukturens djup.
* **Inaktivera skuggning** - Standardvärdet för om skuggning ska inaktiveras när en navigeringskomponent läggs till

### Fliken Format {#styles-tab}

Navigeringskomponenten har stöd för AEM [Formatsystem](/help/get-started/authoring.md#component-styling).

## Adobe-klientdatalager {#data-layer}

Navigeringskomponenten har stöd för [Adobe Client Data Layer.](/help/developing/data-layer/overview.md)
