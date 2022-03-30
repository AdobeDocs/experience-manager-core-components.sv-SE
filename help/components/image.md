---
title: Bildkomponent
description: Core Component Image Component Component är en adaptiv bildkomponentfunktion för redigering på plats.
role: Architect, Developer, Admin, User
exl-id: c5e57f4b-139f-40e7-8d79-be9a74360b63
source-git-commit: 1a02aea6cda2bb1f70ab97d7a439e2c8e64add52
workflow-type: tm+mt
source-wordcount: '1799'
ht-degree: 0%

---

# Bildkomponent{#image-component}

Core Component Image Component Component är en adaptiv bildkomponent med redigering på plats.

## Användning {#usage}

Bildkomponenten har anpassningsbar bildmarkering och responsiv funktionalitet med lat inläsningsbeteende för sidbesökaren samt enkel bildplacering och beskärning för innehållsförfattaren.

Bildbredderna och ytterligare inställningar kan definieras av mallskaparen i [designdialogruta](#design-dialog). Innehållsredigeraren kan överföra eller välja resurser i [dialogrutan konfigurera.](#configure-dialog)

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Image Component är v3, som introducerades i version 2.18.0 av Core Components i februari 2022, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v3 | - | Kompatibel | Kompatibel |
| [v2](v2/image.md) | Kompatibel | Kompatibel | Kompatibel |
| [v1](v1/image-v1.md) | Kompatibel | Kompatibel | - |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Huvudkomponentversioner](/help/versions.md).

## Responsiva funktioner {#responsive-features}

