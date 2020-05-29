---
title: Content Fragment List Component
description: Med komponenten Core Component Content Fragment List kan du visa en lista med innehållsfragment.
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '762'
ht-degree: 0%

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

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Kompatibel | Kompatibel | Kompatibel |

Mer information om Core Component-versioner och -versioner finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill se komponenterna i listan Innehållsfragmentlista samt se exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_cflist).

## Teknisk information {#technical-details}

The latest technical documentation about the Content Fragment List Component [can be found on GitHub](https://adobe.com/go/aem_cmp_tech_cflist_v1).

Mer information om hur du utvecklar kärnkomponenter finns i dokumentationen till [Core Components Developer](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

The configure dialog allows the content author to define the which content fragments comprise the list and the elements of those fragments to be included.

### Fliken Egenskaper

Fliken **Egenskaper** definierar vilka innehållsfragment som ska tas med i listan. Detta baseras i första hand på en vald modell för innehållsfragment, men det finns andra filteralternativ tillgängliga.

![Properties tab of the edit dialog of the Content Fragment List Component](/help/assets/content-fragment-list-properties.png)

* **Modell** - Sökväg till innehållsfragmentmodellen som listan baseras på.
   * By default, all content fragments of the model defined as **Model Path** are included in the list.
* **Parent Path** - Parent path from which the list should be built.
   * The content fragments based on the selected **Model Path** will be filtered to those on the specified **Parent Path**.
      * Klicka eller tryck på knappen **Öppna dialogrutan** för markering till höger om fältet för att ange sökvägen.
* **Tags** - Only the Content Fragments with the specified tags will be included in the list.
   * Klicka eller tryck på knappen **Öppna dialogrutan** för markering till höger om fältet för att ange taggarna.
   * Click or tap the X next to selected tags to remove them.
* **Order By** - Field of the content fragment model by which the list will be ordered
   * Only text fields (including numeric, date, and time) are selectable.
* **Sort Order** - How the list will be sorted by the **Order By** field
   * Ascending or descending
* **Max Items** - Maximum number of items to be shown in the list
   * No value will return all items.
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [datalagret](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

>[!NOTE]
>Alternativen **Ordna efter**, **Sorteringsordning** och **Max. objekt** introducerades i version 2.7.0 av kärnkomponenterna.

### Fliken Element

Som standard tas alla element i innehållsfragmentmodellen med i listan (såvida de inte begränsas av fältet **Max. objekt** ). The **Elements** tab allows you to specify only specific elements to include.

![Elements tab of the edit dialog of the Content Fragment List Component](/help/assets/content-fragment-list-elements.png)

* **Element** - Endast elementen i innehållsfragmenten i den angivna listan visas.
   * Click or tap the **Add** button to add a new element.
   * Klicka eller tryck på knappen **Ta bort** för att ta bort ett markerat element.
   * Dra i **ordningshandtaget** om du vill ändra ordningen på elementen.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera de format som ska användas på List-komponenten för innehållsfragment.
