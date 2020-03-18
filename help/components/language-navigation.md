---
title: Språknavigeringskomponent
description: Språknavigeringskomponenten tillhandahåller en språk-/landsnavigering för en webbplats, så att besökare kan navigera till samma sida på en annan språkinställning.
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# Språknavigeringskomponent{#language-navigation-component}

Språknavigeringskomponenten är ett språk-/landsnavigeringssätt för en webbplats, så att besökare kan navigera till samma sida på ett annat språk.

## Användning {#usage}

Webbplatser finns ofta på flera språk för olika regioner. Med språknavigeringskomponenten kan besökaren visa samma sida på olika språk/språk. Om du läser på den schweiziska tyska versionen av webbplatsen kan du enkelt växla till den engelska versionen av samma sida. Komponenten Språknavigering hanterar förståelsen av webbplatsens språkstruktur och söker automatiskt efter motsvarande sida.

* Ett exempel på hur lokaliseringsfunktionen för språknavigeringskomponenten fungerar finns [i avsnittet nedan](#example).
* Ett exempel på hur lokaliseringsfunktionerna för de andra kärnkomponenterna fungerar tillsammans finns i [Lokaliseringsfunktioner på sidan](/help/get-started/localization.md)för kärnkomponenter.

I [redigeringsdialogrutan](#edit-dialog) kan du definiera den globala platsnavigeringsroten samt hur djupt in i strukturen navigeringen ska gå. I [designdialogrutan](#design-dialog)kan mallskaparen ange standardvärden för samma alternativ.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av språknavigeringskomponenten är v1, som introducerades i version 2.0.0 av grundkomponenterna i januari 2018, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponentversionerna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |--- |---|
| v1 | Kompatibel | Kompatibel | Kompatibel | Kompatibel |

Mer information om Core Component-versioner och -versioner finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill se både Language Navigation Component (Språknavigeringskomponent) och exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_langnav).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om språknavigeringskomponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_langnav_v1).

Mer information om hur du utvecklar kärnkomponenter finns i dokumentationen till [Core Components Developer](/help/developing/overview.md).

## Designdialogruta {#design-dialog}

I redigeringsdialogrutan kan du definiera den globala platsnavigeringsroten samt hur djupt in i strukturen navigeringen ska gå.

Vanligtvis behöver dessa konfigurationer bara göras på sidmallsnivå. De kan dock ändras på sidnivå via [redigeringsdialogrutan](#edit-dialog).

### Fliken Egenskaper {#properties-tab}

![](/help/assets/screen_shot_2018-01-12at133642.png)

* **Navigeringsrot**
   * Det är här som webbplatsens språknavigering ska börja.
   * Platsens språkstruktur börjar på nästa nivå under den här roten.
* **Språkstrukturdjup**
   * Detta är hur många nivåer i innehållsträdet nedanför **navigeringsroten** som representerar webbplatsens språkstruktur. Exempel:
      * `1` betyder vanligtvis att du bara kan välja språk.
      * `2` betyder vanligtvis att du kan välja språk och land.
      * `3` betyder vanligtvis att du kan välja språk, land och region.

#### Exempel {#example}

Låt oss säga att innehållet ser ut ungefär så här:

```
/content
+-- we-retail
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

För webbplatsen We.Retail vill du förmodligen placera komponenten Language Navigation i en sidmall som en del av sidhuvudet. När du är en del av mallen kan du ange komponentens **navigeringsrot** till `/content/we-retail` , eftersom det är där det lokaliserade innehållet för den platsen börjar. Du bör också ange att **språkstrukturdjupet** ska vara `2` eftersom strukturen är på två nivåer (land och sedan språk).

Med **navigeringsrotvärdet** vet språkkomponenten att efter `/content/we-retail` det kan navigeringen starta och språknavigeringsalternativen genereras genom att de två nästa nivåerna i innehållsträdet identifieras som webbplatsens språknavigeringsstruktur (enligt **språkstrukturdjupets** värde).

Oavsett vilken sida en användare visar kan komponenten Språknavigering hitta motsvarande sida på ett annat språk genom att känna till platsen för den aktuella sidan och arbeta bakåt till roten och sedan vidarebefordra till motsvarande sida.

### Fliken Format {#styles-tab}

Språknavigeringskomponenten har stöd för AEM [Style System](/help/get-started/authoring.md#component-styling).

## Dialogrutan Redigera {#edit-dialog}

Vanligtvis behöver komponenten Språknavigering bara läggas till och konfigureras på sidmallarna för en plats. Om komponenten Språknavigering måste läggas till på en enskild innehållssida kan en innehållsförfattare i redigeringsdialogrutan konfigurera samma värden som beskrivs i [designdialogrutan](#design-dialog).

![](/help/assets/screen_shot_2018-01-12at133353.png)
