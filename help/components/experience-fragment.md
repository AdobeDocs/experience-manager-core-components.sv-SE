---
title: Experience Fragment Component
description: Med Experience Fragment Component kan innehållsförfattaren lägga till en upplevelsefragmentvariant på en sida.
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# Experience Fragment Component{#experience-fragment-component}

Med kärnkomponentens Experience Fragment-komponent kan innehållsförfattaren placera en variant av upplevelsefragment på en sida med stöd för en lokaliserad webbplatsstruktur.

## Användning {#usage}

Med kärnkomponentens Experience Fragment-komponent kan innehållsförfattaren välja bland befintliga upplevelsefragmentvarianter och placera en på innehållssidan. Experience Fragment-komponenten har också stöd för en lokaliserad platsstruktur.

* Komponentens egenskaper kan definieras i [konfigurationsdialogrutan](#configure-dialog).
* Standardvärden för komponenten när du lägger till den på en sida kan definieras i [designdialogrutan](#design-dialog).

## Lokaliserat stöd för webbplatsstruktur {#localized-site-structure}

Experience Fragment-komponenten är anpassad till lokaliserade webbplatsstrukturer och återger rätt upplevelsefragment baserat på sidans lokalisering. För att göra detta måste upplevelsefragmentet uppfylla följande villkor.

* Experience Fragment-komponenten läggs till i en mall.
* Den mallen används för att skapa en ny innehållssida som är en del av en lokaliserad struktur nedan `/content/<site>`.
* Det upplevelsefragment som refereras på en innehållssida är en del av en lokaliserad upplevelsefragmentstruktur nedan `/content/experience-fragments` som följer samma mönster som webbplatsen nedan, `/content/<site>` inklusive användning av samma komponentnamn.

I det här fallet återges fragmentet med samma lokalisering (språk, utkast eller live-kopia) som den aktuella sidan som en del av mallen.

Det här beteendet är begränsat till Experience Fragment Components som lagts till i mallar. Experience Fragment Components som lagts till på enskilda innehållssidor återger de exakta upplevelsefragmentåtergivningarna som konfigurerats i komponenten.

* Ett exempel på hur lokaliseringsfunktionerna i Experience Fragment Component fungerar finns [i avsnittet nedan](#example).
* Ett exempel på hur lokaliseringsfunktionerna för kärnkomponenterna fungerar tillsammans finns i [Lokaliseringsfunktioner på sidan](/help/get-started/localization.md)Core Components (Kärnkomponenter).

### Exempel {#example}

Låt oss säga att innehållet ser ut ungefär så här:

```
/content
+-- experience-fragments
   \-- we-retail
      +-- language-masters
      +-- us
         +-- en
            +-- footerTextXf
            \-- headerTextXf
         \-- es
            +-- footerTextXf
            \-- headerTextXf
      \-- ch
         +-- de
            +-- footerTextXf
            \-- headerTextXf
         +-- fr
            +-- footerTextXf
            \-- headerTextXf
         \-- it
            +-- footerTextXf
            \-- headerTextXf
+-- we-retail
   +-- language-masters
   +-- us
      +-- en
      \-- es
   +-- ch
      +-- de
      +-- fr
      \-- it
+-- wknd-events
\-- wknd-shop
```

Observera att strukturen under `/content/experience-fragments/we-retail` speglar strukturen för `/content/we-retail`.

Om Experience Fragment-komponenten i det här fallet `/content/experience-fragments/we-retail/us/en/footerTextXf` placeras i en mall, kommer de lokaliserade sidor som skapas baserat på den mallen automatiskt att återge det lokaliserade upplevelsefragment som motsvarar den lokaliserade innehållssidan.

Om du navigerar till en innehållssida under `/content/we-retail/ch/de` som använder samma mall `/content/experience-fragments/we-retail/ch/de/footerTextXf` återges den i stället för `/content/experience-fragments/we-retail/us/en/footerTextXf`.

### Reserv {#fallback}

Experience Fragment-komponenten kommer att försöka hitta en motsvarande lokaliserad komponent i följande ordning.

1. Först försöker den hitta en språkrot.
1. Om den inte hittas försöker den hitta en plan.
1. Om den inte hittas försöker den hitta en live-kopia.
1. Om det inte hittas används det Experience fragment som konfigurerats i komponenten som standard.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Experience Fragment Component är v1, som introducerades i version 2.6.0 av Core Components i september 2019, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponentversionerna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|---|
| v1 | Kompatibel | Kompatibel | Kompatibel | Kompatibel |

Mer information om Core Component-versioner och -versioner finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill visa Experience Fragment Component och se exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_xf).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Experience Fragment Component [finns på GitHub](https://adobe.com/go/aem_cmp_tech_xf_v1).

Mer information om hur du utvecklar kärnkomponenter finns i dokumentationen till [Core Components Developer](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren välja den variant av upplevelsefragment som ska återges på sidan.

![](/help/assets/screen-shot-2019-08-23-10.49.21.png)

Använd knappen **Öppna dialogrutan** Markering för att öppna komponentväljaren och välja vilken typ av upplevelsefragmentkomponent som ska läggas till på innehållssidan.

Om du lägger till Experience Fragment-komponenten i en mall bör du tänka på att den automatiskt lokaliseras, förutsatt att Experience Fragments lokaliseras, så att det som återges på sidan kan variera från den komponent som du uttryckligen väljer. [Se exemplet ovan](#example) för mer information.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera de alternativ som är tillgängliga för den som använder Experience Fragment-komponenten och de standardvärden som anges när Experience Fragment-komponenten monteras.

![](/help/assets/screen-shot-2019-08-23-10.48.36.png)

Experience Fragment-komponenten stöder AEM [Style System](/help/get-started/authoring.md#component-styling).
