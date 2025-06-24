---
title: Navigeringskomponent
description: Med Navigation Component (Navigeringskomponent) kan användarna enkelt navigera i en globaliserad platsstruktur.
role: Architect, Developer, Admin, User
exl-id: 9154f2a3-3d1e-4865-a413-298748fa66d3
source-git-commit: dd30def59a8f037864da875ef4c831b11f766e57
workflow-type: tm+mt
source-wordcount: '1544'
ht-degree: 0%

---


# Navigeringskomponent{#navigation-component}

Med Navigation Component (Navigeringskomponent) kan användarna enkelt navigera i en globaliserad platsstruktur.

{{traditional-aem}}

## Användning {#usage}

Navigeringskomponenten listar ett träd med sidor så att användare på en webbplats enkelt kan navigera i webbplatsstrukturen.

Navigeringskomponenten kan automatiskt identifiera platsens globaliserade struktur och [anpassa automatiskt till en lokaliserad sida.](#localized-site-structure) Dessutom kan den ha stöd för valfri struktur för godtycklig plats genom att använda [skuggomdirigeringssidor](#shadow-structure) för att representera en annan struktur än huvudinnehållsstrukturen.

I [redigeringsdialogrutan](#edit-dialog) kan innehållsförfattaren definiera navigeringsrotsidan tillsammans med navigeringsdjupet. I [designdialogrutan](#design-dialog) kan mallskaparen definiera standardvärden för navigeringsroten och -djupet.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Navigation Component är v2, som introducerades i version 2.18.0 av Core Components i februari 2022, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponenterna är kompatibla med samt länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|--- |--- |--- |---|---|
| v2 | - | Kompatibel | Kompatibel | Kompatibel |
| [v1](v1/navigation.md) | Kompatibel | Kompatibel | - | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Core Components Versions](/help/versions.md).

## Lokaliserat stöd för webbplatsstruktur {#localized-site-structure}

Webbplatser finns ofta på flera språk för olika regioner. Vanligtvis innehåller varje lokaliserad sida ett navigeringselement som ingår i sidmallen. Med navigeringskomponenten kan du placera den en gång i en mall för alla sidor på platsen, och den anpassas sedan automatiskt för de enskilda lokaliserade sidorna baserat på den globaliserade webbplatsstrukturen.

* Ett exempel på hur lokaliseringsfunktionen för navigeringskomponenten fungerar finns i [avsnittet nedan](#example-localization).
* Ett exempel på hur lokaliseringsfunktionerna för kärnkomponenterna fungerar tillsammans finns i [Lokaliseringsfunktioner på sidan för kärnkomponenter](/help/get-started/localization.md).

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

För platsen WKND vill du förmodligen placera navigeringskomponenten i en sidmall som en del av sidhuvudet. När du är en del av mallen kan du ange **navigeringsrot** för komponenten till `/content/wknd/language-masters/en` eftersom det är där huvudinnehållet för den webbplatsen börjar. Du kanske också vill ange **Navigeringsstrukturdjupet** till `2` eftersom du antagligen inte vill att hela innehållsträdet ska visas av komponenten, utan i stället de två första nivåerna så att det fungerar som en översikt.

Med värdet **Navigeringsrot** vet navigeringskomponenten att efter `/content/wknd/language-masters/en` som navigeringen börjar och kan generera navigeringsalternativ genom att repetera platsens struktur två nivåer nedåt (enligt värdet för **Navigeringsstrukturens djup** ).

Oavsett vilken lokaliserad sida en användare visar kan navigeringskomponenten hitta motsvarande lokaliserad sida genom att känna till platsen för den aktuella sidan, arbeta bakåt till roten och sedan vidarebefordra till motsvarande sida.

Om en besökare visar `/content/ch/de/experience/arctic-surfing-in-lofoten` kan komponenten generera navigeringsstrukturen baserat på `/content/wknd/language-masters/de`. Om besökaren visar `/content/us/en/experience/arctic-surfing-in-lofoten` kan komponenten också generera navigeringsstrukturen baserat på `/content/wknd/language-masters/en`.

## Stöd för Shadow Site Structure {#shadow-structure}

Ibland är det nödvändigt att skapa en navigeringsmeny för besökaren som skiljer sig från den faktiska platsstrukturen. En kampanj kanske ska lyfta fram visst innehåll på menyn genom att ordna om innehållslistan. Med hjälp av skuggsidor, som helt enkelt omdirigeras till andra innehållssidor, kan navigeringskomponenten generera en godtycklig navigeringsstruktur som behövs.

För att göra detta måste du:

1. Skapa skuggsidor som tomma sidor som representerar den önskade webbplatsstrukturen. Detta kallas ofta för en skuggplatsstruktur.
1. Ange värdena för **Omdirigering** i sidegenskaperna på de här sidorna så att de pekar på de faktiska innehållssidorna.
1. Ange alternativet **Dölj i navigering** i sidegenskaperna för skuggsidorna.
1. Ange värdet **Navigeringsrot** för navigeringskomponenten så att det pekar på roten för den nya skuggwebbplatsstrukturen.

Navigeringskomponenten återger sedan menyn baserat på skuggwebbplatsens struktur. Länkarna som återges av komponenten är de faktiska innehållssidorna som skuggsidorna dirigerar om till och inte till själva skuggsidorna. Dessutom visar komponenten namnen på de faktiska sidorna och markerar den aktiva sidan korrekt, även när navigeringen baseras på skuggsidor. Navigeringskomponenten gör skuggsidorna helt genomskinliga för besökaren.

>[!NOTE]
>Skuggsidor gör navigeringsalternativen mycket mer flexibla, men tänk på att det är helt manuellt att behålla strukturen. Om du sorterar om det faktiska webbplatsinnehållet eller lägger till/tar bort innehåll måste du uppdatera skuggstrukturen manuellt efter behov.

>[!NOTE]
>När du återger en skuggwebbplatsstruktur är det bara skuggsidorna som rekursiveras av navigeringslogiken. Logiken ger inte en rekursiv omdirigering av destinationerna.

## Omdirigeringar i navigering {#redirects}

När en sida har ett omdirigeringsmål (oavsett om det pekar på en extern URL eller en annan AEM-sida), är det en navigeringskomponent som innehåller länkar till den punkten direkt till URL:en för omdirigeringsmålet.

### Exempel {#redirect-example}

* Skapa en sida A som dirigeras om till sida B.
* Skapa en sida C som omdirigeras till `https://aemcomponents.dev`
* På en sida D infogar du en komponent eller navigeringskomponent som innehåller sidorna A och C
* De länkar som genereras pekar sedan direkt på sidan B och `https://aemcomponents.dev`

## Exempel på komponentutdata {#sample-component-output}

Om du vill visa navigeringskomponenten och se exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_navigation).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om navigeringskomponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_navigation_v2).

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).

