---
title: Hur får du exempelteman och mallar för AEM Forms Core Components?
description: AEM Forms Core Components innehåller exempel på adaptiva formulärteman, mallar och formulärdatamodeller.
solution: Experience Manager Forms
topic: Administration
role: Admin, User
level: Intermediate
exl-id: aef6e88b-dcae-4777-9893-9257d7702f43
source-git-commit: 0f0c20c9fba6f062021721d6f48a42cc830b5a7c
workflow-type: tm+mt
source-wordcount: '1239'
ht-degree: 0%

---

# Exempelteman, mallar och formulärdatamodeller {#sample-themes-templates-and-data-models}

[!DNL AEM Forms] Core Components tillhandahåller färdiga exempelteman, mallar och formulärdatamodeller för att snabbt skapa flexibla formulär. Dessa hjälper också formulärförfattare att lära sig hur flexibla [adaptiva Forms Core-komponenter](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html?lang=sv-SE) är och hur snabbt de ska kunna skapa enkla formulär på nolltid och komplexa formulär utan problem när de ansluter till databasen.

Exempelteman, mallar och formulärdatamodeller som ingår i referensinnehållspaketet är:

| Mallar | Teman | Formulärdatamodeller |
---------|----------|---------
| [Tom](#Blank) | [Arbetsyta](#Canvas) | Microsoft® Dynamics 365 |
| [Kontakta oss](#Contact-Us) | [WKND](#WKND) | Salesforce |
| [Uppdatera kontaktinformation](#Contact-Details-Update) | [Easel](#Easel) |   |
| [Samtyckesformulär](#Consent-Form) | [FSI](#FSI) |  |
| [Loggtjänstbegäran](#Log-Service-Request) | [Hälsovård](#Healthcare) |  |
| [Ge feedback](#Give-Feedback) |  |  |
| [Registrering av förmåner](#Benefits-Enrollment) |  |   |
| [Sammanfattning av medarbetarförmåner](#Employee-Benefits-Summary) |   |   |
| [Begär kontoutdrag](#Request-for-Account-Statement) |   |   |
| [Formulär för säkerhetskontroll](#Safety-Inspection) |   |   |
| [Kvalitetskontrollsinspektion](#Quality-Control-Inspection) |   |   |
| [Inköpsbegäran](#Purchase-Request) |  |  |

## Exempelteman {#Sample-Themes}

Med exempelteman kan man använda, definiera och anpassa formateringen efter blanketterna - författare med t.o.m. grundläggande kunskaper i CSS kan anpassa temat efter behov.

**Hur skaffar jag teman?**
Du får dessa teman genom att följa stegen nedan för **AEM as a Cloud Service** -miljön:

1. [Aktivera kärnkomponenter för adaptiva formulär](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/setup-configure-migrate/enable-adaptive-forms-core-components.html?lang=sv-SE)
1. [Distribuera ett AEM Archetype 47-projekt eller senare till din miljö](https://github.com/adobe/aem-project-archetype)


När du distribuerar en AEM-arkitektur kan du bara använda OTB-teman i dina formulär. Om du vill anpassa teman efter dina behov kan du [använda frontpipeline](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-themes-in-core-components.html?lang=sv-SE) för att distribuera teman.

>[!NOTE]
>
> * Temana är inte tillgängliga för miljön **AEM 6.5**.

<!--

1. **AEM 6.5**

    1. [Enable Adaptive Form Core Components](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-core-components/enable-adaptive-forms-core-components.html?lang=sv-SE)
    1. [Deploy an AEM Archetype 47 or later project to your environment](https://github.com/adobe/aem-project-archetype)


    When you deploy an AEM Archetype, you can only use the OOTB themes in your forms, To customize the themes as per your requirements, [Use the front-end pipeline](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-core-components/create-or-customize-themes-for-adaptive-forms-core-components.html?lang=sv-SE) to deploy the themes.

-->


<!--

### Deploying an AEM Archetype 47 or later project to your environment {#using-archetype-to-deploy-themes}

You can get these themes by deploying an [AEM Archetype 47 or later](https://github.com/adobe/aem-project-archetype) to your **AEM Forms as a Cloud Service** or **AEM 6.5** Forms environment.

### Enable core components and use front-end pipeline to deploy themes {#use-front-end-pipeline-to-deploy-themes}

1. To get these themes on **Forms as a Cloud Service** environment, [enable Adaptive Forms Core Components](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/setup-configure-migrate/enable-adaptive-forms-core-components.html?lang=sv-SE) and use the [front-end pipeline](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-themes-in-core-components.html?lang=sv-SE) to deploy these themes.
    
1. To get these themes on **AEM 6.5 Forms** environment, [enable Adaptive Forms Core Components](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-core-components/enable-adaptive-forms-core-components.html?lang=sv-SE) and use the [Package Manager](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-core-components/create-or-customize-themes-for-adaptive-forms-core-components.html?lang=sv-SE) to deploy these themes.

[Learn to use and customize themes in AEM Forms as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-themes-in-core-components.html?lang=sv-SE). 

[Learn to use and customize themes in AEM 6.5](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-core-components/create-or-customize-themes-for-adaptive-forms-core-components.html?lang=sv-SE).

-->

**i rutan** [Kärnkomponenter för adaptiv form](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html?lang=sv-SE) innehåller följande teman:

![OTB-teman](/help/adaptive-forms/assets/archetype-45-themes-1.png)

### Arbetsyta {#Canvas}

Arbetsytans tema är standardtema för formulär och betonar användningen av grundläggande färger, genomskinlighet och platta ikoner. På skärmbilden nedan ser du hur Canvas-temat ser ut.

![Arbetsytans tema](/help/adaptive-forms/assets/Safety-Inspection-Theme-Canvas.png)

### WKND {#WKND}

WKND-temat innehåller en livlig, fantasifull och engagerande design som visar ett snyggt utseende på dina formulär. Temat baseras på utseendet och formatet på [WKND-webbplatsen](https://wknd.site/us/en.html), som är en rese- och äventyrswebbplats som bygger på [Adobe Experience Manager Core Components](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html?lang=sv-SE).

![WKND-tema](/help/adaptive-forms/assets/Safety-Inspection-Form-Theme.png)


### Easel {#Easel}

Easel-temat hjälper dig att skapa ett snyggt och lättkonfigurerat formulärutseende som är anpassat för enkelhet och användarvänlighet. Easeltemat bygger på konceptet där en bärbar stativ används av konstnärer för att stödja en arbetsyta medan de arbetar med sina målningar.

![Easel-tema](/help/adaptive-forms/assets/Safety-Inspection-Theme-Easel.png)

### FSI (Finansiella tjänster och försäkringar) {#FSI}

FSI-temat lägger vikt vid att ge din form ett rent och praktiskt utseende. Den milda nyansen blått används i formuläret när du använder FSI-temat, vilket du kan se i bilden.

![FSI-tema](/help/adaptive-forms/assets/fsi-theme-new1.png)


### Sjukvård {#Healthcare}

Temat för hälso- och sjukvård använder avancerade, övertoningar för att framhäva element som tabbar, paneler, textrutor och knappar i formuläret.

![Vårdtema](/help/adaptive-forms/assets/healthcare-new-theme.png)


## Exempelmallar {#Sample-templates}

Mallar definierar den inledande formulärstrukturen, innehållet och de åtgärder som ska replikeras i formuläret eller använder en mallstruktur som liknar den i formuläret, till exempel Samtyckesformulär, Förmånsregistreringsformulär och många andra.

**Hur skaffar jag mallarna?**

Du kan hämta de här mallarna genom att distribuera en [AEM Archetype 47 eller senare](https://github.com/adobe/aem-project-archetype) till din **AEM Forms as a Cloud Service** -miljö eller **AEM 6.5 Forms** -miljö.

<!--

>[!NOTE]
>
> * If you have [enabled core components and used front-end pipeline to deploy themes](#use-front-end-pipeline-to-deploy-themes), you need not to deploy an AEM Archetype.
> * You can find list of all OOTB templates when you create a form.

-->


**i rutan** [Kärnkomponenter för adaptiva formulär](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html?lang=sv-SE) är:

![Referensmallar](/help/adaptive-forms/assets/reference-templates-core-components.png)

<!--

### Basic {#Basic}

A basic template helps you quickly create an enrollment experience form. You can also use it to preview the functionality of [Adaptive Forms Core Components](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html?lang=sv-SE). It provides a wizard layout for section-by-section presentation of data.

![Basic Template](/help/adaptive-forms/assets/Basic-template-desktop-view.png)

-->

### Tom {#Blank}

En tom arbetsytemall används för att skapa en anpassad formulärstruktur, innehåll och regler från grunden. Inga formulärkomponenter har förintegrerats i den tomma mallen.

![Tom mall](/help/adaptive-forms/assets/Blank-temp-desktop-view.png)

### Kontakta oss {#Contact-Us}

Använd vår formulärmall för att skapa ett formulär som underlättar kommunikationen mellan webbplatsbesökare och formuläradministratörer. Användare kan skicka frågor, feedback eller supportförfrågningar via formuläret.

![Kontakta oss-mall](/help/adaptive-forms/assets/Contact-us-desktop-view.png)

### Uppdatering av kontaktinformation {#Contact-Details-Update}

Kontaktuppgifter uppdaterar mallar så att författare kan skapa ett formulär för att uppdatera kundens adress och kontaktinformation. Blanketten kan även hjälpa kunderna att uppdatera personuppgifter som rör prenumeration eller förmåner för att säkerställa smidig kommunikation och oavbruten tillgång till tjänsterna eller förmånerna.

![Kontaktinformation-uppdatering](/help/adaptive-forms/assets/Contact-details-update.png)

### Samtyckesformulär {#Consent-Form}

Blankettmallen för samtycke används för att skapa ett formulär för att köpa ett juridiskt dokument från deltagare som deltar i en viss verksamhet, en forskningsundersökning, ett medicinskt förfarande eller en situation där deras personuppgifter eller rättigheter kan vara inblandade. Formuläret säkerställer öppenhet, skyddar deltagarens rättigheter och skapar en tydlig förståelse för vad personen går med på.

![Samtyckesformulär](/help/adaptive-forms/assets/Consent-form-desktop-view.png)

### Loggtjänstbegäran {#Log-Service-Request}

Med loggtjänstens begärandemall kan du skapa ett formulär som begär loggspecifika loggningstjänster från en tjänsteleverantör. Formuläret fungerar som en formell begäran om att skapa en biljett för händelser, aktiviteter eller dataloggar för övervakning eller spårningsstatus.

![Loggtjänstbegärandemall](/help/adaptive-forms/assets/Log-service-request-desktop-view.png)


### Ge feedback {#Give-Feedback}

Ge feedback-formulärmallar hjälper till att skapa ett formulär som ger konstruktiv feedback till en annan person eller grupp. Formuläret ser till att det är tydligt, specifikt och åtgärdbart att ge feedback, vilket främjar öppen kommunikation och förbättring.

![Ge feedback-mall](/help/adaptive-forms/assets/Give-feedback-desktop-view.png)


### Registrering av förmåner {#Benefits-Enrollment}

Blankettmall för förmånsregistrering används för att skapa ett formulär som samlar in viktig information från medarbetarna om vilka förmåner de föredrar och vilka täckningsalternativ de har. Det är vanligtvis en del av den årliga perioden för förmånsregistrering.

![Registreringsmall för förmåner](/help/adaptive-forms/assets/Benefits-enrollment-form-template.png)


### Sammanfattning av medarbetarförmåner {#Employee-Benefits-Summary}

En mall för en sammanfattande mall för löneförmåner används för att skapa ett formulär som samlar in viktig information om en persons förmåner. Det hjälper till att snabbt och korrekt utvärdera täckningen och ger en heltäckande översikt för effektivt stöd och stöd.
![Sammanfattning av anställningsförmåner](/help/adaptive-forms/assets/Employee-benefits-summary.png)


### Kontoutdrag för förfrågan {#Request-for-Account-Statement}

En mall för kontoutdrag hjälper till att skapa ett formulär som initierar processen att få en korrekt och aktuell kundredovisning. Rapporten innehåller detaljerad information om finansiella transaktioner, aktiviteter eller annan relevant information om kunder som använder formuläret.

![Request-for-account-statement](/help/adaptive-forms/assets/Request-for-account-statment.png)

### Säkerhetsinspektion {#Safety-Inspection}

Formulärmallen för säkerhetsinspektioner hjälper till att skapa ett formulär med inmatningsinformation för en säker arbetsmiljö. Genom regelbundna inspektioner med hjälp av denna blankett kan potentiella risker identifieras. Formuläret omfattar olika aspekter såsom nödutgångar, brandsäkerhet, elsäkerhet, farligt material, personlig skyddsutrustning, arbetsstationens ergonomi för anställdas, besökares och kunders säkerhet och välbefinnande.

![Säkerhetskontrollformulär](/help/adaptive-forms/assets/Safety-inspection-form.png)

### Kvalitetskontrollinspektion {#Quality-Control-Inspection}

Formulärmallen för kvalitetskontroll används för att skapa ett formulär för att bedöma och dokumentera en produkts eller objektets visuella utseende, dimensioner, funktionalitet, dokumentation, testresultat och övergripande kvalitet. Det hjälper till att identifiera brister, avvikelser och korrigerande åtgärder som är nödvändiga för att säkerställa att kvalitetsnormerna följs.

![Kvalitetskontrollinspektion](/help/adaptive-forms/assets/Quality-Control-Inspection.png)


### Inköpsbegäran {#Purchase-Request}

Formulärmallen för inköpsbegäran hjälper till att skapa ett formulär som initierar upphandlingsprocessen och gör det möjligt för medarbetarna att formellt begära inköp av varor eller tjänster som är nödvändiga för deras arbete. Formuläret innehåller viktig information som artikelbeskrivning, kvantitet, föredragen leverantör (om tillämpligt), budgetallokering, motivering för inköp, leveransinformation och obligatoriska godkännanden.

![purchase-request-form](/help/adaptive-forms/assets/Purchase-request-form.png)

## Referensformulärdatamodeller {#reference-models}

När du har skapat ett adaptivt formulär baserat på [kärnkomponenten](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html?lang=sv-SE) kan du ansluta formuläret med databasservrarna Microsoft® Dynamics 365 och Salesforce för att aktivera arbetsflöden. Till exempel:

* Skriv data i Microsoft® Dynamics 365 och Salesforce när du skickar adaptiva formulär.
* Skriv data i Microsoft® Dynamics 365 och Salesforce via anpassade entiteter som definierats i formulärdatamodellen och vice versa.
* Fråga Microsoft® Dynamics 365- och Salesforce-servern efter data och fyll i Adaptiv Forms i förväg.
* Läs data från Microsoft® Dynamics 365- och Salesforce-servern.

Du kan hämta följande formulärdatamodeller genom att installera [referensinnehållspaketet](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-forms-reference-content.ui.content-2.1.0.zip):

* Microsoft® Dynamics 365
* Salesforce

Information om hur du använder de här modellerna finns i [Konfigurera molntjänsterna Microsoft® Dynamics 365 och Salesforce](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/integrate/use-form-data-model/configure-msdynamics-salesforce.html?lang=sv-SE#configure-dynamics-cloud-service)