Image Component har robusta responsiva funktioner som är klara direkt vid leverans. På sidmallsnivå visas [designdialogruta](#design-dialog) kan användas för att definiera bildresursens standardbredder. Bildkomponenten läser sedan automatiskt in rätt bredd för visning beroende på storleken på webbläsarfönstret. När fönstrets storlek ändras läser Image Component in rätt bildstorlek dynamiskt i farten. Komponentutvecklare behöver inte bekymra sig om att definiera anpassade mediefrågor eftersom Image Component redan är optimerat för att läsa in ditt innehåll.

Dessutom har Image Component stöd för lazy loading för att skjuta upp inläsningen av den faktiska bildresursen tills den syns i webbläsaren, vilket gör sidorna mer responsiva.

>[!TIP]
>
>Se avsnittet [Adaptiv bildserver](#adaptive-image-servlet) om du vill ha mer teknisk information om dessa funktioner och tips för hur du optimerar urvalet av renderingar.

## Dynamic Media Support {#dynamic-media}

Bildkomponenten (från och med [version 2.13.0](/help/versions.md)) har stöd för [Dynamic Media](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/dynamic-media.html#dynamicmedia) resurser. [När det är aktiverat](#design-dialog) Med de här funktionerna kan du lägga till Dynamic Media bildresurser med en enkel dra och släpp-funktion eller via resursläsaren på samma sätt som med andra bilder. Dessutom stöds även bildmodifierare, bildförinställningar och smarta beskärningar.

Dina webbupplevelser som byggts med Core Components har inga omfattande, Sensei-baserade, robusta, högpresterande, plattformsoberoende Dynamic Media Image-funktioner.

## Stöd för SVG {#svg-support}

Skalbar vektorgrafik (SVG) stöds av bildkomponenten.

* Både dra-och-släpp av en SVG-resurs från DAM och överföring av en SVG-filöverföring från ett lokalt filsystem stöds.
* Den adaptiva bildservern strömmar den ursprungliga SVG-filen (omformningar hoppas över).
* För en SVG-bild ställs&quot;smarta bilder&quot; och&quot;smarta storlekar&quot; in på en tom array i bildmodellen.

### Dokumentskydd {#security}

Av säkerhetsskäl anropas aldrig SVG direkt av bildredigeraren. Den kallas för `<img src=“path-to-component”>`. Detta förhindrar webbläsaren från att köra skript som är inbäddade i filen SVG.

>[!NOTE]
>
>För SVG-support krävs version 2.1.0 av Core Components eller senare tillsammans med [Service Pack 2](https://experienceleague.adobe.com/docs/experience-manager-64/release-notes/sp-release-notes.html) för AEM 6.4 eller senare för [bildredigeringsfunktioner](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/full-stack/components-templates/image-editor.html) inom AEM.

## Exempel på komponentutdata {#sample-component-output}

Om du vill se både Image Component (Bildkomponent) och exempel på dess konfigurationsalternativ samt HTML och JSON-utdata går du till [Komponentbibliotek](https://adobe.com/go/aem_cmp_library_image).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Image Component [finns på GitHub](https://adobe.com/go/aem_cmp_tech_image_v2).

Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

Bildkomponenten har stöd för [schema.org, mikrodata](https://schema.org).

## Konfigurera dialogruta {#configure-dialog}

I bildkomponenten finns en konfigurationsdialogruta där själva bilden definieras tillsammans med dess beskrivning och grundläggande egenskaper.

### Fliken Resurser {#asset-tab}

![Fliken Resurser i dialogrutan Konfigurera för bildkomponenten](/help/assets/image-configure-asset.png)

* **Ärv bild från sida** - Det här alternativet använder [bild av den länkade sidan](page.md) eller den aktuella sidans aktuella bild om bilden inte är länkad.

* **Alternativ text för tillgänglighet** - I det här fältet kan du definiera en beskrivning av bilden för användare med nedsatt syn.

   * **Ärv alternativ text från sida** - Det här alternativet använder den alternativa beskrivningen av det länkade tillgångsvärdet för `dc:description` metadata i DAM eller på den aktuella sidan om ingen resurs är länkad.

* **Bildresurs**
   * Släpp en resurs från [resursläsare](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) eller tryck på **bläddra** om du vill överföra från ett lokalt filsystem.
   * Tryck eller klicka **Rensa** för att avmarkera den markerade bilden.
   * Tryck eller klicka **Redigera** till [hantera återgivningar av resursen](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) i resursredigeraren.

* **Ange inte en alternativ text** - Med det här alternativet markeras den bild som ska ignoreras av hjälpmedelstekniker, som skärmläsare, om bilden är helt dekorativ eller på annat sätt inte förmedlar någon ytterligare information till sidan.

### Fliken Metadata {#metadata-tab}

![Fliken Metadata i dialogrutan Konfigurera för Image Component](/help/assets/image-configure-metadata.png)

* **Förinställningstyp** - Detta definierar de typer av bildförinställningar som är tillgängliga, antingen **Bildförinställning** eller **Smart beskärning** och är bara tillgängligt när [Funktioner i Dynamic Media](#dynamic-meida) är aktiverade.
   * **Bildförinställning** - När **Förinställningstyp** av **Bildförinställning** är markerat, listrutan **Bildförinställning** är tillgängligt och du kan välja bland de tillgängliga förinställningarna för Dynamic Media. Detta är bara tillgängligt om förinställningar har definierats för den valda resursen.
   * **Smart beskärning** - När **Förinställningstyp** av **Smart beskärning** är markerat i listrutan **Återgivning** är tillgängligt och du kan välja bland de tillgängliga återgivningarna av den valda resursen. Detta är bara tillgängligt om återgivningar har definierats för den valda resursen.
   * **Bildmodifierare** - Ytterligare kommandon för att visa bilder i Dynamic Media kan definieras här avgränsade med `&`oavsett vilka **Förinställningstyp** är markerat.
* **Bildtext** - Ytterligare information om bilden, som visas under bilden som standard.
   * **Hämta beskrivning från DAM** - När det här alternativet är markerat fylls bildtexten i med värdet för `dc:title` metadata i DAM.
   * **Visa bildtext som popup-fönster** - När det här alternativet är markerat visas inte bildtexten nedanför bilden, utan som ett popup-fönster som visas av vissa webbläsare när de hovrar över bilden.
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
>**Smart beskärning** och **Bildförinställning** alternativ som utesluter varandra. Om en författare behöver använda en bildförinställning tillsammans med en rendering för smart beskärning måste författaren använda **Bildmodifierare** om du vill lägga till förinställningar manuellt.

### Fliken Format {#styles-tab-edit}

![Fliken Stilar i redigeringsdialogrutan för Bildkomponent](/help/assets/image-configure-styles.png)

Bildkomponenten stöder AEM [Formatsystem.](/help/get-started/authoring.md#component-styling).

Använd listrutan för att välja de format som du vill använda på komponenten. Markeringar som görs i redigeringsdialogrutan har samma effekt som de som väljs i komponentverktygsfältet.

Format måste konfigureras för den här komponenten i [designdialogruta](#design-dialog) för att den nedrullningsbara menyn ska vara tillgänglig.

## Designdialogruta {#design-dialog}

![Huvudflik i designdialogrutan för bildkomponenten](/help/assets/image-design-main.png)

* **Aktivera DM-funktioner** - När det är markerat, [Funktioner i Dynamic Media](#dynamic-media) är tillgängliga.
   * Det här alternativet visas bara när Dynamic Media är aktiverat i miljön.
* **Inaktivera lazy loading** - När det här alternativet är markerat kommer komponenten att förhandsladda alla bilder utan att läsas in.
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
      * Använd handtagen för att ordna om storlekarna.
      * Använd **Ta bort** om du vill ta bort en bredd.
   * Som standard skjuts inläsningen av bilder tills de blir synliga.
      * Välj alternativet **Inaktivera lazy loading** för att läsa in bilderna när sidan läses in.
* **JPEG-kvalitet** - Kvalitetsfaktorn (i procent mellan 0 och 100) för omformade (t.ex. skalade eller beskurna) bilder i JPEG.

>[!TIP]
>
>Se avsnittet [Adaptiv bildserver](#adaptive-image-servlet) om du vill ha mer teknisk information om dess funktioner och tips för att optimera markeringen av renderingar genom att noggrant definiera bredderna.

### Fliken Format {#styles-tab}

Bildkomponenten stöder AEM [Formatsystem](/help/get-started/authoring.md#component-styling).

## Adaptiv bildserver {#adaptive-image-servlet}

Bildkomponenten använder kärnkomponentens adaptiva bildserver. [Adaptiv bildserver](https://github.com/adobe/aem-core-wcm-components/wiki/The-Adaptive-Image-Servlet) ansvarar för bildbehandling och direktuppspelning och kan utnyttjas av utvecklare i [anpassningar av kärnkomponenterna](/help/developing/customizing.md).

### Optimera återgivningsmarkering {#optimizing-rendition-selection}

Den adaptiva bildservern kommer att försöka välja den bästa återgivningen för den önskade bildstorleken och bildtypen. Vi rekommenderar att DAM-återgivningar och tillåtna bildkomponentbredder definieras synkroniserade så att den adaptiva bildservern utför så lite bearbetning som möjligt.

Detta förbättrar prestanda och förhindrar att vissa bilder bearbetas felaktigt av det underliggande bildbehandlingsbiblioteket.

>[!NOTE]
>
>Villkorliga begäranden via `Last-Modified` -huvudet stöds av Adaptive Image Servlet, men cachelagringen av `Last-Modified` header [måste aktiveras i Dispatcher](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html?lang=en#caching-http-response-headers).
>
>[AEM Project Archetype](/help/developing/archetype/overview.md)Exempelkonfigurationen för Dispatcher innehåller redan den här konfigurationen.

## Adobe-klientdatalager {#data-layer}

Bildkomponenten har stöd för [Adobe Client Data Layer.](/help/developing/data-layer/overview.md)
