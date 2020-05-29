---
title: Teaser Component
description: Teaser-komponenten kan visa en bild, en titel, RTF och eventuellt länka till ytterligare innehåll.
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '751'
ht-degree: 1%

---


# Teaser Component {#teaser-component}

Core Component Teaser Component Component Component kan visa en bild, en titel, RTF-text och eventuellt länka till ytterligare innehåll.

## Användning {#usage}

Teaser Component (Teaser Component) gör det enkelt för innehållsförfattaren att skapa ett suddgummi för ytterligare innehåll med hjälp av en bild, en titel eller formaterad text och länka till ytterligare innehåll eller andra åtgärder.

Mallförfattaren kan använda [designdialogrutan](#design-dialog) för att definiera om alternativen för att skapa anrop till åtgärder och lägga till länkar är tillgängliga samt inaktivera olika visningsalternativ. Innehållsförfattaren kan använda dialogrutan [](#configure-dialog) Konfigurera för att ställa in en bild, definiera CTA, ange titlar och beskrivningar och konfigurera länkar till den enskilda teaser. Du kommer åt [redigeringsdialogrutan](image.md#edit-dialog) för [bildkomponenten](image.md) för att ändra suddgummibilden.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Teaser Component är v1, som introducerades i version 2.1.0 av Core Components i juli 2018, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponentversionerna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|---|
| v1 | Kompatibel | Kompatibel | Kompatibel |

## Exempel på komponentutdata {#sample-component-output}

Om du vill se både Teaser Component (Teaser-komponenten) och exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_teaser).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Teaser Component [finns på GitHub](https://adobe.com/go/aem_cmp_tech_teaser_v1).

Mer information om hur du utvecklar kärnkomponenter finns i dokumentationen till [Core Components Developer](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Innehållsförfattaren kan använda dialogrutan Konfigurera för att definiera egenskaperna för det enskilda lagret. Det finns också en [redigeringsdialogruta](#edit-dialog) där du kan ändra suddgummibilden om du har valt en sådan.

### Bild {#image}

![Fliken Redigera i dialogrutan Teaser Component](/help/assets/teaser-edit-image.png)

* **Bildresurs**
   * Släpp en resurs från [resursläsaren](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) eller tryck på **bläddringsalternativet** om du vill överföra den från ett lokalt filsystem.
   * Tryck eller klicka på **Radera** för att avmarkera den markerade bilden.
   * Tryck eller klicka på **Redigera** för att [hantera återgivningarna av resursen](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) i resursredigeraren.

### Text {#text}

![Textflik i redigeringsdialogrutan för Teaser Component](/help/assets/teaser-edit-text.png)

* **Pretitle** - Förrubriken visas före teaser&#39;s title.
* **Titel** - Definierar en rubrik som ska visas som rubrik för suddgummit.
   * **Hämta rubrik från länkad sida** - När den är markerad fylls rubriken i med den länkade sidans rubrik.
* **Beskrivning** - Definierar en beskrivning som ska visas som underrubrik till suddgummit.
   * **Hämta beskrivning från länkad sida** - Om det här alternativet är markerat fylls beskrivningen i med den länkade sidans beskrivning.
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [datalagret](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

### Länkar och åtgärder {#links-actions}

![Länk-flik i redigeringsdialogrutan för Teaser Component](/help/assets/teaser-edit-link.png)

* **Link** - Link applied to the teaser. Använd sökvägsläsaren för att välja länkmålet.
* **Aktivera anrop-till-åtgärder** - När det här alternativet är markerat aktiveras definitionen av anrop-till-åtgärder. Den första Call-To-Action-länken i listan används som länk för andra teaserelement.

## Dialogrutan Redigera {#edit-dialog}

Teaser Component (Teaser-komponenten) delegerar bildåtergivning till [Image Component (Bildkomponent](image.md)). Därför är dialogrutan [för]redigering (image.md#edit-dialog) av Image Component tillgänglig för innehållsförfattaren så att den kan manipulera teaserbilden.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera de laseralternativ som innehållsförfattaren har när den här komponenten används.

### Teaser Tab {#teaser-tab}

![Teaser Component&#39;s design dialog](/help/assets/teaser-design.png)

* **Call-to-actions**
   * **Inaktivera Call-To-Actions** - Dölj alternativet **Call-To-Actions** för innehållsförfattare
* **Element**
   * **Dölj pretitel** - Döljer alternativet **Pretitle** för innehållsförfattare
   * **Dölj rubrik** - Döljer alternativet **Titel** för innehållsförfattare
      * Om du väljer det här alternativet döljs **titeltypen**
   * **Dölj beskrivning** - Dölj alternativet **Beskrivning** för innehållsförfattare
* **Titeltyp** - Definierar H-taggen som ska användas av teaser-titeln.
* **Länkar**
   * **Länka inte bilden** - När det här alternativet är markerat är inte suddgummibilden länkad
   * **Länka inte titeln** - När det här alternativet är markerat är inte lagernamnet länkat
* **Bilddelegering** - Informativ visning som visar vilken komponent Teaser delegerar bildhantering till.

### Fliken Format {#styles-tab}

Teaser Component har stöd för AEM [Style System](/help/get-started/authoring.md#component-styling).
