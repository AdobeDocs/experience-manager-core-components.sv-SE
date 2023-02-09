---
title: Introduktion till AEM adaptiva Forms Core-komponenter
description: Skapa övertygande registreringsupplevelser (formulär) med flexibiliteten i de adaptiva Forms Core Components och leverera dem med kraften i Adobe Experience Manager.
role: Architect, Developer, Admin, User
source-git-commit: 945e1793ae4e959f83960db46d2de4257916fe32
workflow-type: tm+mt
source-wordcount: '1202'
ht-degree: 2%

---


# Introduktion till adaptiva Forms Core-komponenter {#adaptive-forms-core-components-introduction}

Med de adaptiva Forms Core-komponenterna i Adobe Experience Manager kan ni skapa övertygande registreringsupplevelser genom att utnyttja de flexibla och anpassningsbara alternativ som finns.

## Kärnkomponenter  {#overview}

I Adobe Experience Manager (AEM) är komponenter byggstenarna som används för att skapa sidor och formulär. De är ett enkelt och kraftfullt sätt för skribenter att skapa och hantera innehåll, samtidigt som de ger utvecklarna den flexibilitet och utbyggbarhet som behövs för att skapa anpassade komponenter.

De är utformade för att snabba upp utvecklingstiden och minska underhållskostnaderna för webbplatser och formulär, vara flexibla och kan enkelt anpassas efter specifika behov på en webbplats och i ett formulär.

Core-komponenterna är också utformade för att vara responsiva och ha stöd för ett stort antal enheter, bland annat stationära datorer, surfplattor och smarttelefoner. De följer också de senaste webbstandarderna och de bästa metoderna, vilket gör dem till en robust och tillförlitlig lösning för att skapa webbinnehåll.

De viktigaste komponenterna är generellt sett ett oumbärligt verktyg för att skapa och hantera webbinnehåll i AEM, en kraftfull och flexibel lösning som kan minska utvecklingstiden och underhållskostnaderna, samtidigt som de ger webbplatsens besökare en bra användarupplevelse.

## Adaptiva Forms Core-komponenter

De adaptiva Forms Core-komponenterna är en uppsättning med 24 BEM-kompatibla komponenter med öppen källkod som bygger på grundvalen för Adobe Experience Manager WCM Core Components. De är särskilt utformade för att användas för att skapa Adaptiv Forms, som är formulär som anpassar sig efter användarens enhet, webbläsare och skärmstorlek.

Dessa komponenter kan användas för att skapa enastående datainhämtnings- och registreringsupplevelser genom ett stort antal alternativ för formulärfält, inklusive textfält, kryssrutor, listrutor med mera. De innehåller även funktioner som validering, villkorsstyrd logik och responsiv design, som kan användas för att skapa formulär som är användarvänliga och enkla att använda.

Eftersom dessa komponenter är öppen källkod kan utvecklare dessutom enkelt anpassa och utöka komponenterna så att de passar organisationens specifika behov. Och dessa komponenter bygger på BEM-metoder som ser till att de är skalbara och underhållbara.

![](assets/sample-adaptive-form.png)

## Funktioner {#features}

