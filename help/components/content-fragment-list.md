---
title: Content Fragment List Component
description: Med komponenten Core Component Content Fragment List kan du visa en lista med innehållsfragment.
role: Architect, Developer, Administrator, Business Practitioner
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '767'
ht-degree: 0%

---


# Content Fragment List Component{#content-fragment-list-component}

Med komponenten Core Component Content Fragment List kan du visa en lista med [innehållsfragment](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/content-fragments/content-fragments.html).

## Användning {#usage}

Med listkomponenten Core Component Content Fragment kan du inkludera en lista med [innehållsfragment](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/content-fragments/content-fragments.html) på en sida baserat på en Content Fragment-modell. Detta kan vara särskilt användbart när du skapar [headless-innehåll](https://helpx.adobe.com/experience-manager/6-5/sites/developing/user-guide.html?topic=/experience-manager/6-5/sites/developing/morehelp/headless.ug.js) som enkelt kan användas i andra program.

* Listan och dess egenskaper kan väljas i [konfigurationsdialogrutan](#configure-dialog).
* Format kan användas på komponenten i [designdialogrutan](#design-dialog).

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Content Fragment Component är v1, som introducerades i version 2.4.0 av Core Components i maj 2019, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Kompatibel | Kompatibel | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempelkomponentutdata {#sample-component-output}

Om du vill se komponenterna i listan Innehållsfragmentlista samt se exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_cflist).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om List-komponenten för innehållsfragment [finns på GitHub](https://adobe.com/go/aem_cmp_tech_cflist_v1).

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen till Core Components developer](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera vilka innehållsfragment som ska utgöra listan och vilka element i fragmenten som ska inkluderas.

### Fliken Egenskaper

På fliken **Egenskaper** definieras vilka innehållsfragment som ska tas med i listan. Detta baseras i första hand på en vald modell för innehållsfragment, men det finns andra filteralternativ tillgängliga.

![Fliken Egenskaper i redigeringsdialogrutan för komponenten Innehållsfragmentlista](/help/assets/content-fragment-list-properties.png)

* **Modell**  - Sökväg till innehållsfragmentmodellen som listan baseras på.
   * Som standard tas alla innehållsfragment i modellen som är definierade som **modellsökväg** med i listan.
* **Överordnad sökväg**  - överordnad sökväg som listan ska skapas från.
   * Innehållsfragmenten som baseras på den valda **modellsökvägen** kommer att filtreras till de på den angivna **överordnade sökvägen**.
      * Klicka eller tryck på knappen **Öppna markeringsdialogrutan** till höger om fältet för att ange sökvägen.
* **Taggar**  - Endast innehållsfragment med de angivna taggarna kommer att tas med i listan.
   * Klicka på eller tryck på knappen **Öppna urvalsdialogrutan** till höger om fältet för att ange taggarna.
   * Klicka eller tryck på X bredvid de markerade taggarna för att ta bort dem.
* **Ordna efter** - Fält för innehållsfragmentmodellen som listan ska sorteras efter
   * Endast textfält (inklusive numeriska fält, datum och tid) kan markeras.
* **Sorteringsordning**  - Så här sorteras listan efter  **ordningsbytefältet** 
   * Stigande eller fallande
* **Max Items**  - Maximalt antal objekt som ska visas i listan
   * Inget värde returnerar alla objekt.
* **ID**  - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i  [datalagret](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

>[!NOTE]
>Alternativen **Ordna efter**, **Sorteringsordning** och **Max. objekt** introducerades i version 2.7.0 av Core Components.

### Fliken Element

Som standard tas alla element i innehållsfragmentmodellen med i listan (såvida de inte begränsas av fältet **Max. objekt**). På fliken **Elements** kan du bara ange specifika element som ska inkluderas.

![Fliken Element i redigeringsdialogrutan för komponenten Innehållsfragmentlista](/help/assets/content-fragment-list-elements.png)

* **Element**  - Endast elementen i innehållsfragmenten i den angivna listan visas.
   * Klicka eller tryck på **Lägg till**-knappen för att lägga till ett nytt element.
   * Klicka eller tryck på **Ta bort**-knappen om du vill ta bort ett markerat element.
   * Dra handtaget för **Ordning** om du vill ändra ordningen på elementen.

## Designdialog {#design-dialog}

I designdialogrutan kan mallskaparen definiera de format som ska användas på List-komponenten för innehållsfragment.
