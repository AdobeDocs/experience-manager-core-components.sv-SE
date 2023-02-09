---
title: Introduktion till AEM adaptiva Forms Core-komponenter
description: Skapa övertygande registreringsupplevelser (formulär) med flexibiliteten i de adaptiva Forms Core Components och leverera dem med kraften i Adobe Experience Manager.
role: Architect, Developer, Admin, User
source-git-commit: 781cf351ef52cbb56ff33c2674c8af591c81a30e
workflow-type: tm+mt
source-wordcount: '1069'
ht-degree: 2%

---


# Introduktion till adaptiva Forms Core-komponenter {#adaptive-forms-core-components-introduction}

Med de adaptiva Forms Core-komponenterna i Adobe Experience Manager kan ni skapa övertygande registreringsupplevelser genom att utnyttja de flexibla och anpassningsbara alternativ som finns.

## Kärnkomponenter  {#overview}

I Adobe Experience Manager (AEM) är komponenter byggstenarna som används för att skapa sidor och formulär. De är ett enkelt och kraftfullt sätt för skribenter att skapa och hantera innehåll, samtidigt som de ger utvecklarna den flexibilitet och utbyggbarhet som behövs för att skapa anpassade komponenter.

Core Components är en uppsättning färdiga, standardiserade WCM-komponenter som är utformade för att snabba upp utvecklingstiden och minska underhållskostnaderna för webbplatser. Dessa komponenter innehåller bl.a. textfält, bilder och videor. De är utformade för att vara flexibla och kan enkelt anpassas efter behoven på en webbplats.

Core-komponenterna är också utformade för att vara responsiva och ha stöd för ett stort antal enheter, bland annat stationära datorer, surfplattor och smarttelefoner. De följer också de senaste webbstandarderna och de bästa metoderna, vilket gör dem till en robust och tillförlitlig lösning för att skapa webbinnehåll.

Dessutom är kärnkomponenterna utformade för att fungera sömlöst med andra delar av AEM, vilket gör att skribenter och utvecklare kan skapa mer engagerande och interaktiva formulär enklare och snabbare.

De viktigaste komponenterna är generellt sett ett oumbärligt verktyg för att skapa och hantera webbinnehåll i AEM, en kraftfull och flexibel lösning som kan minska utvecklingstiden och underhållskostnaderna, samtidigt som de ger webbplatsens besökare en bra användarupplevelse.

I Adobe Experience Manager är komponenterna de strukturella element som utgör innehållet i de sidor och formulär som skapas. Komponenter har alltid varit en grundläggande del av AEM och gjort det enkelt att skapa sidor och formulär, men kraftfullt för författaren och utveckling av komponenter flexibelt och utbyggbart för utvecklaren. De centrala komponenterna är en uppsättning standardiserade WCM-komponenter (Web Content Management) som snabbar upp utvecklingstiden och minskar underhållskostnaderna för dina webbplatser.

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

Datainhämtningsupplevelser är avgörande för generering och registrering av leads, och de adaptiva Forms Core-komponenterna är en kraftfull lösning för att skapa formulär som är optimerade för datainhämtning. Några av skälen till att använda kärnkomponenter för att skapa dessa upplevelser är:

* **Anpassning**: Med adaptiva Forms Core Components kan utvecklare enkelt anpassa utseendet och beteendet för formulärkomponenter som textfält, kryssrutor och listrutor så att de uppfyller specifika krav.

* **Tillgänglighet**: Adaptiva Forms Core-komponenter stöder standarder och riktlinjer för tillgänglighet, som  [WCAG 2.1-standard](https://www.w3.org/TR/WCAG21/), för att säkerställa att formulär kan användas av personer med funktionshinder, inklusive sådana som använder hjälpmedelstekniker som skärmläsare.

* **Enhetliga formulär**: Genom att använda adaptiva Forms Core-komponenter kan utvecklare skapa formulär som ser likadana ut och känns som de ska, vilket gör det enklare för användarna att förstå och fylla i formulären, vilket leder till ökat engagemang och förbättrad användarupplevelse.

* **WYSIWYG-redigerare**: AEM Forms har ett användarvänligt gränssnitt, lättanvänt WYSIWYG-redigeringsprogram där du kan använda dessa komponenter för att skapa ett adaptivt formulär. Man kan skapa och redigera blanketter utan att behöva kunna koda dem. Den innehåller även en visuell regelredigerare som hjälper dig att enkelt skapa regelbaserade åtgärder och implementera komplex logik för att automatisera formulärbeteenden utan att behöva skriva kod.

* **Villkorlig logik**: Adaptiva Forms Core-komponenter har stöd för villkorsstyrd logik, vilket innebär att formulärkomponenternas utseende eller beteende kan ändras baserat på de värden som användaren anger. Vissa fält kan t.ex. döljas eller göras obligatoriska baserat på det val som gjorts i andra fält.

* **Dataverifiering**: Med adaptiva Forms Core-komponenter får du inbyggda datavalideringsfunktioner som gör det möjligt för utvecklare att se till att inmatade data uppfyller specifika kriterier, som minsta och högsta längd, obligatoriska värden och specifika format.

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

