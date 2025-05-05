---
title: Teaser Component
description: Teaser-komponenten kan visa en bild, en titel, RTF-text och eventuellt länka till ytterligare innehåll.
role: Architect, Developer, Admin, User
exl-id: ec75e168-6f3b-4dff-8df6-06ca7dc18688
source-git-commit: 6fbc781db555bc6abaed1d122a9a8756e3d53222
workflow-type: tm+mt
source-wordcount: '1046'
ht-degree: 0%

---

# Teaser Component {#teaser-component}

Core Component Teaser Component Component Component kan visa en bild, en titel, RTF-text och eventuellt länka till ytterligare innehåll.

## Användning {#usage}

Teaser Component (Teaser Component) gör det enkelt för innehållsförfattaren att skapa ett suddgummi för ytterligare innehåll med hjälp av en bild, en titel eller formaterad text och länka till ytterligare innehåll eller andra åtgärder.

Mallförfattaren kan använda [designdialogrutan](#design-dialog) för att definiera om alternativen för att skapa anrop till åtgärder och lägga till länkar är tillgängliga samt inaktivera olika visningsalternativ. Innehållsförfattaren kan använda dialogrutan [Konfigurera](#configure-dialog) för att ange en bild, definiera CTA, ange titlar och beskrivningar och konfigurera länkar till det enskilda lagret. Dialogrutan [Redigera](image.md#edit-dialog) för [bildkomponenten](image.md) är tillgänglig för att ändra suddgummibilden.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Teaser Component är v2, som introducerades i version 2.18.0 av Core Components i februari 2022, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponenterna är kompatibla med samt länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|---|---|---|---|---|
| v2 | - | Kompatibel | Kompatibel | Kompatibel |
| [v1](v1/teaser.md) | Kompatibel | Kompatibel | - | Kompatibel |

## Fjärrsupport för Assets {#remote-assets}

Teaser Component (från och med [version 2.23.2](/help/versions.md)) stöder fjärrresurser. [När du har konfigurerat](/help/developing/remote-assets.md) kan du välja resurser från en fjärrtjänst för din teaserkomponent.

## Exempel på komponentutdata {#sample-component-output}

Om du vill se både Teaser Component (Teaser-komponenten) och exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_teaser).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Teaser Component [finns på GitHub](https://adobe.com/go/aem_cmp_tech_teaser_v1).

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Innehållsförfattaren kan använda dialogrutan Konfigurera för att definiera egenskaperna för det enskilda lagret. Det finns också en [redigeringsdialogruta](#edit-dialog) där du kan ändra suddgummibilden om en sådan är markerad.

### Fliken Länkar {#links-tab}

![Länkflik i redigeringsdialogrutan för komponenten Teaser](/help/assets/teaser-edit-links.png)

Teaser title, description and image can be inherited from the linked page, or from the page linked in the first call to action. Om varken en länk eller ett anrop till en åtgärd anges ärvs titeln, beskrivningen och bilden från den aktuella sidan.

* **Länk** - Den här filen länkar till en innehållssida, extern URL eller sidankarpunkt.
* **Öppna länken på den nya fliken** - Om den är aktiverad öppnas länken på en ny webbläsarflik.
* **Call-to-actions** - Med det här alternativet kan du länka till flera mål.
   * Den sida som är länkad i den första call-to-action-filen används när du ärver teaser titel, beskrivning eller bild.

### Fliken Text {#text-tab}

![Textflik i redigeringsdialogrutan för Teaser Component](/help/assets/teaser-edit-text.png)

* **Förrubrik** - Förrubriken visas före teasertiteln.
* **Titel** - Definierar en titel som ska visas som rubrik för suddgummit.
   * **Hämta rubrik från länkad sida** - Om det här alternativet är markerat fylls rubriken i med den länkade sidans rubrik.
* **Beskrivning** - Definierar en beskrivning som ska visas som underrubrik till suddgummit.
   * **Hämta beskrivning från länkad sida** - Om det här alternativet är markerat fylls beskrivningen i med den länkade sidans beskrivning.
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [datalagret](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

### Fliken Resurser {#asset-tab}

![Fliken Redigera dialogruta för Teaser Component](/help/assets/teaser-edit-image.png)

* **Ärv bild från sida** - Använd bilden som definierats i sidegenskaperna för den länkade sidan eller den aktuella sidan om ingen finns.
* **Bildresurs** - Släpp en resurs från [resursläsaren](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html?lang=sv-SE) eller tryck på alternativet **bläddra** om du vill överföra från ett lokalt filsystem.
   * Tryck eller klicka på **Radera** för att avmarkera den markerade bilden.
   * Tryck eller klicka på **Välj** för att öppna [resursläsaren](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html?lang=sv-SE) och välja en bild.
      * Om [Fjärrsupport för Assets](#remote-assets) är aktiverat har du flera alternativ för att välja en resurs:
         * **Lokal** väljer från det lokala AEM-resursbiblioteket.
         * **Fjärr** väljer från ett dynamiskt mediebibliotek utanför din AEM-instans.
   * Tryck eller klicka på **Redigera** om du vill [hantera återgivningarna av resursen](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html?lang=sv-SE) i resursredigeraren.
* **Alternativ text för hjälpmedel** - I det här fältet kan du definiera en beskrivning av bilden för användare med nedsatt syn.
   * **Ärv alternativ text från sida** - Det här alternativet använder den alternativa beskrivningen av det länkade objektvärdet för `dc:description` -metadata i DAM eller för den aktuella sidan om ingen resurs är länkad.
* **Tillhandahåll inte alternativ text** - Med det här alternativet markeras bilden som ska ignoreras av hjälpmedelstekniker som skärmläsare om bilden är enbart dekorativ eller på annat sätt inte förmedlar någon ytterligare information till sidan.

### Fliken Format {#styles-tab-edit}

![Fliken Stilar i redigeringsdialogrutan för komponenten Teaser List ](/help/assets/teaser-edit-styles.png)

Teaser Component har stöd för AEM [Style System.](/help/get-started/authoring.md#component-styling).

Använd listrutan för att välja de format som du vill använda på komponenten. Markeringar som görs i redigeringsdialogrutan har samma effekt som de som väljs i komponentverktygsfältet.

Format måste konfigureras för den här komponenten i [designdialogrutan](#design-dialog) för att den nedrullningsbara menyn ska vara tillgänglig.

## Dialogrutan Redigera {#edit-dialog}

Teaser Component (Teaser-komponenten) delegerar bildåtergivning till [Image Component (Bildkomponent)](image.md). Därför är dialogrutan [redigera]&#x200B;(image.md#edit-dialog för Image Component tillgänglig för innehållsförfattaren så att den kan manipulera teaserbilden.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera de laseralternativ som innehållsförfattaren har när den här komponenten används.

### Teaser Tab {#teaser-tab}

![Teaser Components designdialogruta](/help/assets/teaser-design.png)

* **Call-to-actions**
   * **Inaktivera Call-To-Actions** - Dölj alternativet **Call-To-Actions** för innehållsförfattare
* **Elements**
   * **Dölj pretitle** - Döljer alternativet **Pretitle** för innehållsförfattare
   * **Dölj titel** - Döljer alternativet **Titel** för innehållsförfattare
      * När **titeltypen** är markerad döljs den
   * **Dölj beskrivning** - Dölj alternativet **Beskrivning** för innehållsförfattare
* **Standardtiteltyp** - Definierar H-taggen som ska användas av teaser-titeln.
* **Bilddelegat** - Informativ visning som anger till vilken komponent Teaser delegerar bildhantering.

### Fliken Format {#styles-tab}

Teaser Component har stöd för AEM [Style System](/help/get-started/authoring.md#component-styling).

## Adobe Client Data Layer {#data-layer}

Teaser-komponenten stöder [Adobe Client Data Layer.](/help/developing/data-layer/overview.md)
