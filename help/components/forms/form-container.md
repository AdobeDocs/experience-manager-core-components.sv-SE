---
title: Formulärbehållarkomponent
description: Med komponenten Core Component Form Container Component kan man skapa enkla inskickningsformulär.
translation-type: tm+mt
source-git-commit: 95c0621f5423bfa515fe5e8b693e127ea56b4ae0

---


# Formulärbehållarkomponent {#form-container-component}

Med komponenten Core Component Form Container Component kan man skapa enkla inskickningsformulär.

## Användning {#usage}

Med formulärbehållarkomponenten kan du skapa enkla formulär och funktioner för inlämning av information genom att stödja enkla WCM-formulär och använda en kapslad struktur för att tillåta ytterligare formulärkomponenter.

Genom att använda dialogrutan [](#configure-dialog) Konfigurera kan innehållsredigeraren definiera åtgärden som ska aktiveras när formulär skickas, var det skickade innehållet ska lagras och om ett arbetsflöde ska aktiveras. Mallförfattaren kan använda [designdialogrutan](#design-dialog) för att definiera de tillåtna komponenterna och deras mappningar som liknar designdialogrutan för [standardlayoutbehållaren i mallredigeraren](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html).

>[!NOTE]
>
>Huvudkomponenterna Form Container Component har endast stöd för användning av kärnkomponenter i form av komponenter (knapp, text, dold etc.). Det går inte att använda [baskomponenter](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/siteandpage/default-components-foundation.html) i kärnkomponentens formulärbehållare (och vice versa).

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Form Container Component är v2, som introducerades i version 2.0.0 av Core Components i januari 2018, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponentversionerna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |--- |---|
| v2 | Kompatibel | Kompatibel | Kompatibel | Kompatibel |
| [v1](/help/components/v1/form-container-v1.md) | Kompatibel | Kompatibel | Kompatibel | - |

Mer information om Core Component-versioner och -versioner finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill visa komponenterna i Form Container samt se exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_form_container).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Form Container Component [finns på GitHub](https://adobe.com/go/aem_cmp_tech_form_container_v2).

Mer information om hur du utvecklar kärnkomponenter finns i dokumentationen till [Core Components Developer](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera vilka åtgärder som ska vidtas när komponenten skickas.

![](/help/assets/screen_shot_2018-01-12at122046.png)

Beroende på den valda **åtgärdstypen**&#x200B;ändras de tillgängliga alternativen i behållaren. De tillgängliga åtgärdstyperna är:

* [E-post](#mail)
* [Lagra innehåll](#store-content)
* [Skicka beställning](#submit-order)
* [Uppdatera ordning](#update-order)

Oavsett typ finns det [allmänna inställningar](#general-settings) för varje åtgärd.

### E-post {#mail}

När formuläret skickas skickar poståtgärdstypen ett e-postmeddelande till angivna mottagare.

![](/help/assets/screen_shot_2018-01-12at122554.png)

* **Ämne**&#x200B;Ämnet för det e-postmeddelande som ska skickas när formulär skickas
* **Från** e-postadressen som kommer att skickas när formulär skickas
* **Till** adresserna till mottagarna som får ett e-postmeddelande när formuläret skickas

   * Tryck eller klicka på knappen **Lägg till** för att lägga till ytterligare adresser
   * Tryck eller klicka på knappen **Ta bort** för att ta bort en e-postadress
* **CC** Adresserna till mottagarna som ska få en kopia av e-postmeddelandet som skickas när formuläret skickas in
   * Tryck eller klicka på knappen **Lägg till** för att lägga till ytterligare adresser
   * Tryck eller klicka på knappen **Ta bort** för att ta bort en e-postadress

### Lagra innehåll {#store-content}

När formuläret skickas kommer innehållet i formuläret att lagras på en angiven plats i databasen.

![](/help/assets/screen_shot_2018-01-12at122538.png)

* **Sökväg till innehållsdatabas** Sökväg till innehållsdatabas där skickat innehåll lagras
* **Visa data** Tryck eller klicka för att visa lagrade skickade data som JSON
* **Starta arbetsflöde** Konfigurera för att starta ett arbetsflöde med det lagrade innehållet som nyttolast när formuläret skickas

### Skicka beställning {#submit-order}

När formuläret skickas in skickas ordern.

![](/help/assets/chlimage_1-3.png)

### Uppdatera ordning {#update-order}

När formuläret skickas uppdateras ordern.

![](/help/assets/chlimage_1-4.png)

### Allmänna inställningar {#general-settings}

Oavsett vilken åtgärdstyp du väljer kan du alltid definiera en tacksida.

![](/help/assets/chlimage_1-5.png)

Användaren omdirigeras till den angivna sidan när formuläret har skickats.

* Använd dialogrutan Välj för att välja en resurs i AEM.
* Om tacksidan inte finns i AEM anger du den absoluta URL:en. Icke-absoluta URL:er tolkas i förhållande till AEM.
* Lämna tomt om du vill visa formuläret igen när det har skickats.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera de tillåtna komponenterna och deras mappningar för behållaren som liknar designdialogrutan för [standardlayoutbehållaren i mallredigeraren](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html).
