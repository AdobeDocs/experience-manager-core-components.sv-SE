---
title: AEM Adaptive Forms Core Components Introduction
description: Skapa övertygande registreringsupplevelser (formulär) med flexibiliteten i de adaptiva Forms Core Components och leverera dem med kraften i Adobe Experience Manager.
role: Architect, Developer, Admin, User
exl-id: 6d0f2845-bbb8-4488-a254-b69d7a6290b1
source-git-commit: 6725784bd4c94d433c91d6bd65d14d03cbefd954
workflow-type: tm+mt
source-wordcount: '2123'
ht-degree: 0%

---


# Adaptiva Forms Core-komponenter  {#adaptive-forms-core-components-introduction}

Med de adaptiva Forms Core-komponenterna i Adobe Experience Manager kan ni skapa övertygande registreringsupplevelser.

{{traditional-aem}}

## Kärnkomponenter {#overview}

I Adobe Experience Manager (AEM) är komponenter byggstenarna som används för att skapa sidor och formulär. De är ett enkelt och kraftfullt sätt för skribenter att skapa och hantera innehåll, samtidigt som de ger utvecklarna den flexibilitet och utbyggbarhet som behövs för att skapa anpassade komponenter. Dessa är utformade för att snabba upp utvecklingstiden och minska underhållskostnaderna för webbplatser och formulär, vara flexibla och kan enkelt anpassas efter specifika behov på en webbplats och i ett formulär.

Core-komponenterna är också utformade för att vara responsiva och ha stöd för ett stort antal enheter, bland annat stationära datorer, surfplattor och smarttelefoner. De följer också de senaste webbstandarderna och de bästa metoderna, vilket gör dem till en robust och tillförlitlig lösning för att skapa webbinnehåll.

De viktigaste komponenterna är generellt ett oumbärligt verktyg för att skapa och hantera webbinnehåll i AEM, en kraftfull och flexibel lösning som kan minska utvecklingstiden och underhållskostnaderna, samtidigt som de ger webbplatsens besökare en bra användarupplevelse.

## Adaptiva Forms Core-komponenter

De adaptiva Forms Core-komponenterna är en uppsättning med 30 BEM-kompatibla komponenter med öppen källkod som bygger på grundvalen för Adobe Experience Manager WCM Core Components. De är särskilt utformade för att användas för att skapa Adaptiv Forms, som är formulär som anpassar sig efter användarens enhet, webbläsare och skärmstorlek.

Dessa komponenter kan användas för att skapa enastående datainhämtnings- och registreringsupplevelser genom ett stort antal alternativ för formulärfält, inklusive textfält, kryssrutor, listrutor med mera. De innehåller även funktioner som validering, villkorsstyrd logik och responsiv design, som kan användas för att skapa formulär som är användarvänliga och enkla att använda.

Eftersom dessa komponenter är öppen källkod kan utvecklare dessutom enkelt anpassa och utöka komponenterna så att de passar organisationens specifika behov. Och dessa komponenter bygger på BEM-metoden som ser till att de är skalbara och underhållbara.

![adaptiv formulärbild](assets/sample-adaptive-form.png)

## Funktioner {#features}

