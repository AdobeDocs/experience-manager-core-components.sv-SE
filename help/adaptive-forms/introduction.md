---
title: Introduktion till AEM adaptiva Forms Core-komponenter
description: Skapa övertygande registreringsupplevelser (formulär) med flexibiliteten i de adaptiva Forms Core Components och leverera dem med kraften i Adobe Experience Manager.
role: Architect, Developer, Admin, User
exl-id: 6d0f2845-bbb8-4488-a254-b69d7a6290b1
source-git-commit: efc42e6c615987a1d85abe18b650ac23a6d84bf6
workflow-type: tm+mt
source-wordcount: '1176'
ht-degree: 0%

---

# Introduktion till adaptiva Forms Core-komponenter {#adaptive-forms-core-components-introduction}

Med de adaptiva Forms Core-komponenterna i Adobe Experience Manager kan ni skapa övertygande registreringsupplevelser genom att utnyttja de flexibla och anpassningsbara alternativ som finns.

## Kärnkomponenter  {#overview}

I Adobe Experience Manager (AEM) är komponenter byggstenarna som används för att skapa sidor och formulär. De är ett enkelt och kraftfullt sätt för skribenter att skapa och hantera innehåll, samtidigt som de ger utvecklarna den flexibilitet och utbyggbarhet som behövs för att skapa anpassade komponenter. Dessa är utformade för att snabba upp utvecklingstiden och minska underhållskostnaderna för webbplatser och formulär, vara flexibla och kan enkelt anpassas efter specifika behov på en webbplats och i ett formulär.

Core-komponenterna är också utformade för att vara responsiva och ha stöd för ett stort antal enheter, bland annat stationära datorer, surfplattor och smarttelefoner. De följer också de senaste webbstandarderna och de bästa metoderna, vilket gör dem till en robust och tillförlitlig lösning för att skapa webbinnehåll.

De viktigaste komponenterna är generellt sett ett oumbärligt verktyg för att skapa och hantera webbinnehåll i AEM, en kraftfull och flexibel lösning som kan minska utvecklingstiden och underhållskostnaderna, samtidigt som de ger webbplatsens besökare en bra användarupplevelse.

## Adaptiva Forms Core-komponenter

De adaptiva Forms Core-komponenterna är en uppsättning med 24 BEM-kompatibla komponenter med öppen källkod som bygger på grundvalen för Adobe Experience Manager WCM Core Components. De är särskilt utformade för att användas för att skapa Adaptiv Forms, som är formulär som anpassar sig efter användarens enhet, webbläsare och skärmstorlek.

Dessa komponenter kan användas för att skapa enastående datainhämtnings- och registreringsupplevelser genom ett stort antal alternativ för formulärfält, inklusive textfält, kryssrutor, listrutor med mera. De innehåller även funktioner som validering, villkorsstyrd logik och responsiv design, som kan användas för att skapa formulär som är användarvänliga och enkla att använda.

Eftersom dessa komponenter är öppen källkod kan utvecklare dessutom enkelt anpassa och utöka komponenterna så att de passar organisationens specifika behov. Och dessa komponenter bygger på BEM-metoder som ser till att de är skalbara och underhållbara.

![adaptiv formulärbild](assets/sample-adaptive-form.png)

## Funktioner {#features}

