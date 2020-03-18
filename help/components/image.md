---
title: Bildkomponent
description: Core Component Image Component Component är en adaptiv bildkomponentfunktion för redigering på plats.
translation-type: tm+mt
source-git-commit: 6be0028c45ce9f8b36ea278f8e569f3d6a626ae2

---


# Bildkomponent{#image-component}

Core Component Image Component Component är en adaptiv bildkomponent med redigering på plats.

## Användning {#usage}

Bildkomponenten har anpassningsbar bildmarkering och responsiv funktionalitet med lat inläsningsbeteende för sidbesökaren samt enkel bildplacering och beskärning för innehållsförfattaren.

Bildbredderna, beskärningen och ytterligare inställningar kan definieras av mallskaparen i [designdialogrutan](#design-dialog). Innehållsredigeraren kan överföra eller välja resurser i [konfigurationsdialogrutan](#configure-dialog) och beskära bilden i [redigeringsdialogrutan](#edit-dialog). För enkelhetens skull finns även en enkel ändring på plats av bilden.

## Responsiva funktioner {#responsive-features}

Image Component har robusta responsiva funktioner som är klara direkt vid leverans. På sidmallsnivå kan [designdialogrutan](#design-dialog) användas för att definiera standardbredderna för bildresursen. Bildkomponenten läser sedan automatiskt in rätt bredd för visning beroende på storleken på webbläsarfönstret. När fönstrets storlek ändras läser Image Component in rätt bildstorlek dynamiskt i farten. Komponentutvecklare behöver inte bekymra sig om att definiera anpassade mediefrågor eftersom Image Component redan är optimerat för att läsa in ditt innehåll.

Dessutom har Image Component stöd för lazy loading för att skjuta upp inläsningen av den faktiska bildresursen tills den syns i webbläsaren, vilket gör sidorna mer responsiva.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Image Component är v2, som introducerades i version 2.0.0 av Core Components i januari 2018, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponentversionerna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |--- |---|
| v2 | Kompatibel | Kompatibel | Kompatibel | Kompatibel |
| [v1](v1/image-v1.md) | Kompatibel | Kompatibel | Kompatibel | - |

Mer information om Core Component-versioner och -versioner finns i dokumentet [Core Components Versions](/help/versions.md).

## SVG-stöd {#svg-support}

SVG (Scalable Vector Graphics) stöds av Image Component.

* Både dra-och-släpp av en SVG-resurs från DAM och överföring av en SVG-filöverföring från ett lokalt filsystem stöds.
* Den adaptiva bildservern direktuppspelar den ursprungliga SVG-filen (omformningar hoppas över).
* För en SVG-bild ställs&quot;smarta bilder&quot; och&quot;smarta storlekar&quot; in på en tom array i bildmodellen.

### Dokumentskydd {#security}

Av säkerhetsskäl anropas aldrig den ursprungliga SVG-filen direkt av bildredigeraren. Den kallas igenom `<img src=“path-to-component”>`. Detta förhindrar webbläsaren från att köra skript som är inbäddade i SVG-filen.

>[!CAUTION]
>
>SVG-stöd kräver version 2.1.0 av Core Components eller senare tillsammans med [Service Pack 2](https://docs.adobe.com/content/help/en/experience-manager-64/release-notes/sp-release-notes.html) för AEM 6.4 eller [Service Pack 3](https://helpx.adobe.com/experience-manager/6-3/release-notes/sp3-release-notes.html) för AEM 6.3 eller senare för att ge stöd åt [nya bildredigeringsfunktioner](https://docs.adobe.com/content/help/en/experience-manager-64/developing/components/image-editor.html) i AEM.

## Exempel på komponentutdata {#sample-component-output}

Om du vill se både Image Component (Bildkomponent) och exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [Component Library](https://adobe.com/go/aem_cmp_library_image)(Komponentbibliotek).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Image Component [finns på GitHub](https://adobe.com/go/aem_cmp_tech_image_v2).

Mer information om hur du utvecklar kärnkomponenter finns i dokumentationen till [Core Components Developer](/help/developing/overview.md).

>[!NOTE]
>
>Från och med Core Components version 2.1.0 stöder Image Component [schema.org-mikrodata](https://schema.org).

## Konfigurera dialogruta {#configure-dialog}

Förutom den vanliga [redigeringsdialogrutan](#edit-dialog) och [designdialogrutan](#design-dialog)erbjuder bildkomponenten en konfigurationsdialogruta där själva bilden definieras tillsammans med dess beskrivning och grundläggande egenskaper.

### Fliken Resurser {#asset-tab}

![](/help/assets/screen_shot_2018-01-08at114245.png)

* **Bildresurs**
   * Släpp en resurs från [resursläsaren](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) eller tryck på **bläddringsalternativet** om du vill överföra den från ett lokalt filsystem.
   * Tryck eller klicka på **Radera** för att avmarkera den markerade bilden.
   * Tryck eller klicka på **Redigera** för att [hantera återgivningarna av resursen](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) i resursredigeraren.

### Fliken Metadata {#metadata-tab}

![](/help/assets/screen_shot_2018-01-08at114527.png)

* **Bilden är dekorativ** Kontrollera om bilden ska ignoreras av hjälpmedelstekniken och därför inte kräver någon alternativ text. Detta gäller endast dekorativa bilder.
* **Alternativ text** Textuellt alternativ för innebörden eller funktionen i bilden för läsare med nedsatt syn.
   * Hämta alternativ text från DAM - När det här alternativet är markerat fylls bildens alternativa text med värdet för `dc:description` metadata i DAM.

* **Bildtext** Ytterligare information om bilden, som visas under bilden som standard.
   * **Hämta bildtext från DAM** När den är markerad fylls bildtexten i med värdet för `dc:title` metadata i DAM.
   * **Visa bildtext som popup** När den är markerad visas inte bildtexten nedanför bilden, utan som en popup-meny som visas i vissa webbläsare när du hovrar över bilden.

* **Länk**
   * Länka bilden till en annan resurs.
   * Använd urvalsdialogrutan för att länka till en annan AEM-resurs.
   * Om du inte länkar till en AEM-resurs anger du den absoluta URL:en. Icke-lösliga URL:er tolkas som relativa till AEM.

## Dialogrutan Redigera {#edit-dialog}

I redigeringsdialogrutan kan författaren beskära, ändra startkartan och zooma bilden.

![](/help/assets/chlimage_1-8.png)

* Starta beskärning

   ![](/help/assets/chlimage_1-9.png)

   Om du väljer det här alternativet öppnas en listruta för fördefinierade beskärningsproportioner.

   * Välj alternativet **Free Hand** (Free Hand) för att definiera din egen beskärning.
   * Välj alternativet **Ta bort beskärning** för att visa den ursprungliga resursen.
   När du har valt ett beskärningsalternativ använder du de blå handtagen för att ändra storlek på beskärningen i bilden.

   ![](/help/assets/chlimage_1-10.png)

* Rotera åt höger

   ![](/help/assets/chlimage_1-11.png)

   Använd det här alternativet om du vill rotera bilden 90° åt höger (medurs).

* Vänd vågrätt

   ![](/help/assets/screen_shot_2018-04-16at091404.png)

   Använd det här alternativet om du vill vända bilden vågrätt eller vrida bilden 180° längs y-axeln.

* Vänd lodrätt

   ![](/help/assets/screen_shot_2018-04-16at091410.png)

   Använd det här alternativet om du vill vända bilden lodrätt eller vrida bilden 180° längs x-axeln.

* Starta karta

   >[!CAUTION]
   >
   >Funktionen Launch Map kräver version 2.1.0 av Core Components eller senare tillsammans med [Service Pack 2](https://docs.adobe.com/content/help/en/experience-manager-64/release-notes/sp-release-notes.html) för AEM 6.4 eller [Service Pack 3](https://helpx.adobe.com/experience-manager/6-3/release-notes/sp3-release-notes.html) för AEM 6.3 eller senare för att stödja [nya bildredigeringsfunktioner](https://docs.adobe.com/content/help/en/experience-manager-64/developing/components/image-editor.html) i AEM.

   ![](/help/assets/chlimage_1-12.png)

   Använd det här alternativet om du vill använda en startkarta för bilden. Om du väljer det här alternativet öppnas ett nytt fönster där användaren kan välja kartans form:

   * **Lägg till rektangulär karta**
   * **Lägg till cirkulär karta**
   * **Lägg till polygonkarta**
      * Som standard läggs ett triangelschema till. Dubbelklicka på en linje i formen för att lägga till ett nytt blått handtag på en ny sida.
   När du har markerat en schemaform läggs den ovanpå bilden så att du kan ändra storlek på den. Dra och släpp handtagen för blå storleksändring för att justera formen.

   ![](/help/assets/chlimage_1-13.png)

   När du har ändrat storlek på startkartan klickar du på den för att öppna ett flytande verktygsfält och definiera länkens sökväg.

   * **Bana**
      * Använd alternativet Banväljaren för att välja en bana i AEM
      * Om sökvägen inte är i AEM använder du den absoluta URL:en. Icke-absoluta sökvägar tolkas i förhållande till AEM.
   * **Alternativ text** Alternativ beskrivning av sökvägsmålet
   * **Mål**
      * **Samma flik**
      * **Ny flik**
      * **Överordnad ram**
      * **Övre bildruta**
   Tryck eller klicka på den blå bockmarkeringen för att spara, det svarta x för att avbryta och det röda papperskorgen för att ta bort kartan.

   ![](/help/assets/chlimage_1-14.png)

* Återställ zoomning

   ![](/help/assets/chlimage_1-15.png)

   Om bilden redan har zoomats kan du återställa zoomnivån med det här alternativet.

* Öppna zoomreglaget

   ![](/help/assets/chlimage_1-16.png)

   Använd det här alternativet om du vill visa ett reglage för att styra bildens zoomnivå.

   ![](/help/assets/chlimage_1-17.png)

Du kan även använda redigeraren på plats för att ändra bilden. På grund av utrymmesbegränsningar är endast grundläggande alternativ tillgängliga. Använd helskärmsläget för redigeringsalternativ.

![](/help/assets/chlimage_1-18.png)

>[!NOTE]
>
>Bildredigeringsåtgärder (beskärning, vändning, rotering) stöds inte för GIF-bilder. Alla sådana ändringar som görs i redigeringsläget för GIF-filer bevaras inte.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera de alternativ för beskärning, uppladdning, rotation och överföring som innehållsförfattaren har när den här komponenten används.

### Huvudflik {#main-tab}

På fliken **Huvudsida** kan du definiera en lista med bredder i pixlar för bilden. Komponenten laddar automatiskt den mest lämpliga bredden baserat på webbläsarens storlek. Detta är en viktig del av de [responsiva funktionerna](#responsive-features) i Image-komponenten.

Dessutom kan du definiera vilka allmänna komponentalternativ som automatiskt eller inaktiveras när författaren lägger till komponenten på en sida.

![](/help/assets/screenshot_2018-10-19at102756.png)

* **Aktivera lazy loading** Definiera om alternativet för lazy loading automatiskt aktiveras när bildkomponenten läggs till på en sida.
* **Bilden är dekorativ** Definiera om alternativet för dekorativa bilder aktiveras automatiskt när du lägger till bildkomponenten på en sida.
* **Hämta alternativ text från DAM** Definiera om alternativet att hämta alternativ text från DAM automatiskt aktiveras när bildkomponenten läggs till på en sida.
* **Hämta beskrivning från DAM** Definiera om alternativet att hämta bildtexten från DAM automatiskt aktiveras när bildkomponenten läggs till på en sida.
* **Visa bildtext som popup** Definiera om alternativet att visa bildtexten som en popup-ruta automatiskt aktiveras när bildkomponenten läggs till på en sida.
* **Inaktivera UUID-spårning** för att inaktivera spårning av bildresursens UUID.

* **Bredder** Definierar en lista med bredder i pixlar för bilden och komponenten läser automatiskt in den mest lämpliga bredden baserat på webbläsarens storlek.
   * Tryck eller klicka på knappen **Lägg till** om du vill lägga till en annan storlek.
      * Använd handtagen för att ordna om storlekarna.
      * Använd ikonen **Ta bort** för att ta bort en bredd.
   * Som standard skjuts inläsningen av bilder tills de blir synliga.
      * Välj alternativet **Inaktivera lazy loading** för att läsa in bilderna vid sidinläsning.
* **JPEG-kvalitet** Kvalitetsfaktorn (i procent mellan 0 och 100) för omformade (t.ex. skalade eller beskurna) JPEG-bilder.

>[!CAUTION]
>
>Alternativet JPEG-kvalitet är tillgängligt från och med version 2.2.0 av kärnkomponenterna.

>[!NOTE]
>
>Från och med version 2.2.0 av Core Components lägger Image Component till det unika UUID-attributet `data-asset-id` i bildresursen för att möjliggöra spårning och analys av antalet vyer som enskilda resurser får.

### Fliken Funktioner {#features-tab}

På fliken **Funktioner** kan du ange vilka alternativ som är tillgängliga för innehållsförfattarna när de använder komponenten, inklusive överföringsalternativ, orientering och beskärningsalternativ.

* Källa

   ![](/help/assets/chlimage_1-19.png)

   Välj alternativet **Tillåt överföring av resurser från filsystemet** för att tillåta innehållsförfattare att överföra bilder från sin lokala dator. Om du bara vill tvinga innehållsförfattare att välja resurser från AEM avmarkerar du det här alternativet.

* Orientering

   ![](/help/assets/chlimage_1-20.png)

* **Rotera** Använd det här alternativet om du vill tillåta innehållsförfattaren att använda alternativet **Rotera åt höger** .
* **Vänd** Använd det här alternativet om du vill att innehållsförfattaren ska kunna använda alternativen **Vänd vågrätt** och **Vänd lodrätt** .

   >[!CAUTION]
   >
   >Alternativet **Vänd** är inaktiverat som standard. Om du aktiverar det visas knapparna **Vänd lodrätt** och **Vänd vågrätt** i redigeringsdialogrutan för bildkomponenten, men funktionen stöds för närvarande inte av AEM och ändringar som görs med dessa alternativ bevaras inte.

* Beskärning

   ![](/help/assets/chlimage_1-21.png)

   Välj alternativet **Tillåt beskärning** så att innehållsförfattaren kan beskära bilden i komponenten i redigeringsdialogrutan.
   * Klicka på **Lägg** till för att lägga till en fördefinierad beskärningsproportion.
   * Ange ett beskrivande namn som visas i listrutan **Starta beskärning** .
   * Ange proportionerna i siffror.
   * Använd draghandtagen för att ordna om proportionerna
   * Använd papperskorgsikonen för att ta bort proportioner.
   >[!CAUTION]
   >
   >Observera att beskärningsproportionerna definieras som **höjd/bredd** i AEM. Detta skiljer sig från den vanliga definitionen av bredd/höjd och görs av kompatibilitetsskäl. Innehållsförfattarna är inte medvetna om några skillnader så länge du anger ett tydligt namn på förhållandet eftersom namnet visas i gränssnittet och inte själva förhållandet.

### Fliken Format {#styles-tab-1}

Bildkomponenten stöder AEM [Style System](/help/get-started/authoring.md#component-styling).

## Adaptiv bildserver {#adaptive-image-servlet}

Bildkomponenten använder kärnkomponentens adaptiva bildserver. [Den adaptiva bildservern](https://github.com/adobe/aem-core-wcm-components/wiki/The-Adaptive-Image-Servlet) ansvarar för bildbearbetning och direktuppspelning och kan utnyttjas av utvecklare i deras [anpassningar av kärnkomponenterna](/help/developing/customizing.md).

>[!NOTE]
>
>Villkorliga begäranden via `Last-Modified` huvudet stöds av Adaptive Image Server, men cachelagringen av `Last-Modified` huvudet [måste aktiveras i Dispatcher](https://docs.adobe.com/content/help/en/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html#caching-http-response-headers).
>
>[Den här konfigurationen finns redan i exempelkonfigurationen för AEM Project Archetype](/help/developing/archetype/overview.md).
