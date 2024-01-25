---
title: Front-end-utveckling med AEM Project Archetype
description: Läs mer om AEM Project Archetypes valfria, dedikerade frontendkonstruktionsmekanism som bygger på WebPack.
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 99132b49-bd06-4ac2-9348-12c0dfdfe8b2
source-git-commit: bd92a5d1884056ca7b44ea28e5817d8bde10a4d9
workflow-type: tm+mt
source-wordcount: '654'
ht-degree: 0%

---


# Front-end-utveckling med AEM Project Archetype {#front-end}

AEM Project Archetype innehåller en dedikerad front-end-konstruktionsmekanism som bygger på WebPack som tillval. Modulen ui.front blir alltså den centrala platsen för alla projektets frontresurser, inklusive JavaScript- och CSS-filer. För att till fullo kunna utnyttja denna användbara och flexibla funktion är det viktigt att förstå hur frontendutvecklingen passar in i ett AEM projekt.

Det här dokumentet fokuserar på allmänna användningsmönster för frontendmodulen och vad det gör för dig. Detaljerade byggalternativ och tekniska anvisningar finns i dokumentationen i arkivtypens GitHub-databas.

>[!TIP]
>
>Den senaste AEM Project Archetype och tillhörande teknisk dokumentation [finns på GitHub.](https://github.com/adobe/aem-project-archetype)

## AEM Front-End och Back-End Development {#front-end-back-end}

I betydligt förenklade termer kan man tänka sig att AEM projekt består av två separata men sammanhörande delar:

* Bakgrundsutveckling som driver logiken i AEM och skapar Java-bibliotek, OSGi-tjänster osv.
* Framtidsutveckling som driver presentationen och beteendet på den slutliga webbplatsen och skapar JavaScript- och CSS-bibliotek

Eftersom dessa två utvecklingsprocesser är inriktade på olika delar av projektet kan både back-end och front-end-utveckling ske parallellt.

![arbetsflödesdiagram för frontend](/help/assets/front-end-flow.png)

Alla resulterande projekt måste dock använda resultatet från båda dessa utvecklingssatsningar, dvs. både back end och front end.

## Bestämma markeringen {#determining-markup}

Oavsett vilket utvecklingsarbetsflöde ni bestämmer er för att implementera för projektet måste backend-utvecklarna och front end-utvecklarna först komma överens om koden. AEM definierar vanligtvis koden, som tillhandahålls av kärnkomponenterna. [Detta kan dock anpassas vid behov.](/help/developing/customizing.md#customizing-the-markup)

## Möjliga arbetsflöden för utveckling i gränssnittet {#possible-workflows}

Framtidsmodulen är ett användbart och mycket flexibelt verktyg, men har ingen särskild åsikt om hur den ska användas. Följande är två exempel på *möjligt* -användning, men dina individuella projektbehov kan påverka andra användningsmodeller.

### Använda Statisk utvecklingsserver för Webpack {#using-webpack}

Med Webpack kan du utforma och utveckla baserat på statiska utdata från AEM webbsidor i modulen ui.front.

1. Förhandsgranska sida i AEM med förhandsgranskningsläge eller skicka i `wcmmode=disabled` i URL:en
1. Visa sidkällan och spara som statisk HTML i modulen ui.front
1. [Starta webbpaket](#webpack-dev-server) och börja formatera och generera nödvändigt JavaScript och CSS
1. Kör `npm run dev` för att generera klientlibs

I det här flödet kan en AEM utföra steg ett och två och skicka det statiska HTML vidare till den frontendutvecklare som utvecklar baserat på utdata från AEM HTML.

>[!TIP]
>
>Man kan också utnyttja [Komponentbibliotek](https://adobe.com/go/aem_cmp_library) för att hämta exempel på markeringsutdata för varje komponent för att fungera på komponentnivå i stället för på sidnivå.

### Använda Storybook {#using-storybook}

Använda [Storybook](https://storybook.js.org) kan du utföra mer atomiska framtagningsfunktioner. Även om Storybook inte ingår i AEM Project Archetype kan du installera den och lagra dina Storybook-artefakter i modulen ui.front. När de är klara för testning i AEM kan de distribueras som klientlibs genom att köra `npm run dev`.

>[!NOTE]
>
>[Storybook](https://storybook.js.org) ingår inte i AEM Project Archetype. Om du väljer att använda den måste du installera den separat.

## Översikt över Clientlibs {#clientlibs}

Framtöjningsmodulen är tillgänglig med en [AEM clientlib.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html). När NPM-byggskriptet körs skapas programmet och `aem-clientlib-generator` paketet tar fram det genererade materialet och omvandlar det till ett sådant clientlib.

En clientlib består av följande filer och kataloger:

* `css/`: CSS-filer som kan begäras i HTML
* `css.txt`: AEM ordning och namn på filer i `css/` så att de kan sammanfogas
* `js/`: JavaScript-filer som kan begäras i HTML
* `js.txt` AEM ordning och namn på filer i `js/` så att de kan sammanfogas
* `resources/`: Källkartor, kodsegment som inte är ingångspunkter (till följd av koddelning), statiska resurser (t.ex. ikoner) osv.

>[!TIP]
>
>Läs mer om hur AEM hanterar klientlibs i [AEM](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html) om hur du inkluderar dem i [Dokumentation för kärnkomponenter.](/help/developing/including-clientlibs.md)
