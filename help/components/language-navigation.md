---
title: Språknavigeringskomponent
description: Språknavigeringskomponenten tillhandahåller en språk-/landsnavigering för en webbplats, så att besökare kan navigera till samma sida på en annan språkinställning.
role: Architect, Developer, Admin, User
exl-id: 10b218b4-c439-4a0f-a46f-0b15d78b0360
source-git-commit: 327c239b02e0aecee878784c918bfa98d960530e
workflow-type: tm+mt
source-wordcount: '949'
ht-degree: 0%

---

# Språknavigeringskomponent{#language-navigation-component}

Språknavigeringskomponenten är ett språk-/landsnavigeringssätt för en webbplats, så att besökare kan navigera till samma sida på en annan språkinställning.

## Användning {#usage}

Webbplatser finns ofta på flera språk för olika regioner. Med språknavigeringskomponenten kan besökaren visa samma sida på olika språk/språk. Om du läser på den schweiziska tyska versionen av webbplatsen kan du enkelt växla till den engelska versionen av samma sida. Komponenten Språknavigering hanterar förståelsen av webbplatsens språkstruktur och söker automatiskt efter motsvarande sida.

* Ett exempel på hur lokaliseringsfunktionen för språknavigeringskomponenten fungerar finns i [avsnittet nedan](#example).
* Ett exempel på hur lokaliseringsfunktionerna för de andra kärnkomponenterna fungerar tillsammans finns i [Lokaliseringsfunktionerna på sidan för kärnkomponenter](/help/get-started/localization.md).

I [redigeringsdialogrutan](#edit-dialog) kan du definiera den globala platsnavigeringsroten samt hur djupt in i strukturen navigeringen ska gå. Med hjälp av [designdialogrutan](#design-dialog) kan mallskaparen ange standardvärden för samma alternativ.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av språknavigeringskomponenten är v2, som introducerades i version 2.18.0 av grundkomponenterna i februari 2022, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | - | Kompatibel | Kompatibel |
| [v1](v1/language-navigation.md) | Kompatibel | Kompatibel | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill se både Language Navigation Component (Språknavigeringskomponenten) och exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_langnav).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om språknavigeringskomponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_langnav_v2).

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).

## Designdialogruta {#design-dialog}

I designdialogrutan kan du definiera den globala platsnavigeringsroten samt hur djupt in i strukturen navigeringen ska gå.

Vanligtvis behöver dessa konfigurationer bara göras på sidmallsnivå. De kan dock ändras på sidnivå via [redigeringsdialogrutan](#edit-dialog).

### Fliken Egenskaper {#properties-tab}

![Designdialogrutan för komponenten för språknavigering](/help/assets/language-navigation-design.png)

* **Navigeringsrot**
   * Det är här som webbplatsens språknavigering ska börja.
   * Platsens språkstruktur börjar på nästa nivå under den här roten.
* **Språkstrukturdjup**
   * Detta är hur många nivåer i innehållsträdet under **Navigeringsrot** som representerar webbplatsens språkstruktur. Exempel:
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

Med värdet **Navigeringsrot** vet språkkomponenten att efter `/content/wknd` som navigeringen börjar, och kan generera språknavigeringsalternativ genom att identifiera de två nästa nivåerna i innehållsträdet som webbplatsens språknavigeringsstruktur (som definieras av värdet **Språkstrukturdjup** ).

Oavsett vilken sida en användare visar kan komponenten Språknavigering hitta motsvarande sida på ett annat språk genom att känna till platsen för den aktuella sidan och arbeta bakåt till roten och sedan vidarebefordra till motsvarande sida.

### Fliken Format {#styles-tab}

Språknavigeringskomponenten stöder AEM [Style System](/help/get-started/authoring.md#component-styling).

## Dialogrutan Redigera {#edit-dialog}

### Fliken Egenskaper {#properties-tab-edit}

Vanligtvis behöver komponenten Språknavigering bara läggas till och konfigureras på sidmallarna för en plats. Om komponenten Språknavigering måste läggas till på en enskild innehållssida kan en innehållsförfattare i redigeringsdialogrutan konfigurera samma värden som beskrivs i [designdialogrutan](#design-dialog)

Dessutom kan du ange ett **ID**. Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [datalagret](/help/developing/data-layer/overview.md).

* Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
* Om ett ID anges är det författarens ansvar att se till att det är unikt.
* Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

![Redigeringsdialogrutan för språknavigeringskomponenten](/help/assets/language-navigation-edit.png)

### Fliken Tillgänglighet {#accessibility-tab}

* **Etikett** - Det här alternativet bör definieras om det finns mer än en språknavigering på sidan för att ange attributet aria-etikett för komponenten.

![Fliken Språknavigeringstillgänglighet](/help/assets/language-navigation-edit-accessibility.png)

### Fliken Format {#styles-tab-edit}

Språknavigeringskomponenten stöder AEM [Style System.](/help/get-started/authoring.md#component-styling).

Använd listrutan för att välja de format som du vill använda på komponenten. Markeringar som görs i redigeringsdialogrutan har samma effekt som de som väljs i komponentverktygsfältet.

Format måste konfigureras för den här komponenten i [designdialogrutan](#design-dialog) för att den nedrullningsbara menyn ska vara tillgänglig.

![Fliken Format i redigeringsdialogrutan för språknavigeringskomponenten](/help/assets/language-navigation-edit-styles.png)

## Adobe-klientdatalager {#data-layer}

Språknavigeringskomponenten stöder datalagret [Adobe Client.](/help/developing/data-layer/overview.md)
