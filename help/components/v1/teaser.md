---
title: Teaser Component (v1)
description: Teaser-komponenten kan visa en bild, en titel, RTF och eventuellt länka till ytterligare innehåll.
role: Architect, Developer, Admin, User
exl-id: 48e56938-660a-43e7-9e62-8069283ae73f
source-git-commit: 84e09fa64b3a7ae40ff3ff1a04ea1c7504db29d2
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 0%

---

# Teaser Component (v1) {#teaser-component}

Core Component Teaser Component Component Component kan visa en bild, en titel, RTF-text och eventuellt länka till ytterligare innehåll.

## Användning {#usage}

Teaser Component (Teaser Component) gör det enkelt för innehållsförfattaren att skapa ett suddgummi för ytterligare innehåll med hjälp av en bild, en titel eller formaterad text och länka till ytterligare innehåll eller andra åtgärder.

Mallförfattaren kan använda [designdialogruta](#design-dialog) för att definiera om alternativen för att skapa anrop till åtgärder och lägga till länkar är tillgängliga samt inaktivera olika visningsalternativ. Innehållsförfattaren kan använda [konfigurera dialogruta](#configure-dialog) för att ställa in en bild, definiera CTA, ange titlar och beskrivningar och konfigurera länkar till den enskilda teaser. The [redigeringsdialogruta](image-v1.md#edit-dialog) i [Bildkomponent](image-v1.md) kan användas för att ändra suddgummibilden.

## Version och kompatibilitet {#version-and-compatibility}

I det här dokumentet beskrivs v1 av Teaser Component, som introducerades i version 2.1.0 av Core Components i juli 2018.

>[!CAUTION]
>
>I det här dokumentet beskrivs v1 för Teaser Component.
>
>Information om den aktuella versionen av Teaser Component finns i [Teaser Component](/help/components/teaser.md) -dokument.

## Exempel på komponentutdata {#sample-component-output}

Om du vill se både Teaser Component och exempel på dess konfigurationsalternativ samt HTML och JSON-utdata går du till [Komponentbibliotek](https://adobe.com/go/aem_cmp_library_teaser).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Teaser Component [finns på GitHub](https://adobe.com/go/aem_cmp_tech_teaser_v1).

Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Innehållsförfattaren kan använda dialogrutan Konfigurera för att definiera egenskaperna för det enskilda lagret. Det finns också en [redigeringsdialogruta](#edit-dialog) om du vill ändra suddgummibilden om en sådan är markerad.

### Bild {#image}

![Fliken Redigera i dialogrutan Teaser Component](/help/assets/teaser-edit-image.png)

* **Bildresurs**
   * Släpp en resurs från [resursläsare](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) eller tryck på **bläddra** om du vill överföra från ett lokalt filsystem.
   * Tryck eller klicka **Rensa** för att avmarkera den markerade bilden.
   * Tryck eller klicka **Redigera** till [hantera återgivningar av resursen](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) i resursredigeraren.

>[!NOTE]
>
>[Funktioner i Dynamic Media](image-v1.md#dynamic-media) är för närvarande inte tillgängliga i Teaser Component.

### Text {#text}

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

### Länkar och åtgärder {#links-actions}

![Länk-flik i redigeringsdialogrutan för Teaser Component](/help/assets/teaser-edit-link.png)

* **Länk** - Länken används på teaser. Använd sökvägsläsaren för att välja länkmålet.
* **Aktivera anrop till åtgärder** - När det här alternativet är markerat aktiveras definitionen av&quot;Call-To-Actions&quot;. Den första Call-To-Action-länken i listan används som länk för andra teaserelement.

## Dialogrutan Redigera {#edit-dialog}

Teaser Component delegerar bildåtergivning till [Bildkomponent](image-v1.md). Därför [redigeringsdialogruta](image-v1.md#edit-dialog) av Image Component (Bildkomponent) är tillgängligt för innehållsförfattaren för att ändra den teaseravbildningen.

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
* **Titeltyp** - Definierar H-taggen som ska användas av teaser-titeln.
* **Länkar**
   * **Länka inte bilden** - När det här alternativet är markerat är suddgummibilden inte länkad
   * **Länka inte titeln** - När det här alternativet är markerat länkas inte teasertitel
* **Bildombud** - Informativ visning som anger vilken komponent Teaser delegerar bildhanteringen.

### Fliken Format {#styles-tab}

Teaser Component har stöd för AEM [Formatsystem](/help/get-started/authoring.md#component-styling).

## Adobe-klientdatalager {#data-layer}

Teaser Component har stöd för [Adobe Client Data Layer.](/help/developing/data-layer/overview.md)
