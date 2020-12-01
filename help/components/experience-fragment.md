---
title: Experience Fragment Component
description: Med Experience Fragment Component kan innehållsförfattaren lägga till en upplevelsefragmentvariant på en sida.
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '816'
ht-degree: 0%

---


# Experience Fragment Component{#experience-fragment-component}

Med kärnkomponentens Experience Fragment-komponent kan innehållsförfattaren placera en variant av upplevelsefragment på en sida med stöd för en lokaliserad webbplatsstruktur.

## Användning {#usage}

Med kärnkomponentens Experience Fragment-komponent kan innehållsförfattaren välja bland befintliga upplevelsefragmentvarianter och placera en på innehållssidan. Experience Fragment-komponenten har också stöd för en lokaliserad platsstruktur.

* Komponentens egenskaper kan definieras i [konfigurationsdialogrutan](#configure-dialog).
* Standardvärden för komponenten när du lägger till den på en sida kan definieras i [designdialogrutan](#design-dialog).

## Lokaliserat stöd för platsstruktur {#localized-site-structure}

Experience Fragment-komponenten är anpassad till lokaliserade webbplatsstrukturer och återger rätt upplevelsefragment baserat på sidans lokalisering. För att göra detta måste upplevelsefragmentet uppfylla följande villkor.

* Experience Fragment-komponenten läggs till i en mall.
* Den mallen används för att skapa en ny innehållssida som är en del av en lokaliserad struktur under `/content/<site>`.
* Det upplevelsefragment som refereras på en innehållssida är en del av en lokaliserad upplevelsefragmentstruktur under `/content/experience-fragments` som följer samma mönster som webbplatsen under `/content/<site>`, inklusive användning av samma komponentnamn.

I det här fallet återges fragmentet med samma lokalisering (språk, utkast eller live-kopia) som den aktuella sidan som en del av mallen.

Det här beteendet är begränsat till Experience Fragment Components som lagts till i mallar. Experience Fragment Components som lagts till på enskilda innehållssidor återger de exakta upplevelsefragmentåtergivningarna som konfigurerats i komponenten.

* Ett exempel på hur lokaliseringsfunktionerna i Experience Fragment Component fungerar finns i [avsnittet nedan](#example).
* Ett exempel på hur lokaliseringsfunktionerna i de centrala komponenterna fungerar tillsammans finns i [Lokaliseringsfunktionerna på sidan Core Components](/help/get-started/localization.md).

### Exempel {#example}

Låt oss säga att innehållet ser ut ungefär så här:

```
/content
+-- experience-fragments
   \-- wknd
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
+-- wknd
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

Observera att strukturen under `/content/experience-fragments/wknd` speglar strukturen för `/content/wknd`.

Om Experience Fragment-komponenten `/content/experience-fragments/wknd/us/en/footerTextXf` i det här fallet placeras i en mall, kommer de lokaliserade sidor som skapas baserat på den mallen automatiskt att återge det lokaliserade upplevelsefragment som motsvarar den lokaliserade innehållssidan.

Om du navigerar till en innehållssida under `/content/wknd/ch/de` som använder samma mall återges `/content/experience-fragments/wknd/ch/de/footerTextXf` i stället för `/content/experience-fragments/wknd/us/en/footerTextXf`.

### Reserv {#fallback}

Experience Fragment-komponenten kommer att försöka hitta en motsvarande lokaliserad komponent i följande ordning.

1. Först försöker den hitta en språkrot.
1. Om den inte hittas försöker den hitta en plan.
1. Om den inte hittas försöker den hitta en live-kopia.
1. Om det inte hittas används det Experience fragment som konfigurerats i komponenten som standard.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Experience Fragment Component är v1, som introducerades i version 2.6.0 av Core Components i september 2019, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Kompatibel | Kompatibel | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempelkomponentutdata {#sample-component-output}

Om du vill visa Experience Fragment Component och se exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_xf).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Experience Fragment-komponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_xf_v1).

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen till Core Components developer](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren välja den variant av upplevelsefragment som ska återges på sidan.

![Experience Fragment Components redigeringsdialogruta](/help/assets/experience-fragment-edit.png)

Använd knappen **Öppna dialogrutan Markering** för att öppna komponentväljaren och välja vilken upplevelsefragmentkomponentvariation som ska läggas till på innehållssidan.

Om du lägger till Experience Fragment-komponenten i en mall bör du tänka på att den automatiskt lokaliseras, förutsatt att Experience Fragments lokaliseras, så att det som återges på sidan kan variera från den komponent som du uttryckligen väljer. [Se exemplet ](#example) ovan för mer information.

Du kan också definiera ett **ID**. Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [datalagret](/help/developing/data-layer/overview.md).

* Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
* Om ett ID anges är det författarens ansvar att se till att det är unikt.
* Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

## Designdialog {#design-dialog}

I designdialogrutan kan mallskaparen definiera de alternativ som är tillgängliga för den som använder Experience Fragment-komponenten och de standardvärden som anges när Experience Fragment-komponenten monteras.

### Fliken Format {#styles-tab}

Experience Fragment-komponenten stöder AEM [Style System](/help/get-started/authoring.md#component-styling).
