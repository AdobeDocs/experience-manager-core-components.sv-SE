---
title: AEM Project Archettype
description: Läs om den AEM Project Archetype som fungerar som mall för AEM program.
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 58994726-9b65-4035-9d45-60b745d577bb
source-git-commit: 8940285f4c5e5870b6a135dac674f06e4c1d8b5a
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 0%

---


# AEM Project Archettype {#aem-project-archetype}

AEM Project Archetype är en Maven-mall som skapar ett minimalt, metodbaserat Adobe Experience Manager-projekt (AEM) som utgångspunkt för webbplatsen. Den här dokumentationen ger en översikt över fördelarna med arketypen och allmän användning. Detaljerade tekniska instruktioner och dokumentation finns i arkivtypsdatabasen för GitHub.

>[!TIP]
>
>Den senaste AEM Project Archetype och tillhörande tekniska dokumentationen [finns på GitHub.](https://github.com/adobe/aem-project-archetype)

## Varför använda Arketype {#why-use-the-archetype}

Med den AEM Project Archetype-tekniken kan du skapa ett AEM projekt med bästa praxis och bara några få tangenttryckningar. Genom att använda arkivtypen kommer alla delar redan att vara på plats, så även om det resulterande projektet är minimalt, implementerar det redan alla [nyckelfunktioner](/help/developing/archetype/using.md#what-you-get) i AEM så att allt du behöver göra är att bygga vidare och utöka.

Det finns förstås många element som går in i [ett lyckat AEM](/help/developing/success.md), men att använda AEM Project Archetype är en bra grund och rekommenderas starkt för alla AEM projekt.

## Funktioner {#features}

* **Bästa praxis:** Bootstrap din webbplats med alla Adobe senaste rekommenderade praxis.
* **Lågkod:** Redigera dina mallar, skapa innehåll, distribuera CSS och webbplatsen är klar för publicering.
* **Cloud-Ready:** Om du vill kan du använda [AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html?lang=sv-SE) för att publicera på några dagar och förenkla skalbarhet och underhåll.
* **Dispatcher:** Ett projekt är endast färdigt med en [Dispatcher-konfiguration](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/dispatcher.html?lang=sv-SE) som garanterar hastighet och säkerhet.
* **Multi-Site:** Om det behövs genererar arkivtypen innehållsstrukturen för en [flerspråkig och flerregionskonfiguration](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/msm/overview.html?lang=sv-SE).
* **Kärnkomponenter:** Författare kan skapa nästan vilken layout som helst med vår mångsidiga [uppsättning standardiserade komponenter](/help/introduction.md).
* **Redigerbara mallar:** Sammanställ praktiskt taget alla [mallar utan kod](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html?lang=sv-SE) och definiera vad författarna får redigera.
* **Responsiv layout:** På mallar eller enskilda sidor definierar [hur elementen flödar om](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/get-started/localization.html?lang=sv-SE) för de definierade brytpunkterna.
* **Sidhuvud och sidfot:** Sammanställ och lokalisera dem utan kod med hjälp av komponenternas [lokaliseringsfunktioner](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/get-started/localization.html?lang=sv-SE).
* **Style System:** Undvik att bygga anpassade komponenter genom att tillåta författare att [använda olika format](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/project-archetype/style-system.html?lang=sv-SE) på dem.
* **Front-End Build:** Front-end-utvecklare kan [skapa AEM sidor och bygga klientbibliotek](front-end.md) med Webpack, TypeScript och SASS.
* **WebApp-Ready:** För webbplatser som använder React eller Angular använder du [SPA SDK](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/hybrid/developing.html?lang=sv-SE) för att behålla [kontextredigeringen av appen](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html?lang=sv-SE).
* **Commerce-aktiverad:** För projekt som vill integrera [AEM Commerce](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/home.html?lang=sv-SE) med handelslösningar som [Magento](https://magento.com/) med [Commerce Core-komponenter](https://github.com/adobe/aem-core-cif-components).
* **Exempelkod:** Checka ut HelloWorld-komponenten och exempelmodellerna, servletarna, filtren och schemaläggaren.
* **Öppen källa:** Om något inte är som det ska, [bidrar](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) dina förbättringar!

## Ytterligare läsning {#further-reading}

* **[AEM Project Archetype GitHub](https://github.com/adobe/aem-project-archetype)** - För fullständig användning och teknisk information om arkitetypen
* **[Använda arkitypen](using.md)** - en översikt över hur du använder arkitypen i ditt projekt och de resulterande modulerna som genereras
* **[Front-End Development with the AEM Project Archetype](front-end.md)** - How to use the front-end module of the archietype
* **Följande självstudiekurser är baserade på arketypen:**
   * **[WKND-plats](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html?lang=sv-SE)** - Lär dig hur du startar en ny ny webbplats.
   * **[WKND-app för en sida](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html?lang=sv-SE)** - Lär dig hur du skapar en React- eller Angular-webbapp som är helt redigerbar i AEM.
