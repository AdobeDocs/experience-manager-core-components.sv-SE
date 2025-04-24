---
title: E-postsidkomponent
description: E-postsidkomponenten
role: Architect, Developer, Admin, User
exl-id: 17fd0f5e-2b85-41a1-abaf-8ad190a5341a
source-git-commit: 91969e4956bef1a511b8d588d5290a7999bf86ec
workflow-type: tm+mt
source-wordcount: '780'
ht-degree: 0%

---


# E-postsidkomponent {#email-page-component}

Sidkomponenten för e-post är en utökningsbar sidkomponent som är utformad för att fungera med [mallredigeraren](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html) och som gör att sidhuvud/sidfot och strukturkomponenter kan sättas ihop med mallredigeraren, som är anpassad för att skapa Adobe Campaign-innehåll.

## Användning {#usage}

Sidkomponenten E-post utgör grunden för alla sidor som utformats med e-postkärnkomponenter och redigerbara mallar. Genom att använda Sidkomponent för e-post kan sidhuvuden, sidfötter och sidstrukturen definieras som en mall med hjälp av de andra huvudkomponenterna för e-post.

* Med hjälp av designdialogrutan [kan ](#design-dialog) anpassade klientbibliotek definieras för sidan.
* Till skillnad från andra komponenter som har en redigeringsdialogruta som är tillgänglig direkt från komponenten, eftersom e-postsidkomponenten är själva sidan, är [redigeringsdialogrutan](#edit-dialog) för e-postsidkomponenten sidegenskapsfönstret.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av e-postsidkomponenten är v1, som introducerades i version X av e-postkärnkomponenterna i oktober 2022, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponenterna är kompatibla med samt länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|---|---|---|---|
| v1 | Kompatibel | - | - |

Mer information om grundkomponentversioner och releaser för e-postmeddelanden finns i dokumentet [E-postversioner av kärnkomponenter](/help/email/versions.md)

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om sidkomponenten [finns på GitHub.](https://adobe.com/go/aem_cmp_tech_email_page_v1)

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).

## Dialogrutan Redigera {#edit-dialog}

Eftersom komponenten representerar hela sidan, finns inställningar som normalt skulle finnas i en redigeringsdialogruta i fönstret [Sidegenskaper](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html).

### Fliken Molntjänster {#cloud-services}

För att e-postkärnkomponenterna ska kunna hämta kampanjvariabler och data måste sidan vara länkad till en Adobe Campaign-konfiguration.

![Egenskaper för e-postsida](/help/email/assets/email-page-properties.png)

Under rubriken **Cloud Service Configuration** väljer du **Add Configuration** i listrutan.

Under rubriken **Adobe Campaign** väljer du konfigurationen för din integrering med Adobe Campaign.

Mer information om hur du konfigurerar e-postkärnkomponenter finns i dokumentet [Använda e-postkärnkomponenter](/help/email/using.md).

### Fliken E-post {#email-tab}

Fliken E-post definierar egenskaper för e-postmeddelanden som skickas via Adobe Campaign utifrån innehållet på den här sidan, till exempel e-postmeddelandets ämne och oformaterad text.

![Egenskaper för e-postsida](/help/email/assets/email-page-properties-email.png)

* **Ämne** - Ämnet för e-postmeddelandet som skickas av Adobe Campaign baserat på den här sidan
   * Klicka på ikonen **Välj Adobe Campaign-variabel** för att öppna dialogrutan [Välj Adobe Campaign-variabel](/help/email/campaign-variables.md) och infoga dynamiskt innehåll från Adobe Campaign.
* **Förrubrik**
   * Klicka på ikonen **Välj Adobe Campaign-variabel** för att öppna dialogrutan [Välj Adobe Campaign-variabel](/help/email/campaign-variables.md) och infoga dynamiskt innehåll från Adobe Campaign.
* **Oformaterad text** - Den oformaterade textversionen av e-postmeddelandet som skickas av Adobe Campaign
   * Klicka på ikonen **Välj Adobe Campaign-variabel** för att öppna dialogrutan [Välj Adobe Campaign-variabel](/help/email/campaign-variables.md) och infoga dynamiskt innehåll från Adobe Campaign.
* **Referens-URL**

## Designdialogruta {#design-dialog}

Eftersom komponenten representerar hela sidan öppnas designdialogrutan via **Sidinformation -> Sidprofil** när du redigerar sidmallen.

![Sidprincip](/help/assets/page-policy.png)

### Fliken Egenskaper {#properties-tab}

I fönstret Siddesign kan du definiera vilka klientbibliotek som ska läsas in samt webbresursbiblioteket för sidan.

![Dialogrutan Utformning av sidkomponent för e-post](/help/email/assets/email-page-design.png)

* **Klientbibliotek** - Detta definierar de klientbibliotekskategorier som ska läsas in. JavaScript läggs till i innehållsslutet och CSS läggs till i sidhuvudet.
* **Klientbibliotek JavaScript sidhuvud** - Här definieras de JavaScript klientbibliotekskategorier som ska läsas in i sidhuvudet.
   * För de kategorier som definieras här och som också finns i fältet **Klientbibliotek** läses JavaScript in i sidhuvudet i stället för i innehållsslutet.
   * Ingen CSS läses in om inte kategorin också finns i fältet **Klientbibliotek**.
* **Läs in JavaScript-bibliotek asynkront** - Om det här alternativet är aktiverat läses de anpassade JavaScript-biblioteken in asynkront.
* **Klientbibliotek för webbresurser** - Klientbibliotekskategorin som används för webbresurser som till exempel favoritikoner.
* **Hoppa till väljaren för elementet i huvudinnehållet** - Används som hjälpmedelsfunktion för att hoppa direkt till huvudinnehållet på sidan

Bibliotek kan konfigureras för både fälten **Klientbibliotek** och **Klientbibliotek JavaScript sidhuvud** enligt följande:

* Klicka eller tryck på knappen **Lägg till** under fälten om du vill lägga till ett nytt fält.
* Om du vill ta bort ett fält klickar eller trycker du på papperskorgsikonen bredvid fältet som ska tas bort.
* Om du vill ändra inläsningsordningen klickar eller trycker du och drar handtaget bredvid fältet som ska flyttas.

Mer information om hur du använder bibliotek på klientsidan finns i [Använda bibliotek på klientsidan.](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/clientlibs.html)

### Fliken Format {#styles-tab}

Sidkomponenten stöder AEM [Style System](/help/get-started/authoring.md#component-styling).
