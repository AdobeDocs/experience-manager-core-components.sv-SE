---
title: Email Teaser Component
description: Med e-postlaserkomponenten kan du visa en bild, en titel, RTF-text och eventuellt länka till mer innehåll.
role: Architect, Developer, Admin, User
exl-id: d6123b22-7cba-406c-986d-b6f00322d135
source-git-commit: 91969e4956bef1a511b8d588d5290a7999bf86ec
workflow-type: tm+mt
source-wordcount: '1002'
ht-degree: 0%

---


# Email Teaser Component {#email-teaser-component}

Med e-postlaserkomponenten kan du visa en bild, en titel, RTF-text och eventuellt länka till mer innehåll.

## Användning {#usage}

Med e-postteamkomponenten kan innehållsförfattaren enkelt skapa ett suddgummi med en bild, en titel eller formaterad text och länka till ytterligare innehåll eller andra åtgärder.

* Mallförfattaren kan använda [designdialogrutan](#design-dialog) för att definiera om alternativen för att skapa anrop till åtgärder och lägga till länkar är tillgängliga samt inaktivera olika visningsalternativ.
* Innehållsförfattaren kan använda dialogrutan [Konfigurera](#configure-dialog) för att ange en bild, definiera CTA, ange titlar och beskrivningar och konfigurera länkar till det enskilda lagret.
* Dialogrutan [Redigera](image.md#edit-dialog) för [E-postbildkomponenten](image.md) är tillgänglig för att ändra suddgummibilden.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av E-postteamkomponenten är v1, som introducerades med version x av e-postkärnkomponenterna i oktober 2022, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponenterna är kompatibla med samt länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|---|---|---|---|
| v1 | Kompatibel | - | - |

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om E-postteamkomponenten [finns på GitHub.](https://adobe.com/go/aem_cmp_tech_email_teaser_v1)

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen till utvecklaren av kärnkomponenter.](/help/developing/overview.md)

## Konfigurera dialogruta {#configure-dialog}

Innehållsförfattaren kan använda dialogrutan Konfigurera för att definiera egenskaperna för det enskilda lagret. Det finns också en [redigeringsdialogruta](#edit-dialog) där du kan ändra suddgummibilden om en sådan är markerad.

### Fliken Länkar {#links-tab}

![Länk i redigeringsdialogrutan för e-postlaserkomponenten](/help/email/assets/email-teaser-edit-links.png)

Teaser title, description och image kan ärvas från det länkade innehållet eller från det innehåll som är länkat i den första call-to-action. Om varken en länk eller en call-to-action anges ärvs titeln, beskrivningen och bilden från det aktuella innehållet.

* **Länk** - Den här filen länkar till innehåll, extern URL eller ankarpunkt.
   * Klicka på Campaign-ikonen för att öppna dialogrutan [Välj Adobe Campaign-variabel](/help/email/campaign-variables.md) och infoga dynamiskt innehåll från Adobe Campaign.
* **Call-to-actions** - Med det här alternativet kan du länka till flera mål.
   * Den sida som är länkad i den första call-to-action-filen används när du ärver teaser titel, beskrivning eller bild.
   * Klicka på Campaign-ikonen för att öppna dialogrutan [Välj Adobe Campaign-variabel](/help/email/campaign-variables.md) och infoga dynamiskt innehåll från Adobe Campaign.

### Fliken Text {#text-tab}

![Textflik i redigeringsdialogrutan för e-postlaserkomponenten](/help/email/assets/email-teaser-edit-text.png)

* **Förrubrik** - Förrubriken visas före teasertiteln.
* **Titel** - Definierar en titel som ska visas som rubrik för suddgummit.
   * Klicka på Campaign-ikonen för att öppna dialogrutan [Välj Adobe Campaign-variabel](/help/email/campaign-variables.md) och infoga dynamiskt innehåll från Adobe Campaign.
   * **Hämta rubrik från länkad sida** - Om det här alternativet är markerat fylls rubriken i med den länkade sidans rubrik.
* **Beskrivning** - Definierar en beskrivning som ska visas som underrubrik till suddgummit.
   * Klicka på ikonen **Välj Adobe Campaign-variabel** för att öppna dialogrutan [Välj Adobe Campaign-variabel](/help/email/campaign-variables.md) och infoga dynamiskt innehåll från Adobe Campaign.
   * **Hämta beskrivning från länkad sida** - Om det här alternativet är markerat fylls beskrivningen i med den länkade sidans beskrivning.
* **ID** - Med det här alternativet kan du kontrollera den unika identifieraren för komponenten i HTML.
   * Om du inte anger något värde genereras ett unikt ID automatiskt och du hittar det genom att kontrollera innehållet.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka CSS.

### Fliken Resurser {#asset-tab}

![Fliken Redigera dialogruta för e-postunderkomponentredigering](/help/email/assets/email-teaser-edit-image.png)

* **Ärv bild från sida** - Använd bilden som definierats i sidegenskaperna för den länkade sidan eller den aktuella sidan om ingen finns.
* **Bildresurs** - Släpp en resurs från [resursläsaren](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) eller tryck på alternativet **bläddra** om du vill överföra från ett lokalt filsystem.
   * Tryck eller klicka på **Radera** för att avmarkera den markerade bilden.
   * Tryck eller klicka på **Redigera** om du vill [hantera återgivningarna av resursen](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) i resursredigeraren.
* **Alternativ text för hjälpmedel** - I det här fältet kan du definiera en beskrivning av bilden för användare med nedsatt syn.
   * **Ärv alternativ text från sida** - Det här alternativet använder den alternativa beskrivningen av det länkade objektvärdet för `dc:description` -metadata i DAM eller för den aktuella sidan om ingen resurs är länkad.
* **Tillhandahåll inte alternativ text** - Med det här alternativet markeras bilden som ska ignoreras av hjälpmedelstekniker som skärmläsare om bilden är enbart dekorativ eller på annat sätt inte förmedlar någon ytterligare information till sidan.

>[!NOTE]
>
>[Dynamiska mediefunktioner](image.md#dynamic-media) är för närvarande inte tillgängliga i Teaser Component.

### Fliken Format {#styles-tab-edit}

Komponenten Email Teaser stöder AEM [Style System.](/help/get-started/authoring.md#component-styling)

Använd listrutan för att välja de format som du vill använda på komponenten. Markeringar som görs i redigeringsdialogrutan har samma effekt som de som väljs i komponentverktygsfältet.

Format måste konfigureras för den här komponenten i [designdialogrutan](#design-dialog) för att fliken ska vara tillgänglig.

## Dialogrutan Redigera {#edit-dialog}

E-postteamkomponenten delegerar bildåtergivning till [bildkomponenten](image.md). Därför är [redigeringsdialogrutan](image.md#edit-dialog) för Image-komponenten tillgänglig för innehållsförfattaren så att den kan manipulera teaserbilden.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera de laseralternativ som innehållsförfattaren har när den här komponenten används.

### Teaser Tab {#teaser-tab}

![Email Teaser Components designdialogruta](/help/email/assets/email-teaser-design.png)

* **Tillåtna rubrikelement** - Använd listrutan för att definiera vilken rubrik i HTML-element som kan väljas av en författare för lärarens titeltyp.
* **Standardrubrikelement för rubriken** - Standardrubrikelementet för HTML som används för teaserns titeltyp
* **Call-to-actions**
   * **Inaktivera Call-To-Actions** - Dölj alternativet **Call-To-Actions** för innehållsförfattare
* **Elements**
   * **Dölj pretitle** - Döljer alternativet **Pretitle** för innehållsförfattare
   * **Dölj titel** - Döljer alternativet **Titel** för innehållsförfattare
      * När **titeltypen** är markerad döljs den
   * **Visa titeltyp**
   * **Dölj beskrivning** - Dölj alternativet **Beskrivning** för innehållsförfattare
* **Bilddelegat** - Informativ visning som anger till vilken komponent som e-postteamet delegerar bildhantering.

### Fliken Format {#styles-tab}

Komponenten Email Teaser stöder AEM [Style System.](/help/get-started/authoring.md#component-styling)
