---
title: Content Fragment List Component
description: Med komponenten Core Component Content Fragment List kan du visa en lista med innehållsfragment.
role: Architect, Developer, Admin, User
exl-id: 0f2295b1-d287-4f72-8ee4-fa98c4850e53
source-git-commit: 395a1669cf3e17f649c23852addc37316b923bfd
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 0%

---

# Content Fragment List Component{#content-fragment-list-component}

Med komponenten Core Component Content Fragment List kan du visa en lista med [innehållsfragment](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html).

## Användning {#usage}

Med Core Component Content Fragment List Component kan du ta med en lista med [innehållsfragment](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html) på en sida baserad på en modell för innehållsfragment. Detta kan vara praktiskt när du skapar [headless content](https://helpx.adobe.com/experience-manager/6-5/sites/developing/user-guide.html?topic=/experience-manager/6-5/sites/developing/morehelp/headless.ug.js) som enkelt kan användas i andra program.

* Listan och dess egenskaper kan väljas i [konfigurera dialogruta](#configure-dialog).
* Format kan användas på komponenten i [designdialogruta](#design-dialog).

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Content Fragment Component är v2, som introducerades i version 2.18.0 av Core Components i februari 2022, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|---|----|---|---|
| v2 | - | Kompatibel | Kompatibel |
| [v1](v1/content-fragment-list.md) | Kompatibel | Kompatibel | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Huvudkomponentversioner](/help/versions.md).

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

### Fliken Format {#styles-tab-edit}

![Fliken Format i redigeringsdialogrutan för komponenten Innehållsfragmentlista](/help/assets/content-fragment-list-styles.png)

Komponenten Content Fragment List har stöd för AEM [Formatsystem.](/help/get-started/authoring.md#component-styling).

Använd listrutan för att välja de format som du vill använda på komponenten. Markeringar som görs i redigeringsdialogrutan har samma effekt som de som väljs i komponentverktygsfältet.

Format måste konfigureras för den här komponenten i [designdialogruta](#design-dialog) för att den nedrullningsbara menyn ska vara tillgänglig.

## Designdialogruta {#design-dialog}

### Fliken Format {#styles-tab}

Komponenten Content Fragment List har stöd för AEM [Formatsystem](/help/get-started/authoring.md#component-styling).
