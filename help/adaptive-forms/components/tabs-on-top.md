---
title: Adaptiv Forms Core-komponent - flikar överst
description: Använda eller anpassa de adaptiva Forms-flikarna i den främsta kärnkomponenten.
role: Architect, Developer, Admin, User
source-git-commit: d2a6108f17f6e0c6b91bec84893d64a8bd48effd
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 1%

---


# Tabbar överst {#tabs-on-top-adaptive-forms-core-component}

En tabb-på-plats-layout i ett adaptivt formulär är ett sätt att ordna och gruppera relaterade fält och avsnitt i ett formulär på olika flikar. Varje flik representeras av en fliketikett, som vanligtvis finns högst upp i formuläret, och som innehåller en viss uppsättning formulärfält och avsnitt. Med den här layouten kan användarna enkelt navigera och komma åt olika delar av formuläret, vilket gör det mer användarvänligt och mindre överväldigande. Det används vanligtvis när formuläret innehåller många fält och avsnitt, och det är nödvändigt att dela upp dem i mindre, hanterbara segment. Flikar kan också förbättra tillgängligheten genom att användarna kan navigera i formuläret med kortkommandon, vilket gör det enklare för användare med funktionshinder att komma åt formuläret.

**Exempel**

![](/help/adaptive-forms/assets/tabs.png)

## Användning {#reasons-to-use-tab-on-the-top-layout}

Det finns flera skäl att använda tabbar i den översta layouten i ett adaptivt formulär:

* **Organisation**: Du kan använda flikar för att ordna olika avsnitt i ett formulär i olika kategorier, vilket gör det enklare för användarna att navigera och hitta den information de behöver.

* **Utrymmesbevarande**: Med hjälp av flikar kan du spara utrymme på en sida genom att bara ett avsnitt i formuläret kan visas åt gången.

* **Förbättrad användarupplevelse**: Flikar kan förbättra användarupplevelsen genom att göra formuläret mer visuellt tilltalande och lättare att använda.

* **Mobilvänligt**: Flikar gör formulär mer mobilvänliga genom att minska bläddringen och gör det enkelt att växla mellan fält.

Kort och gott: Med flikarna blir formulären mer välorganiserade, utrymmeseffektiva, användarvänliga och tillgängliga.

## Version och kompatibilitet {#version-and-compatibility}

Den adaptiva Forms Accordion Core-komponenten släpptes i februari 2023 som en del av Core Components 2.0.4 för Cloud Service och Core Components 1.1.12 för AEM 6.5.16.0 Forms eller senare. Här är en tabell med alla versioner som stöds, AEM kompatibilitet och länkar till motsvarande dokumentation:

| Komponentversion | AEM as a Cloud Service | AEM 6.5.16.0 Forms eller senare |
|---|---|---|
| v1 | Kompatibel med<br>[version 2.0.4](/help/adaptive-forms/version.md) och senare | Kompatibel med<br>[version 1.1.12](/help/adaptive-forms/version.md) och senare men mindre än 2.0.0. |

Information om versioner och versioner av kärnkomponenter finns i [Huvudkomponentversioner](/help/adaptive-forms/version.md) -dokument.

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Teknisk information {#technical-details}

Få den senaste informationen om de adaptiva Forms-flikarna i Top Core-komponenten i den tekniska dokumentationen om [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/tabsontop/v1/tabsontop). Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Med dialogrutan Konfigurera kan du enkelt anpassa flikarna efter besökarna. Du kan också enkelt definiera flikar för de vanligaste alternativen för en smidig användarupplevelse.

## Designdialogruta {#design-dialog}
