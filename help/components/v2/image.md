---
title: Bildkomponent (v2)
description: Core Component Image Component Component är en adaptiv bildkomponentfunktion för redigering på plats.
role: Architect, Developer, Admin, User
exl-id: 3f2b93f9-c48d-43ef-a78a-accd5090fe6f
index: n
source-git-commit: 3908828cf62043483a74e908204c3e9bf540300b
workflow-type: tm+mt
source-wordcount: '2048'
ht-degree: 0%

---


# Bildkomponent (v2) {#image-component}

Core Component Image Component Component är en adaptiv bildkomponent med redigering på plats.

## Användning {#usage}

Bildkomponenten har anpassningsbar bildmarkering och responsiv funktionalitet med lat inläsningsbeteende för sidbesökaren samt enkel bildplacering och beskärning för innehållsförfattaren.

Bildbredderna, beskärningen och ytterligare inställningar kan definieras av mallskaparen i [designdialogrutan](#design-dialog). Innehållsredigeraren kan överföra eller välja resurser i dialogrutan [Konfigurera](#configure-dialog) och beskära bilden i dialogrutan [Redigera](#edit-dialog). För enkelhetens skull finns även en enkel ändring på plats av bilden.

## Version och kompatibilitet {#version-and-compatibility}

I det här dokumentet beskrivs v2 av Image Component, som introducerades i version 2.0.0 av Core Components i januari 2018.

>[!CAUTION]
>
>I det här dokumentet beskrivs v1 för bildkomponenten.
>
>Mer information om den aktuella versionen av bildkomponenten finns i dokumentet [Bildkomponent](/help/components/image.md).

## Responsiva funktioner {#responsive-features}

Image Component har robusta responsiva funktioner som är klara direkt vid leverans. På sidmallsnivå kan du använda [designdialogrutan](#design-dialog) för att definiera standardbredderna för bildresursen. Bildkomponenten läser sedan automatiskt in rätt bredd för visning beroende på storleken på webbläsarfönstret. När fönstrets storlek ändras läses bildkomponenten in dynamiskt med rätt bildstorlek. Komponentutvecklare behöver inte bekymra sig om att definiera anpassade mediefrågor eftersom Image Component redan är optimerat för att läsa in ditt innehåll.

Dessutom har Image Component stöd för lazy loading för att skjuta upp inläsningen av den faktiska bildresursen tills den syns i webbläsaren, vilket gör sidorna mer responsiva.

>[!TIP]
>
>Image Component (Bildkomponenten) drivs av Adaptive Image Server. Se dokumentet [Adaptive Image Server](/help/developing/adaptive-image-servlet.md) för mer information om hur det fungerar.

## Stöd för dynamiska media {#dynamic-media}

Bildkomponenten (från och med [version 2.13.0](/help/versions.md)) har stöd för [Dynamiska media](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/dynamic-media.html?lang=sv-SE#dynamicmedia)-resurser. [När det här alternativet är aktiverat kan du använda ](#design-dialog) för att lägga till bildresurser i dynamiska media genom att dra och släppa eller via resursläsaren på samma sätt som med andra bilder. Dessutom stöds även bildmodifierare, bildförinställningar och smarta beskärningar.

Dina webbupplevelser som skapats med Core Components har inga omfattande, Sensei-baserade, robusta, plattformsoberoende Dynamic Media Image-funktioner.

## SVG Support {#svg-support}

Scalable Vector Graphics (SVG) stöds av Image Component.

* Både dra-och-släpp av en SVG-resurs från DAM och överföring av en SVG-filöverföring från ett lokalt filsystem stöds.
* Den ursprungliga SVG-filen direktuppspelas (omformningar hoppas över).
* För en SVG-bild ställs&quot;smarta bilder&quot; och&quot;smarta storlekar&quot; in på en tom array i bildmodellen.

### Dokumentskydd {#security}

Av säkerhetsskäl anropas aldrig den ursprungliga SVG direkt av bildredigeraren. Den anropas via `<img src=“path-to-component”>`. Detta förhindrar webbläsaren från att köra skript som är inbäddade i SVG-filen.

## Exempel på komponentutdata {#sample-component-output}

Om du vill se både Image Component (Bildkomponent) och exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [Component Library](https://adobe.com/go/aem_cmp_library_image).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Image-komponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_image_v2).

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).

Bildkomponenten stöder [schema.org ](https://schema.org).

## Konfigurera dialogruta {#configure-dialog}

Förutom den vanliga [redigeringsdialogrutan](#edit-dialog) och [designdialogrutan](#design-dialog) erbjuder bildkomponenten en konfigurationsdialogruta där själva bilden definieras tillsammans med dess beskrivning och grundläggande egenskaper.

### Fliken Resurser {#asset-tab}

![Fliken Resurser i dialogrutan Konfigurera i bildkomponenten](/help/assets/image-configure-asset.png)

* **Bildresurs**
   * Släpp en resurs från [resursläsaren](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html?lang=sv-SE) eller tryck på alternativet **bläddra** om du vill överföra från ett lokalt filsystem.
   * Tryck eller klicka på **Radera** för att avmarkera den markerade bilden.
   * Tryck eller klicka på **Redigera** om du vill [hantera återgivningarna av resursen](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html?lang=sv-SE) i resursredigeraren.

### Fliken Metadata {#metadata-tab}

![Fliken Metadata i dialogrutan Konfigurera för Image Component (Bildkomponent)](/help/assets/image-configure-metadata.png)

* **Förinställningstyp** - Detta definierar de typer av bildförinställningar som är tillgängliga, antingen **Bildförinställning** eller **Smart beskärning**, och är bara tillgängligt när [Dynamiska mediefunktioner](#dynamic-meida) är aktiverade.
   * **Bildförinställning** - När **Förinställningstyp** för **Bildförinställning** är markerad är listrutan **Bildförinställning** tillgänglig, vilket gör att du kan välja bland de tillgängliga dynamiska medieförinställningarna. Detta är bara tillgängligt om förinställningar har definierats för den valda resursen.
   * **Smart beskärning** - När **förinställningstyp** för **smart beskärning** har valts är listrutan **Återgivning** tillgänglig, vilket gör att du kan välja bland de tillgängliga återgivningarna för den valda resursen. Detta är bara tillgängligt om återgivningar har definierats för den valda resursen.
   * **Bildmodifierare** - Fler kommandon för visning av dynamiska bilder kan definieras här avgränsade med `&`, oavsett vilken **förinställningstyp** som har valts.
* **Bilden är dekorativ** - Kontrollera om bilden ska ignoreras av hjälpmedelstekniken och därför inte kräver någon alternativ text. Detta gäller endast dekorativa bilder.
* **Alternativ text** - Textalternativ för innebörden eller funktionen i bilden för läsare med nedsatt syn.
   * **Hämta alternativ text från DAM** - När det här alternativet markeras fylls bildens alternativa text med värdet för `dc:description`-metadata i DAM.
* **Bildtext** - Ytterligare information om bilden, som visas under bilden som standard.
   * **Hämta bildtext från DAM** - När den är markerad fylls bildtexten i med värdet för `dc:title`-metadata i DAM.
   * **Visa bildtext som popup-fönster** - Om det här alternativet är markerat visas inte bildtexten under bilden, utan som ett popup-fönster som visas av vissa webbläsare när de hovrar över bilden.
* **Länk** - Länka bilden till en annan resurs.
   * Använd urvalsdialogrutan för att länka till en annan AEM-resurs.
   * Om du inte länkar till en AEM-resurs anger du den absoluta URL:en. Icke-lösliga URL:er tolkas som relativa till AEM.
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [datalagret](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

>[!TIP]
>
>**Smart beskärning** och **Bildförinställning** kan inte användas samtidigt. Om en författare behöver använda en bildförinställning tillsammans med en rendering för smart beskärning måste författaren använda **bildmodifieraren** för att lägga till förinställningar manuellt.

## Dialogrutan Redigera {#edit-dialog}

I redigeringsdialogrutan kan författaren beskära, ändra startkartan och zooma bilden.

>[!NOTE]
>
>Funktionerna för beskärning, rotering och zoomning gäller inte för Dynamic Media-resurser. Om funktionen [Dynamiska media](#dynamic-media) är aktiverad bör all sådan redigering av dynamiska medieresurser utföras via dialogrutan [Konfigurera.](#configure-dialog)

![Redigeringsdialogrutan för bildkomponenten](/help/assets/image-edit.png)

* Starta beskärning

  ![Ikonen Starta beskärning](/help/assets/image-start-crop.png)

  Om du väljer det här alternativet öppnas en listruta för fördefinierade beskärningsproportioner.

   * Välj alternativet **Free Hand** för att definiera din egen beskärning.
   * Välj alternativet **Ta bort beskärning** om du vill visa den ursprungliga resursen.

  När du har valt ett beskärningsalternativ använder du de blå handtagen för att ändra storlek på beskärningen i bilden.

  ![Beskärningsalternativ](/help/assets/image-crop-options.png)

* Rotera åt höger

  ![Rotera höger ikon](/help/assets/image-rotate-right.png)

  Använd det här alternativet om du vill rotera bilden 90° åt höger (medurs).

* Vänd vågrätt

  ![Ikon för att vända vågrätt](/help/assets/image-flip-horizontal.png)

  Använd det här alternativet om du vill vända bilden vågrätt eller vrida bilden 180° längs y-axeln.

* Vänd lodrätt

  ![Ikonen Vänd lodrätt](/help/assets/image-flip-vertical.png)

  Använd det här alternativet om du vill vända bilden lodrätt eller vrida bilden 180° längs x-axeln.

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
>Bildredigeringsåtgärder (beskärning, vändning, rotering) stöds inte för GIF-bilder. Alla sådana ändringar som görs i redigeringsläget för GIF-filer bevaras inte.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera de alternativ för beskärning, uppladdning, rotation och överföring som innehållsförfattaren har när den här komponenten används.

### Huvudflik {#main-tab}

På fliken **Huvudsida** kan du definiera en lista med bredder i pixlar för bilden. Komponenten läses automatiskt in med den mest lämpliga bredden baserat på webbläsarens storlek. Detta är en viktig del av [responsiva funktioner](#responsive-features) i Image-komponenten.

Dessutom kan du definiera vilka allmänna komponentalternativ som automatiskt eller inaktiveras när författaren lägger till komponenten på en sida.

![Huvudflik i designdialogrutan för bildkomponenten](/help/assets/image-design-main-v2.png)

* **Aktivera DM-funktioner** - När det här alternativet är markerat är aktiveringsfunktionerna för [dynamiska media](#dynamic-media) tillgängliga.
* **Aktivera webboptimerade bilder** - När det här alternativet är markerat levererar den [webboptimerade bildleveranstjänsten](/help/developing/web-optimized-image-delivery.md) bilder i WebP-format, vilket minskar bildstorleken med i genomsnitt 25 %.
   * Det här alternativet är endast tillgängligt i AEMaaCS.
   * Om du inte markerar alternativet eller om den webboptimerade bildleveranstjänsten inte är tillgänglig används [Adaptiv bildserver](/help/developing/adaptive-image-servlet.md).
* **Aktivera lazy loading** - Definiera om det lazy loading-alternativet aktiveras automatiskt när bildkomponenten läggs till på en sida.
* **Bilden är dekorativ** - Definiera om alternativet för dekorativ bild automatiskt är aktiverat när du lägger till bildkomponenten på en sida.
* **Hämta alternativ text från DAM**- Definiera om alternativet att hämta alternativ text från DAM automatiskt aktiveras när bildkomponenten läggs till på en sida.
* **Hämta beskrivning från DAM** - Ange om alternativet att hämta bildtexten från DAM automatiskt ska aktiveras när bildkomponenten läggs till på en sida.
* **Visa bildtext som popup-fönster** - Definiera om alternativet att visa bildtexten som ett popup-fönster automatiskt ska aktiveras när bildkomponenten läggs till på en sida.
* **Inaktivera UUID-spårning** - Markera för att inaktivera spårning av bildresursens UUID.
* **Bredder** - Definierar en lista med bredder i pixlar för bilden och komponenten läser automatiskt in den mest lämpliga bredden baserat på webbläsarens storlek.
   * Tryck eller klicka på knappen **Lägg till** om du vill lägga till en annan storlek.
      * Använd handtagen för att ordna om storlekarna.
      * Använd ikonen **Ta bort** för att ta bort en bredd.
   * Inläsningen av bilder fördröjs som standard tills de blir synliga.
      * Välj alternativet **Inaktivera lazy loading** om du vill läsa in bilderna vid sidinläsning.
* **JPEG-kvalitet** - Kvalitetsfaktorn (i procent från 0 och 100) för omformade (t.ex. skalade eller beskurna) JPEG-bilder.

>[!TIP]
>
>I dokumentet [Adaptiv bildserver](/help/developing/adaptive-image-servlet.md) finns tips om hur du kan optimera markeringen av återgivning genom att definiera dina bredder noggrant.

### Fliken Funktioner {#features-tab}

På fliken **Funktioner** kan du definiera vilka alternativ som är tillgängliga för innehållsförfattarna när de använder komponenten, inklusive överföringsalternativ, orientering och beskärningsalternativ.

* Source

  ![Fliken Funktioner i designdialogrutan för bildkomponenten](/help/assets/image-design-features-source.png)

  Välj alternativet **Tillåt överföring av resurser från filsystemet** om du vill tillåta innehållsförfattare att överföra bilder från sin lokala dator. Om du bara vill tvinga innehållsförfattare att välja resurser från AEM avmarkerar du det här alternativet.

* Orientering

  ![Fliken Funktioner i designdialogrutan för bildkomponenten](/help/assets/image-design-features-orientation.png)

* **Rotera**
Använd det här alternativet om du vill tillåta innehållsförfattaren att använda alternativet **Rotera höger** .
* **Vänd**
Använd det här alternativet om du vill tillåta innehållsförfattaren att använda alternativen **Vänd vågrätt** och **Vänd lodrätt** .

  >[!CAUTION]
  >
  >Alternativet **Vänd** är inaktiverat som standard. Om du aktiverar det visas knapparna **Vänd lodrätt** och **Vänd vågrätt** i redigeringsdialogrutan för bildkomponenten, men funktionen stöds för närvarande inte av AEM och ändringar som görs med dessa alternativ bevaras inte.

* Beskärning

  ![Fliken Funktioner i designdialogrutan för bildkomponenten](/help/assets/image-design-features-cropping.png)

  Välj alternativet **Tillåt beskärning** så att innehållsförfattaren kan beskära bilden i komponenten i redigeringsdialogrutan.
   * Klicka på **Lägg till** om du vill lägga till en fördefinierad beskärningsproportion.
   * Ange ett beskrivande namn som visas i listrutan **Starta beskärning**.
   * Ange de numeriska proportionerna för proportionerna.
   * Använd draghandtagen för att ändra ordningen på proportionerna
   * Använd papperskorgsikonen för att ta bort proportioner.

  >[!CAUTION]
  >
  >Observera att beskärningsproportioner definieras som **höjd/bredd** i AEM. Detta skiljer sig från den vanliga definitionen av bredd/höjd och görs av bakåtkompatibilitetsskäl. Innehållsförfattarna är inte medvetna om några skillnader så länge du anger ett tydligt namn på förhållandet eftersom namnet visas i gränssnittet och inte själva förhållandet.

### Fliken Format {#styles-tab-1}

Bildkomponenten stöder AEM [Style System](/help/get-started/authoring.md#component-styling).

## Adobe Client Data Layer {#data-layer}

Image-komponenten stöder [Adobe Client Data Layer.](/help/developing/data-layer/overview.md)
