---
title: Bildkomponent
description: Komponenten Core Component Image är en adaptiv bildkomponent.
role: Architect, Developer, Admin, User
exl-id: c5e57f4b-139f-40e7-8d79-be9a74360b63
source-git-commit: a10c98aecf6d3c0d989f2e3c18affc51850f60bc
workflow-type: tm+mt
source-wordcount: '2061'
ht-degree: 0%

---


# Bildkomponent {#image-component}

Komponenten Core Component Image är en adaptiv bildkomponent.

## Användning {#usage}

Bildkomponenten har adaptiv bildmarkering och responsivt beteende med lat inläsningsalternativ för sidbesökaren och enkel bildplacering för innehållsförfattaren.

Innehållsförfattaren kan använda [redigeringsdialogruta](#edit-dialog) om du vill redigera bildresursen, till exempel tillämpa en beskärning eller rotera bilden.

Bildbredderna och ytterligare inställningar kan definieras av mallskaparen i [designdialogruta](#design-dialog). Innehållsredigeraren kan överföra eller välja resurser i [dialogrutan konfigurera.](#configure-dialog)

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Image Component är v3, som introducerades i version 2.18.0 av Core Components i februari 2022, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v3 | - | Kompatibel | Kompatibel |
| [v2](v2/image.md) | Kompatibel | Kompatibel | Kompatibel |
| [v1](v1/image-v1.md) | Kompatibel | Kompatibel | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Huvudkomponentversioner](/help/versions.md).

## Responsiva funktioner {#responsive-features}

Image Component har robusta responsiva funktioner som är klara direkt vid leverans. På sidmallsnivå visas [designdialogruta](#design-dialog) kan användas för att definiera bildresursens standardbredder. Bildkomponenten läser automatiskt in rätt bredd för visning beroende på storleken på webbläsarfönstret. När fönstrets storlek ändras läses bildkomponenten in dynamiskt med rätt bildstorlek. Komponentutvecklare behöver inte bekymra sig om att definiera anpassade mediefrågor eftersom Image Component redan är optimerat för att läsa in ditt innehåll.

Dessutom har Image Component stöd för lazy loading för att skjuta upp inläsningen av den faktiska bildresursen tills den syns i webbläsaren, vilket gör sidorna mer responsiva.

>[!TIP]
>
>Som standard drivs Image-komponenten av Adaptive Image Server. Se [Adaptiv bildserver](/help/developing/adaptive-image-servlet.md) om du vill ha mer information om hur det fungerar.

## Dynamic Media Support {#dynamic-media}

Bildkomponenten (från [version 2.13.0](/help/versions.md)) har stöd [Dynamic Media](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/dynamicmedia/dynamic-media.html) resurser. [När det är aktiverat](#design-dialog) Med de här funktionerna kan du lägga till Dynamic Media-bildresurser med en enkel dra och släpp-funktion eller via filläsaren på samma sätt som med andra bilder. Dessutom stöds även bildmodifierare, bildförinställningar och smarta beskärningar.

Dina webbupplevelser som byggts med Core Components kan innehålla omfattande, Sensei-baserade, robusta, högpresterande, plattformsoberoende Dynamic Media Image-funktioner.

## Nästa generations Dynamic Media-support {#next-gen-dm}

Bildkomponenten (från [version 2.23.2](/help/versions.md)) har stöd för nästa generations Dynamic Media fjärrresurser.

[När konfigurationen är klar](/help/developing/next-gen-dm.md) du kan välja resurser från en fjärr-Dynamic Media-tjänst för nästa generation för din bildkomponent.

## Stöd för SVG {#svg-support}

Skalbar vektorgrafik (SVG) stöds av bildkomponenten.

* Både dra-och-släpp av en SVG-resurs från DAM och överföring av en SVG-fil som överförts från ett lokalt filsystem stöds.
* Den ursprungliga SVG-filen direktuppspelas (omformningar hoppas över).
* För en SVG-bild ställs&quot;smarta bilder&quot; och&quot;smarta storlekar&quot; in på en tom array i bildmodellen.

### Dokumentskydd {#security}

Av säkerhetsskäl anropas aldrig SVG direkt av bildredigeraren. Den kallas för `<img src="path-to-component">`. Detta förhindrar webbläsaren från att köra skript som är inbäddade i filen SVG.

## Exempel på komponentutdata {#sample-component-output}

Om du vill se exempel på Image Component (Bildkomponent) och dess konfigurationsalternativ samt HTML och JSON-utdata går du till [Komponentbibliotek](https://adobe.com/go/aem_cmp_library_image).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Image Component [finns på GitHub](https://adobe.com/go/aem_cmp_tech_image_v3).

Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

Bildkomponenten har stöd för [schema.org](https://schema.org).

## Dialogrutan Redigera {#edit-dialog}

I redigeringsdialogrutan kan författaren beskära och zooma bilden.

Beroende på om du har [Dynamic Media](#dynamic-media) aktiverad eller [Nästa generations Dynamic Media](#next-gen-dm) om du aktiverar det här alternativet skiljer sig alternativen för att redigera bilder åt.

### Standardredigering av resurser {#standard-assets}

Om du redigerar AEM resurser kan du klicka på **Redigera** -ikonen på snabbmenyn för bildkomponenten.

![Redigeringsdialogruta för bildkomponent](/help/assets/image-edit.png)

* Starta beskärning

  ![Ikonen Starta beskärning](/help/assets/image-start-crop.png)

  Om du väljer det här alternativet öppnas en listruta för fördefinierade beskärningsproportioner.

   * Välj alternativ **Ta bort beskärning** för att visa den ursprungliga resursen.

  När du har valt ett beskärningsalternativ använder du de blå handtagen för att ändra storlek på beskärningen i bilden.

  ![Beskärningsalternativ](/help/assets/image-crop-options.png)

* Rotera åt höger

  ![Rotera höger ikon](/help/assets/image-rotate-right.png)

  Använd det här alternativet om du vill rotera bilden 90° åt höger (medurs).

* Återställ zoomning

  ![Återställ zoomningsikon](/help/assets/image-reset-zoom.png)

  Om bilden redan har zoomats kan du återställa zoomnivån med det här alternativet.

* Öppna zoomreglaget

  ![Öppna zoomskjutningsikonen](/help/assets/image-zoom.png)

  Använd det här alternativet om du vill visa ett reglage för att styra bildens zoomnivå.

  ![Zoomreglage](/help/assets/image-zoom-slider.png)

Du kan även använda redigeraren på plats för att ändra bilden. På grund av utrymmesbegränsningar är endast grundläggande alternativ tillgängliga. Använd helskärmsläget för redigeringsalternativ.

![Redigeringsalternativ för bilder på plats](/help/assets/image-in-place-edit.png)

>[!NOTE]
>
>Bildredigeringsåtgärder stöds inte för bilder i GIF. Alla sådana ändringar som gjorts i redigeringsläget för GIF bevaras inte.

### Dynamic Media resursredigering {#dynamic-media-assets}

Om du har [Dynamic Media-funktioner aktiverade,](#dynamic-media) redigering av själva bilden måste utföras i resurskonsolen.

### Nästa generation av Dynamic Media Asset Editing {#next-gen-dm-assets}

Om du har [Nästa generations Dynamic Media konfigurerade,](#next-gen-dm) den **Smart beskärning** är tillgängligt på komponentens snabbmenyer.

![Smart beskärning](/help/assets/image-smart-crop.png)

Använd dialogrutan för att justera den smarta beskärningen.

![Dialogrutan Smart beskärning](/help/assets/image-smart-crop-dialog.png)

>[!TIP]
>
>Mer information om smart beskärning finns i [den här videon om funktionen.](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/dynamic-media/images/smart-crop-feature-video-use.html)

## Konfigurera dialogruta {#configure-dialog}

I bildkomponenten finns en konfigurationsdialogruta där själva bilden definieras tillsammans med dess beskrivning och grundläggande egenskaper.

### Fliken Resurser {#asset-tab}

![Fliken Resurser i dialogrutan Konfigurera för bildkomponenten](/help/assets/image-configure-asset.png)

* **Ärv bild från sida** - Det här alternativet använder [bild av den länkade sidan](page.md) eller den aktuella sidans aktuella bild om bilden inte är länkad.

* **Bildresurs** - Detta fylls i automatiskt om **Ärv bild från sida** är markerat. Avmarkera om du vill definiera bilden manuellt genom att ange följande alternativ.

   * Släpp en resurs från [resursläsare](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/environment-tools.html) eller tryck på **bläddra** så att du kan överföra från ett lokalt filsystem.
   * Tryck eller klicka **Rensa** för att avmarkera den markerade bilden.
   * Tryck eller klicka **Välj** för att öppna [resursläsare](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/environment-tools.html) så att du kan markera en bild.
      * If [Nästa generations Dynamic Media-funktioner](#next-gen-dm) är aktiverade har du flera alternativ för att välja en resurs:
         * **Lokal** väljer från det lokala AEM resursbiblioteket.
         * **Fjärr** väljer från ett Dynamic Media-bibliotek utanför din AEM.
   * Tryck eller klicka **Redigera** till [hantera återgivningar av resursen](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/manage/manage-digital-assets.html) i Resursredigeraren.

* **Alternativ text för tillgänglighet** - I det här fältet kan du definiera en beskrivning av bilden för användare med nedsatt syn.

   * **Ärv alternativ text från sida** - Det här alternativet använder den alternativa beskrivningen av det länkade tillgångsvärdet för `dc:description` metadata i DAM eller på den aktuella sidan om ingen resurs är länkad.

* **Ange inte en alternativ text** - Markerar bilden som ska ignoreras av hjälpmedelstekniker, t.ex. skärmläsare, i de fall där bilden är helt dekorativ eller på annat sätt inte förmedlar någon ytterligare information till sidan.

### Fliken Metadata {#metadata-tab}

![Fliken Metadata i dialogrutan Konfigurera för Image Component](/help/assets/image-configure-metadata.png)

* **Förinställningstyp** - Detta definierar de typer av bildförinställningar som är tillgängliga, antingen **Bildförinställning** eller **Smart beskärning** och är bara tillgängligt när [Dynamic Media-funktioner](#dynamic-meida) är aktiverade.
   * **Bildförinställning** - När **Förinställningstyp** av **Bildförinställning** är markerat, listrutan **Bildförinställning** är tillgängligt och du kan välja bland de tillgängliga förinställningarna för Dynamic Media. Detta är bara tillgängligt om förinställningar har definierats för den valda resursen.
   * **Smart beskärning** - När **Förinställningstyp** av **Smart beskärning** är markerat, listrutan **Återgivning** är tillgängligt och du kan välja bland de tillgängliga återgivningarna av den valda resursen. Detta är bara tillgängligt om återgivningar har definierats för den valda resursen.
   * **Bildmodifierare** - Ytterligare kommandon för att visa bilder i Dynamic Media kan definieras här avgränsade med `&`, oavsett vilka **Förinställningstyp** är markerat.
* **Bildtext** - Ytterligare information om bilden, som visas under bilden som standard.
   * **Hämta beskrivning från DAM** - När det här alternativet är markerat fylls bildtexten i med värdet för `dc:title` metadata i DAM.
   * **Visa bildtext som popup-fönster** - När det här alternativet är markerat visas inte bildtexten nedanför bilden, utan som en popup-ruta som visas av vissa webbläsare när de hovrar över bilden.
* **Länk** - Länka bilden till en annan resurs.
   * Använd urvalsdialogrutan för att länka till en annan AEM.
   * Om du inte länkar till en AEM resurs anger du den absoluta URL:en. Icke-lösliga URL:er tolkas som relativa till AEM.
   * **Öppna länk på ny flik** - Med det här alternativet öppnas länken i ett nytt webbläsarfönster.
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [Datalager](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

>[!TIP]
>
>**Smart beskärning** och **Bildförinställning** alternativ som utesluter varandra. Om en författare måste använda en bildförinställning tillsammans med en rendering för smart beskärning måste författaren använda **Bildmodifierare** om du vill lägga till förinställningar manuellt.

### Fliken Format {#styles-tab-edit}

![Fliken Stilar i redigeringsdialogrutan för Bildkomponent](/help/assets/image-configure-styles.png)

Bildkomponenten stöder AEM [Formatsystem](/help/get-started/authoring.md#component-styling).

Använd listrutan för att välja de format som du vill använda på komponenten. Markeringar som görs i redigeringsdialogrutan har samma effekt som de som väljs i komponentverktygsfältet.

Format måste konfigureras för den här komponenten i [designdialogruta](#design-dialog) för att den nedrullningsbara menyn ska vara tillgänglig.

## Designdialogruta {#design-dialog}

### Huvudflik {#main-tab}

![Huvudflik i designdialogrutan för bildkomponenten](/help/assets/image-design-main.png)

* **Aktivera DM-funktioner** - När det är markerat, [Dynamic Media-funktioner](#dynamic-media) är tillgängliga.
   * Det här alternativet visas bara när Dynamic Media är aktiverat i miljön.
* **Aktivera webboptimerade bilder** - När det är markerat, [webboptimerad bildleveranstjänst](/help/developing/web-optimized-image-delivery.md) levererar bilder i WebP-format, vilket minskar bildstorleken med i genomsnitt 25 %.
   * Det här alternativet är endast tillgängligt i AEMaaCS.
   * Om alternativet inte är markerat eller webboptimerad bildleveranstjänst inte är tillgänglig visas [Adaptiv bildserver](/help/developing/adaptive-image-servlet.md) används.
* **Inaktivera lazy loading** - När det här alternativet är markerat läser komponenten in alla bilder i förväg utan att de läses in.
* **Bilden är dekorativ** - Ange om alternativet för dekorativa bilder ska aktiveras automatiskt när du lägger till bildkomponenten på en sida.
* **Hämta alternativ text från DAM**- Ange om alternativet att hämta alternativ text från DAM automatiskt ska aktiveras när bildkomponenten läggs till på en sida.
* **Hämta beskrivning från DAM** - Ange om alternativet att hämta bildtexten från DAM-modulen ska aktiveras automatiskt när bildkomponenten läggs till på en sida.
* **Visa bildtext som popup-fönster** - Ange om alternativet att visa bildtexten som en popup-ruta automatiskt ska aktiveras när bildkomponenten läggs till på en sida.
* **Ändra bredd** - Det här värdet används för att ändra bredden på basbilderna som är DAM-resurser.
   * Bildernas proportioner bevaras.
   * Om värdet är större än bildens faktiska bredd har det här värdet ingen effekt.
   * Det här värdet påverkar inte bilder i SVG.

Du kan definiera en lista med bredder i pixlar för bilden så läser komponenten automatiskt in den mest lämpliga bredden baserat på webbläsarens storlek. Detta är en viktig del av [responsiva funktioner](#responsive-features) för bildkomponenten.

* **Bredd** - Definierar en lista med bredder i pixlar för bilden och komponenten läser automatiskt in den mest lämpliga bredden baserat på webbläsarens storlek.
   * Tryck eller klicka på **Lägg till** om du vill lägga till en annan storlek.
      * Använd handtagen för att ordna om storleken.
      * Använd **Ta bort** om du vill ta bort en bredd.
   * Inläsningen av bilder fördröjs som standard tills de blir synliga.
      * Välj alternativet **Inaktivera lazy loading** så att du kan läsa in bilderna när sidan läses in.
* **JPEG-kvalitet** - Kvalitetsfaktorn (i procent mellan 0 och 100) för omformade (t.ex. skalade eller beskurna) bilder i JPEG.

>[!TIP]
>
>Se dokumentet [Adaptiv bildserver](/help/developing/adaptive-image-servlet.md) för tips om hur du kan optimera markeringen av återgivning genom att definiera dina bredder noggrant.

### Fliken Format {#styles-tab}

Bildkomponenten stöder AEM [Formatsystem](/help/get-started/authoring.md#component-styling).

## Adobe-klientdatalager {#data-layer}

Bildkomponenten har stöd för [Adobe Client Data Layer.](/help/developing/data-layer/overview.md)
