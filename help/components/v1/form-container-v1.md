---
title: Formulärbehållarkomponent (v1)
description: Med komponenten Core Component Form Container Component kan man skapa enkla inskickningsformulär.
index: n
role: Architect, Developer, Admin, User
exl-id: 1e34219f-fa82-494e-82e2-1b4d63d37fea
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 0%

---


# Formulärbehållarkomponent (v1) {#form-container-component-v1}

Med komponenten Core Component Form Container Component kan man skapa enkla inskickningsformulär.

## Användning {#usage}

Komponenten Form Container gjorde det möjligt att skapa enkla formulär och funktioner för inlämning av information genom att stödja enkla WCM-formulär och genom att använda en kapslad struktur för att tillåta ytterligare formulärkomponenter.

Genom att använda dialogrutan [inställning](#settings-dialog) kan innehållsredigeraren definiera vilken typ av åtgärd som utlöser formulärsändning, var det skickade innehållet ska lagras och om ett arbetsflöde ska utlösas. Mallförfattaren kan använda [designdialogrutan](#design-dialog) för att definiera tillåt-komponenter och deras mappningar som liknar designdialogrutan för [standardlayoutbehållaren i mallredigeraren](https://helpx.adobe.com/se/experience-manager/6-4/sites/authoring/using/templates.html).

## Version och kompatibilitet {#version-and-compatibility}

I det här dokumentet beskrivs v1 av Form Container Component, som ursprungligen introducerades i version 1.0.0 av Core Components med AEM 6.3.

I följande tabell visas kompatibiliteten för v1 för komponenten Form Container.

| AEM Version | Formulärbehållarkomponent v1 |
|--- |--- |
| 6,3 | Kompatibel |
| 6,4 | Kompatibel |

>[!CAUTION]
>
>I det här dokumentet beskrivs v1 för komponenten Form Container.
>
>Mer information om den aktuella versionen av formulärbehållarkomponenten finns i dokumentet [Formulärbehållarkomponent](/help/components/forms/form-container.md).

## Dialogrutan Inställningar {#settings-dialog}

I inställningsdialogrutan kan innehållsförfattaren definiera vilka åtgärder som ska vidtas när komponenten skickas.

![](/help/assets/chlimage_1.png)

Beroende på vald **åtgärdstyp** ändras de tillgängliga alternativen i behållaren. De tillgängliga åtgärdstyperna är:

* [E-post](#mail)
* [Lagra innehåll](#store-content)
* [Skicka beställning](#submit-order)
* [Uppdatera ordning](#update-order)

Oavsett typ finns det [allmänna inställningar](#general-settings) som gäller för varje åtgärd.

### E-post {#mail}

När formuläret skickas skickar poståtgärdstypen ett e-postmeddelande till angivna mottagare.

![](/help/assets/chlimage_1-1.png)

* **Ämne** - Ämnet i det e-postmeddelande som skickas när formulär skickas
* **Från** - Från-e-postadressen för det e-postmeddelande som ska skickas när formulär skickas
* **Till** - Adresserna till mottagarna som får ett e-postmeddelande när formuläret skickas
   * Tryck eller klicka på knappen **Lägg till** för att lägga till ytterligare adresser
   * Tryck eller klicka på knappen **Ta bort** för att ta bort en e-postadress
* **CC** - Adresserna till mottagare som ska få en kopia av e-postmeddelandet som skickas när formuläret skickas
   * Tryck eller klicka på knappen **Lägg till** för att lägga till ytterligare adresser
   * Tryck eller klicka på knappen **Ta bort** för att ta bort en e-postadress

### Lagra innehåll {#store-content}

När formuläret skickas kommer innehållet i formuläret att lagras på en angiven plats i databasen.

![](/help/assets/chlimage_1-2.png)

* **Innehållssökväg** - Sökväg till innehållsdatabas där skickat innehåll lagras
* **Visa data** - Tryck eller klicka för att visa lagrade skickade data som JSON
* **Starta arbetsflöde** - Konfigurera för att starta ett arbetsflöde med det lagrade innehållet som nyttolast när formulär skickas

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

* Använd dialogrutan Markering för att välja en resurs i AEM.
* Om tacksidan inte finns i AEM anger du den absoluta URL:en. Icke-absoluta URL:er tolkas i förhållande till AEM.
* Lämna tomt om du vill visa formuläret igen när det har skickats.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera de tillåtna komponenterna och deras mappningar för behållaren som liknar designdialogrutan för standardlayoutbehållaren [i mallredigeraren](https://helpx.adobe.com/se/experience-manager/6-4/sites/authoring/using/templates.html#main-pars_title_1754153843).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Form Container-komponenten [finns på GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/container/v1/container).

Hela kärnkomponentprojektet kan hämtas från GitHub.

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).