|  |  |
|---|---|
| Produktionsklart | De adaptiva Forms Core-komponenterna är 24 robusta WCM-komponenter. |
| Molnklar | Finns för  [AEM Forms as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/home.html). |
| Mångsidig | Komponenterna representerar generiska begrepp som Forms-författare kan använda för att sammanställa praktiskt taget vilken layout som helst. |
| Konfigurerbar | Mallnivå [innehållsprinciper](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/full-stack/components-templates/templates.html#content-policies) ange vilka funktioner som får användas eller inte. |
| Tillgänglig | De innehåller ARIA-etiketter, stöd för tangentbordsnavigering och text för hjälpmedelstekniker som skärmläsare. |
| Temabell | Komponenterna implementerar [Formatsystem](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/style-system.html)och koden följer [BEM CSS-konventioner](https://getbem.com/). |
| Anpassningsbar | Flera mönster gör det enkelt att anpassa, från att justera HTML till att återanvända avancerade funktioner. |
| Versioner | The [versionsprincip](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-policies) säkerställer att kärnkomponenterna inte bryter din plats när du förbättrar saker som kan påverka dig. |
| Öppen källkod | Om något inte är som det ska, bidrar du till förbättringen. |

<!-- comply with [WCAG 2.1 standard](https://www.w3.org/TR/WCAG21/), -->


## Fördelar {#benefits}

Datainhämtningsupplevelser är avgörande för generering och registrering av leads, och de adaptiva Forms Core-komponenterna är en kraftfull lösning för att skapa formulär som är optimerade för datainhämtning. En del skäl till att använda kärnkomponenter för att skapa dessa upplevelser över grundläggande komponenter är:

* **GitHub och omfattande dokumentation**: De AEM adaptiva Forms Core-komponenterna har öppen källkod och finns på GitHub tillsammans med omfattande dokumentation. Detta gör det enklare för utvecklare att förstå komponenterna och hur de fungerar, samt att bidra till utvecklingen av dem. The [aemcomponents.dev](https://www.aemcomponents.dev/) är också en värdefull resurs där utvecklare kan se komponenterna i praktiken och få tillgång till detaljerad dokumentation.

* **BEM-modell för formatering**: Kärnkomponenterna följer BEM-modellen (Block Element Modifier) för formatering, som är en väletablerad och allmänt använd metod för att organisera CSS. Det gör det enklare för utvecklare att förstå hur formaten är ordnade och hur de kan ändras för att passa just deras behov.

* **Inget beroende av tredjepartsbibliotek**: En av fördelarna med Core Components är att de inte är beroende av JavaScript-bibliotek från tredje part, inklusive JQuery och Underscore. Detta gör komponenterna snabbare och enklare samt enklare att integrera i en befintlig AEM.

* **Fokus på prestanda och tillgänglighet**: Kärnkomponenterna byggs med prestanda och tillgänglighet i åtanke, vilket återspeglas i deras höga poäng för Google Lightroom och webbinarium. Detta gör det enklare för utvecklare att skapa tillgängliga och högpresterande webbsidor, vilket blir allt viktigare i dagens digitala landskap.

* **Formulärkomponenter i webbplatserna 30, mallar och teman**: De centrala komponenterna har stöd för formulärkomponenter i webbplatserna 30-mallen och -teman, vilket gör det enklare för utvecklare att skapa och anpassa formulär i AEM.

* **Enklare att formatera**: Kärnkomponenterna är enklare att formatera än deras motsvarigheter i grundkomponenterna. Processen för att skapa teman liknar Sites, med möjlighet att ärva samma tema/CSS från den överordnade webbplatssidan. Dessutom gör BEM-modellen för formatering det enklare att förstå och ändra formaten.

* **Tillgänglighet**: Adaptiva Forms Core-komponenter stöder standarder och riktlinjer för tillgänglighet för att säkerställa att formulär kan användas av personer med funktionshinder, inklusive sådana som använder hjälpmedelstekniker som skärmläsare

## Adaptiva Forms Core-komponenter {#components}

Den aktuella versionen av de adaptiva Forms Core-komponenterna innehåller komponenterna nedan.

* [Dragspel](/help/adaptive-forms/components/accordion.md)
* [Knapp](/help/adaptive-forms/components/button.md)
* [Kryssrutegrupp](/help/adaptive-forms/components/checkbox-group.md)
* [Datumväljaren](/help/adaptive-forms/components/date-picker.md)
* [Nedrullningsbar lista](/help/adaptive-forms/components/drop-down-list.md)
* [E-postinmatning](/help/adaptive-forms/components/email-input.md)
* [Formulärbehållare](/help/adaptive-forms/components/form-container.md)
* [Bifogad fil](/help/adaptive-forms/components/file-attachment.md)
* [Sidfot](/help/adaptive-forms/components/footer.md)
* [Sidhuvud](/help/adaptive-forms/components/header.md)
* [Vågräta flikar](/help/adaptive-forms/components/horizontal-tabs.md)
* [Bild](/help/adaptive-forms/components/image.md)
* [Numerisk ruta](/help/adaptive-forms/components/numeric-box.md)
* [Panel](/help/adaptive-forms/components/panel.md)
* [Alternativknapp](/help/adaptive-forms/components/radio-button.md)
* [Återställ knapp](/help/adaptive-forms/components/reset-button.md)
* [Skicka-knapp](/help/adaptive-forms/components/submit-button.md)
* [Telefonindata](/help/adaptive-forms/components/telephone-input.md)
* [Textruta](/help/adaptive-forms/components/text-box.md)
* [Text](/help/adaptive-forms/components/text.md)
* [Titel](/help/adaptive-forms/components/title.md)
* [guide](/help/adaptive-forms/components/wizard.md)

## Konfigurera adaptiva Forms Core-komponenter

Genom att aktivera adaptiva Forms Core-komponenter på AEM Forms as a Cloud Service kan du börja skapa, publicera och leverera Core Components-baserade adaptiva Forms och Headless Forms med hjälp av AEM Forms Cloud Service-instanser i flera kanaler. Detaljerade instruktioner om hur du aktiverar kärnkomponenter i adaptiva formulär finns i [Aktivera adaptiva Forms Core-komponenter i AEM Forms as a Cloud Service och lokala utvecklingsmiljö](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/setup-configure-migrate/enable-adaptive-forms-core-components.html).

De adaptiva Forms Core-komponenterna har följande krav.

| AEM | AEM Forms-tillägg | Adaptiva Forms Core-komponenter |
|---|---|---|
| AEM as a Cloud Service | Forms - digital registrering | [Version 2.0.10](version.md)+ |
| AEM 6.5 | Forms-tillägg | [Version 1.1.12](version.md)+ |

Om din AEM Cloud Service SDK-version är äldre än 2023.02.0, [se till att du har `prerelease` flagga aktiverad i din miljö](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/release-notes/prerelease.html?lang=en#new-features) som adaptiva Forms Core Components ingick i förleasingen före version 2023.02.0.


## Skapa en grundkomponentbaserad adaptiv form

Du kan utföra följande åtgärder i både AEM Forms as a Cloud Service- och AEM 6.5 Forms-miljöer:

| Åtgärd | AEM Forms Version |
|--------|------------------|
| Skapa ett fristående anpassat formulär | [AEM Forms som Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html) |
| Skapa ett anpassat formulär på AEM Sites Page | [AEM 6.5 Forms](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-basic-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html?lang=en#create-an-adaptive-form-in-sites-editor-or-experience-fragment), [AEM Forms som Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html#create-an-adaptive-form-in-sites-editor-or-experience-fragment) |
| Skapa ett anpassat formulär i AEM Experience Fragment | [AEM 6.5 Forms](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-basic-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html?lang=en#create-an-adaptive-form-in-experience-fragment), [AEM Forms som Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html#create-an-adaptive-form-in-experience-fragment) |
| Konvertera ett anpassat formulär till ett upplevelsefragment | [AEM 6.5 Forms](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-basic-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html?lang=en#convert-an-adaptive-form-in-sites-page-to-an-experience-fragment), [AEM Forms som Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html#convert-an-adaptive-form-in-sites-page-to-an-experience-fragment) |





<!-- >, such as  [WCAG 2.1 standard](https://www.w3.org/TR/WCAG21/), to ensure that forms can be used by people with disabilities, including those using assistive technologies such as screen readers.

*   **Alignment with AEM Sites**: The Core Components are designed to be more aligned with AEM Sites, making it easier for Sites users to adopt and use them without having to learn anything new. The components use the same front-end pipeline as Sites, making it easier to style and modify their appearance. 

<!-- Additionally, the following points further illustrate this alignment:

    *   **Authoring experience inline with Page editor**: The Core Components have an authoring experience that is inline with the Sites editor, with dialogs and other experiences similar to the Page editor. This makes it easier for Sites users to create and manage forms within the familiar context of the Sites editor.

    *   **Inline form editing in Sites editor**: The Core Components allow  inline form editing within the Sites editor, avoiding the need to switch back and forth between editors. This streamlines the authoring experience and makes it easier to create and manage forms.

    *   **Inheriting Sites features in Forms**: Forms authored within a Sites page inherit the same features as Sites. This provides a seamless and integrated experience for creating and managing forms within the context of AEM Sites 
    
    <!--including Multi Site Manager, the ability to use Sites components within a form for static content, support for scheduled publish/unpublish, form translation aligned with Sites translation, versioning, and targeting -->

## Se även {#see-also}

{{see-also}}
