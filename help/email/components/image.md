---
title: E-postbildkomponent
description: E-postbildkomponenten är en adaptiv bildkomponent med redigering på plats.
role: Architect, Developer, Admin, User
exl-id: f5d40047-3082-4edd-a5f6-6ab3e33997f9
source-git-commit: 33976c0e745ad091a142109f70541f01a31edc5b
workflow-type: tm+mt
source-wordcount: '1683'
ht-degree: 0%

---


# E-postbildkomponent {#email-image-component}

E-postbildkomponenten är en adaptiv bildkomponent med redigering på plats.

## Användning {#usage}

E-postbildkomponenten har adaptiv bildmarkering och responsivt beteende med lat inläsningsbeteende för sidbesökaren samt enkel dra-och-släpp-montering och konfiguration för innehållsförfattaren.

* Bildbredderna och ytterligare inställningar kan definieras av mallskaparen i [designdialog.](#design-dialog)
* Innehållsredigeraren kan överföra eller välja resurser i [dialogrutan konfigurera.](#configure-dialog)

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av e-postbildkomponenten är v1, som introducerades med version x av e-postkärnkomponenterna i oktober 2022, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | Kompatibel | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Huvudkomponentversioner för e-post](/help/email/versions.md).

## Responsiva funktioner {#responsive-features}

E-postbildkomponenten har robusta responsiva funktioner som är klara direkt vid leverans. På sidmallsnivå visas [designdialogruta](#design-dialog) kan användas för att definiera bildresursens standardbredder. E-postbildkomponenten läser sedan automatiskt in rätt bredd för visning beroende på storleken på webbläsarfönstret. När fönstrets storlek ändras läser e-postbildkomponenten in rätt bildstorlek dynamiskt direkt. Komponentutvecklare behöver inte bekymra sig om att definiera anpassade mediefrågor eftersom e-postbildkomponenten redan är optimerad för att läsa in ditt innehåll.

Dessutom har e-postbildkomponenten stöd för lazy loading för att skjuta upp inläsningen av den faktiska bildresursen tills den syns i webbläsaren, vilket gör att innehållet blir mer responsivt.

>[!TIP]
>
>Som standard drivs e-postbildkomponenten av den adaptiva bildservern. Se dokumentet [Adaptiv bildserver](#adaptive-image-servlet) om du vill ha mer information om hur det fungerar.

## Dynamic Media Support {#dynamic-media}

E-postbildkomponenten stöder [Dynamic Media](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/dynamic-media.html#dynamicmedia) resurser. [När det är aktiverat](#design-dialog) Med de här funktionerna kan du lägga till Dynamic Media bildresurser med en enkel dra och släpp-funktion eller via resursläsaren på samma sätt som med andra bilder. Dessutom stöds även bildmodifierare, bildförinställningar och smarta beskärningar.

Dina e-postupplevelser som byggts med e-postkärnkomponenterna kan innehålla omfattande, Sensei-baserade, robusta, högpresterande, plattformsoberoende Dynamic Media Image-funktioner.

## Stöd för SVG {#svg-support}

Scalable Vector Graphics (SVG) stöds av Email Image Component.

* Både dra-och-släpp av en SVG-resurs från DAM och överföring av en SVG-filöverföring från ett lokalt filsystem stöds.
* Den ursprungliga SVG-filen direktuppspelas (omformningar hoppas över).
* För en SVG-bild ställs&quot;smarta bilder&quot; och&quot;smarta storlekar&quot; in på en tom array i bildmodellen.

### Dokumentskydd {#security}

Av säkerhetsskäl anropas aldrig SVG direkt av bildredigeraren. Den kallas för `<img src=“path-to-component”>`. Detta förhindrar webbläsaren från att köra skript som är inbäddade i filen SVG.

## Exempel på komponentutdata {#sample-component-output}

Om du vill visa e-postbildkomponenten och se exempel på dess konfigurationsalternativ samt HTML och JSON-utdata går du till [Komponentbibliotek.](https://adobe.com/go/aem_cmp_library_email_image)

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om e-postbildkomponenten [finns på GitHub.](https://adobe.com/go/aem_cmp_tech_email_image_v1)

Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentens utvecklare.](/help/developing/overview.md)

Bildkomponenten har stöd för [schema.org-mikrodata.](https://schema.org)

## Konfigurera dialogruta {#configure-dialog}

E-postbildkomponenten innehåller en konfigureringsdialogruta där själva bilden definieras tillsammans med dess beskrivning och grundläggande egenskaper.

### Fliken Resurser {#asset-tab}

![Fliken Resurser i dialogrutan Konfigurera e-postbildkomponent](/help/email/assets/email-image-configure-asset.png)

* **Ärv bild från sida** - Det här alternativet använder [bild av den länkade sidan](page.md) eller den aktuella sidans aktuella bild om bilden inte är länkad.

* **Alternativ text för tillgänglighet** - I det här fältet kan du definiera en beskrivning av bilden för användare med nedsatt syn.

   * **Ärv alternativ text från sida** - Det här alternativet använder den alternativa beskrivningen av det länkade tillgångsvärdet för `dc:description` metadata i DAM eller på den aktuella sidan om ingen resurs är länkad.

* **Bildresurs**
   * Släpp en resurs från [resursläsare](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) eller tryck på **bläddra** om du vill överföra från ett lokalt filsystem.
   * Tryck eller klicka **Rensa** för att avmarkera den markerade bilden.
   * Tryck eller klicka **Redigera** till [hantera återgivningar av resursen](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) i Resursredigeraren.

* **Ange inte en alternativ text** - Med det här alternativet markeras den bild som ska ignoreras av hjälpmedelstekniker, som skärmläsare, om bilden är helt dekorativ eller på annat sätt inte förmedlar någon ytterligare information till sidan.

* **Inaktivera lazy loading** - Det här alternativet läser in alla bildkomponenter i förväg utan att läsas in efter behov.

### Fliken Metadata {#metadata-tab}

![Fliken Metadata i dialogrutan Konfigurera för Image Component](/help/email/assets/email-image-configure-metadata.png)

* **Förinställningstyp** - Detta definierar de typer av bildförinställningar som är tillgängliga, antingen **Bildförinställning** eller **Smart beskärning** och är bara tillgängligt när [Funktioner i Dynamic Media](#dynamic-meida) är aktiverade.
   * **Bildförinställning** - När **Förinställningstyp** av **Bildförinställning** är markerat, listrutan **Bildförinställning** är tillgängligt och du kan välja bland de tillgängliga förinställningarna för Dynamic Media. Detta är bara tillgängligt om förinställningar har definierats för den valda resursen.
   * **Smart beskärning** - När **Förinställningstyp** av **Smart beskärning** är markerat i listrutan **Återgivning** är tillgängligt och du kan välja bland de tillgängliga återgivningarna av den valda resursen. Detta är bara tillgängligt om återgivningar har definierats för den valda resursen.
   * **Bildmodifierare** - Här kan du definiera ytterligare bildserverkommandon från Dynamic Media avgränsade med `&`oavsett vilka **Förinställningstyp** är markerat.
* **Bildtext** - Ytterligare information om bilden, som visas under bilden som standard.
   * **Hämta beskrivning från DAM** - När det här alternativet är markerat fylls bildtexten i med värdet för `dc:title` metadata i DAM. Endast tillgängligt när en resurs väljs från DAM.
   * **Visa bildtext som popup-fönster** - När det här alternativet är markerat visas inte bildtexten nedanför bilden, utan som ett popup-fönster som visas av vissa webbläsare när de hovrar över bilden.
* **Länk** - Länka bilden till en annan resurs.
   * Använd urvalsdialogrutan för att länka till en annan AEM.
   * Om du inte länkar till en AEM resurs anger du den absoluta URL:en. Icke-lösliga URL:er tolkas som relativa till AEM.
   * **Öppna länk på ny flik** - Med det här alternativet öppnas länken i ett nytt webbläsarfönster.
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML.
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka CSS.
* **Åtgärdat med** - Det här alternativet definierar bildens bredd i pixlar.
* **Anpassa bilden till tillgänglig bredd** - Det här alternativet gäller `"width":"100%"` till bildformatsattributet.

>[!TIP]
>
>**Smart beskärning** och **Bildförinställning** alternativ som utesluter varandra. Om en författare behöver använda en bildförinställning tillsammans med en rendering för smart beskärning måste författaren använda **Bildmodifierare** om du vill lägga till förinställningar manuellt.

### Fliken Format {#styles-tab-edit}

![Fliken Format i redigeringsdialogrutan för e-postbildkomponent](/help/assets/image-configure-styles.png)

E-postbildkomponenten stöder AEM [Formatsystem.](/help/get-started/authoring.md#component-styling)

Använd listrutan för att välja de format som du vill använda på komponenten. Markeringar som görs i redigeringsdialogrutan har samma effekt som de som väljs i komponentverktygsfältet.

Format måste konfigureras för den här komponenten i [designdialogruta](#design-dialog) för att fliken ska vara tillgänglig.

## Designdialogruta {#design-dialog}

### Huvudflik {#main-tab}

![Huvudflik i designdialogrutan för bildkomponenten](/help/email/assets/email-image-design-main.png)

* **Aktivera DM-funktioner** - När det är markerat, [Funktioner i Dynamic Media](#dynamic-media) är tillgängliga.
   * Det här alternativet visas bara när Dynamic Media är aktiverat i miljön.
* **Aktivera webboptimerade bilder** - När det är markerat, [webboptimerad bildleveranstjänst](/help/developing/web-optimized-image-delivery.md) kommer att leverera bilder i WebP-format, vilket i genomsnitt minskar bildstorlekarna med 25 %.
   * Det här alternativet är endast tillgängligt i AEMaaCS.
   * När alternativet är avmarkerat eller när den webboptimerade bildleveranstjänsten inte är tillgänglig visas [Adaptiv bildserver](/help/developing/adaptive-image-servlet.md) används.
* **Bilden är dekorativ** - Ange om alternativet för dekorativa bilder ska aktiveras automatiskt när du lägger till bildkomponenten på en sida.
* **Hämta alternativ text från DAM**- Ange om alternativet att hämta alternativ text från DAM automatiskt ska aktiveras när bildkomponenten läggs till på en sida.
* **Hämta beskrivning från DAM** - Ange om alternativet att hämta bildtexten från DAM-modulen ska aktiveras automatiskt när bildkomponenten läggs till på en sida.
* **Visa bildtext som popup-fönster** - Ange om alternativet att visa bildtexten som en popup-ruta automatiskt ska aktiveras när bildkomponenten läggs till på en sida.
* **Ändra bredd** - Det här värdet används för att ändra bredden på basbilderna som är DAM-resurser.
   * Bildernas proportioner bevaras.
   * Om värdet är större än bildens faktiska bredd har det här värdet ingen effekt.
   * Det här värdet påverkar inte bilder i SVG.

Du kan definiera en lista med bredder i pixlar för bilden så läser komponenten automatiskt in den mest lämpliga bredden baserat på webbläsarens storlek. Detta är en viktig del av [responsiva funktioner](#responsive-features) för e-postbildkomponenten.

* **Bredd** - Definierar en lista med bredder i pixlar för bilden och komponenten läser automatiskt in den mest lämpliga bredden baserat på webbläsarens storlek.
   * Tryck eller klicka på **Lägg till** om du vill lägga till en annan storlek.
      * Använd handtagen för att ordna om storlekarna.
      * Använd **Ta bort** om du vill ta bort en bredd.
   * Som standard skjuts inläsningen av bilder tills de blir synliga.
      * Välj alternativet **Inaktivera lazy loading** för att läsa in bilderna när sidan läses in.
* **JPEG-kvalitet** - Kvalitetsfaktorn (i procent mellan 0 och 100) för omformade (t.ex. skalade eller beskurna) bilder i JPEG.
* **Standardbredd** - Standardbredden för bilder i pixlar som ska användas i designdialogrutan

>[!TIP]
>
>Se dokumentet [Adaptiv bildserver](/help/developing/adaptive-image-servlet.md) för tips om hur du kan optimera markeringen av återgivning genom att definiera dina bredder noggrant.

### Fliken Format {#styles-tab}

E-postbildkomponenten stöder AEM [Formatsystem](/help/get-started/authoring.md#component-styling).
