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
>Den senaste AEM Project Archetype och tillhörande teknisk dokumentation [finns på GitHub.](https://github.com/adobe/aem-project-archetype)

## Varför använda Arketype {#why-use-the-archetype}

Med den AEM Project Archetype-tekniken kan du skapa ett AEM projekt med bästa praxis och bara några få tangenttryckningar. Genom att använda arkivtypen kommer alla delar redan att vara på plats, så även om det resulterande projektet är minimalt, implementeras redan alla [viktiga funktioner](/help/developing/archetype/using.md#what-you-get) AEM så att allt du behöver göra är att bygga vidare.

Det finns förstås många element som [ett framgångsrikt AEM,](/help/developing/success.md) men att använda AEM Project Archetype är en bra grund och rekommenderas starkt för alla AEM projekt.

## Funktioner {#features}

* **God praxis:** Bootstrap er sajt med alla de senaste Adobe rekommenderade metoderna.
* **Lågkod:** Redigera mallarna, skapa innehåll, distribuera CSS så är sajten klar att publiceras.
* **Molnklart:** Om du vill kan du använda [AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html) att publicera på bara några dagar och förenkla skalbarhet och underhåll.
* **Dispatcher:** Ett projekt är bara färdigt med en [Dispatcher-konfiguration](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/dispatcher.html) som garanterar hastighet och säkerhet.
* **Flera platser:** Vid behov genereras innehållsstrukturen för en [flerspråkig och flerregionsinstallation](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/msm/overview.html).
* **Kärnkomponenter:** Författare kan skapa nästan vilken layout som helst med vår mångsidiga [uppsättning standardiserade komponenter](/help/introduction.md).
* **Redigerbara mallar:** Sammanställ praktiskt taget alla [mall utan kod](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html)och definiera vad författarna får redigera.
* **Responsiv layout:** På mallar eller enskilda sidor [definiera hur elementen flödar om](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/get-started/localization.html) för definierade brytpunkter.
* **Sidhuvud och sidfot:** Sammanställ och lokalisera dem utan kod med [komponenternas lokaliseringsfunktioner](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/get-started/localization.html).
* **Formatsystem:** Undvik att bygga anpassade komponenter genom att tillåta författare att [använda olika format](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/project-archetype/style-system.html) till dem.
* **Front-End Build:** Utvecklare kan [skapa AEM sidor och bygga klientbibliotek](front-end.md) med Webpack, TypeScript och SASS.
* **WebApp-Ready:** För webbplatser som använder Reagera eller Angular använder du [SPA SDK](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/hybrid/developing.html) för att behålla [kontextredigering av appen](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html).
* **Handel aktiverad:** För projekt som vill integreras [AEM](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/home.html) med e-handelslösningar [Magento](https://magento.com/) med [Kärnkomponenter i Commerce](https://github.com/adobe/aem-core-cif-components).
* **Exempelkod** Checka ut HelloWorld-komponenten och exempelmodellerna, servletarna, filtren och schemaläggaren.
* **Öppen källa:** Om något inte är som det ska, [contribute](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) förbättringar!

## Ytterligare läsning {#further-reading}

* **[AEM Project Archetype GitHub](https://github.com/adobe/aem-project-archetype)** - För fullständig användning och teknisk information om arketypen
* **[Använda Arketype](using.md)** - En översikt över hur du använder typen av arkiv i ditt projekt och de moduler som genereras
* **[Front-end-utveckling med AEM Project Archetype](front-end.md)** - Så här använder du bågformets frontmodul
* **Följande självstudiekurser är baserade på arketypen:**
   * **[WKND-plats](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)** - Lär dig hur du skapar en ny webbplats.
   * **[WKND-app för en sida](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)** - Lär dig hur du skapar en React- eller Angular-webbapp som är helt redigerbar i AEM.
