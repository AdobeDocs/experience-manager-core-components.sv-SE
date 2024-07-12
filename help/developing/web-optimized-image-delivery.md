---
title: Webboptimerad bildleverans
description: Läs om hur Core Components kan utnyttja AEM as a Cloud Service webboptimerade funktioner för bildleverans för att leverera bilder effektivare.
role: Architect, Developer, Admin, User
exl-id: 6080ab8b-f53c-4d5e-812e-16889da4d7de
source-git-commit: eb1822cb41a849695afb5125745ed5f78e3e70a4
workflow-type: tm+mt
source-wordcount: '1061'
ht-degree: 0%

---

# Webboptimerad bildleverans {#web-optimized-image-delivery}

Läs om hur Core Components kan utnyttja AEM as a Cloud Service webboptimerade funktioner för bildleverans för att leverera bilder effektivare.

## Ökning {#overview}

Den webboptimerade bildleveransfunktionen i AEM som en molntjänst levererar bildresurser från DAM i [WebP-format.](https://developers.google.com/speed/webp) WebP kan minska hämtningsstorleken för en bild med i genomsnitt cirka 25 %, vilket ger snabbare sidinläsning.

Det är enkelt att aktivera webboptimerad bildleverans i Core Components, och eftersom alla vanliga webbläsare har stöd för WebP blir upplevelsen transparent för slutanvändaren. Den enda skillnaden de kommer att märka är att innehållet laddas snabbare!

## Aktivera webboptimerad bildleverans för kärnkomponenter {#activating}

Om du vill aktivera webboptimerad bildleverans redigerar du en sidmall och aktiverar bara alternativet **Aktivera webboptimerade bilder** i designdialogrutan för [bildkomponenten.](/help/components/image.md#design-dialog) Det här alternativet är tillgängligt för v1, v2 och v3 i Image-komponenten.

[Granska det här dokumentet om du inte känner till designdialogrutor och AEM sidmallar.](/help/get-started/authoring.md#pre-configuring-core-components)

![Aktivera webboptimerad bildleverans i designdialogrutan](/help/assets/web-optimized-image-delivery.png)

Så ja! Bilderna levereras nu med Image Component i WebP-format.

När du har aktiverat webboptimerad bildleverans kanske du vill kontrollera din dispatcherkonfiguration för att verifiera att den inte blockerar begäran till bildleveranstjänsten. Mer information finns i [den här posten med vanliga frågor](#failure-to-deliver).

## Verifierar WebP-leverans {#verifying}

Webboptimerad bildleverans är transparent för konsumenten. Det enda som slutanvändaren kommer att märka är snabbare laddningstid. För att kunna observera eventuella beteendeförändringar måste du därför kontrollera innehållstypen för de återgivna bilderna i webbläsaren. Alla moderna webbläsare har stöd för WebP. Mer information om stöd för webbläsare finns på [den här webbplatsen](https://caniuse.com/webp).

1. I AEM redigerar du en sida som är baserad på mallen där du [aktiverade webboptimerad bildleverans](#activating) för bildkomponenten.
1. I sidredigeraren väljer du knappen **Sidinformation** längst upp till vänster och sedan **Visa som publicerad**.
1. Öppna webbläsarens utvecklarverktyg och välj fliken Nätverk.
1. Läs in sidan igen och sök efter HTTP-begäranden som läser in bilderna och kontrollera innehållstypen för bilden som webbläsaren tog emot.

## När webboptimerad bildleverans inte är tillgänglig {#fallback}

Webboptimerad bildleverans är endast tillgängligt i AEM as a Cloud Service. Om den inte är tillgänglig, till exempel om AEM 6.5 körs lokalt eller på en lokal utvecklingsinstans, återgår bildleveransen till att använda [den adaptiva bildservern.](/help/developing/adaptive-image-servlet.md)

Om du återgår till den adaptiva bildservern ändras attributet `src` för elementen `img` i sidkällan.

## Vanliga frågor {#faq}

### Varför finns det inget alternativ för att aktivera webboptimerade bilder i min miljö? {#missing-option}

Funktionen är bara tillgänglig på AEM as a Cloud Service. Om du kör AEM lokalt eller lokalt återgår bildkomponenten [till att använda den adaptiva bildservern ](#fallback).

### Varför fungerar inte tjänsten med den lokala SDK:n? {#local-sdk}

När du använder AEM SDK på `localhost` är inte bildtjänsten tillgänglig, och bildåtergivningen [ återgår ](#fallback) till att använda den adaptiva bildservern.

Om du vill använda den webboptimerade bildleveranstjänsten ska du driftsätta projektet i en AEMaaCS-utvecklingsmiljö och exakt testa hur bildtjänsten fungerar med bildtjänsten.

### Varför fungerar inte tjänsten för vissa bilder på min sida? {#some-images}

Bilden fungerar bara för resurser som finns under `/content/dam` och fungerar inte för bilder som överförs direkt till sidan och lagras under ett `cq:Page`-objekt. Sådana resurser levereras fortfarande med Adaptive Image Server som [reservresurs.](#fallback)

### Varför visas en bild med sämre kvalitet eller så begränsas bildstorleken? {#quality}

När bildobjekt under `/content/dam` bearbetas genererar AEM as a Cloud Service-miljöer optimerade återgivningar med olika dimensioner. Den webboptimerade bildtjänsten analyserar den bredd som krävs av Image Core Component, tar hänsyn till den ursprungliga bilden och alla renderingar som är 2 048 pixlar och mindre, och väljer den största av dessa (inom bildtjänsten för storlek och dimensionsgränser kan hantera, för närvarande 50 MB och `12k` x`12k`) som den bas som den ska använda de begärda inställningarna på (bredd, beskärning, format, kvalitet osv.).

För att bevara originalets återgivning skalförändras inte bilderna. Ovannämnda återgivningar definierar den bästa kvalitet som bildtjänsten kan leverera. Eftersom du ofta inte kan påverka storleken och/eller dimensionerna på den ursprungliga bildresursen bör du kontrollera att alla bildresurser har en zoomåtergivning på 2 048 pixlar och om de inte gör det, bearbeta om dem.

### URL:en till mina bilder slutar fortfarande med .JPG eller .PNG, inte .WEBP, och det finns inget SRCSET-attribut eller PICTURE-element. Använder detta verkligen optimerade webbformat? {#content-negotiation}

För att kunna leverera WebP-format utför den webboptimerade bildleveranstjänsten [serverdrivna innehållsförhandlingar.](https://developer.mozilla.org/en-US/docs/Web/HTTP/Content_negotiation#server-driven_content_negotiation) Detta hjälper till att välja det optimala utdataformatet för bilden baserat på klientannonserade funktioner, vilket gör att bildleveranstjänsten kan ignorera filtillägget.

Fördelen med att använda innehållsförhandling är att webbläsare som inte annonserar stöd för WebP fortfarande får filformatet JPG eller PNG utan att behöva ändra sidans kod. Detta ger optimal kompatibilitet för befintliga webbplatser och garanterar en så smidig övergång som möjligt till webboptimerad bildleverans.

### Kan jag använda webboptimerad bildleverans med min egen komponent?

Ja, den webboptimerade bildleveranstjänsten kan användas av anpassade komponenter, som byggs av [en utökning av bildkomponenten](/help/developing/customizing.md)

Följande är ett gränssnitt som kan användas för att generera resurs-URL:en.

```
com.adobe.cq.wcm.spi.AssetDelivery.getDeliveryURL(Resource resource, Map<String, Object> parameterMap)
```

>[!WARNING]
>
>Direkt URL-inbäddning i en upplevelse som inte har byggts via den tidigare SPI (som är tillgänglig på AEM as a Cloud Service Sites) bryter mot [Media Library användningsvillkor](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/admin/medialibrary.html?lang=en#use-media-library).

### Kan bilder inte visas när webboptimerade bilder har aktiverats? {#failure-to-deliver}

Nej, det ska aldrig ske av följande skäl.

* I HTML ändras inte markeringen när du aktiverar webboptimerade bilder, bara värdet för attributet `src` i bildelementet ändras.
* När den nya bildtjänsten inte är tillgänglig eller inte kan bearbeta den önskade bilden kommer den URL som genereras att [återgå till den adaptiva bildservern.](#fallback)

Dispatcheringsregler kan dock blockera den webboptimerade bildleveranstjänsten. URL:er för bildleveranstjänsten börjar med `/adobe`, och i dispatcherloggarna görs en undersökning av avvisade begäranden, som [beskrivs här](https://experienceleague.adobe.com/docs/experience-manager-learn/ams/dispatcher/common-logs.html#filter-rejects), så att du kan felsöka eventuella fel som uppstår vid leveransen av bilderna till webbläsaren.
