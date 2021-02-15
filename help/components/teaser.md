---
title: Teaser Component
description: Teaser-komponenten kan visa en bild, en titel, RTF och eventuellt länka till ytterligare innehåll.
translation-type: tm+mt
source-git-commit: d3ebcea5fa1523c1a986841cd3d1a64e16e85f6d
workflow-type: tm+mt
source-wordcount: '775'
ht-degree: 1%

---


# Teaser Component {#teaser-component}

Core Component Teaser Component Component Component kan visa en bild, en titel, RTF-text och eventuellt länka till ytterligare innehåll.

## Användning {#usage}

Teaser Component (Teaser Component) gör det enkelt för innehållsförfattaren att skapa ett suddgummi för ytterligare innehåll med hjälp av en bild, en titel eller formaterad text och länka till ytterligare innehåll eller andra åtgärder.

Mallförfattaren kan använda [designdialogrutan](#design-dialog) för att definiera om alternativen för att skapa anrop till åtgärder och lägga till länkar är tillgängliga samt inaktivera olika visningsalternativ. Innehållsförfattaren kan använda dialogrutan [Konfigurera](#configure-dialog) för att ställa in en bild, definiera CTA, ange titlar och beskrivningar och konfigurera länkar till den enskilda teaser. Dialogrutan [Redigera](image.md#edit-dialog) för [Image Component](image.md) kan öppnas för att ändra suddgummibilden.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Teaser Component är v1, som introducerades i version 2.1.0 av Core Components i juli 2018, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|---|
| v1 | Kompatibel | Kompatibel | Kompatibel |

## Exempelkomponentutdata {#sample-component-output}

Om du vill visa Teaser Component (Teaser-komponenten) och se exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_teaser).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Teaser Component [finns på GitHub](https://adobe.com/go/aem_cmp_tech_teaser_v1).

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen till Core Components developer](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Innehållsförfattaren kan använda dialogrutan Konfigurera för att definiera egenskaperna för det enskilda lagret. Det finns också en [redigeringsdialogruta](#edit-dialog) där du kan ändra suddgummibilden om en sådan är markerad.

### Bild {#image}

![Fliken Redigera i dialogrutan Teaser Component](/help/assets/teaser-edit-image.png)

* **Bildresurs**
   * Släpp en resurs från [resursläsaren](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) eller tryck på **bläddra** om du vill överföra från ett lokalt filsystem.
   * Tryck eller klicka på **Rensa** för att avmarkera den markerade bilden.
   * Tryck eller klicka på **Redigera** för att [hantera återgivningarna av resursen](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) i resursredigeraren.

>[!NOTE]
>
>[Dynamic Media-](image.md#dynamic-media) funktioner är för närvarande inte tillgängliga i Teaser Component.

### Text {#text}

![Textflik i redigeringsdialogrutan för Teaser Component](/help/assets/teaser-edit-text.png)

* **Pretitle**  - Förrubriken visas före teaser&#39;s title.
* **Titel**  - Definierar en titel som ska visas som rubrik för suddgummit.
   * **Hämta rubrik från länkad sida**  - Om det här alternativet är markerat fylls rubriken i med den länkade sidans rubrik.
* **Beskrivning**  - Definierar en beskrivning som ska visas som underrubrik till suddgummit.
   * **Hämta beskrivning från länkad sida**  - Om det här alternativet är markerat fylls beskrivningen i med den länkade sidans beskrivning.
* **ID**  - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i  [datalagret](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

### Länkar och åtgärder {#links-actions}

![Länk-flik i redigeringsdialogrutan för Teaser Component](/help/assets/teaser-edit-link.png)

* **Link** - Link applied to the teaser. Använd sökvägsläsaren för att välja länkmålet.
* **Aktivera anrop-till-åtgärder** - När det här alternativet är markerat aktiveras definitionen av anrop-till-åtgärder. Den första Call-To-Action-länken i listan används som länk för andra teaserelement.

## Redigera dialogruta {#edit-dialog}

Teaser Component (Teaser-komponenten) delegerar bildåtergivning till [Image Component](image.md). Därför är dialogrutan [redigera](image.md#edit-dialog för Image Component tillgänglig för innehållsförfattaren så att den kan manipulera teaserbilden.

## Designdialog {#design-dialog}

I designdialogrutan kan mallskaparen definiera de laseralternativ som innehållsförfattaren har när den här komponenten används.

### Teaser Tab {#teaser-tab}

![Teaser Component&#39;s design dialog](/help/assets/teaser-design.png)

* **Call-to-actions**
   * **Inaktivera Call-To-Actions** - Dölj alternativet  **Call-To-** Action för innehållsförfattare
* **Element**
   * **Dölj pretitel**  - Döljer alternativet  **** Förnamn för innehållsförfattare
   * **Dölj rubrik**  - Döljer alternativet  **** Titel för innehållsförfattare
      * När **titeltypen** är markerad döljs den
   * **Dölj beskrivning** - Dölj  **** beskrivningsalternativet för innehållsförfattare
* **Titeltyp**  - Definierar H-taggen som ska användas av teaser-titeln.
* **Länkar**
   * **Länka inte bilden**  - När det här alternativet är markerat är suddgummibilden inte länkad
   * **Länka inte titeln** - När det här alternativet är markerat är inte lagernamnet länkat
* **Bilddelegering**  - Informativ visning som visar vilken komponent Teaser delegerar bildhantering till.

### Fliken Format {#styles-tab}

Teaser Component har stöd för AEM [Style System](/help/get-started/authoring.md#component-styling).

## Adobe-klientdatalagret {#data-layer}

Teaser Component (Teaser-komponenten) stöder [Adobe Client Data Layer.](/help/developing/data-layer/overview.md)
