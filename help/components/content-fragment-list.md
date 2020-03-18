---
title: Content Fragment List Component
description: Med komponenten Core Component Content Fragment List kan du visa en lista med innehållsfragment.
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# Content Fragment List Component{#content-fragment-list-component}

Med komponenten Core Component Content Fragment List kan du visa en lista med [innehållsfragment](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/content-fragments/content-fragments.html).

## Användning {#usage}

Med listkomponenten Core Component Content Fragment kan du inkludera en lista med [innehållsfragment](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/content-fragments/content-fragments.html) på en sida baserat på en Content Fragment-modell. Detta kan vara praktiskt när du vill skapa [headless-innehåll](https://helpx.adobe.com/experience-manager/6-5/sites/developing/user-guide.html?topic=/experience-manager/6-5/sites/developing/morehelp/headless.ug.js) som enkelt kan användas i andra program.

* Listan och dess egenskaper kan väljas i [dialogrutan](#configure-dialog)Konfigurera.
* Format kan användas på komponenten i [designdialogrutan](#design-dialog).

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Content Fragment Component är v1, som introducerades i version 2.4.0 av Core Components i maj 2019, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponentversionerna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|---|
| v1 | Kompatibel | Kompatibel | Kompatibel | Kompatibel |

Mer information om Core Component-versioner och -versioner finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill se komponenterna i listan Innehållsfragmentlista samt se exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_cflist).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Content Fragment List Component [finns på GitHub](https://adobe.com/go/aem_cmp_tech_cflist_v1).

Mer information om hur du utvecklar kärnkomponenter finns i dokumentationen till [Core Components Developer](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera vilka innehållsfragment som ska utgöra listan och vilka element i fragmenten som ska inkluderas.

### Fliken Egenskaper

Fliken **Egenskaper** definierar vilka innehållsfragment som ska tas med i listan. Detta baseras i första hand på en vald modell för innehållsfragment, men det finns andra filteralternativ tillgängliga.

![](/help/assets/screen-shot-2019-09-25-10.32.10.png)

* **Modell** - Sökväg till innehållsfragmentmodellen som listan baseras på.
   * Som standard tas alla innehållsfragment i modellen som är definierade som **modellsökväg** med i listan.
* **Överordnad sökväg** - överordnad sökväg som listan ska skapas från.
   * Innehållsfragmenten som baseras på den valda **modellsökvägen** filtreras efter dem på den angivna **överordnade sökvägen**.
      * Klicka eller tryck på knappen **Öppna dialogrutan** för markering till höger om fältet för att ange sökvägen.
* **Taggar** - Endast innehållsfragment med de angivna taggarna tas med i listan.
   * Klicka eller tryck på knappen **Öppna dialogrutan** för markering till höger om fältet för att ange taggarna.
   * Klicka eller tryck på X bredvid de markerade taggarna för att ta bort dem.
* **Ordna efter** - Fält i innehållsfragmentmodellen där listan ska sorteras
   * Endast textfält (inklusive numeriska fält, datum och tid) kan markeras.
* **Sorteringsordning** - Så här sorteras listan efter fältet **Ordna efter**
   * Stigande eller fallande
* **Max Items** - Maximalt antal objekt som ska visas i listan
   * Inget värde returnerar alla objekt.

>[!NOTE]
>Alternativen **Ordna efter**, **Sorteringsordning** och **Max. objekt** introducerades i version 2.7.0 av kärnkomponenterna.

### Fliken Element

Som standard tas alla element i innehållsfragmentmodellen med i listan (såvida de inte begränsas av fältet **Max. objekt** ). På fliken **Elements** kan du bara ange specifika element som ska inkluderas.

![](/help/assets/screen-shot-2019-05-08-10.47.34.png)

* **Element** - Endast elementen i innehållsfragmenten i den angivna listan visas.
   * Klicka eller tryck på knappen **Lägg till** för att lägga till ett nytt element.
   * Klicka eller tryck på knappen **Ta bort** för att ta bort ett markerat element.
   * Dra i **ordningshandtaget** om du vill ändra ordningen på elementen.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera de format som ska användas på List-komponenten för innehållsfragment.
