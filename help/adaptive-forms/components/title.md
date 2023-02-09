---
title: Adaptiv Forms Core-komponent - titel
description: Använda eller anpassa den adaptiva huvudkomponenten i Forms Title.
role: Architect, Developer, Admin, User
source-git-commit: 0e4fb8454b7ef84eb5b1b73b01c982a2f9c12381
workflow-type: tm+mt
source-wordcount: '836'
ht-degree: 1%

---


# Titel {#title-input-adaptive-forms-core-component}

I ett adaptivt formulär avser en&quot;titel&quot; texten som visas högst upp i formuläret, vanligtvis under rubriken. Titeln anges med komponenten Title. Den här komponenten kan läggas till i formulärlayouten och dess text kan redigeras för att passa formulärets syfte eller ämne. Titeln fungerar som en etikett eller en kort beskrivning av formuläret för användaren, vilket gör det lättare att skilja formuläret från andra.

**Exempel**

![](/help/adaptive-forms/assets/title.png)

## Användning {#reasons-to-use-title-in-an-adaptive-form}

Det finns flera skäl till att det är bra att använda en titel i ett formulär:

* **Klarhet**: En titel identifierar tydligt formulärets syfte, vilket hjälper användarna att förstå vilken information de behöver ange.

* **Organisation**: En titel kan hjälpa till att organisera formulären efter ämne eller syfte, vilket gör det enklare för användarna att hitta det formulär de behöver.

* **Tillgänglighet**: En titel är ett nyckelelement för användare med tillgänglighetsbehov, eftersom den läses upp högt av skärmläsare, vilket hjälper användarna att förstå formulärets sammanhang.

* **Varumärke**: En titel kan också användas för att visa ett företags eller en organisations namn, vilket gör det lättare att skapa en känsla av förtroende och kunskap om användaren.

* **Navigering**: En titel kan också vara användbar för att navigera i formuläret, särskilt om formuläret är långt eller komplext.

* **Sökmotoroptimering (SEO)**: Att ha en titel på formuläret är också till hjälp i SEO, eftersom sökmotorer använder titeln för att avgöra hur relevant en webbsida är för en sökfråga.

På det hela taget är titeln på ett formulär en viktig aspekt av användarupplevelsen och bör användas för att skapa en tydlig och koncis etikett för formuläret som hjälper användarna att förstå formulärets sammanhang och syfte.

## Version och kompatibilitet {#version-and-compatibility}

Den adaptiva huvudkomponenten i Forms Title lanserades i februari 2023 som en del av kärnkomponenterna 2.0.4. Här är en tabell med alla versioner som stöds, AEM kompatibilitet och länkar till motsvarande dokumentation:

| Komponentversion | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Kompatibel med<br>[version 2.0.4](/help/versions.md) och senare | Kompatibel | Kompatibel |

Information om versioner och versioner av kärnkomponenter finns i [Huvudkomponentversioner](/help/versions.md) -dokument.

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->


## Teknisk information {#technical-details}

Den senaste informationen om den adaptiva huvudkomponenten i Forms Title finns i den tekniska dokumentationen om [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/title/v1/title). Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Du kan enkelt anpassa din titelupplevelse för besökare med dialogrutan Konfigurera. Du kan också enkelt definiera rubrikalternativ för en smidig användarupplevelse.

![Fliken Grundläggande](/help/adaptive-forms/assets/title_properties.png)

I redigeringsdialogrutan kan innehållsförfattaren definiera titeltexten och välja rubriknivå.

* **Titel** - Med dess titel kan du enkelt identifiera en komponent i ett formulär. Som standard visas titeln ovanpå komponenten. Om du inte lägger till en titel visas komponentens namn i stället för titeltexten.
* **Typ /Storlek** - Definierar rubriknivån för titeln.
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i datalagret.
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

## Designdialogruta {#design-dialog}

Designdialogrutan används för att definiera och hantera CSS-format för komponenten Date-Picker.

### Titel

På fliken Titel kan mallskapare ange standardrubrikelement och tillåtna rubrikelement för HTML för formulärförfattare:

![Titelflik i designdialogrutan](/help/assets/accordion-design-properties.png)

* **Tillåtna rubrikelement**: En lista med flera alternativ som gör att mallskaparen kan välja vilka rubrikelement som kan användas som rubrik av formulärförfattaren.

* **Standardrubrikelement**: En nedrullningsbar lista som anger standardrubrikelementet för komponenten Title.


### Fliken Format {#styles-tab}

Designdialogrutan används för att definiera och hantera CSS-format för en komponent. Core-komponenten för datumväljaren i den adaptiva Forms stöder AEM [Formatsystem](/help/get-started/authoring.md#component-styling).

**CSS-standardklasser**: Du kan ange en standard-CSS-klass för den adaptiva Forms Date-picker Core Component.

**Tillåtna format**: Du kan definiera format genom att ange ett namn och den CSS-klass som representerar formatet. Du kan till exempel skapa ett format med namnet&quot;bold text&quot; och ge CSS-klassen&quot;font-weight: fet&quot;. Du kan använda eller tillämpa dessa format på ett adaptivt formulär i den adaptiva Forms-redigeraren. Om du vill använda ett format väljer du den komponent du vill använda formatet på i Adaptiv Forms-redigerare, navigerar till egenskapsdialogrutan och väljer önskat format i dialogrutan **Stilar** nedrullningsbar lista. Om du behöver uppdatera eller ändra formaten går du tillbaka till designdialogrutan, uppdaterar formaten på formatfliken och sparar ändringarna.

### Fliken Format {#format-tab}

På fliken Format kan du ange standardformat och anpassade datumformat.