|  |  |
|---|---|
| Produktionsklart | De adaptiva Forms Core-komponenterna är 24 robusta WCM-komponenter. |
| Molnklar | Finns för [AEM Forms as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/home.html?lang=sv-SE). |
| Mångsidig | Komponenterna representerar generiska begrepp som Forms-författare kan använda för att sammanställa praktiskt taget vilken layout som helst. |
| Konfigurerbar | [Innehållsprinciper](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/full-stack/components-templates/templates.html?lang=sv-SE#content-policies) på mallnivå definierar vilka funktioner som får användas eller inte. |
| Tillgänglig | De innehåller ARIA-etiketter, stöd för tangentbordsnavigering och text för hjälpmedelstekniker som skärmläsare. |
| Temabell | Komponenterna implementerar [Style System](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/style-system.html?lang=sv-SE) och koden följer [BEM CSS-konventioner](https://getbem.com/). |
| Anpassningsbar | Flera mönster gör det enkelt att anpassa, från att justera HTML till avancerad återanvändning av funktioner. |
| Versioner | Versionsprincipen [för ](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-policies) säkerställer att kärnkomponenterna inte bryter din plats när du förbättrar saker som kan påverka dig. |
| Öppen källkod | Om något inte är som det ska, bidrar du till förbättringen. |

<!-- comply with [WCAG 2.1 standard](https://www.w3.org/TR/WCAG21/), -->


## Fördelar {#benefits}

Datainhämtningsupplevelser är avgörande för generering och registrering av leads, och de adaptiva Forms Core-komponenterna är en kraftfull lösning för att skapa formulär som är optimerade för datainhämtning. En del skäl till att använda kärnkomponenter för att skapa dessa upplevelser över grundläggande komponenter är:

* **[Tillgänglighet på GitHub](https://github.com/adobe/aem-core-forms-components)**: AEM Adaptive Forms Core Components har öppen källkod och är tillgängliga på GitHub tillsammans med omfattande dokumentation. Detta gör det enklare för utvecklare att förstå komponenterna och hur de fungerar, samt att bidra till utvecklingen av dem. Webbplatsen [aemcomponents.dev](https://www.aemcomponents.dev/) är också en värdefull resurs, där utvecklare kan se komponenterna i praktiken och få tillgång till detaljerad dokumentation.

* **[BEM-modell för formatering](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-themes-in-core-components)**: Kärnkomponenterna följer BEM-modellen (Block Element Modifier) för formatering, som är en väletablerad och allmänt använd metod för att organisera CSS. Det gör det enklare för utvecklare att förstå hur formaten är ordnade och hur de kan ändras för att passa just deras behov.

* **Inget beroende av tredjepartsbibliotek**: En av fördelarna med kärnkomponenterna är att de inte är beroende av JavaScript-bibliotek från tredje part, inklusive JQuery och Underscore. Detta gör komponenterna snabbare och enklare samt enklare att integrera i en befintlig AEM-implementering.

* **Fokusera på prestanda och tillgänglighet**: Kärnkomponenterna har byggts med prestanda och tillgänglighet i åtanke, vilket återspeglas i deras höga poäng för Google Lightroom och webbinarium. Detta gör det enklare för utvecklare att skapa tillgängliga och högpresterande webbsidor, vilket blir allt viktigare i dagens digitala landskap.

* **Formulärkomponenter i webbplatserna 30, mallar och teman**: De centrala komponenterna har stöd för formulärkomponenter i webbplatserna 30, mallar och teman, vilket gör det enklare för utvecklare att skapa och anpassa formulär i AEM.

* **[Enklare att formatera](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-themes-in-core-components)**: Det är enklare att formatera kärnkomponenterna än deras motsvarigheter till grundkomponenterna. Processen för att skapa teman liknar Sites, med möjlighet att ärva samma tema/CSS från den överordnade webbplatssidan. Dessutom gör BEM-modellen för formatering det enklare att förstå och ändra formaten.

* **Hjälpmedel**: Adaptiva Forms Core-komponenter har stöd för hjälpmedelsstandarder och riktlinjer för att säkerställa att formulär kan användas av personer med funktionshinder, inklusive sådana som använder hjälpmedelstekniker som skärmläsare.

* **[Versionshantering](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/add-comments-annotations-versioning-adaptive-form-core-components)**: Du kan skapa och hantera flera versioner av en Core Components-baserad Adaptive Forms, delta i samverkansdiskussioner via kommentarer och bifoga anteckningar till specifika formulärkomponenter, vilket förbättrar den övergripande formuläruppbyggnadsupplevelsen.

## Tillgängliga komponenter: En uppdelning efter komponenttyp

Den aktuella versionen av AEM Forms har följande huvudkomponenter, [Foundation Components](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/create-an-adaptive-form-on-forms-cs/introduction-forms-authoring#component-toolbar) och [Form Block Components (Edge Delivery Services)](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/edge-delivery/build-forms/forms-references/form-components).

| Komponenter | Foundation Components | Kärnkomponenter | Formulärblockskomponenter | Ytterligare information |
|------------|:---------------------:|:---------------:|:---------------------:|-----------------------|
| Adobe Sign-block | ✔️ | | | [Adobe Sign-integrering](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/forms/integrate/services/adobe-sign-integration-adaptive-forms#adobe-acrobat-sign-for-government) är bara tillgänglig för Foundation Components. |
| Dragspel | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/accordion.md)</span> | | För Foundation-komponenter kan du konfigurera dragspelslayouten i [panelkomponentegenskaperna](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/configure-layout-of-an-adaptive-form/layout-capabilities-adaptive-forms#panel-layout). |
| Adaptivt formulärfragment | ✔️ | ✔️ | | För Foundation Components (Foundation-komponenter) kan du [lägga till ett fragment](https://experienceleague.adobe.com/sv/docs/experience-manager-65/content/forms/adaptive-forms-basic-authoring/adaptive-form-fragments#insert-a-fragment-in-an-adaptive-form) från Assets Browser. |
| Adaptiv form reCAPTCHA | ✔️ | ✔️ | ✔️ | För Foundation-komponenter använder du Captcha-komponenten för att [lägga till Google reCaptcha i ett formulär](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/add-components-to-an-adaptive-form/captcha-adaptive-forms#google-reCAPTCHA). |
| Knapp | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/button.md)</span> | ✔️ | |
| Diagram | ✔️ | | | |
| Kryssruta | ✔️ | ✔️ | | |
| Kryssrutegrupp | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/checkbox-group.md)</span> | ✔️ | För Foundation-komponenter använder du kryssrutekomponenten för att lägga till flera kryssrutor |
| Datumindatafält | ✔️ | | | Använd komponenten [datumväljare](/help/adaptive-forms/components/date-picker.md) för kärnkomponenter. Du kan också lägga till separata komponenter för [textruta](/help/adaptive-forms/components/text-box.md) eller [numerisk ruta](/help/adaptive-forms/components/numeric-box.md) för att hämta dag, månad och år. |
| Datumväljaren | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/date-picker.md)</span> | ✔️ | |
| Listruta | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/drop-down-list.md)</span> | ✔️ | |
| E-post | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/email.md)</span> | ✔️ | |
| Bifogad fil | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/file-attachment.md)</span> | ✔️ | |
| Lista över bifogade filer | ✔️ | | | |
| Sidfot | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/footer.md)</span> | ✔️ | |
| Fotnotsplatshållare | ✔️ | | | |
| Formulärbehållare | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/form-container.md)</span> | ✔️ | Använd komponenten [Rotpanel](https://experienceleague.adobe.com/sv/docs/experience-manager-learn/cloud-service/forms/create-first-af/configure-root-panel) för Foundation-komponenter. |
| Formulärtitel | ✔️ | ✔️ | | Använd komponenten title för Foundation-komponenter. |
| hCaptcha | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/hcaptcha.md)</span> |  | För Foundation-komponenter kan du [ansluta dina adaptiva formulär med hCaptcha](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/add-components-to-an-adaptive-form/integrate-adaptive-forms-turnstile.html?lang=sv-SE) för grundläggande komponentbaserade formulär. |
| Sidhuvud | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/header.md)</span> | ✔️ | |
| Vågräta flikar | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/horizontal-tabs.md)</span> | | För Foundation Components (Foundation-komponenter) kan du konfigurera layouten [tabbar överst (vågräta flikar)](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/configure-layout-of-an-adaptive-form/layout-capabilities-adaptive-forms#panel-layout) i panelkomponentegenskaperna. |
| Bild | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/image.md)</span> | ✔️ | |
| Knappen Nästa | ✔️ | ✔️ | | Använd [guidekomponenten](/help/adaptive-forms/components/wizard.md) för nästa och föregående knappar för att flytta mellan flera paneler. |
| Numerisk ruta | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/numeric-box.md)</span> | ✔️ | |
| Numerisk stege | ✔️ | | | |
| Panel | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/panel.md)</span> | ✔️ | |
| Telefon | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/phone.md)</span> | ✔️ | |
| Knappen Föregående | ✔️ | ✔️ | | Använd [guidekomponenten](/help/adaptive-forms/components/wizard.md) för nästa och föregående knappar för att flytta mellan flera paneler. |
| Grupp med alternativknappar | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/radio-button.md)</span> | ✔️ | |
| Återställ knapp | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/reset-button.md)</span> | ✔️ | |
| Granska |  | <span style="color:blue">[✔️](/help/adaptive-forms/components/reset-button.md)</span> |  | |
| Klottersignatur | ✔️ | | | |
| Avgränsare | ✔️ | | | Använd WCM-komponenten [Seperator](/help/components/separator.md) |
| Skicka-knapp | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/submit-button.md)</span> | ✔️ | |
| Sammanfattningssteg | ✔️ | | | |
| Byt | ✔️ | <span style="color:blue"> [✔️](/help/adaptive-forms/components/adaptive-form-switch.md) | | |
| Tabell | ✔️ | | | |
| Villkor | ✔️ | ✔️ | | |
| Text | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/text.md)</span> | ✔️ | |
| Textruta | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/text-box.md)</span> | ✔️ | |
| Turnstile Captcha | ✔️ | | | [Turnstile Captcha](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/add-components-to-an-adaptive-form/integrate-adaptive-forms-turnstile) är bara tillgängligt för Foundation-komponenter. |
| Lodräta tabbar | ✔️ | ✔️ | | För Foundation-komponenter kan du konfigurera [flikarna till vänster (lodräta flikar) layout](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/configure-layout-of-an-adaptive-form/layout-capabilities-adaptive-forms#panel-layout) i panelkomponentegenskaperna |
| guide | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/wizard.md)</span> | ✔️ | För Foundation-komponenter kan du konfigurera [guidelayouten](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/configure-layout-of-an-adaptive-form/layout-capabilities-adaptive-forms#panel-layout) i panelkomponentegenskaperna |

<!--| Password Box | ✔️ | ✔️| ✔️ | |
| Image Choice | ✔️ | | | |
-->


>[!NOTE]
>
>
> * Förutom de komponenter som anges ovan stöder Forms-blocket alla giltiga [HTML5-indatatyper](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#input_types) och [textområde](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) som komponenter.
> * Vill du ha en komponent som inte listas ovan? Begär det via e-post aem-forms-ea@adobe.com från din officiella adress.


<!-- >
* [Accordion](/help/adaptive-forms/components/accordion.md)
* [Adaptive Form Fragment](/help/adaptive-forms/components/adaptive-form-fragment.md)
* [Adaptive Form Switch](/help/adaptive-forms/components/adaptive-form-switch.md)
* [Button](/help/adaptive-forms/components/button.md)
* [Check Box Group](/help/adaptive-forms/components/checkbox-group.md)
* [Date Picker](/help/adaptive-forms/components/date-picker.md)
* [Drop-down list](/help/adaptive-forms/components/drop-down-list.md)
* [Email](/help/adaptive-forms/components/email.md)
* [Form Container](/help/adaptive-forms/components/form-container.md)
* [File Attachment](/help/adaptive-forms/components/file-attachment.md)
* [Footer](/help/adaptive-forms/components/footer.md)
* [Header](/help/adaptive-forms/components/header.md)
* [Horizontal Tabs](/help/adaptive-forms/components/horizontal-tabs.md)
* [Image](/help/adaptive-forms/components/image.md)
* [Numeric Box](/help/adaptive-forms/components/numeric-box.md)
* [Panel](/help/adaptive-forms/components/panel.md)
* [Phone](/help/adaptive-forms/components/phone.md)
* [Radio Button](/help/adaptive-forms/components/radio-button.md)
* [Adaptive Form reCAPTCHA](/help/adaptive-forms/components/adaptive-form-recaptcha.md)
* [Reset Button](/help/adaptive-forms/components/reset-button.md)
* [Submit Button](/help/adaptive-forms/components/submit-button.md)
* [Text Box](/help/adaptive-forms/components/text-box.md)
* [Text](/help/adaptive-forms/components/text.md)
* [Form Title](/help/adaptive-forms/components/form-title.md)
* [Wizard](/help/adaptive-forms/components/wizard.md)

-->

## Lättanvänd formulärredigerare

Redigeraren för Core Components based Adaptive Forms liknar den du redan använder för att skapa AEM Sites Pages. Det här får du:


* **Välbekanta gränssnittselement och inställningar**: När du konfigurerar egenskaper för formulärkomponenter ser du en egenskapsdialogruta som liknar den du använder för WCM Core-komponenter. Det gör det snabbare att hitta de alternativ du behöver. Precis som för WCM Core Components visas egenskapsdialogrutan i mitten av redigeraren med tydliga flikar som avgränsar grundläggande och avancerade alternativ, hjälptext och hjälpmedelsinformation - allt i ett flikformat för enkel navigering.

* **[Regelredigeraren](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/rule-editor-core-components)**: Du kan lägga till logiska och dynamiska funktioner i formulären utan att skriva kod. Med den inbyggda regelredigeraren kan du:
   * Visa eller dölj fält baserat på användarval
   * Aktivera eller inaktivera ett objekt
   * Ange ett värde för ett objekt
   * Utför beräkningar
   * Ange ett objekts egenskap
   * Validera datapost
   * Anropa en tjänst (anropa extern funktion)
   * Använd inbyggda funktioner (fördefinierade funktioner för vanliga uppgifter)
   * Använd anpassade funktioner (egen kod för specifika behov)
   * Validera fält och paneler (kontrollera att data uppfyller kraven)
   * Validera ett objekts värde
   * Utför funktioner för att beräkna värdet för ett objekt
   * Anropa en FDM-tjänst (Form Data Model) och utföra en åtgärd
   * Lägg till format dynamiskt (ändra utseendet baserat på villkor)
   * Skapa andra regler (kedjeåtgärder och logik)
   * med mera!

  Regelredigeraren saknar kodredigerare. Du kan använda [anpassade funktioner](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/create-and-use-custom-functions) för att lägga till egen kod för specifika behov i regelredigeraren.



* **Fylla i formulär i förväg**: Du kan automatiskt fylla i vissa fält i ett formulär med befintliga data när en användare öppnar det. Detta sparar tid och arbete eftersom användaren inte behöver ange information som redan är tillgänglig manuellt. Core Components Editor erbjuder en tjänst för OOTB-förifyllning för att fylla i formulärfält med hjälp av en formulärdatamodell. Du kan också skapa anpassade förifyllningstjänster för mer komplexa scenarier.

* **[Registreringsdokument (DoR)](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/generate-document-of-record-core-components)**: En DoR-referens (Document of Record) refererar till en formell, utskrivbar representation av data som skickas via formuläret. Det fungerar som en permanent post för den information en användare angett och ger en ögonblicksbild av inskickade data i ett användarvänligt format, vanligtvis ett PDF-dokument. Du kan använda redigeraren för att enkelt konfigurera en anpassad mall eller använda en OTB-mall för att generera en DoR-fil.

* **[Formulärdatamodell](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/forms/integrate/use-form-data-model/using-form-data-model)**: En adaptiv Forms datamodell (FDM) fungerar som en brygga mellan din adaptiva Forms och dina datakällor. Det definierar i huvudsak strukturen och strukturen för de data som formulären samlar in och interagerar med. Du kan använda redigeraren för att enkelt ansluta formuläret till en Forms datamodell (FDM).

* **[Skicka formulär](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components#:~:text=Adaptive%20Form%20Submit%20Action&text=Adobe%20recommends%20using%20Core%20Components,to%20create%20standalone%20Adaptive%20Forms.&text=A%20Submit%20Action%20lets%20you,button%20on%20an%20Adaptive%20Form)**: En formuläröverföring avser processen för användare som fyller i och skickar sina ifyllda formulär. Detta utlöser en serie åtgärder som definieras i formulärets konfiguration, vilket i slutänden leder till lagring eller bearbetning av skickade data. Den adaptiva Forms-redigeraren erbjuder en mängd alternativ för att konfigurera formulärinskickat material. En del vanliga åtgärder för att skicka är:

   * [Skicka e-post](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components#:~:text=Adaptive%20Form%20Submit%20Action&text=Adobe%20recommends%20using%20Core%20Components,to%20create%20standalone%20Adaptive%20Forms.&text=A%20Submit%20Action%20lets%20you,button%20on%20an%20Adaptive%20Form.)
   * [Anropa ett Power Automate-flöde](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/forms/integrate/services/forms-microsoft-power-automate-integration)
   * [Skicka till SharePoint](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-action-sharepoint)
   * [Anropa en Workfront Fusion](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components#:~:text=Invoke%20a%20Workfront%20Fusion)
   * [Skicka med FDM (Form Data Model)](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/forms/integrate/use-form-data-model/using-form-data-model)
   * [Skicka till Azure Blob Storage](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components#:~:text=Submit%20to%20Azure%20Blob%20Storage)
   * [Skicka till REST-slutpunkt](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-action-restpoint)
   * [Skicka till OneDrive](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components#:~:text=to%20REST%20endpoint-,Submit%20to%20OneDrive,-Invoke%20an%20AEM)
   * [Starta ett AEM-arbetsflöde](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components#:~:text=Invoke%20an%20AEM%20Workflow)


* [Adaptiva Forms Core-komponenter i webbplatssidredigeraren](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page): Du kan aktivera och använda adaptiva Forms Core-komponenter i AEM Page Editor och AEM Experience Fragments för att skapa datainhämtningsupplevelser direkt tillsammans med att skapa en webbplatssida.

  >[!VIDEO](https://video.tv.adobe.com/v/3419284?quality=12&learn=on)


<!-- 
* **Preview Forms**: You can use the editor to  simulates how the form would appear on various devices like desktops, tablets, and smartphones.
-->



## Aktivera adaptiva Forms Core-komponenter

Genom att aktivera adaptiva Forms Core-komponenter i AEM Forms as a Cloud Service kan du börja skapa, publicera och leverera Core Components-baserade adaptiva Forms och Headless Forms med hjälp av AEM Forms Cloud Service-instanser i flera kanaler. Detaljerade instruktioner om hur du aktiverar komponenter i adaptiv Form Core finns i [Aktivera adaptiva Forms Core-komponenter i AEM Forms as a Cloud Service och den lokala utvecklingsmiljön](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/setup-configure-migrate/enable-adaptive-forms-core-components.html?lang=sv-SE).

De adaptiva Forms Core-komponenterna har följande krav.

| AEM Version | AEM Forms-tillägg | Adaptiva Forms Core-komponenter |
|---|---|---|
| AEM as a Cloud Service | Forms - digital registrering | [Version 2.0.10](version.md)+ |
| AEM 6.5 | Forms-tillägg | [Version 1.1.12](version.md)+ |

Om din AEM Cloud Service SDK-version är äldre än 2023.02.0 [kontrollerar du att `prerelease` flagga är aktiverad i din miljö](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/release-notes/prerelease.html?lang=sv-SE#new-features) eftersom adaptiva Forms Core-komponenter ingick i förhandsversionen från 2023.02.0.


## Skapa en grundkomponentbaserad adaptiv form

Du kan utföra följande åtgärder i både AEM Forms as a Cloud Service- och AEM 6.5 Forms-miljöer:

| Åtgärd | AEM Forms Version |
|--------|------------------|
| Skapa ett fristående anpassat formulär | [AEM Forms som Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html?lang=sv-SE) |
| Skapa ett anpassat formulär på AEM Sites Page | [AEM 6.5 Forms](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-basic-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html?lang=sv-SE#create-an-adaptive-form-in-sites-editor-or-experience-fragment), [AEM Forms som Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html?lang=sv-SE#create-an-adaptive-form-in-sites-editor-or-experience-fragment) |
| Skapa ett anpassat formulär i AEM Experience Fragment | [AEM 6.5 Forms](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-basic-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html?lang=sv-SE#create-an-adaptive-form-in-experience-fragment), [AEM Forms som Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html?lang=sv-SE#create-an-adaptive-form-in-experience-fragment) |
| Konvertera ett anpassat formulär till ett upplevelsefragment | [AEM 6.5 Forms](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-basic-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html?lang=sv-SE#convert-an-adaptive-form-in-sites-page-to-an-experience-fragment), [AEM Forms som Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html?lang=sv-SE#convert-an-adaptive-form-in-sites-page-to-an-experience-fragment) |





<!-- >, such as  [WCAG 2.1 standard](https://www.w3.org/TR/WCAG21/), to ensure that forms can be used by people with disabilities, including those using assistive technologies such as screen readers.

*   **Alignment with AEM Sites**: The Core Components are designed to be more aligned with AEM Sites, making it easier for Sites users to adopt and use them without having to learn anything new. The components use the same front-end pipeline as Sites, making it easier to style and modify their appearance. 

<!-- Additionally, the following points further illustrate this alignment:

    *   **Authoring experience inline with Page editor**: The Core Components have an authoring experience that is inline with the Sites editor, with dialogs and other experiences similar to the Page editor. This makes it easier for Sites users to create and manage forms within the familiar context of the Sites editor.

    *   **Inline form editing in Sites editor**: The Core Components allow  inline form editing within the Sites editor, avoiding the need to switch back and forth between editors. This streamlines the authoring experience and makes it easier to create and manage forms.

    *   **Inheriting Sites features in Forms**: Forms authored within a Sites page inherit the same features as Sites. This provides a seamless and integrated experience for creating and managing forms within the context of AEM Sites 
    
    <!--including Multi Site Manager, the ability to use Sites components within a form for static content, support for scheduled publish/unpublish, form translation aligned with Sites translation, versioning, and targeting -->

## Se även {#see-also}

{{see-also}}
