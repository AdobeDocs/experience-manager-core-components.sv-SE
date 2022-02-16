---
title: Teaser Component
description: Teaser-komponenten kan visa en bild, en titel, RTF och eventuellt länka till ytterligare innehåll.
role: Architect, Developer, Admin, User
exl-id: ec75e168-6f3b-4dff-8df6-06ca7dc18688
source-git-commit: 395a1669cf3e17f649c23852addc37316b923bfd
workflow-type: tm+mt
source-wordcount: '999'
ht-degree: 0%

---

# Teaser Component {#teaser-component}

Core Component Teaser Component Component Component kan visa en bild, en titel, RTF-text och eventuellt länka till ytterligare innehåll.

## Användning {#usage}

Teaser Component (Teaser Component) gör det enkelt för innehållsförfattaren att skapa ett suddgummi för ytterligare innehåll med hjälp av en bild, en titel eller formaterad text och länka till ytterligare innehåll eller andra åtgärder.

Mallförfattaren kan använda [designdialogruta](#design-dialog) för att definiera om alternativen för att skapa anrop till åtgärder och lägga till länkar är tillgängliga samt inaktivera olika visningsalternativ. Innehållsförfattaren kan använda [konfigurera dialogruta](#configure-dialog) för att ställa in en bild, definiera CTA, ange titlar och beskrivningar och konfigurera länkar till den enskilda teaser. The [redigeringsdialogruta](image.md#edit-dialog) i [Bildkomponent](image.md) kan användas för att ändra suddgummibilden.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Teaser Component är v2, som introducerades i version 2.18.0 av Core Components i februari 2022, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|---|
| v2 | - | Kompatibel | Kompatibel |
| [v1](v1/teaser.md) | Kompatibel | Kompatibel | Kompatibel |

## Exempel på komponentutdata {#sample-component-output}

Om du vill se både Teaser Component och exempel på dess konfigurationsalternativ samt HTML och JSON-utdata går du till [Komponentbibliotek](https://adobe.com/go/aem_cmp_library_teaser).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Teaser Component [finns på GitHub](https://adobe.com/go/aem_cmp_tech_teaser_v1).

Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Innehållsförfattaren kan använda dialogrutan Konfigurera för att definiera egenskaperna för det enskilda lagret. Det finns också en [redigeringsdialogruta](#edit-dialog) om du vill ändra suddgummibilden om en sådan är markerad.

### Fliken Länkar {#links-tab}

![Länkflik i redigeringsdialogrutan för Teaser Component](/help/assets/teaser-edit-links.png)

Teaser title, description and image can be inherited from the linked page, or from the page linked in the first call to action. Om varken en länk eller ett anrop till en åtgärd anges ärvs titeln, beskrivningen och bilden från den aktuella sidan.

* **Länk** - Den här filen länkas till en innehållssida, extern URL eller sidankarpunkt.
* **Öppna länk på ny flik** - Om det här alternativet är aktiverat öppnas länken på en ny webbläsarflik.
* **Call-to-actions** - Med det här alternativet kan du länka till flera mål.
   * Den sida som är länkad i det första anropet används när du ärver teasertitel, beskrivning eller bild.

### Fliken Text {#text-tab}

![Textflik i redigeringsdialogrutan för Teaser Component](/help/assets/teaser-edit-text.png)

* **Förtitel** - Förrubriken visas före teaser titel.
* **Titel** - Definierar en titel som ska visas som rubrik för suddgummit.
   * **Hämta rubrik från länkad sida** - När det här alternativet är markerat fylls rubriken i med den länkade sidans rubrik.
* **Beskrivning** - Definierar en beskrivning som ska visas som underrubrik till suddgummit.
   * **Hämta beskrivning från länkad sida** - När det här alternativet är markerat fylls beskrivningen i med den länkade sidans beskrivning.
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [Datalager](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

### Fliken Resurser {#asset-tab}

![Fliken Redigera i dialogrutan Teaser Component](/help/assets/teaser-edit-image.png)

* **Ärv bild från sida** - Använd bilden som är definierad i sidegenskaperna för den länkade sidan eller den aktuella sidan om ingen finns.
* **Bildresurs** - Släpp en resurs från [resursläsare](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) eller tryck på **bläddra** om du vill överföra från ett lokalt filsystem.
   * Tryck eller klicka **Rensa** för att avmarkera den markerade bilden.
   * Tryck eller klicka **Redigera** till [hantera återgivningar av resursen](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) i resursredigeraren.
* **Alternativ text för tillgänglighet** - I det här fältet kan du definiera en beskrivning av bilden för användare med nedsatt syn.
   * **Ärv alternativ text från sida** - Det här alternativet använder den alternativa beskrivningen av det länkade tillgångsvärdet för `dc:description` metadata i DAM eller på den aktuella sidan om ingen resurs är länkad.
* **Ange inte en alternativ text** - Med det här alternativet markeras den bild som ska ignoreras av hjälpmedelstekniker, som skärmläsare, om bilden är helt dekorativ eller på annat sätt inte förmedlar någon ytterligare information till sidan.

>[!NOTE]
>
>[Funktioner i Dynamic Media](image.md#dynamic-media) är för närvarande inte tillgängliga i Teaser Component.

### Fliken Format {#styles-tab-edit}

![Fliken Stilar i redigeringsdialogrutan för komponenten Teaser List](/help/assets/teaser-edit-styles.png)

Teaser Component har stöd för AEM [Formatsystem.](/help/get-started/authoring.md#component-styling).

Använd listrutan för att välja de format som du vill använda på komponenten. Markeringar som görs i redigeringsdialogrutan har samma effekt som de som väljs i komponentverktygsfältet.

Format måste konfigureras för den här komponenten i [designdialogruta](#design-dialog) för att den nedrullningsbara menyn ska vara tillgänglig.

## Dialogrutan Redigera {#edit-dialog}

Teaser Component delegerar bildåtergivning till [Bildkomponent](image.md). Därför [redigeringsdialogruta](image.md#edit-dialog of the Image Component is available to the content author to manipulate the teaser image.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera de laseralternativ som innehållsförfattaren har när den här komponenten används.

### Teaser Tab {#teaser-tab}

![Teaser Component&#39;s design dialog](/help/assets/teaser-design.png)

* **Call-to-actions**
   * **Inaktivera anrop till åtgärder** - Dölj **Call-to-actions** alternativ för innehållsförfattare
* **Element**
   * **Dölj pretitle** - Döljer **Förtitel** alternativ för innehållsförfattare
   * **Dölj titel** - Döljer **Titel** alternativ för innehållsförfattare
      * När du har valt **Titeltyp** är dold
   * **Dölj beskrivning** - Dölj **Beskrivning** alternativ för innehållsförfattare
* **Standardtiteltyp** - Definierar H-taggen som ska användas av teaser-titeln.
* **Bildombud** - Informativ visning som anger vilken komponent Teaser delegerar bildhanteringen.

### Fliken Format {#styles-tab}

Teaser Component har stöd för AEM [Formatsystem](/help/get-started/authoring.md#component-styling).

## Adobe-klientdatalager {#data-layer}

Teaser Component har stöd för [Adobe Client Data Layer.](/help/developing/data-layer/overview.md)
