---
title: Email Teaser Component
description: Med e-postlaserkomponenten kan du visa en bild, en titel, RTF-text och eventuellt länka till mer innehåll.
role: Architect, Developer, Admin, User
exl-id: d6123b22-7cba-406c-986d-b6f00322d135
source-git-commit: 33976c0e745ad091a142109f70541f01a31edc5b
workflow-type: tm+mt
source-wordcount: '1056'
ht-degree: 0%

---


# Email Teaser Component {#email-teaser-component}

Med e-postlaserkomponenten kan du visa en bild, en titel, RTF-text och eventuellt länka till mer innehåll.

## Användning {#usage}

Med e-postteamkomponenten kan innehållsförfattaren enkelt skapa ett suddgummi med en bild, en titel eller formaterad text och länka till ytterligare innehåll eller andra åtgärder.

* Mallförfattaren kan använda [designdialogruta](#design-dialog) för att definiera om alternativen för att skapa anrop till åtgärder och lägga till länkar är tillgängliga samt inaktivera olika visningsalternativ.
* Innehållsförfattaren kan använda [konfigurera dialogruta](#configure-dialog) för att ställa in en bild, definiera CTA, ange titlar och beskrivningar och konfigurera länkar till den enskilda teaser.
* The [redigeringsdialogruta](image.md#edit-dialog) i [E-postbildkomponent](image.md) kan användas för att ändra suddgummibilden.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av E-postteamkomponenten är v1, som introducerades med version x av e-postkärnkomponenterna i oktober 2022, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | Kompatibel | Kompatibel |

## Exempel på komponentutdata {#sample-component-output}

Om du vill se exempel på e-postlaserkomponenten och dess konfigurationsalternativ samt HTML och JSON-utdata går du till [Komponentbibliotek.](https://adobe.com/go/aem_cmp_library_email_teaser)

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om e-postteamkomponenten [finns på GitHub.](https://adobe.com/go/aem_cmp_tech_email_teaser_v1)

Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentens utvecklare.](/help/developing/overview.md)

## Konfigurera dialogruta {#configure-dialog}

Innehållsförfattaren kan använda dialogrutan Konfigurera för att definiera egenskaperna för det enskilda lagret. Det finns också en [redigeringsdialogruta](#edit-dialog) om du vill ändra suddgummibilden om en sådan är markerad.

### Fliken Länkar {#links-tab}

![Länkflik i dialogrutan Redigera för e-postkomponenten](/help/email/assets/email-teaser-edit-links.png)

Teaser title, description och image kan ärvas från det länkade innehållet eller från det innehåll som länkats i den första anropet. Om varken en länk eller ett anrop till åtgärd anges ärvs titeln, beskrivningen och bilden från det aktuella innehållet.

* **Länk** - Den här filen länkar till innehåll, extern URL eller ankarpunkt.
   * Klicka på Campaign-ikonen för att öppna [Välj Adobe Campaign-variabel](/help/email/campaign-variables.md) för att infoga dynamiskt innehåll från Adobe Campaign.
* **Call-to-actions** - Med det här alternativet kan du länka till flera mål.
   * Den sida som är länkad i det första anropet används när du ärver teasertitel, beskrivning eller bild.
   * Klicka på Campaign-ikonen för att öppna [Välj Adobe Campaign-variabel](/help/email/campaign-variables.md) för att infoga dynamiskt innehåll från Adobe Campaign.

### Fliken Text {#text-tab}

![Textflik i redigeringsdialogrutan för e-postkomponenten](/help/email/assets/email-teaser-edit-text.png)

* **Förtitel** - Förrubriken visas före teaser titel.
* **Titel** - Definierar en titel som ska visas som rubrik för suddgummit.
   * Klicka på Campaign-ikonen för att öppna [Välj Adobe Campaign-variabel](/help/email/campaign-variables.md) för att infoga dynamiskt innehåll från Adobe Campaign.
   * **Hämta rubrik från länkad sida** - När det här alternativet är markerat fylls rubriken i med den länkade sidans rubrik.
* **Beskrivning** - Definierar en beskrivning som ska visas som underrubrik till suddgummit.
   * Klicka på **Välj Adobe Campaign-variabel** -ikonen för att öppna [Välj Adobe Campaign-variabel](/help/email/campaign-variables.md) för att infoga dynamiskt innehåll från Adobe Campaign.
   * **Hämta beskrivning från länkad sida** - När det här alternativet är markerat fylls beskrivningen i med den länkade sidans beskrivning.
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML.
   * Om du inte anger något värde genereras ett unikt ID automatiskt och du hittar det genom att kontrollera innehållet.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka CSS.

### Fliken Resurser {#asset-tab}

![Fliken Redigera dialogruta för e-postundervisningskomponentens redigeringsdialogruta](/help/email/assets/email-teaser-edit-image.png)

* **Ärv bild från sida** - Använd bilden som är definierad i sidegenskaperna för den länkade sidan eller den aktuella sidan om ingen finns.
* **Bildresurs** - Släpp en resurs från [resursläsare](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) eller tryck på **bläddra** om du vill överföra från ett lokalt filsystem.
   * Tryck eller klicka **Rensa** för att avmarkera den markerade bilden.
   * Tryck eller klicka **Redigera** till [hantera återgivningar av resursen](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) i Resursredigeraren.
* **Alternativ text för tillgänglighet** - I det här fältet kan du definiera en beskrivning av bilden för användare med nedsatt syn.
   * **Ärv alternativ text från sida** - Det här alternativet använder den alternativa beskrivningen av det länkade tillgångsvärdet för `dc:description` metadata i DAM eller på den aktuella sidan om ingen resurs är länkad.
* **Ange inte en alternativ text** - Med det här alternativet markeras den bild som ska ignoreras av hjälpmedelstekniker, som skärmläsare, om bilden är helt dekorativ eller på annat sätt inte förmedlar någon ytterligare information till sidan.

>[!NOTE]
>
>[Funktioner i Dynamic Media](image.md#dynamic-media) är för närvarande inte tillgängliga i Teaser Component.

### Fliken Format {#styles-tab-edit}

E-postteamkomponenten stöder AEM [Formatsystem.](/help/get-started/authoring.md#component-styling)

Använd listrutan för att välja de format som du vill använda på komponenten. Markeringar som görs i redigeringsdialogrutan har samma effekt som de som väljs i komponentverktygsfältet.

Format måste konfigureras för den här komponenten i [designdialogruta](#design-dialog) för att fliken ska vara tillgänglig.

## Dialogrutan Redigera {#edit-dialog}

E-postteamkomponenten delegerar bildåtergivning till [Bildkomponent](image.md). Därför [redigeringsdialogruta](image.md#edit-dialog) av Image Component (Bildkomponent) är tillgängligt för innehållsförfattaren för att ändra den teaseravbildningen.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera de laseralternativ som innehållsförfattaren har när den här komponenten används.

### Teaser Tab {#teaser-tab}

![Email Teaser Component&#39;s design dialog](/help/email/assets/email-teaser-design.png)

* **Tillåtna rubrikelement** - Använd listrutan för att definiera vilka rubrikelement i HTML som kan väljas av en författare för teaser titeltyp.
* **Rubrikens standardrubrikelement** - Standardelementet för rubrik HTML som används för suddgummits titeltyp
* **Call-to-actions**
   * **Inaktivera anrop till åtgärder** - Dölj **Call-to-actions** alternativ för innehållsförfattare
* **Element**
   * **Dölj pretitle** - Döljer **Förtitel** alternativ för innehållsförfattare
   * **Dölj titel** - Döljer **Titel** alternativ för innehållsförfattare
      * När du har valt **Titeltyp** är dold
   * **Visa titeltyp**
   * **Dölj beskrivning** - Dölj **Beskrivning** alternativ för innehållsförfattare
* **Bildombud** - Informativ visning som anger vilken komponent som e-postteamet delegerar bildhanteringen till.

### Fliken Format {#styles-tab}

E-postteamkomponenten stöder AEM [Formatsystem.](/help/get-started/authoring.md#component-styling)
