---
title: Språknavigeringskomponent
description: Språknavigeringskomponenten tillhandahåller en språk-/landsnavigering för en webbplats, så att besökare kan navigera till samma sida på en annan språkinställning.
translation-type: tm+mt
source-git-commit: d3ebcea5fa1523c1a986841cd3d1a64e16e85f6d
workflow-type: tm+mt
source-wordcount: '846'
ht-degree: 1%

---


# Språknavigeringskomponent{#language-navigation-component}

Språknavigeringskomponenten är ett språk-/landsnavigeringssätt för en webbplats, så att besökare kan navigera till samma sida på ett annat språk.

## Användning {#usage}

Webbplatser finns ofta på flera språk för olika regioner. Med språknavigeringskomponenten kan besökaren visa samma sida på olika språk/språk. Om du läser på den schweiziska tyska versionen av webbplatsen kan du enkelt växla till den engelska versionen av samma sida. Komponenten Språknavigering hanterar förståelsen av webbplatsens språkstruktur och söker automatiskt efter motsvarande sida.

* Ett exempel på hur lokaliseringsfunktionen för språknavigeringskomponenten fungerar finns i [avsnittet nedan](#example).
* Ett exempel på hur lokaliseringsfunktionerna för de andra kärnkomponenterna fungerar tillsammans finns i [Lokaliseringsfunktionerna på sidan Core Components](/help/get-started/localization.md).

I dialogrutan [redigera](#edit-dialog) kan du definiera den globala platsnavigeringsroten samt hur djupt in i strukturen navigeringen ska gå. Med hjälp av [designdialogrutan](#design-dialog) kan mallskaparen ange standardvärden för samma alternativ.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av språknavigeringskomponenten är v1, som introducerades i version 2.0.0 av grundkomponenterna i januari 2018, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v1 | Kompatibel | Kompatibel | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempelkomponentutdata {#sample-component-output}

Om du vill visa språknavigeringskomponenten och se exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_langnav).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om språknavigeringskomponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_langnav_v1).

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen till Core Components developer](/help/developing/overview.md).

## Designdialog {#design-dialog}

I redigeringsdialogrutan kan du definiera den globala platsnavigeringsroten samt hur djupt in i strukturen navigeringen ska gå.

Vanligtvis behöver dessa konfigurationer bara göras på sidmallsnivå. De kan dock ändras på sidnivå via dialogrutan [Redigera](#edit-dialog).

### Fliken Egenskaper {#properties-tab}

![Designdialogrutan för komponenten för språknavigering](/help/assets/language-navigation-design.png)

* **Navigeringsrot**
   * Det är här som webbplatsens språknavigering ska börja.
   * Platsens språkstruktur börjar på nästa nivå under den här roten.
* **Språkstrukturdjup**
   * Detta är hur många nivåer i innehållsträdet under **navigeringsrot** som representerar webbplatsens språkstruktur. Exempel:
      * `1` betyder vanligtvis att du bara kan välja språk.
      * `2` betyder vanligtvis att du kan välja språk och land.
      * `3` betyder vanligtvis att du kan välja språk, land och region.

#### Exempel {#example}

Låt oss säga att innehållet ser ut ungefär så här:

```
/content
+-- wknd
   +-- language-masters
   +-- us
      +-- en
      \-- es
   \-- ch
      +-- de
      +-- fr
      \-- it
+-- wknd-events
\-- wknd-shop
```

För webbplatsen WKND vill du förmodligen placera komponenten Språknavigering i en sidmall som en del av sidhuvudet. När du är en del av mallen kan du ange **navigeringsrot** för komponenten till `/content/wknd` eftersom det är där det lokaliserade innehållet för den platsen börjar. Du bör också ange **språkstrukturdjupet** till `2` eftersom strukturen är på två nivåer (land och sedan språk).

Med värdet **Navigeringsrot** vet språkkomponenten att när `/content/wknd` har börjat navigeringen och kan generera språknavigeringsalternativ genom att identifiera de två nästa nivåerna i innehållsträdet som webbplatsens språknavigeringsstruktur (som definieras med värdet **Språkstrukturdjup**).

Oavsett vilken sida en användare visar kan komponenten Språknavigering hitta motsvarande sida på ett annat språk genom att känna till platsen för den aktuella sidan och arbeta bakåt till roten och sedan vidarebefordra till motsvarande sida.

### Fliken Format {#styles-tab}

Språknavigeringskomponenten stöder AEM [Style System](/help/get-started/authoring.md#component-styling).

## Redigera dialogruta {#edit-dialog}

Vanligtvis behöver komponenten Språknavigering bara läggas till och konfigureras på sidmallarna för en plats. Om komponenten Språknavigering måste läggas till på en enskild innehållssida kan en innehållsförfattare i redigeringsdialogrutan konfigurera samma värden som beskrivs i [designdialogrutan](#design-dialog).

Dessutom kan du ange ett **ID**. Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [datalagret](/help/developing/data-layer/overview.md).

* Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
* Om ett ID anges är det författarens ansvar att se till att det är unikt.
* Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

![Redigera-dialogrutan för språknavigeringskomponenten](/help/assets/language-navigation-edit.png)

## Adobe-klientdatalagret {#data-layer}

Språknavigeringskomponenten stöder [Adobe-klientdatalagret.](/help/developing/data-layer/overview.md)
