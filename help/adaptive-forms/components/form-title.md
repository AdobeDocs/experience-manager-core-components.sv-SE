---
title: Adaptiv Forms Core-komponent - titel
description: Använda eller anpassa den adaptiva huvudkomponenten i Forms Title.
role: Architect, Developer, Admin, User
exl-id: 33eac885-8d66-4a5c-9a32-0ba11e6de293
source-git-commit: 6725784bd4c94d433c91d6bd65d14d03cbefd954
workflow-type: tm+mt
source-wordcount: '864'
ht-degree: 0%

---


# Formulärtitelkomponent{#title-input-adaptive-forms-core-component}

I ett adaptivt formulär avser en&quot;titel&quot; texten som visas högst upp i formuläret, vanligtvis under rubriken. Titeln anges med komponenten Title. Den här komponenten kan läggas till i formulärlayouten och dess text kan redigeras för att passa formulärets syfte eller ämne. Titeln fungerar som en etikett eller en kort beskrivning av formuläret för användaren, vilket gör det lättare att skilja formuläret från andra.

{{traditional-aem}}

**Exempel**

![exempel på titel](/help/adaptive-forms/assets/title.png)

## Användning {#reasons-to-use-title-in-an-adaptive-form}

Det finns flera skäl till att det är bra att använda en titel i ett formulär:

- **Klarhet**: En titel identifierar tydligt formulärets syfte, vilket hjälper användarna att förstå vilken information de behöver ange.

- **Organisation**: En titel kan hjälpa dig att ordna formulär efter ämne eller syfte, vilket gör det enklare för användarna att hitta det formulär de behöver.

- **Hjälpmedel**: En titel är ett nyckelelement för användare med hjälpmedelsbehov, eftersom den läses upp högt av skärmläsare, vilket hjälper användarna att förstå formulärets sammanhang.

- **Varumärkning**: En titel kan också användas för att visa ett företags eller en organisations namn, vilket gör att användaren kan känna sig trygg och bekant.

- **Navigering**: En titel kan också vara användbar för att navigera i formuläret, särskilt om formuläret är långt eller komplext.

- **Sökmotoroptimering (SEO)**: Att ha en rubrik i formuläret är också till hjälp i SEO, eftersom sökmotorer använder titeln för att avgöra hur relevant en webbsida är för en sökfråga.

På det hela taget är titeln på ett formulär en viktig aspekt av användarupplevelsen och bör användas för att skapa en tydlig och koncis etikett för formuläret som hjälper användarna att förstå formulärets sammanhang och syfte.

## Version och kompatibilitet {#version-and-compatibility}

Den adaptiva huvudkomponenten i Forms Title lanserades i februari 2023 som en del av Core Components 2.0.4 för Cloud Service och Core Components 1.1.12 för AEM 6.5.16.0 Forms eller senare. Här är en tabell som visar alla versioner som stöds, kompatibiliteten med AEM och länkar till motsvarande dokumentation:

| Komponentversion | AEM as a Cloud Service | AEM 6.5.16.0 Forms eller senare |
|---|---|---|
| v1 | Kompatibel med <br>[version 2.0.4](/help/adaptive-forms/version.md) och senare | Kompatibel med <br>[version 1.1.12](/help/adaptive-forms/version.md) och senare, men mindre än 2.0.0. |

Information om versioner och versioner av kärnkomponenter finns i dokumentet [Core Components Versions](/help/adaptive-forms/version.md) .

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->


## Teknisk information {#technical-details}

Hämta den senaste informationen om den adaptiva huvudkomponenten i Forms Title i den tekniska dokumentationen för [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/title/v1/title). Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Du kan enkelt anpassa din titelupplevelse för besökare med dialogrutan Konfigurera. Du kan också enkelt definiera titelalternativ för en smidig användarupplevelse.

![Fliken Grundläggande](/help/adaptive-forms/assets/title_properties.png)

I redigeringsdialogrutan kan innehållsförfattaren definiera titeltexten och välja rubriknivå.

- **Titel** - Med titeln kan du enkelt identifiera en komponent i ett formulär. Som standard visas titeln ovanpå komponenten. Om du inte lägger till en titel visas komponentens namn i stället för rubriktexten.
- **Typ /Storlek** - Definierar rubriknivån för titeln.
- **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i datalagret.
   - Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   - Om ett ID anges är det författarens ansvar att se till att det är unikt.
   - Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

## Designdialogruta {#design-dialog}

Designfliken används för att definiera och hantera CSS-format för formulärets titelkomponent.

### Titel

På fliken Titel kan mallskapare ange standardrubrikelement och tillåtna rubrikelement för HTML för formulärförfattare:

![Dialogrutans titelflik](/help/adaptive-forms/assets/title_heading.png)

- **Tillåtna rubrikelement**: En lista med flera alternativ som gör att mallskaparen kan välja vilka rubrikelement som kan användas som rubrikförfattare för rubriker.

- **Standardrubrikelement**: En nedrullningsbar lista som anger standardrubrikelementet för rubrikkomponenten.

### Fliken Format {#styles-tab}

Fliken används för att definiera och hantera CSS-format för en komponent. Core-komponenten för datumväljaren i den adaptiva Forms stöder AEM [Style System](/help/get-started/authoring.md#component-styling).

![Dialogrutans titelflik](/help/adaptive-forms/assets/title_styles.png)

- **Standardklasser för CSS**: Du kan ange en standardklass för CSS för den adaptiva kärnkomponenten för Forms Title.

- **Tillåtna format**: Du kan definiera format genom att ange ett namn och den CSS-klass som representerar formatet. Du kan till exempel skapa ett format med namnet&quot;bold text&quot; och ge CSS-klassen&quot;font-weight: bold&quot;. Du kan använda eller tillämpa dessa format på ett adaptivt formulär i en anpassad Forms-redigerare. Om du vill använda ett format väljer du den komponent du vill använda formatet på i Adaptiv Forms-redigerare, navigerar till egenskapsdialogrutan och väljer önskat format i listrutan **Format**. Om du behöver uppdatera eller ändra formaten går du tillbaka till designdialogrutan, uppdaterar formaten på formatfliken och sparar ändringarna.

### Fliken Format {#format-tab}

På fliken Format kan du ange standardformat och anpassade datumformat.

![Fliken Formatera](/help/adaptive-forms/assets/title_styles.png)

<!--

## Related article {#related-article}

* [Create a standalone Adaptive Form](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)

-->

## Relaterade artiklar {#related-articles}


{{more-like-this}}

## Se även {#see-also}

{{see-also}}