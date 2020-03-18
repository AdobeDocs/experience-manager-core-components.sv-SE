---
title: Formulärtextkomponent
description: Med komponenten Core Component Form Text kan du skriva in formulärtext.
translation-type: tm+mt
source-git-commit: 95c0621f5423bfa515fe5e8b693e127ea56b4ae0

---


# Formulärtextkomponent{#form-text-component}

Med komponenten Core Component Form Text kan du skriva in formulärtext.

## Användning {#usage}

Komponenten Form Text gör det möjligt att skicka olika typer av text och är avsedd att användas tillsammans med [formulärbehållarkomponenten](form-container.md). Typen av textvalidering, etiketter och hjälpmeddelanden kan definieras av innehållsredigeraren i [konfigurationsdialogrutan](#configure-dialog).

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Form Text Component är v2, som introducerades i version 2.0.0 av Core Components i januari 2018 och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponentversionerna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |--- |---|
| v2 | Kompatibel | Kompatibel | Kompatibel | Kompatibel |
| [v1](/help/components/v1/form-text-v1.md) | Kompatibel | Kompatibel | Kompatibel | - |

Mer information om Core Component-versioner och -versioner finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill se både Form Text Component (Formulärtextkomponent) och exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_form_text).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Form Text Component [finns på GitHub](https://adobe.com/go/aem_cmp_tech_form_text_v2).

Mer information om hur du utvecklar kärnkomponenter finns i dokumentationen till [Core Components Developer](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera vilken typ av text som ska matas in samt standardvärden och etiketter.

### Huvudflik {#main-tab}

![](/help/assets/chlimage_1-23.png)

* **Begränsning** Den typ av text som ska anges och valideras mot
   * **Text**
   * **Textområde**
   * **E-post**
   * **Tel**
   * **Date**
   * **Siffra**
   * **Lösenord**
* **Textrader** Antal rader som ska visas i textområdet (visas bara när **Begränsning** är inställt på **Textområde**)
* **Etikett** Den etikett som ska visas för fältet
* **Dölj etiketten så att den inte visas** Needed om etiketten endast krävs för hjälpmedelsändamål och inte ger någon ytterligare visuell information om fältet
* **Elementnamn** Namnet på fältet som skickas med formulärdata
* **Värde** Standardvärde som är förifyllt i fältet

### Fliken Om {#about-tab}

![](/help/assets/chlimage_1-24.png)

* **Hjälpmeddelande** Ett tips till användaren om vad som kan anges i fältet
* **Visa hjälpmeddelandet som platshållare** Om du vill visa hjälpmeddelandet i formulärindata när det är tomt och inte fokuserat

### Fliken Begränsningar {#constraints-tab}

![](/help/assets/chlimage_1-25.png)

* **Begränsningsmeddelande**
   * Meddelande som visas som verktygstips när formuläret skickas om värdet inte validerar vald typ
   * Visas inte för begränsningstyperna **Text** och **Textområde**
* **Obligatoriskt** Om det här alternativet är markerat måste användaren fylla i ett värde innan formuläret skickas
* **Gör skrivskyddad** Om du väljer det här alternativet kan användaren inte ändra fältets värde

## Designdialogruta {#design-dialog}

Det finns ingen designdialogruta för komponenten Formulärtext.
