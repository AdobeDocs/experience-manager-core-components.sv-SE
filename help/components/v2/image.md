---
title: Bildkomponent (v2)
description: Core Component Image Component Component är en adaptiv bildkomponentfunktion för redigering på plats.
role: Architect, Developer, Admin, User
source-git-commit: e5251010ca41025eb2bb56b66164ecf4cc0145c8
workflow-type: tm+mt
source-wordcount: '2228'
ht-degree: 0%

---


# Bildkomponent (v2) {#image-component}

Core Component Image Component Component är en adaptiv bildkomponent med redigering på plats.

## Användning {#usage}

Bildkomponenten har anpassningsbar bildmarkering och responsiv funktionalitet med lat inläsningsbeteende för sidbesökaren samt enkel bildplacering och beskärning för innehållsförfattaren.

Bildbredderna, beskärningen och ytterligare inställningar kan definieras av mallskaparen i [designdialogruta](#design-dialog). Innehållsredigeraren kan överföra eller välja resurser i [konfigurera dialogruta](#configure-dialog) och beskära bilden i [redigeringsdialogruta](#edit-dialog). För enkelhetens skull finns även en enkel ändring på plats av bilden.

## Version och kompatibilitet {#version-and-compatibility}

I det här dokumentet beskrivs v2 av Image Component, som introducerades i version 2.0.0 av Core Components i januari 2018.

>[!CAUTION]
>
>I det här dokumentet beskrivs v1 för bildkomponenten.
>
>Mer information om den aktuella versionen av bildkomponenten finns i [Bildkomponent](/help/components/image.md) -dokument.

## Responsiva funktioner {#responsive-features}

Image Component har robusta responsiva funktioner som är klara direkt vid leverans. På sidmallsnivå visas [designdialogruta](#design-dialog) kan användas för att definiera bildresursens standardbredder. Bildkomponenten läser sedan automatiskt in rätt bredd för visning beroende på storleken på webbläsarfönstret. När fönstrets storlek ändras läser Image Component in rätt bildstorlek dynamiskt i farten. Komponentutvecklare behöver inte bekymra sig om att definiera anpassade mediefrågor eftersom Image Component redan är optimerat för att läsa in ditt innehåll.

Dessutom har Image Component stöd för lazy loading för att skjuta upp inläsningen av den faktiska bildresursen tills den syns i webbläsaren, vilket gör sidorna mer responsiva.

>[!TIP]
>
>Se avsnittet [Adaptiv bildserver](#adaptive-image-servlet) om du vill ha mer teknisk information om dessa funktioner och tips för hur du optimerar urvalet av renderingar.

## Dynamic Media Support {#dynamic-media}

Bildkomponenten (från och med [version 2.13.0](/help/versions.md)) har stöd för [Dynamic Media](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/dynamic-media.html?lang=en#dynamicmedia) resurser. [När det är aktiverat](#design-dialog) Med de här funktionerna kan du lägga till Dynamic Media bildresurser med en enkel dra och släpp-funktion eller via resursläsaren på samma sätt som med andra bilder. Dessutom stöds även bildmodifierare, bildförinställningar och smarta beskärningar.

Dina webbupplevelser som byggts med Core Components har inga omfattande, Sensei-baserade, robusta, högpresterande, plattformsoberoende Dynamic Media Image-funktioner.

## Stöd för SVG {#svg-support}

Skalbar vektorgrafik (SVG) stöds av bildkomponenten.

* Både dra-och-släpp av en SVG-resurs från DAM och överföring av en SVG-filöverföring från ett lokalt filsystem stöds.
* Den adaptiva bildservern strömmar den ursprungliga SVG-filen (omformningar hoppas över).
* För en SVG-bild ställs&quot;smarta bilder&quot; och&quot;smarta storlekar&quot; in på en tom array i bildmodellen.

### Dokumentskydd {#security}

Av säkerhetsskäl anropas aldrig SVG direkt av bildredigeraren. Den kallas för `<img src=“path-to-component”>`. Detta förhindrar webbläsaren från att köra skript som är inbäddade i filen SVG.

>[!CAUTION]
>
>För SVG-support krävs version 2.1.0 av Core Components eller senare tillsammans med [Service Pack 2](https://experienceleague.adobe.com/docs/experience-manager-64/release-notes/sp-release-notes.html) för AEM 6.4 eller senare för [bildredigeringsfunktioner](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/components-templates/image-editor.html) inom AEM.

## Exempel på komponentutdata {#sample-component-output}

Om du vill se både Image Component (Bildkomponent) och exempel på dess konfigurationsalternativ samt HTML och JSON-utdata går du till [Komponentbibliotek](https://adobe.com/go/aem_cmp_library_image).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Image Component [finns på GitHub](https://adobe.com/go/aem_cmp_tech_image_v2).

Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

Bildkomponenten har stöd för [schema.org, mikrodata](https://schema.org).

## Konfigurera dialogruta {#configure-dialog}

Förutom standarden [redigeringsdialogruta](#edit-dialog) och [designdialogruta](#design-dialog)innehåller bildkomponenten en konfigurationsdialogruta där själva bilden definieras tillsammans med beskrivning och grundläggande egenskaper.

### Fliken Resurser {#asset-tab}

![Fliken Resurser i dialogrutan Konfigurera för bildkomponenten](/help/assets/image-configure-asset.png)

* **Bildresurs**
   * Släpp en resurs från [resursläsare](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) eller tryck på **bläddra** om du vill överföra från ett lokalt filsystem.
   * Tryck eller klicka **Rensa** för att avmarkera den markerade bilden.
   * Tryck eller klicka **Redigera** till [hantera återgivningar av resursen](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) i resursredigeraren.

### Fliken Metadata {#metadata-tab}

![Fliken Metadata i dialogrutan Konfigurera för Image Component](/help/assets/image-configure-metadata.png)

* **Förinställningstyp** - Detta definierar de typer av bildförinställningar som är tillgängliga, antingen **Bildförinställning** eller **Smart beskärning** och är bara tillgängligt när [Funktioner i Dynamic Media](#dynamic-meida) är aktiverade.
   * **Bildförinställning** - När **Förinställningstyp** av **Bildförinställning** är markerat, listrutan **Bildförinställning** är tillgängligt och du kan välja bland de tillgängliga förinställningarna för Dynamic Media. Detta är bara tillgängligt om förinställningar har definierats för den valda resursen.
   * **Smart beskärning** - När **Förinställningstyp** av **Smart beskärning** är markerat i listrutan **Återgivning** är tillgängligt och du kan välja bland de tillgängliga återgivningarna av den valda resursen. Detta är bara tillgängligt om återgivningar har definierats för den valda resursen.
   * **Bildmodifierare** - Ytterligare kommandon för att visa bilder i Dynamic Media kan definieras här avgränsade med `&`oavsett vilka **Förinställningstyp** är markerat.
* **Bilden är dekorativ** - Kontrollera om bilden ska ignoreras av hjälpmedel och därför inte kräver någon alternativ text. Detta gäller endast dekorativa bilder.
* **Alternativ text** - Textuellt alternativ till bildens innebörd eller funktion, för läsare med nedsatt syn.
   * **Hämta alternativ text från DAM** - När det här alternativet är markerat fylls bildens alternativa text med värdet för `dc:description` metadata i DAM.
* **Bildtext** - Ytterligare information om bilden, som visas under bilden som standard.
   * **Hämta beskrivning från DAM** - När det här alternativet är markerat fylls bildtexten i med värdet för `dc:title` metadata i DAM.
   * **Visa bildtext som popup-fönster** - När det här alternativet är markerat visas inte bildtexten nedanför bilden, utan som ett popup-fönster som visas av vissa webbläsare när de hovrar över bilden.
* **Länk** - Länka bilden till en annan resurs.
   * Använd urvalsdialogrutan för att länka till en annan AEM.
   * Om du inte länkar till en AEM resurs anger du den absoluta URL:en. Icke-lösliga URL:er tolkas som relativa till AEM.
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [Datalager](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

>[!TIP]
>
>**Smart beskärning** och **Bildförinställning** alternativ som utesluter varandra. Om en författare behöver använda en bildförinställning tillsammans med en rendering för smart beskärning måste författaren använda **Bildmodifierare** om du vill lägga till förinställningar manuellt.

## Dialogrutan Redigera {#edit-dialog}

I redigeringsdialogrutan kan författaren beskära, ändra startkartan och zooma bilden.

>[!NOTE]
>
>Funktionerna för beskärning, rotering och zoomning gäller inte för Dynamic Media-resurser. Om [Funktioner i Dynamic Media](#dynamic-media) är aktiverade bör all sådan redigering av Dynamic Media-resurser utföras via [Konfigurera dialogruta.](#configure-dialog)

![Redigeringsdialogruta för bildkomponent](/help/assets/image-edit.png)

* Starta beskärning

   ![Ikonen Starta beskärning](/help/assets/image-start-crop.png)

   Om du väljer det här alternativet öppnas en listruta för fördefinierade beskärningsproportioner.

   * Välj alternativ **Free Hand** för att definiera din egen beskärning.
   * Välj alternativ **Ta bort beskärning** för att visa den ursprungliga resursen.

   När du har valt ett beskärningsalternativ använder du de blå handtagen för att ändra storlek på beskärningen i bilden.

   ![Beskärningsalternativ](/help/assets/image-crop-options.png)

* Rotera åt höger

   ![Rotera höger ikon](/help/assets/image-rotate-right.png)

   Använd det här alternativet om du vill rotera bilden 90° åt höger (medurs).

* Vänd vågrätt

   ![Ikon för att vända vågrätt](/help/assets/image-flip-horizontal.png)

   Använd det här alternativet om du vill vända bilden vågrätt eller vrida bilden 180° längs y-axeln.

* Vänd lodrätt

   ![Vänd lodrätt, ikon](/help/assets/image-flip-vertical.png)

   Använd det här alternativet om du vill vända bilden lodrätt eller vrida bilden 180° längs x-axeln.

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
>Bildredigeringsåtgärder (beskärning, vändning, rotering) stöds inte för bilder i GIF. Alla sådana ändringar som görs i redigeringsläget för GIF bevaras inte.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera de alternativ för beskärning, uppladdning, rotation och överföring som innehållsförfattaren har när den här komponenten används.

### Huvudflik {#main-tab}

På **Huvud** kan du definiera en lista med bredder i pixlar för bilden så läser komponenten automatiskt in den mest lämpliga bredden baserat på webbläsarens storlek. Detta är en viktig del av [responsiva funktioner](#responsive-features) för bildkomponenten.

Dessutom kan du definiera vilka allmänna komponentalternativ som automatiskt eller inaktiveras när författaren lägger till komponenten på en sida.

![Huvudflik i designdialogrutan för bildkomponenten](/help/assets/image-design-main.png)

* **Aktivera DM-funktioner** - När det här alternativet är markerat aktiveras [Funktioner i Dynamic Media](#dynamic-media) är tillgängliga.
* **Aktivera lazy loading** - Definiera om det lat inläsningsalternativet aktiveras automatiskt när du lägger till bildkomponenten på en sida.
* **Bilden är dekorativ** - Ange om alternativet för dekorativa bilder ska aktiveras automatiskt när du lägger till bildkomponenten på en sida.
* **Hämta alternativ text från DAM**- Ange om alternativet att hämta alternativ text från DAM automatiskt ska aktiveras när bildkomponenten läggs till på en sida.
* **Hämta beskrivning från DAM** - Ange om alternativet att hämta bildtexten från DAM-modulen ska aktiveras automatiskt när bildkomponenten läggs till på en sida.
* **Visa bildtext som popup-fönster** - Ange om alternativet att visa bildtexten som en popup-ruta automatiskt ska aktiveras när bildkomponenten läggs till på en sida.
* **Inaktivera UUID-spårning** - Markera för att inaktivera spårning av bildresursens UUID.
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

### Fliken Funktioner {#features-tab}

På **Funktioner** kan du definiera vilka alternativ som är tillgängliga för innehållsförfattarna när de använder komponenten, inklusive överföringsalternativ, orientering och beskärningsalternativ.

* Källa

   ![Dialogrutan Funktioner i Image Components](/help/assets/image-design-features-source.png)

   Välj alternativet **Tillåt överföring av resurser från filsystem** så att skribenterna kan ladda upp bilder från sin dator. Om du bara vill tvinga innehållsförfattare att välja resurser från AEM avmarkerar du det här alternativet.

* Orientering

   ![Dialogrutan Funktioner i Image Components](/help/assets/image-design-features-orientation.png)

* **Rotera**
Använd det här alternativet för att tillåta innehållsförfattaren att använda 
**Rotera åt höger** alternativ.
* **Vänd**
Använd det här alternativet för att tillåta innehållsförfattaren att använda 
**Vänd vågrätt** och **Vänd lodrätt** alternativ.

   >[!CAUTION]
   >
   >The **Vänd** är inaktiverat som standard. Om du aktiverar det visas **Vänd lodrätt** och **Vänd vågrätt** i redigeringsdialogrutan för bildkomponenten, men funktionen stöds för närvarande inte av AEM och ändringar som görs med dessa alternativ bevaras inte.

* Beskärning

   ![Dialogrutan Funktioner i Image Components](/help/assets/image-design-features-cropping.png)

   Välj alternativet **Tillåt beskärning** så att innehållsförfattaren kan beskära bilden i komponenten i redigeringsdialogrutan.
   * Klicka **Lägg till** om du vill lägga till en fördefinierad beskärningsproportion.
   * Ange ett beskrivande namn som visas i **Starta beskärning** listruta.
   * Ange proportionerna i siffror.
   * Använd draghandtagen för att ordna om proportionerna
   * Använd papperskorgsikonen för att ta bort proportioner.

   >[!CAUTION]
   >
   >Observera att beskärningsproportioner definieras som i AEM **höjd/bredd**. Detta skiljer sig från den vanliga definitionen av bredd/höjd och görs av kompatibilitetsskäl. Innehållsförfattarna är inte medvetna om några skillnader så länge du anger ett tydligt namn på förhållandet eftersom namnet visas i gränssnittet och inte själva förhållandet.

### Fliken Format {#styles-tab-1}

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
