---
title: Front-End-utveckling med AEM Project Archetype
description: Läs om AEM Project Archettypes valfria, dedikerade frontendkonstruktionsmekanism som bygger på WebPack.
feature: Core Components, AEM Project Archetype
role: Developer, Admin
exl-id: 99132b49-bd06-4ac2-9348-12c0dfdfe8b2
source-git-commit: 7ba1374bd64686c2e7ac44398d77fb187ff60949
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 0%

---


# Front-End-utveckling med AEM Project Archetype {#front-end}

AEM Project Archetype innehåller en dedikerad front-end-konstruktionsmekanism som bygger på WebPack som tillval. Modulen ui.front blir därmed den centrala platsen för alla projektets frontresurser, inklusive JavaScript- och CSS-filer. Om du vill utnyttja den här användbara och flexibla funktionen till fullo är det viktigt att du förstår hur frontendutvecklingen passar in i ett AEM-projekt.

Det här dokumentet fokuserar på allmänna användningsmönster för frontendmodulen och vad det gör för dig. Detaljerade byggalternativ och tekniska anvisningar finns i dokumentationen i arkivtypens GitHub-databas.

>[!TIP]
>
>Den senaste AEM Project-arkitekturen och tillhörande tekniska dokumentation [finns på GitHub.](https://github.com/adobe/aem-project-archetype)

## AEM Front-End och Back-End Development {#front-end-back-end}

I betydligt förenklade termer kan man tänka sig att AEM-projekt består av två separata men sammanhörande delar:

* Bakgrundsutveckling som driver logiken i AEM och skapar Java-bibliotek, OSGi-tjänster osv.
* Framtidsutveckling som driver presentationen och beteendet på den slutliga webbplatsen och skapar JavaScript- och CSS-bibliotek

Eftersom dessa två utvecklingsprocesser är inriktade på olika delar av projektet kan både back-end och front-end-utveckling ske parallellt.

![arbetsflödesdiagram för frontdel](/help/assets/front-end-flow.png)

Alla resulterande projekt måste dock använda resultatet från båda dessa utvecklingssatsningar, dvs. både back end och front end.

## Bestämma markeringen {#determining-markup}

Oavsett vilket utvecklingsarbetsflöde ni bestämmer er för att implementera för projektet måste backend-utvecklarna och front end-utvecklarna först komma överens om koden. Vanligtvis definierar AEM markeringen, som tillhandahålls av kärnkomponenterna. [Detta kan dock anpassas om det behövs.](/help/developing/customizing.md#customizing-the-markup)

## Möjliga arbetsflöden för utveckling i gränssnittet {#possible-workflows}

Framtidsmodulen är ett användbart och mycket flexibelt verktyg, men har ingen särskild åsikt om hur den ska användas. Nedan följer två exempel på *möjlig*-användning, men dina individuella projektbehov kan styra andra användningsmodeller.

### Använda Statisk utvecklingsserver för Webpack {#using-webpack}

Med Webpack kan du utforma och utveckla baserat på statiska utdata från AEM webbsidor i modulen ui.front.

1. Förhandsgranska sidan i AEM i förhandsgranskningsläge eller skicka `wcmmode=disabled` i URL:en
1. Visa sidkällan och spara som statisk HTML i modulen ui.front
1. [Starta webbpaketet](#webpack-dev-server) och börja formatera och generera nödvändig JavaScript och CSS
1. Kör `npm run dev` för att generera klientlibs

I det här flödet kan en AEM-utvecklare utföra steg ett och två och skicka den statiska HTML vidare till den frontendutvecklare som utvecklar baserat på AEM HTML-utdata.

>[!TIP]
>
>Du kan också använda [komponentbiblioteket](https://adobe.com/go/aem_cmp_library) för att hämta exempel på kodutdata för varje komponent för att arbeta på komponentnivå i stället för på sidnivå.

### Använda Storybook {#using-storybook}

Med [Storybook](https://storybook.js.org) kan du utföra mer atomiska framend-utvecklingsåtgärder. Även om Storybook inte ingår i AEM Project Archetype kan du installera den och lagra dina Storybook-artefakter i modulen ui.front. När de är klara för testning i AEM kan de distribueras som klientlibs genom att köra `npm run dev`.

>[!NOTE]
>
>[Storybook](https://storybook.js.org) ingår inte i AEM Project Archetype. Om du väljer att använda den måste du installera den separat.

## Översikt över Clientlibs {#clientlibs}

Framtend-modulen är tillgänglig med ett [AEM clientlib.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html). När NPM-byggskriptet körs skapas appen och `aem-clientlib-generator` -paketet tar det resulterande build-resultatet och omvandlar det till ett sådant clientlib.

En clientlib består av följande filer och kataloger:

* `css/`: CSS-filer som kan begäras i HTML
* `css.txt`: Anger filernas ordning och namn i `css/` till AEM så att de kan sammanfogas
* `js/`: JavaScript-filer som kan begäras i HTML
* `js.txt` anger filernas ordning och namn i `js/` för AEM så att de kan sammanfogas
* `resources/`: Source-kartor, kodsegment som inte är ingångspunkter (till följd av koddelning), statiska resurser (till exempel ikoner) osv.

>[!TIP]
>
>Läs mer om hur AEM hanterar klientlibs i [AEM-utvecklingsdokumentationen](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html) om hur du inkluderar dem i [dokumentationen för kärnkomponenter.](/help/developing/including-clientlibs.md)