>[!NOTE]
>
>Från och med Core Components version 2.1.0 stöder Navigation Component [schema.org ](https://schema.org).

## Dialogrutan Redigera {#edit-dialog}

I redigeringsdialogrutan kan innehållsförfattaren definiera rotsidan för navigering och navigeringsstrukturens djup.

### Fliken Egenskaper {#properties-tab}

![Egenskaper för redigeringsdialogruta i navigeringskomponenten ](/help/assets/navigation-edit-properties.png)

* **Navigeringsrot** - Rotsidan som används för att generera navigeringsträdet.
* **Uteslut rotnivåer** - ofta ska roten inte tas med i navigeringen. Med det här alternativet kan du ange hur många nivåer upp från roten som du vill utesluta. Till exempel:
   * 0 = visa rotnivån
   * 1 = utelämna rotnivån
   * 2 = exkludera roten och ytterligare 1 nivå upp
   * osv.
* **Samla in alla underordnade sidor** - Samla in alla sidor som är underordnade navigeringsroten.
* **Navigeringsstrukturdjup** - Definierar hur många nivåer i navigeringsträdet som komponenten ska visa i förhållande till navigeringsroten (endast tillgängligt när **Samla in alla underordnade sidor** inte har valts).
* **Inaktivera skuggning** - Om sidan i hierarkin är en omdirigering visas namnet på omdirigeringssidan i stället för målet. Mer information finns i [Stöd för skuggwebbplatsstruktur](#shadow-structure).
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [datalagret](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

### Fliken Tillgänglighet {#accessibility-tab}

![Navigeringskomponentens hjälpmedelsflik i redigeringsdialogrutan](/help/assets/navigation-edit-accessibility.png)

På fliken **Hjälpmedel** kan värden anges för [ARIA-hjälpmedelsetiketter](https://www.w3.org/WAI/standards-guidelines/aria/) för komponenten.

* **Etikett** - Värdet för ett ARIA-etikettattribut för komponenten

### Fliken Format {#styles-tab-edit}

Navigeringskomponenten stöder AEM [Style System.](/help/get-started/authoring.md#component-styling).

Använd listrutan för att välja de format som du vill använda på komponenten. Markeringar som görs i redigeringsdialogrutan har samma effekt som de som väljs i komponentverktygsfältet.

Format måste konfigureras för den här komponenten i [designdialogrutan](#design-dialog) för att den nedrullningsbara menyn ska vara tillgänglig.

![Fliken Stilar i redigeringsdialogrutan för navigeringskomponenten](/help/assets/navigation-edit-styles.png)

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen ange standardvärden för navigeringsrotsidan och navigeringsdjupet som presenteras för innehållsförfattarna.

### Fliken Egenskaper {#properties-tab-design}

![Designdialogrutan för navigeringskomponenten](/help/assets/navigation-design.png)

* **Navigeringsrot** - Standardvärdet för navigeringsstrukturens rotsida, som kommer att användas för att generera navigeringsträdet och standardvärdet när innehållsförfattaren lägger till komponenten på sidan.
* **Uteslut rotnivåer** - ofta ska roten inte tas med i navigeringen. Med det här alternativet kan du ange standardvärdet för hur många nivåer uppåt från roten som du vill utesluta. Till exempel:
   * 0 = visa rotnivån
   * 1 = utelämna rotnivån
   * 2 = exkludera roten och ytterligare 1 nivå upp
   * osv.
* **Samla in alla underordnade sidor** - Standardvärdet för alternativet att samla alla sidor som är underordnade navigeringsroten.
* **Navigeringsstrukturdjup** - Standardvärdet för navigeringsstrukturens djup.
* **Inaktivera skuggning** - Standardvärdet för om skuggning ska inaktiveras när en navigeringskomponent läggs till

### Fliken Format {#styles-tab}

Navigeringskomponenten stöder AEM [Style System](/help/get-started/authoring.md#component-styling).

## Adobe Client Data Layer {#data-layer}

Navigeringskomponenten har stöd för [Adobe-klientdatalagret.](/help/developing/data-layer/overview.md)
