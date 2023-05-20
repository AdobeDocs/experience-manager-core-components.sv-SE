---
title: Komponent för formuläralternativ
description: Alternativkomponenten Core Component Form gör att du kan välja bland fördefinierade alternativ i olika format.
role: Architect, Developer, Admin, User
exl-id: 8a74bd37-9b12-4fa6-bff2-53e337b16251
source-git-commit: 16930ccaa281f9d9c4ddbb890d4222e128557580
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 1%

---

# Komponent för formuläralternativ {#form-options-component}

Komponenten Core Component Form Options gör det möjligt att välja bland fördefinierade alternativ i olika format.

## Användning {#usage}

Komponenten Core Component Form Options gör det möjligt att skicka in olika typer av alternativ som presenteras på många olika sätt och är avsedd att användas tillsammans med [Formulärbehållarkomponent](form-container.md).

Presentationen av alternativ, etiketter och enskilda alternativ kan definieras av innehållsredigeraren i [konfigurera dialogruta](#configure-dialog).

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Form Options Component är v2, som introducerades i version 2.0.0 av Core Components i januari 2018 och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | Kompatibel med<br>[version 2.17.4](/help/versions.md) och tidigare | Kompatibel | Kompatibel |
| [v1](/help/components/v1/form-options-v1.md) | Kompatibel | Kompatibel | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Huvudkomponentversioner](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill se både Form Options-komponenten och exempel på dess konfigurationsalternativ samt HTML och JSON-utdata går du till [Komponentbibliotek](https://adobe.com/go/aem_cmp_library_form_options).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om komponenten Formuläralternativ [finns på GitHub](https://adobe.com/go/aem_cmp_tech_form_options_v2).

Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera vilken typ av alternativ som ska visas, etiketter och vilka alternativ som är tillgängliga.

![Formuläralternativ Komponentens redigeringsdialogruta](/help/assets/form-options-edit.png)

* **Typer** - Hur alternativen presenteras
   * **Kryssrutor**
   * **Alternativknappar**
   * **Nedrullningsbar meny**
   * **Listruta för flera val**
* **Titel** - Den rubrik som ska visas som etikett för alternativen
* **Namn** - Namnet på det fält som har skickats med formulärdata
* **Källa** - Där alternativen är definierade
   * **Lokal** - Definierad i komponenten
      * Tryck eller klicka på **Lägg till** knapp för att lägga till ett värde, **Ta bort** ta bort ett värde
         * **Värde** - Det värde som sparas när det alternativet väljs när formuläret skickas
         * **Text** - Etiketten för alternativet som visas i formuläret
         * **Aktiv** - Alternativet markeras som markerat när formuläret läses in
         * **Handikappade** - Alternativet kan inte markeras men visas ändå
   * **Lista** - En statisk lista som definieras någon annanstans i AEM används för alternativen
      * **Lista** - Sökvägen till den statiska listan i AEM
         * Använd knappen Bläddra för att hitta listresursen
   * **Datakälla** - En datakälla används för alternativen
      * **Datakälla** - Datakällans resurstyp
* **Hjälpmeddelande** - Ett tips till användaren om vad som kan anges i fältet
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [Datalager](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

## Designdialogruta {#design-dialog}

### Fliken Format {#styles-tab}

Komponenten Form Options har stöd för AEM [Formatsystem](/help/get-started/authoring.md#component-styling).
