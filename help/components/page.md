---
title: Sidkomponent
description: Page Component (Sidkomponent) är en utökningsbar sidkomponent som är avsedd att fungera tillsammans med mallredigeraren och som gör att sidhuvud/sidfot och strukturkomponenter kan monteras tillsammans med mallredigeraren.
role: Architect, Developer, Admin, User
exl-id: 2503e067-abed-427d-8a54-8b79e3451487
source-git-commit: 327c239b02e0aecee878784c918bfa98d960530e
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 0%

---

# Sidkomponent{#page-component}

Sidkomponenten är en utökningsbar sidkomponent som är avsedd att fungera med [mallredigeraren](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html) och som gör att sidhuvud/sidfot och strukturkomponenter kan sättas ihop med mallredigeraren.

## Användning {#usage}

Page Component (Sidkomponent) utgör grunden för alla sidor som utformats med Core Components (kärnkomponenter) samt redigerbara mallar. Med hjälp av sidkomponenten kan sidhuvuden, sidfötter och sidstrukturen definieras som en mall med hjälp av de andra kärnkomponenterna.

Med hjälp av [designdialogrutan](#design-dialog) kan anpassade klientbibliotek definieras för sidan. Till skillnad från andra komponenter som har en redigeringsdialogruta som är tillgänglig direkt från komponenten, eftersom sidkomponenten är själva sidan, är dialogrutan [redigera](#edit-dialog) för sidkomponenten sidegenskapsfönstret.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Page Component är v3, som introducerades i version 2.18.0 av Core Components i februari 2022, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|---|
| v3 | - | Kompatibel | Kompatibel |
| [v2](v2/page.md) | Kompatibel | Kompatibel | Kompatibel |
| [v1](v1/page-v1.md) | Kompatibel | Kompatibel | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Core Components Versions](/help/versions.md).

## Progressivt stöd för webbappar {#pwa-support}

I version 2.15.0 av Core Components introducerades stöd för AEM as a Cloud Service inbyggda [Progressiva webbprogram (PWA).](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/enable-pwa.html) Med en enkel konfiguration på webbplatsnivå kan du omvandla din AEM till en PWA!

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om sidkomponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_page_v3).

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).

## Dialogrutan Redigera {#edit-dialog}

Eftersom komponenten representerar hela sidan, finns inställningar som normalt skulle finnas i en redigeringsdialogruta i fönstret [Sidegenskaper](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html).

## Designdialogruta {#design-dialog}

Eftersom komponenten representerar hela sidan öppnas designdialogrutan via **Sidinformation -> Sidprofil** när du redigerar sidmallen.

![Sidprincip](/help/assets/page-policy.png)

>[!NOTE]
>
>I tidigare versioner av AEM kallades **Sidprofil** **Siddesign**.

### Fliken Egenskaper {#properties-tab}

I fönstret Siddesign kan du definiera vilka klientbibliotek som ska läsas in samt webbresursbiblioteket för sidan.

* **Klientbibliotek** - Detta definierar de klientbibliotekskategorier som ska läsas in. JavaScript läggs till i innehållsslutet och CSS läggs till i sidhuvudet.
* **Klientbibliotek JavaScript sidhuvud** - Här definieras de bibliotekskategorier för JavaScript Client som ska läsas in i sidhuvudet.
   * För de kategorier som definieras här och som också finns i fältet **Klientbibliotek** läses JavaScript in i sidhuvudet i stället för i innehållsslutet.
   * Ingen CSS läses in om inte kategorin också finns i fältet **Klientbibliotek**.

* **Klientbibliotek för webbresurser** - Klientbibliotekskategorin som används för webbresurser som till exempel favoritikoner.

* **Hoppa till väljaren för elementet i huvudinnehållet** - Används som hjälpmedelsfunktion för att hoppa direkt till huvudinnehållet på sidan

* **Återge alternativa språklänkar** - Om det här alternativet är aktiverat läggs länkar till alternativa språkversioner av sidan på samma webbplats till i sidhuvudet.

![Utformningsdialogruta för sidkomponent](/help/assets/page-design.png)

Bibliotek kan konfigureras för både fälten **Klientbibliotek** och **Klientbibliotek JavaScript sidhuvud** enligt följande:

* Klicka eller tryck på knappen **Lägg till** under fälten om du vill lägga till ett nytt fält.
* Om du vill ta bort ett fält klickar du på papperskorgsikonen bredvid fältet som ska tas bort.
* Om du vill ändra inläsningsordningen klickar eller trycker du och drar handtaget bredvid fältet som ska flyttas.

Mer information om hur du använder bibliotek på klientsidan finns i [Använda bibliotek på klientsidan](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/clientlibs.html).

>[!CAUTION]
>
>Möjligheten att separat definiera klientbibliotek för sidhuvudet introducerades med huvudkomponentversion 2.2.0.

### Fliken Format {#styles-tab}

Sidkomponenten stöder AEM [Style System](/help/get-started/authoring.md#component-styling).

## Adobe-klientdatalager {#data-layer}

Sidkomponenten stöder datalagret [Adobe Client.](/help/developing/data-layer/overview.md)
