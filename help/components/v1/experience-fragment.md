---
title: Experience Fragment Component (v1)
description: Med Experience Fragment Component kan innehållsförfattaren lägga till en upplevelsefragmentvariant på en sida.
role: Architect, Developer, Admin, User
source-git-commit: 395a1669cf3e17f649c23852addc37316b923bfd
workflow-type: tm+mt
source-wordcount: '780'
ht-degree: 0%

---


# Experience Fragment Component (v1) {#experience-fragment-component}

Med kärnkomponentens Experience Fragment-komponent kan innehållsförfattaren placera en variant av upplevelsefragment på en sida med stöd för en lokaliserad webbplatsstruktur.

## Användning {#usage}

Med kärnkomponentens Experience Fragment-komponent kan innehållsförfattaren välja bland befintliga upplevelsefragmentvarianter och placera en på innehållssidan. Experience Fragment-komponenten har också stöd för en lokaliserad platsstruktur.

* Komponentens egenskaper kan definieras i [konfigurera dialogruta](#configure-dialog).
* Standardvärden för komponenten när du lägger till den på en sida kan definieras i [designdialogruta](#design-dialog).

## Version och kompatibilitet {#version-and-compatibility}

I det här dokumentet beskrivs v1 av Experience Fragment Component, som introducerades i version 2.6.0 av Core Components i september 2019.

>[!CAUTION]
>
>Det här dokumentet beskriver v1 för Experience Fragment-komponenten.
>
>Information om den aktuella versionen av Experience Fragment-komponenten finns i [Experience Fragment Component](/help/components/experience-fragment.md) -dokument.

## Lokaliserat stöd för webbplatsstruktur {#localized-site-structure}

Experience Fragment-komponenten är anpassad till lokaliserade webbplatsstrukturer och återger rätt upplevelsefragment baserat på sidans lokalisering. För att göra detta måste upplevelsefragmentet uppfylla följande villkor.

* Experience Fragment-komponenten läggs till i en mall.
* Den mallen används för att skapa en ny innehållssida som är en del av en lokaliserad struktur nedan `/content/<site>`.
* Det upplevelsefragment som refereras på en innehållssida är en del av en lokaliserad upplevelsefragmentstruktur nedan `/content/experience-fragments` som följer samma mönster som webbplatsen nedan `/content/<site>` och använda samma komponentnamn.

I det här fallet återges fragmentet med samma lokalisering (språk, utkast eller live-kopia) som den aktuella sidan som en del av mallen.

Det här beteendet är begränsat till Experience Fragment Components som lagts till i mallar. Experience Fragment Components som lagts till på enskilda innehållssidor återger de exakta upplevelsefragmentåtergivningarna som konfigurerats i komponenten.

* Ett exempel på hur lokaliseringsfunktionerna i Experience Fragment Component fungerar finns i [avsnittet nedan](#example).
* Ett exempel på hur lokaliseringsfunktionerna för kärnkomponenterna fungerar tillsammans finns i [Lokaliseringsfunktioner för sidan Core Components](/help/get-started/localization.md).

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

Observera att strukturen nedan `/content/experience-fragments/wknd` speglar strukturen i `/content/wknd`.

I det här fallet, om komponenten Experience Fragment `/content/experience-fragments/wknd/us/en/footerTextXf` placeras i en mall, kommer de lokaliserade sidor som skapas baserat på den mallen automatiskt att återge det lokaliserade upplevelsefragment som motsvarar den lokaliserade innehållssidan.

Så om du navigerar till en innehållssida under `/content/wknd/ch/de` som använder samma mall, `/content/experience-fragments/wknd/ch/de/footerTextXf` återges i stället för `/content/experience-fragments/wknd/us/en/footerTextXf`.

### Reserv {#fallback}

Experience Fragment-komponenten kommer att försöka hitta en motsvarande lokaliserad komponent i följande ordning.

1. Först försöker den hitta en språkrot.
1. Om den inte hittas försöker den hitta en plan.
1. Om den inte hittas försöker den hitta en live-kopia.
1. Om det inte hittas används det Experience fragment som konfigurerats i komponenten som standard.

## Exempel på komponentutdata {#sample-component-output}

Om du vill visa Experience Fragment Component och se exempel på dess konfigurationsalternativ samt HTML och JSON-utdata går du till [Komponentbibliotek](https://adobe.com/go/aem_cmp_library_xf).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Experience Fragment-komponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_xf_v1).

Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren välja den variant av upplevelsefragment som ska återges på sidan.

![Experience Fragment Components redigeringsdialogruta](/help/assets/experience-fragment-edit.png)

Använd **Öppna dialogrutan Markering** för att öppna komponentväljaren och välja vilken upplevelsefragmentkomponentvariant som ska läggas till på innehållssidan.

Om du lägger till Experience Fragment-komponenten i en mall bör du tänka på att den automatiskt lokaliseras, förutsatt att Experience Fragments lokaliseras, så att det som återges på sidan kan variera från den komponent som du uttryckligen väljer. [Se exemplet ovan](#example) för mer information.

Du kan också definiera en **ID**. Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [Datalager](/help/developing/data-layer/overview.md).

* Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
* Om ett ID anges är det författarens ansvar att se till att det är unikt.
* Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera de alternativ som är tillgängliga för den som använder Experience Fragment-komponenten och de standardvärden som anges när Experience Fragment-komponenten monteras.

### Fliken Format {#styles-tab}

Experience Fragment-komponenten stöder AEM [Formatsystem](/help/get-started/authoring.md#component-styling).