---
title: Webboptimerad bildleverans
description: Läs om hur Core Components kan utnyttja AEM as a Cloud Service webboptimerade funktioner för bildleverans för att leverera bilder effektivare.
role: Architect, Developer, Admin, User
exl-id: 6080ab8b-f53c-4d5e-812e-16889da4d7de
source-git-commit: a134c2593593efef4df7b01e3a870e03e9860640
workflow-type: tm+mt
source-wordcount: '1169'
ht-degree: 0%

---

# Webboptimerad bildleverans {#web-optimized-image-delivery}

Läs om hur Core Components kan utnyttja AEM as a Cloud Service webboptimerade funktioner för bildleverans för att leverera bilder effektivare.

>[!NOTE]
>
>Den webboptimerade tjänsten för bildleverans är en förhandsversion i juni 2022 av AEM as a Cloud Service med GA som förväntas bli klar i juli.
>
>Mer information om förhandsversionsfunktionerna i AEMaaCS finns i dokumentet [Adobe Experience Manager as a Cloud Service Prerelease Channel](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/release-notes/prerelease.html)

## Översikt {#overview}

Den webboptimerade funktionen för bildleverans i AEM som en molntjänst levererar bildresurser från DAM i [WebP-format.](https://developers.google.com/speed/webp) WebP kan minska hämtningsstorleken för en bild med i genomsnitt 25 %, vilket ger snabbare sidinläsning.

Det är enkelt att aktivera webboptimerad bildleverans i Core Components, och eftersom alla vanliga webbläsare har stöd för WebP blir upplevelsen transparent för slutanvändaren. Den enda skillnaden de kommer att märka är att innehållet laddas snabbare!

## Aktivera webboptimerad bildleverans för kärnkomponenter {#activating}

Om du vill aktivera webboptimerad bildleverans redigerar du en sidmall och aktiverar bara alternativet **Aktivera webboptimerade bilder** i designdialogrutan [Bildkomponent.](/help/components/image.md#design-dialog) Det här alternativet är tillgängligt för v1, v2 och v3 i Image Component.

Om du inte känner till designdialogrutor och AEM sidmallar kan du [kan du läsa det här dokumentet.](/help/get-started/authoring.md#pre-configuring-core-components)

![Aktivera webboptimerad bildleverans i designdialogrutan](/help/assets/web-optimized-image-delivery.png)

Så ja! Bilderna levereras nu med Image Component i WebP-format.

När du har aktiverat webboptimerad bildleverans kanske du också vill kontrollera din dispatcherkonfiguration för att verifiera att den inte blockerar begäran till bildtjänsten. URL:er för den här tjänsten har följande format.

```text
/adobe/dynamicmedia/deliver/dm-aid--741ed388-d5f8-4797-8095-10c896dc9f1d/skitouring.jpg?quality=80&preferwebp=true
```

Detta kan generaliseras med det här reguljära uttrycket.

```text
\/adobe\/dynamicmedia\/deliver\/([^:[]|*\/])\/([\w-])\.(gif|png|png8|jpg|pjpg|bjpg|webp|webpll|webply)(?[a-z0-9=&]*)?
```

## Verifierar WebP-leverans {#verifying}

Webboptimerad bildleverans är transparent för konsumenten och påverkar inte koden. Det enda som slutanvändaren kommer att märka är snabbare laddningstid.

Därför måste du visa sidans källa för att kunna observera den faktiska beteendeändringen.

1. I AEM redigerar du en sida som är baserad på mallen där du [aktiverad webboptimerad bildleverans](#activating) för bildkomponenten.
1. I sidredigeraren väljer du **Sidinformation** längst upp till vänster och sedan **Visa som publicerad**.
1. Visa sidans källa med hjälp av dina webbläsares utvecklingsverktyg och se hur den återgivna markeringen förblir densamma, men att bilden i `src` attributpoäng till [URL:en för den nya bildtjänsten.](#activating)

## När webboptimerad bildleverans inte är tillgänglig {#fallback}

Webboptimerad bildleverans är endast tillgängligt i AEM as a Cloud Service. Om det inte är tillgängligt, t.ex. när AEM 6.5 körs lokalt eller på en lokal utvecklingsinstans, återställs bildleveransen till [den adaptiva bildservern.](/help/developing/adaptive-image-servlet.md)

På samma sätt som aktivering av webboptimerad bildleverans inte påverkar markeringen, har tillbakadragande till den adaptiva bildservern ingen effekt på markeringen eftersom bara URL:en i `src` attributet för `img` -elementet ändras.

## Vanliga frågor {#faq}

### Varför finns det inget sådant alternativ för att aktivera webboptimerade bilder i min miljö? {#missing-option}

Funktionen är bara tillgänglig på AEM as a Cloud Service. Kör AEM lokalt eller lokalt, Image-komponenten [faller bakåt](#fallback) till att använda den adaptiva bildservern.

### Varför fungerar inte tjänsten med den lokala SDK:n? {#local-sdk}

När AEM SDK används på `localhost`, bildtjänsten är inte tillgänglig och bildåtergivningen [faller bakåt](#fallback) till att använda den adaptiva bildservern.

Om du vill använda den webboptimerade bildleveranstjänsten ska du driftsätta projektet i en AEMaaCS-utvecklingsmiljö och exakt testa hur bildtjänsten fungerar med bildtjänsten.

### Varför fungerar inte tjänsten för vissa bilder på min sida? {#some-images}

Bildtjänsten fungerar bara för resurser som finns under `/content/dam` och det fungerar inte för bilder som laddas upp direkt till sidan och lagras under en `cq:Page` -objekt. Sådana resurser levereras fortfarande med Adaptive Image Server som en [fallback.](#fallback)

### Varför visas en bild med sämre kvalitet eller så begränsas bildstorleken? {#quality}

Den webboptimerade bildtjänsten hanterar alla bildåtergivningar som är 2 048 pixlar och mindre och väljer den största av dem som den bas som de ska använda de begärda inställningarna på (bredd, beskärning, format, kvalitet osv.).

Bilden kommer aldrig att skalas upp. Dessa renderingar definierar därför den bästa storlek och kvalitet som bildtjänsten kan leverera. Se därför till att alla dina resurser har zoomrenderingen 2 048 pixlar, och om de inte har det, bearbeta dem på nytt.

### URL-adressen till bilderna slutar fortfarande med .JPG eller .PNG, inte .WEBP, och det finns inget SRCSET-attribut eller PICTURE-element. Använder detta verkligen optimerade webbformat? {#content-negotiation}

För att leverera WebP-format använder den webboptimerade bildleveranstjänsten en teknik som kallas&quot;innehållsförhandling&quot;. Detta innebär att ett WebP-filformat returneras, även om ett JPG- eller PNG-filtillägg begärs, men endast när webbläsaren gjorde begäran fick ett `image/webp` HTTP accept header. Webbläsare som stöder den här tekniken kan sedan ange det här huvudet och äldre webbläsare kommer fortfarande att få filformatet JPG eller PNG.

Fördelen med den här tekniken är att `img` -elementet och dess attribut kan vara desamma, vilket ger optimal kompatibilitet för befintliga webbplatser och garanterar en så smidig övergång som möjligt till webboptimerad bildleverans.

### Kan jag använda webboptimerad bildleverans med min egen komponent?

Ja, den webboptimerade bildleveranstjänsten kan användas av anpassade komponenter. Adobe rekommenderar [utöka bildkomponenten](/help/developing/customizing.md) i detta fall.

Följande är ett gränssnitt som kan användas för att generera resurs-URL:en.

```
com.adobe.cq.wcm.spi.AssetDelivery.getDeliveryURL(Resource resource, Map<String, Object> parameterMap)
```

Den här tjänsten tar en resursresurs som obligatorisk första parameter och kan ta en valfri karta över önskade bildomformningar som ska användas och som kan innehålla följande parametrar.

* `path` - Tillgångs-ID som ska levereras måste ha ett mönster `([^:\[\]\|\*\/]+)` (t.ex.: `unicorn–1234`)
* `seoname` - Användardefinierat SEO-centrerat namn som ska läggas till i bild-URL:en, kan innehålla bindestreck, måste vara av mönstret `([\w-]+)` (t.ex.: `my-friend-the-unicorn`)
* `format` - Det önskade bildformatet, kan `gif`, `png`, `png8`, `jpg`, `pjpg`, `bjpg`, `webp`, `webpll`, `webply` (t.ex.: `webp`)
* `preferwebp` - Leverera om möjligt WebP-utdata utan att ta hänsyn till `format` parameter ([se Frågor och svar om innehållsförhandling](#content-negotiation)), boolesk (t.ex.: `true`)
* `width` - Den önskade bildupplösningen i pixlar måste vara större än 1 (t.ex.: `400`)
* `quality` - den önskade komprimeringen, mellan `1` och `100` (t.ex.: `75`)
* `c` - Önskade bildbeskärningskoordinater, kommaavgränsade pixelvärden (t.ex.: `100,100,400,200`)
* `r` - Den önskade bildrotationen kan `90`, `180`, `270` (t.ex.: `90`)
* `flip` - Den bild som du vill vända, kan `h`, `v`, `hv` (t.ex.: `h`)

### Vad är URL:en för en bild som levereras av den nya bildtjänsten? {#url}

Se föregående avsnitt [Aktivera webboptimerad bildleverans för kärnkomponenter](#activating) för ett exempel-URL och reguljära uttryck.

### Kan bilder inte visas när webboptimerade bilder har aktiverats?

Nej, det här ska aldrig hända.

* I HTML ändras inte markeringen när du aktiverar webboptimerade bilder, bara värdet för SRC-attributet i bildelementet ändras.
* När den nya bildtjänsten inte är tillgänglig eller inte kan bearbeta den önskade bilden, kommer den URL som skapas att [tillbaka till Adaptive Image Server.](#fallback)
* Dispatcher-regler kan blockera den webboptimerade bildtjänsten och [ska kontrolleras när funktionen aktiveras.](#activating)