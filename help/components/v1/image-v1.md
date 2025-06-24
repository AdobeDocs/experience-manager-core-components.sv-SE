---
title: Bildkomponent (v1)
description: Core Component Image Component Component är en adaptiv bildkomponentfunktion för redigering på plats.
index: n
role: Architect, Developer, Admin, User
exl-id: 625ce8de-5c4a-476d-b749-895493d169b1
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: tm+mt
source-wordcount: '1293'
ht-degree: 0%

---


# Bildkomponent (v1) {#image-component-v}

Core Component Image Component Component är en adaptiv bildkomponentfunktion för redigering på plats.

## Användning {#usage}

Med Image Component (Bildkomponent) är det enkelt att placera bildresurser och du får tillgång till redigering på plats. Den har adaptiv bildmarkering med lazy loading och beskärning för innehållsförfattaren.

Tillåtna bildbredder samt beskärning och ytterligare inställningar kan definieras av mallskaparen i [designdialogrutan](#design-dialog). Innehållsredigeraren kan överföra eller välja resurser i dialogrutan [Konfigurera](#configure-dialog) och beskära bilden i dialogrutan [Redigera](#edit-dialog). För enkelhetens skull finns även en enkel ändring på plats av bilden.

## Version och kompatibilitet {#version-and-compatibility}

I det här dokumentet beskrivs v1 av Image Component, som ursprungligen introducerades i version 1.0.0 av Core Components med AEM 6.3.

I följande tabell visas kompatibiliteten för v1 för Image-komponenten.

| AEM Version | Bildkomponent v1 |
|--- |--- |
| 6,3 | Kompatibel |
| 6,4 | Kompatibel |

>[!CAUTION]
>
>I det här dokumentet beskrivs v1 för bildkomponenten.
>
>Mer information om den aktuella versionen av bildkomponenten finns i dokumentet [Bildkomponent](/help/components/image.md).

## Exempel på komponentutdata {#sample-component-output}

Följande är ett exempel från [We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

### Skärmbild {#screenshot}

![](/help/assets/chlimage_1-7.png)

### HTML {#html}

```
<div class="cmp cmp-image aem-GridColumn aem-GridColumn--default--12">
 
        <noscript data-cmp-image="{&#34;smartImages&#34;:[],&#34;smartSizes&#34;:[],&#34;lazyEnabled&#34;:true}">
            <img src="/content/we-retail/us/en/equipment/_jcr_content/root/responsivegrid/image.img.jpg" alt="Surfboard"/>
        </noscript>

</div>
```

### JSON {#json}

```
"image": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              "smartSizes": [],
              "smartImages": [],
              "lazyEnabled": true,
              "src": "/content/we-retail/us/en/equipment/equipment/jcr%3acontent/root/responsivegrid/image.img.jpeg",
              ":type": "weretail/components/content/image"
            }
```

>[!NOTE]
>
>JSON-export från Core Components kräver version 1.1.0 av Core Components. Mer information finns i [kompatibilitetsinformationen för kärnkomponenter v1](/help/versions.md).

## Konfigurera dialogruta {#configure-dialog}

Förutom den vanliga [redigeringsdialogrutan](#edit-dialog) och [designdialogrutan](#design-dialog) erbjuder bildkomponenten en konfigurationsdialogruta där själva bilden definieras tillsammans med dess beskrivning och grundläggande egenskaper.

![](/help/assets/chlimage_1-50.png)

* **Bildresurs**
   * Släpp en resurs från [resursläsaren](https://helpx.adobe.com/experience-manager/6-3/sites/authoring/using/author-environment-tools.html#main-pars_title) eller tryck på alternativet **bläddra** om du vill överföra från ett lokalt filsystem.
   * Tryck eller klicka på **Radera** för att avmarkera den markerade bilden.
   * Tryck eller klicka på **Redigera** om du vill [hantera återgivningarna av resursen](https://helpx.adobe.com/experience-manager/6-3/assets/using/managing-assets-touch-ui.html#main-pars_title_19) i resursredigeraren.

* **Bilden är dekorativ** - Kontrollera om bilden ska ignoreras av hjälpmedelstekniken och därför inte kräver någon alternativ text. Detta gäller endast dekorativa bilder.
* **Alternativ text** - Textalternativ för innebörden eller funktionen i bilden för läsare med nedsatt syn.
* **Länk**
   * Länka bilden till en annan resurs.
   * Använd urvalsdialogrutan för att länka till en annan AEM-resurs.
   * Om du inte länkar till en AEM-resurs anger du den absoluta URL:en. Icke-lösliga URL:er tolkas som relativa till AEM.

* **Bildtext** - Ytterligare information om bilden, som visas under bilden, är standard.
* **Visa bildtext som popup-fönster** -   När det här alternativet är markerat visas inte bildtexten nedanför bilden, utan som en popup-ruta som visas av vissa webbläsare när de hovrar över bilden.

## Dialogrutan Redigera {#edit-dialog}

I redigeringsdialogrutan kan författaren beskära, ändra startkartan och zooma bilden.

![](/help/assets/chlimage_1-8.png)

* Starta beskärning

  ![](/help/assets/chlimage_1-9.png)

  Om du väljer det här alternativet öppnas en listruta för fördefinierade beskärningsproportioner.

   * Välj alternativet **Free Hand** för att definiera din egen beskärning.
   * Välj alternativet **Ta bort beskärning** om du vill visa den ursprungliga resursen.

  När du har valt ett beskärningsalternativ använder du de blå handtagen för att ändra storlek på beskärningen i bilden.

  ![](/help/assets/chlimage_1-10.png)

* Rotera åt höger

  ![](/help/assets/chlimage_1-11.png)

  Använd det här alternativet om du vill rotera bilden 90° åt höger (medurs).

* Starta karta

  ![](/help/assets/chlimage_1-12.png)

  Använd det här alternativet om du vill använda en startkarta för bilden. Om du väljer det här alternativet öppnas ett nytt fönster där användaren kan välja kartans form:

   * **Lägg till rektangulär karta**
   * **Lägg till cirkulär karta**
   * **Lägg till polygonkarta**

      * Som standard läggs ett triangelschema till. Dubbelklicka på en linje i formen för att lägga till ett nytt blått handtag på en ny sida.

  När du har markerat en schemaform läggs den ovanpå bilden så att du kan ändra storlek på den. Dra och släpp handtagen för blå storleksändring för att justera formen.

  ![](/help/assets/chlimage_1-13.png)

  När du har ändrat storlek på startkartan klickar du på den för att öppna ett flytande verktygsfält och definiera länkens sökväg.

   * **Sökväg**
      * Markera en bana i AEM med alternativet Banväljaren
      * Om sökvägen inte finns i AEM använder du den absoluta URL:en. Ej absoluta sökvägar tolkas i förhållande till AEM.

      * **Alt-text**
Alternativ beskrivning av sökvägsmålet
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

I designdialogrutan kan mallskaparen definiera den beskärning, överföring och rotation som innehållsförfattaren har när den här komponenten används.

### Huvud {#main}

På fliken **Huvudsida** kan du definiera en lista med tillåtna bredder i pixlar så att bilden automatiskt läser in den bredd som passar bäst i listan.

![](/help/assets/chlimage_1-51.png)

Tryck eller klicka på knappen Lägg till för att lägga till en annan storlek.

* Använd handtagen för att ordna om storlekarna.
* Använd ikonen Ta bort för att ta bort en bredd.

Inläsningen av bilder fördröjs som standard tills de blir synliga. Välj alternativet **Inaktivera lazy loading** om du vill läsa in bilderna vid sidinläsning.

* **Aktivera webboptimerade bilder** - När det här alternativet är markerat levererar den [webboptimerade bildleveranstjänsten](/help/developing/web-optimized-image-delivery.md) bilder i WebP-format, vilket minskar bildstorleken med i genomsnitt 25 %.
   * Det här alternativet är endast tillgängligt i AEMaaCS.
   * Om du inte markerar alternativet eller om den webboptimerade bildleveranstjänsten inte är tillgänglig används [Adaptiv bildserver](/help/developing/adaptive-image-servlet.md).

### Funktioner {#features}

På fliken **Funktioner** kan du definiera vilka alternativ som är tillgängliga för innehållsförfattarna när de använder komponenten, inklusive överföringsalternativ, orientering och beskärningsalternativ.

* **Aktivera webboptimerade bilder** - När det här alternativet är markerat levererar den webboptimerade bildleveranstjänsten bilder i WebP-format, vilket minskar bildstorleken med i genomsnitt 25 %.
   * Det här alternativet är endast tillgängligt i AEMaaCS.
   * Om du inte markerar alternativet eller om den webboptimerade bildleveranstjänsten inte är tillgänglig används [Adaptiv bildserver](/help/developing/adaptive-image-servlet.md).

* Source

  ![](/help/assets/chlimage_1-19.png)

  Välj alternativet **Tillåt överföring av resurser från filsystemet** om du vill tillåta innehållsförfattare att överföra bilder från sin lokala dator. Om du bara vill tvinga innehållsförfattare att välja resurser från AEM avmarkerar du det här alternativet.

* Orientering

  ![](/help/assets/chlimage_1-20.png)

   * **Rotera** - Använd det här alternativet om du vill tillåta innehållsförfattaren att använda alternativet **Rotera åt höger**.
   * **Vänd**
Använd det här alternativet om du vill tillåta innehållsförfattaren att använda alternativen **Vänd vågrätt** och **Vänd lodrätt** .

  >[!CAUTION]
  >
  >Alternativet **Vänd** är inaktiverat som standard. Om du aktiverar det visas knapparna **Vänd lodrätt** och **Vänd vågrätt** i redigeringsdialogrutan för bildkomponenten, men funktionen stöds för närvarande inte av AEM och ändringar som görs med dessa alternativ bevaras inte.

* Beskärning

  ![](/help/assets/chlimage_1-21.png)

  Välj alternativet **Tillåt beskärning** så att innehållsförfattaren kan beskära bilden i komponenten i redigeringsdialogrutan.
   * Klicka på **Lägg till** om du vill lägga till en fördefinierad beskärningsproportion.
   * Ange ett beskrivande namn som visas i listrutan **Starta beskärning**.
   * Ange de numeriska proportionerna för proportionerna.
   * Använd draghandtagen för att ändra ordningen på proportionerna
   * Använd papperskorgsikonen för att ta bort proportioner.

  >[!CAUTION]
  >
  >Observera att beskärningsproportioner definieras som **höjd/bredd** i AEM. Detta skiljer sig från den vanliga definitionen av bredd/höjd och görs av bakåtkompatibilitetsskäl. Innehållsförfattarna är inte medvetna om några skillnader så länge du anger ett tydligt namn på förhållandet eftersom namnet visas i gränssnittet och inte själva förhållandet.

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Image-komponenten [finns på GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/image/v1/image).

Hela kärnkomponentprojektet kan hämtas från GitHub.

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).
