---
title: Content Fragment List Component (v1)
description: Med komponenten Core Component Content Fragment List kan du visa en lista med innehållsfragment.
role: Architect, Developer, Admin, User
exl-id: 37d6632d-360d-4081-8279-8efbb369a82e
index: n
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 0%

---


# Content Fragment List Component (v1) {#content-fragment-list-component}

Komponenten Core Component Content Fragment List gör det möjligt att visa en lista med [innehållsfragment](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html?lang=sv-SE).

## Användning {#usage}

Med listkomponenten Core Component Content Fragment kan du inkludera en lista med [innehållsfragment](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html?lang=sv-SE) på en sida baserat på en Content Fragment-modell. Detta kan vara särskilt användbart när du skapar [headless-innehåll](https://helpx.adobe.com/se/experience-manager/6-5/sites/developing/user-guide.html?topic=/experience-manager/6-5/sites/developing/morehelp/headless.ug.js) som enkelt kan användas av andra program.

* Listan och dess egenskaper kan väljas i dialogrutan [Konfigurera](#configure-dialog).
* Format kan användas på komponenten i [designdialogrutan](#design-dialog).

## Version och kompatibilitet {#version-and-compatibility}

I dokumentet beskrivs v1 av Content Fragment Component, som introducerades i version 2.4.0 av Core Components i maj 2019.

>[!CAUTION]
>
>Det här dokumentet beskriver v1 för List-komponenten för innehållsfragment.
>
>Mer information om den aktuella versionen av List-komponenten för innehållsfragment finns i dokumentet [List-komponent för innehållsfragment](/help/components/content-fragment-list.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill se komponenterna i listan Innehållsfragment och se exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_cflist).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om List-komponenten för innehållsfragment [&#x200B; finns på GitHub](https://adobe.com/go/aem_cmp_tech_cflist_v1).

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera vilka innehållsfragment som ska utgöra listan och vilka element i fragmenten som ska inkluderas.

### Fliken Egenskaper

Fliken **Egenskaper** definierar vilka innehållsfragment som tas med i listan. Detta baseras i första hand på en vald innehållsfragmentmodell, men det finns andra filteralternativ tillgängliga.

![Fliken Egenskaper i redigeringsdialogrutan för komponenten Lista över innehållsfragment](/help/assets/content-fragment-list-properties.png)

* **Modell** - Sökväg till innehållsfragmentmodellen som listan baseras på.
   * Som standard inkluderas alla innehållsfragment i modellen som är definierade som **modellsökväg** i listan.
* **Överordnad sökväg** - överordnad sökväg som listan ska skapas från.
   * Innehållsfragmenten som baseras på den valda **modellsökvägen** filtreras efter dem på den angivna **överordnade sökvägen**.
      * Klicka på eller tryck på knappen **Öppna markeringsdialogrutan** till höger om fältet för att ange sökvägen.
* **Taggar** - Endast innehållsfragment med de angivna taggarna tas med i listan.
   * Klicka på eller tryck på knappen **Öppna markeringsdialogrutan** till höger om fältet för att ange taggarna.
   * Klicka eller tryck på X bredvid de markerade taggarna för att ta bort dem.
* **Ordna efter** - Fält i innehållsfragmentmodellen som listan ska sorteras efter
   * Endast textfält (inklusive numeriska fält, datum och tid) kan markeras.
* **Sorteringsordning** - Så här sorteras listan efter fältet **Ordna efter**
   * Stigande eller fallande
* **Max antal objekt** - Maximalt antal objekt som ska visas i listan
   * Inget värde returnerar alla objekt.
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [datalagret](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

>[!NOTE]
>Alternativen **Ordna efter**, **Sorteringsordning** och **Max. objekt** introducerades med version 2.7.0 av kärnkomponenterna.

### Fliken Element

Som standard tas alla element i innehållsfragmentmodellen med i listan (såvida de inte begränsas av fältet **Max. objekt**). På fliken **Elements** kan du bara ange specifika element som ska inkluderas.

![Fliken Element i redigeringsdialogrutan för komponenten Lista över innehållsfragment](/help/assets/content-fragment-list-elements.png)

* **Elements** - Endast elementen i innehållsfragmenten i den angivna listan visas.
   * Klicka eller tryck på knappen **Lägg till** för att lägga till ett nytt element.
   * Klicka eller tryck på knappen **Ta bort** för att ta bort ett markerat element.
   * Dra handtaget för **Ordning** om du vill ändra ordningen på elementen.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera de format som ska användas på List-komponenten för innehållsfragment.