|  |  |
|---|---|
| Produktionsklart | De adaptiva Forms Core-komponenterna är 24 robusta WCM-komponenter. |
| Molnklar | Finns för  [AEM Forms as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/home.html). |
| Mångsidig | Komponenterna representerar generiska begrepp som Forms-författare kan använda för att sammanställa praktiskt taget vilken layout som helst. |
| Konfigurerbar | Mallnivå [innehållsprinciper](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/full-stack/components-templates/templates.html#content-policies) ange vilka funktioner som får användas eller inte. |
| Tillgänglig | De följer [WCAG 2.1-standard](https://www.w3.org/TR/WCAG21/), har ARIA-etiketter, stöd för tangentbordsnavigering ([kända problem](https://github.com/adobe/aem-core-wcm-components/issues?utf8=✓&amp;q=is%3Aissue+is%3Aopen+accessibility+in%3Atitle)) och text för hjälpmedelstekniker som skärmläsare. |
| Temaperbar | Komponenterna implementerar [Formatsystem](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/style-system.html)och koden följer [BEM CSS-konventioner](http://getbem.com/). |
| Anpassningsbar | Flera mönster gör det enkelt att anpassa, från att justera HTML till att återanvända avancerade funktioner. |
| Versionshantering | The [versionsprincip](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-policies) säkerställer att kärnkomponenterna inte bryter din plats när du förbättrar saker som kan påverka dig. |
| Öppna källkod | Om något inte är som det ska, bidrar du till förbättringen. |

## Fördelar {#benefits}

Datainhämtningsupplevelser är avgörande för generering och registrering av leads, och de adaptiva Forms Core-komponenterna är en kraftfull lösning för att skapa formulär som är optimerade för datainhämtning. Några skäl till att använda kärnkomponenter för att skapa dessa upplevelser i stället för grundläggande komponenter:

* **GitHub och omfattande dokumentation**: De AEM adaptiva Forms Core-komponenterna har öppen källkod och finns på GitHub tillsammans med omfattande dokumentation. Detta gör det enklare för utvecklare att förstå komponenterna och hur de fungerar, samt att bidra till utvecklingen av dem. Webbplatsen aemcomponents.dev är också en värdefull resurs, där utvecklare kan se komponenterna i praktiken och få tillgång till detaljerad dokumentation.

* **BEM-modell för formatering**: Kärnkomponenterna följer BEM-modellen (Block Element Modifier) för formatering, som är en väletablerad och allmänt använd metod för att organisera CSS. Det gör det enklare för utvecklare att förstå hur formaten är ordnade och hur de kan ändras för att passa just deras behov.

* **Inget beroende av tredjepartsbibliotek**: En av fördelarna med Core Components är att de inte är beroende av JavaScript-bibliotek från tredje part, inklusive JQuery och Underscore. Detta gör komponenterna snabbare och enklare samt enklare att integrera i en befintlig AEM.

* **Fokus på prestanda och tillgänglighet**: Kärnkomponenterna byggs med prestanda och tillgänglighet i åtanke, vilket återspeglas i deras höga poäng för Google Lightroom och webbinarium. Detta gör det enklare för utvecklare att skapa tillgängliga och högpresterande webbsidor, vilket blir allt viktigare i dagens digitala landskap.

* **Formulärkomponenter i webbplatserna 30, mallar och teman**: Core Components har stöd för formulärkomponenter i webbplatserna 30-mallen och -temana, vilket gör det enklare för utvecklare att skapa och anpassa formulär i AEM.

* **Enklare att formatera**: Kärnkomponenterna är enklare att formatera än deras motsvarigheter i grundkomponenterna. Processen för att skapa teman liknar Sites, med möjlighet att ärva samma tema/CSS från den överordnade webbplatssidan. Dessutom gör BEM-modellen för formatering det enklare att förstå och ändra formaten.

* **Tillgänglighet**: Adaptiva Forms Core-komponenter stöder standarder och riktlinjer för tillgänglighet, som  [WCAG 2.1-standard](https://www.w3.org/TR/WCAG21/), för att säkerställa att formulär kan användas av personer med funktionshinder, inklusive sådana som använder hjälpmedelstekniker som skärmläsare.

* **Justering med AEM Sites**: Core Components är utformade för att vara mer anpassade till AEM Sites, vilket gör det enklare för webbplatsanvändare att använda dem utan att behöva lära sig något nytt. Komponenterna använder samma frontpipeline som Sites, vilket gör det enklare att formatera och ändra deras utseende. Följande punkter visar dessutom justeringen:

   * **Redigeringsupplevelsen är integrerad med sidredigeraren**: Core Components har en redigeringsupplevelse som är integrerad med Sites Editor, med dialogrutor och andra upplevelser som liknar Page Editor. Detta gör det enklare för webbplatsanvändare att skapa och hantera formulär i det välkända sammanhanget i webbplatsredigeraren.

   * **Redigering av infogade formulär i webbplatsredigeraren**: Med Core Components kan du redigera inline-formulär i webbplatsredigeraren och slipper växla fram och tillbaka mellan redigerare. Detta effektiviserar redigeringsarbetet och gör det enklare att skapa och hantera formulär.

   * **Ärver webbplatsfunktioner i Forms**: Forms som skapats på en Sites-sida har samma funktioner som Sites. Detta ger en smidig och integrerad upplevelse för att skapa och hantera formulär inom ramen för AEM Sites

   <!--including Multi Site Manager, the ability to use Sites components within a form for static content, support for scheduled publish/unpublish, form translation aligned with Sites translation, versioning, and targeting -->



## Krav {#requirements}

De adaptiva Forms Core-komponenterna har följande krav.

| AEM | AEM Forms-tillägg | Kärnkomponenter |
|---|---|---|
| AEM as a Cloud Service | Forms - digital registrering | [Version 2.20.8](/help/versions.md)+ |


## Adaptiva Forms Core-komponenter {#components}

Den aktuella versionen av de adaptiva Forms Core-komponenterna innehåller följande komponenter.

* Dragspel
* Knapp
* Kryssrutegrupp
* Datumväljaren
* Nedrullningsbar lista
* E-postinmatning
* Formulärbehållare
* Bifogad fil
* Sidfot
* Sidhuvud
* Vågräta flikar
* Bild
* Nummerindata
* Panelbehållare
* Alternativknapp
* Återställningsknapp
* Skicka-knapp
* Telefonindata
* Textindata
* Text
* Titel
* guide

