---
title: Teaser Component (v1)
description: Teaser-komponenten kan visa en bild, en titel, RTF-text och eventuellt länka till ytterligare innehåll.
role: Architect, Developer, Admin, User
exl-id: 48e56938-660a-43e7-9e62-8069283ae73f
index: n
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: tm+mt
source-wordcount: '722'
ht-degree: 0%

---


# Teaser Component (v1) {#teaser-component}

Core Component Teaser Component Component Component kan visa en bild, en titel, RTF-text och eventuellt länka till ytterligare innehåll.

## Användning {#usage}

Teaser Component (Teaser Component) gör det enkelt för innehållsförfattaren att skapa ett suddgummi för ytterligare innehåll med hjälp av en bild, en titel eller formaterad text och länka till ytterligare innehåll eller andra åtgärder.

Mallförfattaren kan använda [designdialogrutan](#design-dialog) för att definiera om alternativen för att skapa anrop till åtgärder och lägga till länkar är tillgängliga samt inaktivera olika visningsalternativ. Innehållsförfattaren kan använda dialogrutan [Konfigurera](#configure-dialog) för att ange en bild, definiera CTA, ange titlar och beskrivningar och konfigurera länkar till det enskilda lagret. Dialogrutan [Redigera](image-v1.md#edit-dialog) för [bildkomponenten](image-v1.md) är tillgänglig för att ändra suddgummibilden.

## Version och kompatibilitet {#version-and-compatibility}

Detta dokument beskriver v1 av Teaser Component, som introducerades i version 2.1.0 av Core Components i juli 2018.

>[!CAUTION]
>
>I det här dokumentet beskrivs v1 för Teaser Component.
>
>Information om den aktuella versionen av Teaser Component finns i dokumentet [Teaser Component](/help/components/teaser.md) .

## Exempel på komponentutdata {#sample-component-output}

Om du vill se både Teaser Component (Teaser-komponenten) och exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_teaser).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Teaser Component [finns på GitHub](https://adobe.com/go/aem_cmp_tech_teaser_v1).

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Innehållsförfattaren kan använda dialogrutan Konfigurera för att definiera egenskaperna för det enskilda lagret. Det finns också en [redigeringsdialogruta](#edit-dialog) där du kan ändra suddgummibilden om en sådan är markerad.

### Bild {#image}

![Fliken Redigera dialogruta för Teaser Component](/help/assets/teaser-edit-image.png)

* **Bildresurs**
   * Släpp en resurs från [resursläsaren](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) eller tryck på alternativet **bläddra** om du vill överföra från ett lokalt filsystem.
   * Tryck eller klicka på **Radera** för att avmarkera den markerade bilden.
   * Tryck eller klicka på **Redigera** om du vill [hantera återgivningarna av resursen](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) i resursredigeraren.

>[!NOTE]
>
>[Dynamiska mediefunktioner](image-v1.md#dynamic-media) är för närvarande inte tillgängliga i Teaser Component.

### Text {#text}

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

### Länkar och åtgärder {#links-actions}

![Länk till redigeringsdialogruta för Teaser Component](/help/assets/teaser-edit-link.png)

* **Länk** - Länken används på suddgummit. Använd sökvägsläsaren för att välja länkmålet.
* **Aktivera anrop-till-åtgärder** - När det här alternativet är markerat aktiveras definitionen av anrop-till-åtgärder. Den första Call-to-action-länken i listan används som länk för andra teaser-element.

## Dialogrutan Redigera {#edit-dialog}

Teaser Component (Teaser-komponenten) delegerar bildåtergivning till [Image Component (Bildkomponent)](image-v1.md). Därför är [redigeringsdialogrutan](image-v1.md#edit-dialog) för Image-komponenten tillgänglig för innehållsförfattaren så att den kan manipulera teaserbilden.

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
* **Titeltyp** - Definierar H-taggen som ska användas av teaser-titeln.
* **Länkar**
   * **Länka inte bilden** - När det här alternativet är markerat är inte suddgummibilden länkad
   * **Länka inte titeln** - När det här alternativet är markerat är inte lagrets titel länkad
* **Bilddelegat** - Informativ visning som anger till vilken komponent Teaser delegerar bildhantering.

### Fliken Format {#styles-tab}

Teaser Component har stöd för AEM [Style System](/help/get-started/authoring.md#component-styling).

## Adobe Client Data Layer {#data-layer}

Teaser-komponenten stöder [Adobe Client Data Layer.](/help/developing/data-layer/overview.md)
