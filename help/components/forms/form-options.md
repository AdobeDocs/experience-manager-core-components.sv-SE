---
title: Komponent för formuläralternativ
description: Alternativkomponenten Core Component Form gör att du kan välja bland fördefinierade alternativ i olika format.
translation-type: tm+mt
source-git-commit: 95c0621f5423bfa515fe5e8b693e127ea56b4ae0

---


# Komponent för formuläralternativ {#form-options-component}

Komponenten Core Component Form Options gör det möjligt att välja bland fördefinierade alternativ i olika format.

## Användning {#usage}

Komponenten Core Component Form Options gör det möjligt att skicka in olika typer av alternativ som presenteras på många olika sätt och är avsedd att användas tillsammans med komponenten [](form-container.md)Form Container.

Presentationen av alternativ, etiketter och enskilda alternativ kan definieras av innehållsredigeraren i [konfigurationsdialogrutan](#configure-dialog).

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Form Options Component är v2, som introducerades i version 2.0.0 av Core Components i januari 2018 och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponentversionerna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |--- |---|
| v2 | Kompatibel | Kompatibel | Kompatibel | Kompatibel |
| [v1](/help/components/v1/form-options-v1.md) | Kompatibel | Kompatibel | Kompatibel | - |

Mer information om Core Component-versioner och -versioner finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill visa komponenterna för formuläralternativ, samt se exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata, går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_form_options).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Form Options-komponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_form_options_v2).

Mer information om hur du utvecklar kärnkomponenter finns i dokumentationen till [Core Components Developer](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera vilken typ av alternativ som ska visas, etiketter och vilka alternativ som är tillgängliga.

![](/help/assets/screen_shot_2018-01-12at113153.png)

* **Typer** - Hur alternativen visas
   * **Kryssrutor**
   * **alternativknappar**
   * **Nedrullningsbar meny**
   * **Listruta för flera val**
* **Titel** Den rubrik som ska visas som etikett för alternativen
* **Namn** Namnet på fältet som skickats med formulärdata
* **Källa** där alternativen definieras
   * **Lokal** definierad i komponenten
      * Tryck eller klicka på knappen **Lägg till** för att lägga till ett värde, **Ta bort** för att ta bort ett värde
      * **Värde** Det värde som sparas när det alternativet väljs när formuläret skickas
      * **Text** Etiketten för alternativet som visas i formuläret
      * **Aktiv** Alternativet markeras som markerat när formuläret läses in
      * **Inaktiverat** Alternativet kan inte markeras men visas ändå
      * **Lista** En statisk lista som definieras någon annanstans i AEM används för alternativen
         * **Lista** sökvägen till den statiska listan i AEM
            * Använd knappen Bläddra för att hitta listresursen
      * **Datakälla** En datakälla används för alternativen
         * **Datakällans** resurstyp för datakällan
* **Hjälpmeddelande** Ett tips till användaren om vad som kan anges i fältet

## Designdialogruta {#design-dialog}

### Fliken Format {#styles-tab}

Komponenten Form Options har stöd för AEM [Style System](/help/get-started/authoring.md#component-styling).
