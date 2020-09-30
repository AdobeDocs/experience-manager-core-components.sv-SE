---
title: Bildkomponent
description: Core Component Image Component Component är en adaptiv bildkomponentfunktion för redigering på plats.
translation-type: tm+mt
source-git-commit: 4813748bcfa83ce7c73e81d4e4d445ecc8215d26
workflow-type: tm+mt
source-wordcount: '1921'
ht-degree: 0%

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

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | Kompatibel | Kompatibel | Kompatibel |
| [v1](v1/image-v1.md) | Kompatibel | Kompatibel | - |

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
>SVG-stöd kräver version 2.1.0 av Core Components eller senare tillsammans med [Service Pack 2](https://docs.adobe.com/content/help/en/experience-manager-64/release-notes/sp-release-notes.html) för AEM 6.4 eller senare för att ge stöd åt [bildredigeringsfunktionerna](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/components-templates/image-editor.html) i AEM.

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

![Fliken Resurser i dialogrutan Konfigurera för bildkomponenten](/help/assets/image-configure-asset.png)

* **Bildresurs**
   * Släpp en resurs från [resursläsaren](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) eller tryck på **bläddringsalternativet** om du vill överföra den från ett lokalt filsystem.
   * Tryck eller klicka på **Radera** för att avmarkera den markerade bilden.
   * Tryck eller klicka på **Redigera** för att [hantera återgivningarna av resursen](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) i resursredigeraren.

### Fliken Metadata {#metadata-tab}

![Fliken Metadata i dialogrutan Konfigurera för Image Component](/help/assets/image-configure-metadata.png)

* **Bilden är dekorativ** Kontrollera om bilden ska ignoreras av hjälpmedelstekniken och därför inte kräver någon alternativ text. Detta gäller endast dekorativa bilder.
* **Alternativ text** Textuellt alternativ för innebörden eller funktionen i bilden för läsare med nedsatt syn.
   * Hämta alternativ text från DAM - När det här alternativet är markerat fylls bildens alternativa text med värdet för `dc:description` metadata i DAM.

* **Bildtext** Ytterligare information om bilden, som visas under bilden som standard.
   * **Hämta bildtext från DAM** När den är markerad fylls bildtexten i med bildens värde 
`dc:title` metadata i DAM.
   * **Visa bildtext som popup** När den är markerad visas inte bildtexten nedanför bilden, utan som en popup-meny som visas i vissa webbläsare när du hovrar över bilden.

* **Länk**
   * Länka bilden till en annan resurs.
   * Använd urvalsdialogrutan för att länka till en annan AEM.
   * Om du inte länkar till en AEM resurs anger du den absoluta URL:en. Icke-lösliga URL:er tolkas som relativa till AEM.

* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [datalagret](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

## Dialogrutan Redigera {#edit-dialog}

I redigeringsdialogrutan kan författaren beskära, ändra startkartan och zooma bilden.

![Redigeringsdialogruta för bildkomponent](/help/assets/image-edit.png)

* Starta beskärning

   ![Ikonen Starta beskärning](/help/assets/image-start-crop.png)

   Om du väljer det här alternativet öppnas en listruta för fördefinierade beskärningsproportioner.

   * Välj alternativet **Free Hand** (Free Hand) för att definiera din egen beskärning.
   * Välj alternativet **Ta bort beskärning** för att visa den ursprungliga resursen.

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
>Bildredigeringsåtgärder (beskärning, vändning, rotering) stöds inte för GIF-bilder. Alla sådana ändringar som görs i redigeringsläget för GIF-filer bevaras inte.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera de alternativ för beskärning, uppladdning, rotation och överföring som innehållsförfattaren har när den här komponenten används.

### Huvudflik {#main-tab}

På fliken **Huvudsida** kan du definiera en lista med bredder i pixlar för bilden. Komponenten laddar automatiskt den mest lämpliga bredden baserat på webbläsarens storlek. Detta är en viktig del av de [responsiva funktionerna](#responsive-features) i Image-komponenten.

Dessutom kan du definiera vilka allmänna komponentalternativ som automatiskt eller inaktiveras när författaren lägger till komponenten på en sida.

![Huvudflik i designdialogrutan för bildkomponenten](/help/assets/image-design-main.png)

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

>[!NOTE]
>
>Alternativet JPEG-kvalitet är tillgängligt från och med version 2.2.0 av kärnkomponenterna.

>[!NOTE]
>
>Från och med version 2.2.0 av Core Components lägger Image Component till det unika UUID-attributet `data-asset-id` i bildresursen för att möjliggöra spårning och analys av antalet vyer som enskilda resurser får.

### Fliken Funktioner {#features-tab}

På fliken **Funktioner** kan du ange vilka alternativ som är tillgängliga för innehållsförfattarna när de använder komponenten, inklusive överföringsalternativ, orientering och beskärningsalternativ.

* Källa

   ![Dialogrutan Funktioner i Image Components](/help/assets/image-design-features-source.png)

   Välj alternativet **Tillåt överföring av resurser från filsystemet** för att tillåta innehållsförfattare att överföra bilder från sin lokala dator. Om du bara vill tvinga innehållsförfattare att välja resurser från AEM avmarkerar du det här alternativet.

* Orientering

   ![Dialogrutan Funktioner i Image Components](/help/assets/image-design-features-orientation.png)

* **Rotera** Använd det här alternativet om du vill tillåta innehållsförfattaren att använda 
**Alternativet Rotera åt höger** .
* **Vänd** Använd det här alternativet om du vill tillåta innehållsförfattaren att använda 
**Alternativen Vänd vågrätt** och **Vänd lodrätt** .

   >[!CAUTION]
   >
   >Alternativet **Vänd** är inaktiverat som standard. Om du aktiverar det visas knapparna **Vänd lodrätt** och **Vänd vågrätt** i redigeringsdialogrutan för bildkomponenten, men funktionen stöds för närvarande inte av AEM och ändringar som görs med dessa alternativ bevaras inte.

* Beskärning

   ![Dialogrutan Funktioner i Image Components](/help/assets/image-design-features-cropping.png)

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

Bildkomponenten har stöd för AEM [Style System](/help/get-started/authoring.md#component-styling).

## Adaptiv bildserver {#adaptive-image-servlet}

Bildkomponenten använder kärnkomponentens adaptiva bildserver. [Den adaptiva bildservern](https://github.com/adobe/aem-core-wcm-components/wiki/The-Adaptive-Image-Servlet) ansvarar för bildbearbetning och direktuppspelning och kan utnyttjas av utvecklare i deras [anpassningar av kärnkomponenterna](/help/developing/customizing.md).

>[!NOTE]
>
>Villkorliga begäranden via `Last-Modified` huvudet stöds av Adaptive Image Server, men cachelagringen av `Last-Modified` huvudet [måste aktiveras i Dispatcher](https://docs.adobe.com/content/help/en/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html#caching-http-response-headers).
>
>[Den AEM Project Archetype](/help/developing/archetype/overview.md)-exempelkonfigurationen för Dispatcher innehåller redan den här konfigurationen.
