---
title: Komponent för formuläralternativ
description: Alternativkomponenten Core Component Form gör att du kan välja bland fördefinierade alternativ i olika format.
translation-type: tm+mt
source-git-commit: 4813748bcfa83ce7c73e81d4e4d445ecc8215d26
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 1%

---


# Formuläralternativkomponent {#form-options-component}

Alternativkomponenten Core Component Form gör att du kan välja bland fördefinierade alternativ i olika format.

## Användning {#usage}

Komponenten Core Component Form Options gör det möjligt att skicka in olika typer av alternativ som presenteras på många olika sätt och är avsedd att användas tillsammans med [formulärbehållarkomponenten](form-container.md).

Presentationen av alternativ, etiketter och enskilda alternativ kan definieras av innehållsredigeraren i [konfigurationsdialogrutan](#configure-dialog).

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Form Options Component är v2, som introducerades i version 2.0.0 av Core Components i januari 2018 och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | Kompatibel | Kompatibel | Kompatibel |
| [v1](/help/components/v1/form-options-v1.md) | Kompatibel | Kompatibel | - |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempelkomponentutdata {#sample-component-output}

Om du vill visa komponenterna för formuläralternativ, samt se exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata, går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_form_options).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Form Options Component [finns på GitHub](https://adobe.com/go/aem_cmp_tech_form_options_v2).

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen till Core Components developer](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera vilken typ av alternativ som ska visas, etiketter och vilka alternativ som är tillgängliga.

![Formuläralternativ Komponentens redigeringsdialogruta](/help/assets/form-options-edit.png)

* **Typer**  - Hur alternativen presenteras
   * **Kryssrutor**
   * **alternativknappar**
   * **Nedrullningsbar meny**
   * **Listruta för flera val**
* **Titel**  - Den rubrik som ska visas som etikett för alternativen
* **Namn**  - Namnet på fältet som skickats med formulärdata
* **Källa**  - Där alternativen definieras
   * **Lokal**  - definierad i komponenten
      * Tryck eller klicka på knappen **Lägg till** för att lägga till ett värde, **Ta bort** för att ta bort ett värde
         * **Värde**  - Värdet som sparas när det alternativet väljs när formuläret skickas
         * **Text**  - Etiketten för alternativet som visas i formuläret
         * **Aktiv**  - Alternativet markeras som markerat när formuläret läses in
         * **Inaktiverad**  - Alternativet kan inte markeras men visas ändå
   * **Lista**  - En statisk lista som definieras någon annanstans i AEM används för alternativen
      * **Lista**  - Sökvägen till den statiska listan i AEM
         * Använd knappen Bläddra för att hitta listresursen
   * **Datakälla**  - En datakälla används för alternativen
      * **Datakälla**  - datakällans resurstyp
* **Hjälpmeddelande**  - Ett tips för användaren om vad som kan anges i fältet
* **ID**  - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i  [datalagret](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

## Designdialog {#design-dialog}

### Fliken Format {#styles-tab}

Komponenten Form Options stöder AEM [Style System](/help/get-started/authoring.md#component-styling).
