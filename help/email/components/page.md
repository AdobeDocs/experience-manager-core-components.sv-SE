---
title: E-postsidkomponent
description: E-postsidkomponenten
role: Architect, Developer, Admin, User
hidefromtoc: true
index: false
source-git-commit: 8bebe3ca036557f3f7c6b8ec0e65d6d104d5ffae
workflow-type: tm+mt
source-wordcount: '804'
ht-degree: 0%

---


# E-postsidkomponent {#email-page-component}

E-postsidkomponenten är en utökningsbar sidkomponent som är utformad för att fungera med [mallredigerare](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html) och gör att sidhuvud/sidfot och strukturkomponenter kan monteras med mallredigeraren, som är anpassad för att skapa Adobe Campaign-innehåll.

## Användning {#usage}

Sidkomponenten E-post utgör grunden för alla sidor som utformats med e-postkärnkomponenter och redigerbara mallar. Genom att använda Sidkomponent för e-post kan sidhuvuden, sidfötter och sidstrukturen definieras som en mall med hjälp av de andra huvudkomponenterna för e-post.

* Använda [Designdialog.](#design-dialog) anpassade klientbibliotek kan definieras för sidan.
* Till skillnad från andra komponenter som har en redigeringsdialogruta som är tillgänglig direkt från komponenten, eftersom e-postsidkomponenten är själva sidan, är [redigeringsdialogruta](#edit-dialog) för e-postsidkomponenten är sidegenskapsfönstret.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av e-postsidkomponenten är v1, som introducerades i version X av e-postkärnkomponenterna i oktober 2022, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | Kompatibel | Kompatibel |

Mer information om e-postkärnkomponentversioner och -versioner finns i dokumentet [Huvudkomponentversioner för e-post](/help/email/versions.md)

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Page Component [finns på GitHub.](https://adobe.com/go/aem_cmp_tech_email_page_v1)

Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Dialogrutan Redigera {#edit-dialog}

Eftersom komponenten representerar hela sidan, finns de inställningar som normalt skulle finnas i en redigeringsdialogruta i [Sidegenskaper](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html) -fönstret.

### Fliken Cloud Services {#cloud-services}

För att e-postkärnkomponenterna ska kunna hämta kampanjvariabler och data måste sidan vara länkad till en Adobe Campaign-konfiguration.

![Egenskaper för e-postsida](/help/email/assets/email-page-properties.png)

Under **Konfiguration av Cloud Service** rubrik, i listrutan väljer **Lägg till konfiguration**.

Under **Adobe Campaign** väljer du konfiguration för integrering med Adobe Campaign.

Se dokumentet [Använda e-postkärnkomponenter](/help/email/using.md) om du vill ha mer information om hur du konfigurerar E-postkärnkomponenter.

### Fliken E-post {#email-tab}

Fliken E-post definierar egenskaper för e-postmeddelanden som skickas via Adobe Campaign utifrån innehållet på den här sidan, till exempel e-postmeddelandets ämne och oformaterad text.

![Egenskaper för e-postsida](/help/email/assets/email-page-properties-email.png)

* **Ämne** - Ämnet för det e-postmeddelande som Adobe Campaign skickar baserat på denna sida
   * Klicka på **Välj Adobe Campaign-variabel** -ikonen för att öppna [Välj Adobe Campaign-variabel](/help/email/campaign-variables.md) för att infoga dynamiskt innehåll från Adobe Campaign.
* **Förrubrik**
   * Klicka på **Välj Adobe Campaign-variabel** -ikonen för att öppna [Välj Adobe Campaign-variabel](/help/email/campaign-variables.md) för att infoga dynamiskt innehåll från Adobe Campaign.
* **Oformaterad text** - Den oformaterade textversionen av e-postmeddelandet som skickas av Adobe Campaign
   * Klicka på **Välj Adobe Campaign-variabel** -ikonen för att öppna [Välj Adobe Campaign-variabel](/help/email/campaign-variables.md) för att infoga dynamiskt innehåll från Adobe Campaign.
* **Referens-URL**

## Designdialogruta {#design-dialog}

Eftersom komponenten representerar hela sidan öppnas designdialogrutan via **Sidinformation -> Sidprofil** när du redigerar sidmallen.

![Sidprofil](/help/assets/page-policy.png)

### Fliken Egenskaper {#properties-tab}

I fönstret Siddesign kan du definiera vilka klientbibliotek som ska läsas in samt webbresursbiblioteket för sidan.

![Designdialogruta för e-postsidkomponent](/help/email/assets/email-page-design.png)

* **Klientbibliotek** - Detta definierar de klientbibliotekskategorier som ska läsas in. JavaScript läggs till i innehållsslutet och CSS läggs till i sidhuvudet.
* **Client Libraries JavaScript Page Head** - Detta definierar de JavaScript-klientbibliotekskategorier som ska läsas in i sidhuvudet.
   * Kategorier som definieras här och som också finns i **Klientbibliotek** ska JavaScript läsas in i sidhuvudet i stället för i slutet.
   * Ingen CSS läses in såvida inte kategorin också finns i **Klientbibliotek** fält.
* **Läs in JavaScript-bibliotek asynkront** - Om det här alternativet är aktiverat läses de anpassade JavaScript-biblioteken in asynkront.
* **Klientbibliotek för webbresurser** - Klientbibliotekskategorin som används för webbresurser som till exempel favoritikoner.
* **Gå till elementväljaren för huvudinnehåll** - Används som hjälpmedelsfunktion för att hoppa direkt till huvudinnehållet på sidan

Bibliotek kan konfigureras för båda **Klientbibliotek** och **Client Libraries JavaScript Page Head** fält enligt följande:

* Om du vill lägga till ett nytt fält klickar eller trycker du på **Lägg till** knappen under fälten.
* Om du vill ta bort ett fält klickar eller trycker du på papperskorgsikonen bredvid fältet som ska tas bort.
* Om du vill ändra inläsningsordningen klickar eller trycker du och drar handtaget bredvid fältet som ska flyttas.

Mer information om hur du använder klientbibliotek finns i [Använda bibliotek på klientsidan.](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/clientlibs.html)

### Fliken Format {#styles-tab}

Page Component har stöd för AEM [Formatsystem](/help/get-started/authoring.md#component-styling).
