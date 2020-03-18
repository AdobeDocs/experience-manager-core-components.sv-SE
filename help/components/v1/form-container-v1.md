---
title: Formulärbehållarkomponent (v1)
description: Med komponenten Core Component Form Container Component kan man skapa enkla inskickningsformulär.
index: n
translation-type: tm+mt
source-git-commit: 68472ab548fb6ebb443a06c12e7b37797a0c1302

---


# Formulärbehållarkomponent (v1) {#form-container-component-v1}

Med komponenten Core Component Form Container Component kan man skapa enkla inskickningsformulär.

## Användning {#usage}

Komponenten Form Container gjorde det möjligt att skapa enkla formulär och funktioner för inlämning av information genom att stödja enkla WCM-formulär och genom att använda en kapslad struktur för att tillåta ytterligare formulärkomponenter.

Genom att använda [inställningsdialogrutan](#settings-dialog) kan innehållsredigeraren definiera vilken typ av åtgärd som utlöser när formuläret skickas, var det skickade innehållet ska lagras och om ett arbetsflöde ska utlösas. Mallförfattaren kan använda [designdialogrutan](#design-dialog) för att definiera tillåt-komponenter och deras mappningar som liknar designdialogrutan för [standardlayoutbehållaren i mallredigeraren](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/templates.html).

## Version och kompatibilitet {#version-and-compatibility}

I det här dokumentet beskrivs v1 av Form Container Component, som ursprungligen introducerades i version 1.0.0 av Core Components med AEM 6.3.

I följande tabell visas kompatibiliteten för v1 för komponenten Form Container.

| AEM-version | Formulärbehållarkomponent v1 |
|--- |--- |
| 6.3 | Kompatibel |
| 6.4 | Kompatibel |

>[!CAUTION]
>
>I det här dokumentet beskrivs v1 för komponenten Form Container.
>
>Mer information om den aktuella versionen av Form Container Component finns i [dokumentet Form Container Component](/help/components/forms/form-container.md) .

## Dialogrutan Inställningar {#settings-dialog}

I inställningsdialogrutan kan innehållsförfattaren definiera vilka åtgärder som ska vidtas när komponenten skickas.

![](/help/assets/chlimage_1.png)

Beroende på den valda **åtgärdstypen**&#x200B;ändras de tillgängliga alternativen i behållaren. De tillgängliga åtgärdstyperna är:

* [E-post](#mail)
* [Lagra innehåll](#store-content)
* [Skicka beställning](#submit-order)
* [Uppdatera ordning](#update-order)

Oavsett typ finns det [allmänna inställningar](#general-settings) för varje åtgärd.

### E-post {#mail}

När formuläret skickas skickar poståtgärdstypen ett e-postmeddelande till angivna mottagare.

![](/help/assets/chlimage_1-1.png)

* **Ämne** - Ämnet för det e-postmeddelande som ska skickas när formulär skickas
* **Från** - Från-e-postadressen till det e-postmeddelande som ska skickas när formulär skickas
* **Till** - Adresserna till mottagarna som ska få ett e-postmeddelande när formuläret skickas in
   * Tryck eller klicka på knappen **Lägg till** för att lägga till ytterligare adresser
   * Tryck eller klicka på knappen **Ta bort** för att ta bort en e-postadress
* **CC** - Adresserna till mottagarna som ska få en kopia av e-postmeddelandet som skickas när formuläret skickas in
   * Tryck eller klicka på knappen **Lägg till** för att lägga till ytterligare adresser
   * Tryck eller klicka på knappen **Ta bort** för att ta bort en e-postadress

### Lagra innehåll {#store-content}

När formuläret skickas kommer innehållet i formuläret att lagras på en angiven plats i databasen.

![](/help/assets/chlimage_1-2.png)

* **Innehållssökväg** - Sökväg till innehållsdatabas där skickat innehåll lagras
* **Visa data** - Tryck eller klicka för att visa lagrade skickade data som JSON
* **Starta arbetsflöde** - Konfigurera för att starta ett arbetsflöde med det lagrade innehållet som nyttolast när formuläret skickas

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

I designdialogrutan kan mallskaparen definiera de tillåtna komponenterna och deras mappningar för behållaren som liknar designdialogrutan för [standardlayoutbehållaren i mallredigeraren](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/templates.html#main-pars_title_1754153843).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Form Container Component [finns på GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/container/v1/container).

Hela kärnkomponentprojektet kan laddas ned från GitHub.

Mer information om hur du utvecklar kärnkomponenter finns i dokumentationen till [Core Components Developer](/help/developing/overview.md).
