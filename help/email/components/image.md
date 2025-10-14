---
title: E-postbildkomponent
description: E-postbildkomponenten är en adaptiv bildkomponent med redigering på plats.
role: Architect, Developer, Admin, User
exl-id: f5d40047-3082-4edd-a5f6-6ab3e33997f9
index: false
source-git-commit: eb77567dc32cccb81a9fc131493d11fb55b7e93b
workflow-type: tm+mt
source-wordcount: '1624'
ht-degree: 0%

---


# E-postbildkomponent {#email-image-component}

E-postbildkomponenten är en adaptiv bildkomponent med redigering på plats.

## Användning {#usage}

E-postbildkomponenten har adaptiv bildmarkering och responsivt beteende med lat inläsningsbeteende för sidbesökaren samt enkel dra-och-släpp-montering och konfiguration för innehållsförfattaren.

* Bildbredderna och ytterligare inställningar kan definieras av mallskaparen i dialogrutan [Design.](#design-dialog)
* Innehållsredigeraren kan överföra eller välja resurser i dialogrutan [Konfigurera.](#configure-dialog)

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av e-postbildkomponenten är v1, som introducerades med version x av e-postkärnkomponenterna i oktober 2022, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponenterna är kompatibla med samt länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|---|---|---|---|
| v1 | Kompatibel | - | - |

Mer information om Core Component-versioner och -versioner finns i dokumentet [Email Core Components Versions](/help/email/versions.md).

## Responsiva funktioner {#responsive-features}

E-postbildkomponenten har robusta responsiva funktioner som är klara direkt vid leverans. På sidmallsnivå kan du använda [designdialogrutan](#design-dialog) för att definiera standardbredderna för bildresursen. E-postbildkomponenten läser sedan automatiskt in rätt bredd för visning beroende på storleken på webbläsarfönstret. När fönstrets storlek ändras läser e-postbildkomponenten in rätt bildstorlek dynamiskt direkt. Komponentutvecklare behöver inte bekymra sig om att definiera anpassade mediefrågor eftersom e-postbildkomponenten redan är optimerad för att läsa in ditt innehåll.

Dessutom har e-postbildkomponenten stöd för lazy loading för att skjuta upp inläsningen av den faktiska bildresursen tills den syns i webbläsaren, vilket gör att innehållet blir mer responsivt.

>[!TIP]
>
>Som standard drivs e-postbildkomponenten av den adaptiva bildservern. Se dokumentet [Adaptive Image Server](#adaptive-image-servlet) för mer information om hur det fungerar.

## Stöd för dynamiska media {#dynamic-media}

E-postbildkomponenten stöder [dynamiska media](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/dynamic-media.html?lang=sv-SE#dynamicmedia)-resurser. [När det här alternativet är aktiverat kan du använda &#x200B;](#design-dialog) för att lägga till bildresurser i dynamiska media genom att dra och släppa eller via resursläsaren på samma sätt som med andra bilder. Dessutom stöds även bildmodifierare, bildförinställningar och smarta beskärningar.

Dina e-postupplevelser som byggts med e-postkärnkomponenterna kan innehålla kraftfulla, Sensei-baserade, robusta, plattformsoberoende Dynamic Media Image-funktioner.

## SVG Support {#svg-support}

Scalable Vector Graphics (SVG) stöds av Email Image Component.

* Både dra-och-släpp av en SVG-resurs från DAM och överföring av en SVG-filöverföring från ett lokalt filsystem stöds.
* Den ursprungliga SVG-filen direktuppspelas (omformningar hoppas över).
* För en SVG-bild ställs&quot;smarta bilder&quot; och&quot;smarta storlekar&quot; in på en tom array i bildmodellen.

### Dokumentskydd {#security}

Av säkerhetsskäl anropas aldrig den ursprungliga SVG direkt av bildredigeraren. Den anropas via `<img src=“path-to-component”>`. Detta förhindrar webbläsaren från att köra skript som är inbäddade i SVG-filen.

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om e-postbildkomponenten [finns på GitHub.](https://adobe.com/go/aem_cmp_tech_email_image_v1)

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen till utvecklaren av kärnkomponenter.](/help/developing/overview.md)

Bildkomponenten stöder [schema.org.](https://schema.org)

## Konfigurera dialogruta {#configure-dialog}

E-postbildkomponenten innehåller en konfigureringsdialogruta där själva bilden definieras tillsammans med dess beskrivning och grundläggande egenskaper.

### Fliken Resurser {#asset-tab}

![Fliken Resurser i konfigurationsdialogrutan för e-postbildkomponenten](/help/email/assets/email-image-configure-asset.png)

* **Ärv bild från sida** - Det här alternativet använder den [aktuella bilden för den länkade sidan](page.md) eller den aktuella sidans bild om bilden inte är länkad.

* **Alternativ text för hjälpmedel** - I det här fältet kan du definiera en beskrivning av bilden för användare med nedsatt syn.

   * **Ärv alternativ text från sida** - Det här alternativet använder den alternativa beskrivningen av det länkade objektvärdet för `dc:description` -metadata i DAM eller för den aktuella sidan om ingen resurs är länkad.

* **Bildresurs**
   * Släpp en resurs från [resursläsaren](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html?lang=sv-SE) eller tryck på alternativet **bläddra** om du vill överföra från ett lokalt filsystem.
   * Tryck eller klicka på **Radera** för att avmarkera den markerade bilden.
   * Tryck eller klicka på **Redigera** om du vill [hantera återgivningarna av resursen](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html?lang=sv-SE) i resursredigeraren.

* **Tillhandahåll inte alternativ text** - Med det här alternativet markeras bilden som ska ignoreras av hjälpmedelstekniker som skärmläsare om bilden är enbart dekorativ eller på annat sätt inte förmedlar någon ytterligare information till sidan.

* **Inaktivera lazy loading** - Det här alternativet läser in alla bildkomponenter i förväg utan att läsas in efter behov.

### Fliken Metadata {#metadata-tab}

![Fliken Metadata i dialogrutan Konfigurera för Image Component (Bildkomponent)](/help/email/assets/email-image-configure-metadata.png)

* **Förinställningstyp** - Detta definierar de typer av bildförinställningar som är tillgängliga, antingen **Bildförinställning** eller **Smart beskärning**, och är bara tillgängligt när [Dynamiska mediefunktioner](#dynamic-meida) är aktiverade.
   * **Bildförinställning** - När **Förinställningstyp** för **Bildförinställning** är markerad är den nedrullningsbara menyn **Bildförinställning** tillgänglig, vilket gör att du kan välja bland de tillgängliga dynamiska medieförinställningarna. Detta är bara tillgängligt om förinställningar har definierats för den valda resursen.
   * **Smart beskärning** - När **förinställningstyp** för **smart beskärning** har valts är den nedrullningsbara menyn **Återgivning** tillgänglig, vilket gör att du kan välja bland de tillgängliga återgivningarna för den valda resursen. Detta är bara tillgängligt om återgivningar har definierats för den valda resursen.
   * **Bildmodifierare** - Fler kommandon för visning av dynamiska media kan definieras här avgränsade med `&`, oavsett vilken **förinställningstyp** som har valts.
* **Bildtext** - Ytterligare information om bilden, som visas under bilden som standard.
   * **Hämta bildtext från DAM** - När den är markerad fylls bildtexten i med värdet för `dc:title`-metadata i DAM. Endast tillgängligt när en resurs väljs från DAM.
   * **Visa bildtext som popup-fönster** - Om det här alternativet är markerat visas inte bildtexten under bilden, utan som ett popup-fönster som visas av vissa webbläsare när de hovrar över bilden.
* **Länk** - Länka bilden till en annan resurs.
   * Använd urvalsdialogrutan för att länka till en annan AEM-resurs.
   * Om du inte länkar till en AEM-resurs anger du den absoluta URL:en. Icke-lösliga URL:er tolkas som relativa till AEM.
   * **Öppna länk på ny flik** - Det här alternativet öppnar länken i ett nytt webbläsarfönster.
* **ID** - Med det här alternativet kan du kontrollera den unika identifieraren för komponenten i HTML.
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka CSS.
* **Fast med** - Det här alternativet definierar bildens bredd i pixlar.
* **Skala bilden till tillgänglig bredd** - Det här alternativet gäller `"width":"100%"` för bildformatsattributet.

>[!TIP]
>
>**Smart beskärning** och **Bildförinställning** kan inte användas samtidigt. Om en författare behöver använda en bildförinställning tillsammans med en rendering för smart beskärning måste författaren använda **bildmodifieraren** för att lägga till förinställningar manuellt.

### Fliken Format {#styles-tab-edit}

![Fliken Format i redigeringsdialogrutan för e-postbildkomponent](/help/assets/image-configure-styles.png)

E-postbildkomponenten stöder AEM [Style System.](/help/get-started/authoring.md#component-styling)

Använd listrutan för att välja de format som du vill använda på komponenten. Markeringar som görs i redigeringsdialogrutan har samma effekt som de som väljs i komponentverktygsfältet.

Format måste konfigureras för den här komponenten i [designdialogrutan](#design-dialog) för att fliken ska vara tillgänglig.

## Designdialogruta {#design-dialog}

### Huvudflik {#main-tab}

![Huvudflik i designdialogrutan för bildkomponenten](/help/email/assets/email-image-design-main.png)

* **Aktivera DM-funktioner** - När det här alternativet är markerat är [Dynamiska mediefunktioner](#dynamic-media) tillgängliga.
   * Det här alternativet visas bara när Dynamic Media är aktiverat i miljön.
* **Aktivera webboptimerade bilder** - När det här alternativet är markerat [levererar den webboptimerade bildleveranstjänsten &#x200B;](/help/developing/web-optimized-image-delivery.md) bilder i WebP-format, vilket minskar bildstorleken med i genomsnitt 25 %.
   * Det här alternativet är endast tillgängligt i AEMaaCS.
   * När det är omarkerat eller när den webboptimerade bildleveranstjänsten inte är tillgänglig används [Adaptiv bildserver](/help/developing/adaptive-image-servlet.md).
* **Bilden är dekorativ** - Definiera om alternativet för dekorativ bild automatiskt är aktiverat när du lägger till bildkomponenten på en sida.
* **Hämta alternativ text från DAM**- Definiera om alternativet att hämta alternativ text från DAM automatiskt aktiveras när bildkomponenten läggs till på en sida.
* **Hämta beskrivning från DAM** - Ange om alternativet att hämta bildtexten från DAM automatiskt ska aktiveras när bildkomponenten läggs till på en sida.
* **Visa bildtext som popup-fönster** - Definiera om alternativet att visa bildtexten som ett popup-fönster automatiskt ska aktiveras när bildkomponenten läggs till på en sida.
* **Ändra storlek på bredd** - Det här värdet används för att ändra storlek på bredden på basbilderna som är DAM-resurser.
   * Bildernas proportioner bevaras.
   * Om värdet är större än bildens faktiska bredd har det här värdet ingen effekt.
   * Det här värdet påverkar inte SVG-bilder.

Du kan definiera en lista med bredder i pixlar för bilden så läser komponenten automatiskt in den mest lämpliga bredden baserat på webbläsarens storlek. Detta är en viktig del av [responsiva funktioner](#responsive-features) i e-postbildkomponenten.

* **Bredder** - Definierar en lista med bredder i pixlar för bilden och komponenten läser automatiskt in den mest lämpliga bredden baserat på webbläsarens storlek.
   * Tryck eller klicka på knappen **Lägg till** om du vill lägga till en annan storlek.
      * Använd handtagen för att ordna om storlekarna.
      * Använd ikonen **Ta bort** för att ta bort en bredd.
   * Inläsningen av bilder fördröjs som standard tills de blir synliga.
      * Välj alternativet **Inaktivera lazy loading** om du vill läsa in bilderna vid sidinläsning.
* **JPEG-kvalitet** - Kvalitetsfaktorn (i procent från 0 och 100) för omformade (t.ex. skalade eller beskurna) JPEG-bilder.
* **Standardbredd** - Standardbredden för bilder i pixlar som ska användas i designdialogrutan

>[!TIP]
>
>I dokumentet [Adaptiv bildserver](/help/developing/adaptive-image-servlet.md) finns tips om hur du kan optimera markeringen av återgivning genom att definiera dina bredder noggrant.

### Fliken Format {#styles-tab}

E-postbildkomponenten stöder AEM [Style System](/help/get-started/authoring.md#component-styling).
