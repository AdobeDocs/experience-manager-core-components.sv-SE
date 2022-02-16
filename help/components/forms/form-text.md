---
title: Formulärtextkomponent
description: Med komponenten Core Component Form Text kan du skriva in formulärtext.
role: Architect, Developer, Admin, User
exl-id: e8fa3881-51fb-4726-9654-8f93acfb7464
source-git-commit: 9767a3a10cb9a77f385edc0ac3fb00096c0087af
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 2%

---

# Formulärtextkomponent{#form-text-component}

Med komponenten Core Component Form Text kan du skriva in formulärtext.

## Användning {#usage}

Komponenten Form Text gör det möjligt att skicka olika typer av text och är avsedd att användas tillsammans med [formulärbehållarkomponent](form-container.md). Typen av textvalidering, etiketter och hjälpmeddelanden kan definieras av innehållsredigeraren i [konfigurera dialogruta](#configure-dialog).

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Form Text Component är v2, som introducerades i version 2.0.0 av Core Components i januari 2018 och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | Kompatibel med<br>[version 2.17.4](/help/versions.md) och tidigare | Kompatibel | Kompatibel |
| [v1](/help/components/v1/form-text-v1.md) | Kompatibel | Kompatibel | - |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Huvudkomponentversioner](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill se både Form Text Component och exempel på dess konfigurationsalternativ samt HTML och JSON-utdata går du till [Komponentbibliotek](https://adobe.com/go/aem_cmp_library_form_text).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Form Text Component [finns på GitHub](https://adobe.com/go/aem_cmp_tech_form_text_v2).

Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera vilken typ av text som ska anges samt standardvärden och etiketter.

### Fliken Egenskaper {#properties-tab}

![Fliken Egenskaper](/help/assets/form-text-edit-properties.png)

* **Begränsning** - Den typ av text som ska anges och valideras mot
   * **Text**
   * **Textområde**
   * **E-post**
   * **Tel**
   * **Date**
   * **Siffra**
   * **Lösenord**
* **Textrader** - Antal rader som ska visas i textområdet (visas endast när **Begränsning** är inställd på **Textområde**)
* **Etikett** - Etiketten som ska visas för fältet
* **Dölj etiketten som visas** - Behövs om etiketten endast krävs för hjälpmedelsändamål och inte ger någon ytterligare visuell information om fältet
* **Elementnamn** - Namnet på fältet som skickas med formulärdata
* **Värde** - Standardvärde som är förifyllt i fältet
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [Datalager](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

### Fliken Om {#about-tab}

![Fliken Om](/help/assets/form-text-edit-about.png)

* **Hjälpmeddelande** - Ett tips till användaren om vad som kan anges i fältet
* **Visa hjälpmeddelande som platshållare** - Visa hjälpmeddelandet i formulärindata när det är tomt och inte i fokus

### Fliken Begränsningar {#constraints-tab}

![Fliken Begränsningar](/help/assets/form-text-edit-constraints.png)

* **Begränsningsmeddelande**
   * Meddelande som visas som verktygstips när formuläret skickas om värdet inte validerar vald typ
   * Visas inte för **Text** och **Textområde** begränsningstyper
* **Obligatoriskt** - Om det här alternativet är markerat måste användaren fylla i ett värde innan formuläret skickas
   * **Nödvändigt meddelande** - Meddelande visas som ett verktygstips om fältet lämnas tomt
* **Gör skrivskyddad** - Om du väljer det här alternativet kan användaren inte ändra fältets värde

## Designdialogruta {#design-dialog}

### Fliken Format {#styles-tab}

Komponenten Form Text har stöd för AEM [Formatsystem](/help/get-started/authoring.md#component-styling).
