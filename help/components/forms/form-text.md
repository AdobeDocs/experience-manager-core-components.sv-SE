---
title: Formulärtextkomponent
description: Med komponenten Core Component Form Text kan du skriva in formulärtext.
role: Arkitekt, utvecklare, administratör, affärsansvarig
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 2%

---


# Formulärtextkomponent{#form-text-component}

Med komponenten Core Component Form Text kan du skriva in formulärtext.

## Användning {#usage}

Komponenten Form Text tillåter olika typer av text och är avsedd att användas tillsammans med [formulärbehållarkomponenten](form-container.md). Typen av textvalidering, etiketter och hjälpmeddelanden kan definieras av innehållsredigeraren i [konfigurationsdialogrutan](#configure-dialog).

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Form Text Component är v2, som introducerades i version 2.0.0 av Core Components i januari 2018 och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | Kompatibel | Kompatibel | Kompatibel |
| [v1](/help/components/v1/form-text-v1.md) | Kompatibel | Kompatibel | - |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempelkomponentutdata {#sample-component-output}

Om du vill visa Form Text Component och se exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_form_text).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Form Text Component [finns på GitHub](https://adobe.com/go/aem_cmp_tech_form_text_v2).

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen till Core Components developer](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera vilken typ av text som ska anges samt standardvärden och etiketter.

### Fliken Egenskaper {#properties-tab}

![Fliken Egenskaper](/help/assets/form-text-edit-properties.png)

* **Begränsning**  - Den typ av text som ska anges och valideras mot
   * **Text**
   * **Textområde**
   * **E-post**
   * **Tel**
   * **Date**
   * **Siffra**
   * **Lösenord**
* **Textrader**  - Antal rader som ska visas i textområdet (visas bara när  **** Begränsningar är inställda på  **textområde**)
* **Etikett**  - Den etikett som ska visas för fältet
* **Dölj att etiketten visas** - Behövs om etiketten endast är nödvändig för hjälpmedelsändamål och inte ger någon ytterligare visuell information om fältet
* **Elementnamn**  - Namnet på fältet som skickas med formulärdata
* **Värde**  - Standardvärde som är förifyllt i fältet
* **ID**  - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i  [datalagret](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

### Fliken {#about-tab}

![Fliken Om](/help/assets/form-text-edit-about.png)

* **Hjälpmeddelande**  - Ett tips till användaren om vad som kan anges i fältet
* **Visa hjälpmeddelandet som platshållare**  - Om du vill visa hjälpmeddelandet i formulärinmatningen när den är tom och inte fokuserad

### Fliken Begränsningar {#constraints-tab}

![Fliken Begränsningar](/help/assets/form-text-edit-constraints.png)

* **Begränsningsmeddelande**
   * Meddelande som visas som verktygstips när formuläret skickas om värdet inte validerar vald typ
   * Visas inte för begränsningstyperna **Text** och **Textområde**
* **Obligatoriskt**  - Om det här alternativet är markerat måste användaren fylla i ett värde innan formuläret skickas
   * **Obligatoriskt meddelande**  - Meddelande visas som ett verktygstips om fältet lämnas tomt
* **Gör skrivskyddad** - Om du väljer det här alternativet kan användaren inte ändra fältets värde

## Designdialog {#design-dialog}

### Fliken Format {#styles-tab}

Komponenten Form Text har stöd för AEM [Style System](/help/get-started/authoring.md#component-styling).
