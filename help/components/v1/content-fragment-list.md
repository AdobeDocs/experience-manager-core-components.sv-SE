---
title: Content Fragment List Component (v1)
description: Med komponenten Core Component Content Fragment List kan du visa en lista med innehållsfragment.
role: Architect, Developer, Admin, User
source-git-commit: e5251010ca41025eb2bb56b66164ecf4cc0145c8
workflow-type: tm+mt
source-wordcount: '725'
ht-degree: 0%

---


# Content Fragment List Component (v1) {#content-fragment-list-component}

Med komponenten Core Component Content Fragment List kan du visa en lista med [innehållsfragment](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html).

## Användning {#usage}

Med Core Component Content Fragment List Component kan du ta med en lista med [innehållsfragment](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html) på en sida baserad på en modell för innehållsfragment. Detta kan vara praktiskt när du skapar [headless content](https://helpx.adobe.com/experience-manager/6-5/sites/developing/user-guide.html?topic=/experience-manager/6-5/sites/developing/morehelp/headless.ug.js) som enkelt kan användas i andra program.

* Listan och dess egenskaper kan väljas i [konfigurera dialogruta](#configure-dialog).
* Format kan användas på komponenten i [designdialogruta](#design-dialog).

## Version och kompatibilitet {#version-and-compatibility}

I dokumentet beskrivs v1 av Content Fragment Component, som introducerades i version 2.4.0 av Core Components i maj 2019.

>[!CAUTION]
>
>Det här dokumentet beskriver v1 för List-komponenten för innehållsfragment.
>
>Mer information om den aktuella versionen av Content Fragment List Component finns i [Content Fragment List Component](/help/components/content-fragment-list.md) -dokument.

## Exempel på komponentutdata {#sample-component-output}

Om du vill se komponenterna i listan Innehållsfragment samt exempel på dess konfigurationsalternativ samt HTML och JSON-utdata går du till [Komponentbibliotek](https://adobe.com/go/aem_cmp_library_cflist).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om komponenten Content Fragment List [finns på GitHub](https://adobe.com/go/aem_cmp_tech_cflist_v1).

Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera vilka innehållsfragment som ska utgöra listan och vilka element i fragmenten som ska inkluderas.

### Fliken Egenskaper

The **Egenskaper** -fliken definierar vilka innehållsfragment som tas med i listan. Detta baseras i första hand på en vald modell för innehållsfragment, men det finns andra filteralternativ tillgängliga.

![Fliken Egenskaper i redigeringsdialogrutan för komponenten Innehållsfragmentlista](/help/assets/content-fragment-list-properties.png)

* **Modell** - Sökväg till innehållsfragmentmodellen som listan baseras på.
   * Som standard definieras alla innehållsfragment i modellen som **Modellsökväg** finns med i listan.
* **Överordnad sökväg** - Överordnad sökväg som listan ska skapas från.
   * Innehållsfragmenten baseras på det markerade **Modellsökväg** kommer att filtreras till de på den angivna **Överordnad sökväg**.
      * Klicka eller tryck på **Öppna dialogrutan Markering** till höger om fältet för att ange sökvägen.
* **Taggar** - Endast innehållsfragment med de angivna taggarna kommer att tas med i listan.
   * Klicka eller tryck på **Öppna dialogrutan Markering** till höger om fältet för att ange taggarna.
   * Klicka eller tryck på X bredvid de markerade taggarna för att ta bort dem.
* **Ordna efter** - Fält i innehållsfragmentmodellen där listan ska sorteras
   * Endast textfält (inklusive numeriska fält, datum och tid) kan markeras.
* **Sorteringsordning** - Hur listan ska sorteras efter **Ordna efter** fält
   * Stigande eller fallande
* **Max. objekt** - Maximalt antal objekt som ska visas i listan
   * Inget värde returnerar alla objekt.
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [Datalager](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

>[!NOTE]
>The **Ordna efter**, **Sorteringsordning** och **Max. objekt** i version 2.7.0 av Core Components.

### Fliken Element

Som standard tas alla element i innehållsfragmentmodellen med i listan (om de inte begränsas av **Max. objekt** fält). The **Element** På -fliken kan du bara ange specifika element som ska inkluderas.

![Fliken Element i redigeringsdialogrutan för komponenten Innehållsfragmentlista](/help/assets/content-fragment-list-elements.png)

* **Element** - Endast elementen i innehållsfragmenten i den angivna listan visas.
   * Klicka eller tryck på **Lägg till** om du vill lägga till ett nytt element.
   * Klicka eller tryck på **Ta bort** om du vill ta bort ett markerat element.
   * Dra **Order** om du vill ändra ordningen på elementen.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera de format som ska användas på List-komponenten för innehållsfragment.
