---
title: Bildkomponent
description: Komponenten Core Component Image är en adaptiv bildkomponent.
role: Architect, Developer, Admin, User
exl-id: c5e57f4b-139f-40e7-8d79-be9a74360b63
source-git-commit: dd30def59a8f037864da875ef4c831b11f766e57
workflow-type: tm+mt
source-wordcount: '2062'
ht-degree: 0%

---


# Bildkomponent {#image-component}

Komponenten Core Component Image är en adaptiv bildkomponent.

{{traditional-aem}}

## Användning {#usage}

Bildkomponenten har adaptiv bildmarkering och responsivt beteende med lat inläsningsalternativ för sidbesökaren och enkel bildplacering för innehållsförfattaren.

Innehållsförfattaren kan använda dialogrutan [Redigera](#edit-dialog) för att redigera bildresursen, till exempel tillämpa en beskärning eller rotera bilden.

Bildbredderna och ytterligare inställningar kan definieras av mallskaparen i [designdialogrutan](#design-dialog). Innehållsredigeraren kan överföra eller välja resurser i dialogrutan [Konfigurera.](#configure-dialog)

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Image Component är v3, som introducerades i version 2.18.0 av Core Components i februari 2022, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponenterna är kompatibla med samt länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|--- |--- |--- |---|---|
| v3 | - | Kompatibel | Kompatibel | Kompatibel |
| [v2](v2/image.md) | Kompatibel | Kompatibel | - | Kompatibel |
| [v1](v1/image-v1.md) | Kompatibel | Kompatibel | - | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Core Components Versions](/help/versions.md).

## Responsiva funktioner {#responsive-features}

Image Component har robusta responsiva funktioner som är klara direkt vid leverans. På sidmallsnivå kan du använda [designdialogrutan](#design-dialog) för att definiera standardbredderna för bildresursen. Bildkomponenten läser automatiskt in rätt bredd för visning beroende på storleken på webbläsarfönstret. När fönstrets storlek ändras läses bildkomponenten in dynamiskt med rätt bildstorlek. Komponentutvecklare behöver inte bekymra sig om att definiera anpassade mediefrågor eftersom Image Component redan är optimerat för att läsa in ditt innehåll.

Dessutom har Image Component stöd för lazy loading för att skjuta upp inläsningen av den faktiska bildresursen tills den syns i webbläsaren, vilket gör sidorna mer responsiva.

>[!TIP]
>
>Som standard drivs Image-komponenten av Adaptive Image Server. Se [Adaptiv bildserver](/help/developing/adaptive-image-servlet.md) för mer information om hur den fungerar.

### Skillnader med v2 {#v2-differences}

Till skillnad från version 2 av Image Component (Bildkomponent) använder version 3 webbläsarbaserad svarstider. Det innebär att webbläsaren får en uppsättning källor för en bild med olika bredder och att webbläsaren väljer det bästa.

För det mesta föredrar webbläsarna att lokalt minska bredden så att den passar en mindre visningsruta i stället för att hämta en bild med mindre bredd från servern. Detta är förväntat och varför bildkomponenten inte ska användas för grafisk riktning (olika bilder/beskärningar för olika visningsrutor).

[Mer information finns i den tekniska dokumentationen för bildkomponenten](https://github.com/adobe/aem-core-wcm-components/tree/main/content/src/content/jcr_root/apps/core/wcm/components/image/v3/image#javascript-data-attribute-bindings).

## Stöd för dynamiska media {#dynamic-media}

Bildkomponenten (från och med [version 2.13.0](/help/versions.md)) har stöd för [Dynamiska media](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/dynamicmedia/dynamic-media.html?lang=sv-SE)-resurser. [När det här alternativet är aktiverat kan du använda ](#design-dialog) för att lägga till bildresurser i dynamiska media genom att dra och släppa eller via resursläsaren på samma sätt som med andra bilder. Dessutom stöds även bildmodifierare, bildförinställningar och smarta beskärningar.

Dina webbupplevelser som byggts med Core Components kan innehålla kraftfulla, Sensei-baserade, robusta, högpresterande, plattformsoberoende Dynamic Media Image-funktioner.

## Fjärrsupport för Assets {#remote-assets}

Bildkomponenten (från och med [version 2.23.2](/help/versions.md)) stöder fjärrresurser. [När du har konfigurerat](/help/developing/remote-assets.md) kan du välja resurser från en fjärrtjänst för din bildkomponent.

## SVG Support {#svg-support}

Scalable Vector Graphics (SVG) stöds av Image Component.

* Både dra-och-släpp av en SVG-resurs från DAM och överföring av en SVG-fil som överförts från ett lokalt filsystem stöds.
* Den ursprungliga SVG-filen direktuppspelas (omformningar hoppas över).
* För en SVG-bild ställs&quot;smarta bilder&quot; och&quot;smarta storlekar&quot; in på en tom array i bildmodellen.

### Dokumentskydd {#security}

Av säkerhetsskäl anropas aldrig den ursprungliga SVG direkt av bildredigeraren. Den anropas via `<img src="path-to-component">`. Detta förhindrar webbläsaren från att köra skript som är inbäddade i SVG-filen.

## Exempel på komponentutdata {#sample-component-output}

Om du vill se exempel på Image-komponenten och dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_image).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Image-komponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_image_v3).

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).

Bildkomponenten stöder [schema.org ](https://schema.org).

## Dialogrutan Redigera {#edit-dialog}

I redigeringsdialogrutan kan författaren beskära och zooma bilden.

Beroende på om [Dynamic Media](#dynamic-media) är aktiverat eller om [Fjärrsupport för Assets](#remote-assets) är aktiverat, skiljer sig alternativen för att redigera bilder åt.

### Standardredigering av resurser {#standard-assets}

Om du redigerar AEM-standardresurser kan du klicka på ikonen **Redigera** på snabbmenyn för bildkomponenten.

![Redigeringsdialogrutan för bildkomponenten](/help/assets/image-edit.png)

* Starta beskärning

  ![Ikonen Starta beskärning](/help/assets/image-start-crop.png)

  Om du väljer det här alternativet öppnas en listruta för fördefinierade beskärningsproportioner.

   * Välj alternativet **Ta bort beskärning** om du vill visa den ursprungliga resursen.

  När du har valt ett beskärningsalternativ använder du de blå handtagen för att ändra storlek på beskärningen i bilden.

  ![Beskärningsalternativ](/help/assets/image-crop-options.png)

* Rotera åt höger

  ![Rotera höger ikon](/help/assets/image-rotate-right.png)

  Använd det här alternativet om du vill rotera bilden 90° åt höger (medurs).

* Återställ zoomning

  ![Återställ zoomningsikonen](/help/assets/image-reset-zoom.png)

  Om bilden redan har zoomats kan du återställa zoomnivån med det här alternativet.

* Öppna zoomreglaget

  ![Öppna ikonen för zoomreglaget](/help/assets/image-zoom.png)

  Använd det här alternativet om du vill visa ett reglage för att styra bildens zoomnivå.

  ![Zoomreglage](/help/assets/image-zoom-slider.png)

Du kan även använda redigeraren på plats för att ändra bilden. På grund av utrymmesbegränsningar är endast grundläggande alternativ tillgängliga. Använd helskärmsläget för redigeringsalternativ.

![Redigeringsalternativ för bilder på plats](/help/assets/image-in-place-edit.png)

>[!NOTE]
>
>Bildredigeringsåtgärder stöds inte för GIF-bilder. Alla sådana ändringar som görs i redigeringsläget för GIF-filer bevaras inte.

### Dynamisk redigering av mediatillgångar {#dynamic-media-assets}

Om du har aktiverat [dynamiska mediefunktioner måste ](#dynamic-media) redigering av själva bilden utföras i resurskonsolen.

## Konfigurera dialogruta {#configure-dialog}

I bildkomponenten finns en konfigurationsdialogruta där själva bilden definieras tillsammans med dess beskrivning och grundläggande egenskaper.

### Fliken Resurser {#asset-tab}

![Fliken Resurser i dialogrutan Konfigurera i bildkomponenten](/help/assets/image-configure-asset.png)

* **Ärv bild från sida** - Det här alternativet använder den [aktuella bilden för den länkade sidan](page.md) eller den aktuella sidans bild om bilden inte är länkad.

* **Bildresurs** - Detta fylls i automatiskt om **Ärv bild från sida** har valts. Avmarkera om du vill definiera bilden manuellt genom att ange följande alternativ.

   * Släpp en resurs från [resursläsaren](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/environment-tools.html?lang=sv-SE) eller tryck på alternativet **bläddra** så att du kan överföra från ett lokalt filsystem.
   * Tryck eller klicka på **Radera** för att avmarkera den markerade bilden.
   * Tryck eller klicka på **Välj** för att öppna [resursläsaren](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/environment-tools.html?lang=sv-SE) så att du kan välja en bild.
      * Om [Stöd för fjärrresurser](#remote-assets) är aktiverat har du flera alternativ för att välja en resurs:
         * **Lokal** väljer från det lokala AEM-resursbiblioteket.
         * **Fjärr** väljer från ett dynamiskt mediebibliotek utanför din AEM-instans.
   * Tryck eller klicka på **Redigera** om du vill [hantera återgivningarna av resursen](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/manage/manage-digital-assets.html?lang=sv-SE) i resursredigeraren.

* **Alternativ text för hjälpmedel** - I det här fältet kan du definiera en beskrivning av bilden för användare med nedsatt syn.

   * **Ärv alternativ text från sida** - Det här alternativet använder den alternativa beskrivningen av det länkade objektvärdet för `dc:description` -metadata i DAM eller för den aktuella sidan om ingen resurs är länkad.

* **Ange inte någon alternativ text** - Markerar bilden som ska ignoreras av hjälpmedelstekniker som skärmläsare för fall där bilden är enbart dekorativ eller på annat sätt inte förmedlar någon ytterligare information till sidan.

### Fliken Metadata {#metadata-tab}

![Fliken Metadata i dialogrutan Konfigurera för Image Component (Bildkomponent)](/help/assets/image-configure-metadata.png)

* **Förinställningstyp** - Detta definierar de typer av bildförinställningar som är tillgängliga, antingen **Bildförinställning** eller **Smart beskärning**, och är bara tillgängligt när [Dynamiska mediefunktioner](#dynamic-meida) är aktiverade.
   * **Bildförinställning** - När **Förinställningstyp** för **Bildförinställning** är markerad är den nedrullningsbara menyn **Bildförinställning** tillgänglig, vilket gör att du kan välja bland de tillgängliga dynamiska medieförinställningarna. Detta är bara tillgängligt om förinställningar har definierats för den valda resursen.
   * **Smart beskärning** - När **förinställningstyp** för **smart beskärning** har valts är listrutan **Återgivning** tillgänglig, vilket gör att du kan välja bland de tillgängliga återgivningarna för den valda resursen. Detta är bara tillgängligt om återgivningar har definierats för den valda resursen.
   * **Bildmodifierare** - Fler kommandon för visning av dynamiska bilder kan definieras här avgränsade med `&`, oavsett vilken **förinställningstyp** som har valts.
* **Bildtext** - Ytterligare information om bilden, som visas under bilden som standard.
   * **Hämta bildtext från DAM** - När den är markerad fylls bildtexten i med värdet för `dc:title`-metadata i DAM.
   * **Visa bildtext som popup-fönster** - Om det här alternativet är markerat visas inte bildtexten under bilden, utan som ett popup-fönster som visas av vissa webbläsare när de hovrar över bilden.
* **Länk** - Länka bilden till en annan resurs.
   * Använd urvalsdialogrutan för att länka till en annan AEM-resurs.
   * Om du inte länkar till en AEM-resurs anger du den absoluta URL:en. Ej lösliga URL:er tolkas som relativa till AEM.
   * **Öppna länk på ny flik** - Det här alternativet öppnar länken i ett nytt webbläsarfönster.
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [datalagret](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

>[!TIP]
>
>**Smart beskärning** och **Bildförinställning** kan inte användas samtidigt. Om en författare måste använda en bildförinställning tillsammans med en rendering för smart beskärning måste författaren använda **bildmodifieraren** för att lägga till förinställningar manuellt.

### Fliken Format {#styles-tab-edit}

![Fliken Stilar i redigeringsdialogrutan för bildkomponenten](/help/assets/image-configure-styles.png)

Bildkomponenten stöder AEM [Style System](/help/get-started/authoring.md#component-styling).

Använd listrutan för att välja de format som du vill använda på komponenten. Markeringar som görs i redigeringsdialogrutan har samma effekt som de som väljs i komponentverktygsfältet.

Format måste konfigureras för den här komponenten i [designdialogrutan](#design-dialog) för att den nedrullningsbara menyn ska vara tillgänglig.

## Designdialogruta {#design-dialog}

### Huvudflik {#main-tab}

![Huvudflik i designdialogrutan för bildkomponenten](/help/assets/image-design-main.png)

* **Aktivera DM-funktioner** - När det här alternativet är markerat är [Dynamiska mediefunktioner](#dynamic-media) tillgängliga.
   * Det här alternativet visas bara när Dynamic Media är aktiverat i miljön.
* **Aktivera webboptimerade bilder** - När det här alternativet är markerat levererar [den webboptimerade bildleveranstjänsten](/help/developing/web-optimized-image-delivery.md) bilder i WebP-format, vilket minskar bildstorleken med i genomsnitt 25 %.
   * Det här alternativet är endast tillgängligt i AEMaaCS.
   * Om alternativet inte är markerat, eller om den webboptimerade bildleveranstjänsten inte är tillgänglig, används [Adaptiv bildserver](/help/developing/adaptive-image-servlet.md).
* **Inaktivera lazy loading** - När det här alternativet är markerat läses alla bilder in i förväg utan att någon lazy läses in.
* **Bilden är dekorativ** - Definiera om alternativet för dekorativ bild automatiskt är aktiverat när du lägger till bildkomponenten på en sida.
* **Hämta alternativ text från DAM**- Definiera om alternativet att hämta alternativ text från DAM automatiskt aktiveras när bildkomponenten läggs till på en sida.
* **Hämta beskrivning från DAM** - Ange om alternativet att hämta bildtexten från DAM automatiskt ska aktiveras när bildkomponenten läggs till på en sida.
* **Visa bildtext som popup-fönster** - Definiera om alternativet att visa bildtexten som ett popup-fönster automatiskt ska aktiveras när bildkomponenten läggs till på en sida.
* **Ändra storlek på bredd** - Det här värdet används för att ändra storlek på bredden på basbilderna som är DAM-resurser.
   * Bildernas proportioner bevaras.
   * Om värdet är större än bildens faktiska bredd har det här värdet ingen effekt.
   * Det här värdet påverkar inte SVG-bilder.

Du kan definiera en lista med bredder i pixlar för bilden så läser komponenten automatiskt in den mest lämpliga bredden baserat på webbläsarens storlek. Detta är en viktig del av [responsiva funktioner](#responsive-features) i Image-komponenten.

* **Bredder** - Definierar en lista med bredder i pixlar för bilden och komponenten läser automatiskt in den mest lämpliga bredden baserat på webbläsarens storlek.
   * Tryck eller klicka på knappen **Lägg till** om du vill lägga till en annan storlek.
      * Använd handtagen för att ordna om storleken.
      * Använd ikonen **Ta bort** för att ta bort en bredd.
   * Inläsningen av bilder fördröjs som standard tills de blir synliga.
      * Välj alternativet **Inaktivera lazy loading** så att du kan läsa in bilderna när sidan läses in.
* **JPEG-kvalitet** - Kvalitetsfaktorn (i procent från 0 och 100) för omformade (till exempel skalade eller beskurna) JPEG-bilder.

>[!TIP]
>
>I dokumentet [Adaptiv bildserver](/help/developing/adaptive-image-servlet.md) finns tips om hur du kan optimera markeringen av återgivning genom att definiera dina bredder noggrant.

### Fliken Format {#styles-tab}

Bildkomponenten stöder AEM [Style System](/help/get-started/authoring.md#component-styling).

## Adobe Client Data Layer {#data-layer}

Image-komponenten stöder [Adobe Client Data Layer.](/help/developing/data-layer/overview.md)
