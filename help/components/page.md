---
title: Sidkomponent
description: Page Component (Sidkomponent) är en utökningsbar sidkomponent som är avsedd att fungera tillsammans med mallredigeraren och som gör att sidhuvud/sidfot och strukturkomponenter kan monteras tillsammans med mallredigeraren.
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '666'
ht-degree: 1%

---


# Sidkomponent{#page-component}

Page Component (Sidkomponent) är en utökningsbar sidkomponent som är utformad för att fungera med [mallredigeraren](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html) och som gör att sidhuvud/sidfot och strukturkomponenter kan sättas ihop med mallredigeraren.

## Användning {#usage}

Sidkomponenten utgör grunden för alla sidor som utformats med kärnkomponenterna samt redigerbara mallar. Med hjälp av sidkomponenten kan sidhuvuden, sidfötter och sidstrukturen definieras som en mall med hjälp av de andra huvudkomponenterna.

Med hjälp av [designdialogrutan](#design-dialog)kan du definiera egna klientbibliotek för sidan. Till skillnad från andra komponenter som har en redigeringsdialogruta som är tillgänglig direkt från komponenten, är sidkomponentens [redigeringsdialogruta](#edit-dialog) sidegenskapsfönstret eftersom komponenten är själva sidan.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Page Component är v2, som introducerades i version 2.0.0 av Core Components i januari 2018, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponentversionerna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|---|---|
| v2 | - | Kompatibel | Kompatibel | Kompatibel |
| [v1](v1/page-v1.md) | Kompatibel | Kompatibel | Kompatibel | - |

Mer information om Core Component-versioner och -versioner finns i dokumentet [Core Components Versions](/help/versions.md).

>[!NOTE]
>
>För att aktivera omdirigering på `cq:Page` nivå för version 2 av sidkomponenten och AEM 6.3 krävs [Service Pack 2](https://helpx.adobe.com/experience-manager/6-3/release-notes/sp2-release-notes.html) eller senare. En sådan omdirigering var inte tillgänglig i tidigare versioner.

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Page Component [finns på GitHub](https://adobe.com/go/aem_cmp_tech_page_v2).

Mer information om hur du utvecklar kärnkomponenter finns i dokumentationen till [Core Components Developer](/help/developing/overview.md).

## Dialogrutan Redigera {#edit-dialog}

Eftersom komponenten representerar hela sidan finns de inställningar som normalt skulle finnas i en redigeringsdialogruta i fönstret [Sidegenskaper](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html) .

## Designdialogruta {#design-dialog}

Eftersom komponenten representerar hela sidan öppnas designdialogrutan via **Sidinformation -> Sidprofil** när du redigerar sidmallen.

![Sidprofil](/help/assets/page-policy.png)

>[!NOTE]
>
>I tidigare versioner av AEM kallades **Page Policy** **Page Design**.

### Fliken Egenskaper {#properties-tab}

I fönstret Siddesign kan du definiera vilka klientbibliotek som ska läsas in samt webbresursbiblioteket för sidan.

* **Klientbibliotek** - Detta definierar de klientbibliotekskategorier som ska läsas in. JavaScript läggs till i innehållsslutet och CSS läggs till i sidhuvudet.
* **Klientbibliotek, JavaScript-sidhuvud** - Detta definierar de JavaScript-klientbibliotekskategorier som ska läsas in i sidhuvudet.
   * För de kategorier som definieras här och som också finns i fältet **Klientbibliotek** läses JavaScript in i sidhuvudet i stället för i innehållsslutet.
   * Ingen CSS läses in om inte kategorin också finns i fältet **Klientbibliotek** .

* **Klientbibliotek** för webbresurser - Klientbibliotekskategorin som används för webbresurser som till exempel favoritikoner.

* **Hoppa till väljaren** för elementet i huvudinnehållet - Används som hjälpmedelsfunktion för att hoppa direkt till huvudinnehållet på sidan

![Designdialogruta för sidkomponent](/help/assets/page-design.png)

Bibliotek kan konfigureras för både **klientbibliotek** och JavaScript Page Head **-fält för** klientbibliotek enligt följande:

* Om du vill lägga till ett nytt fält klickar du på eller trycker på knappen **Lägg till** under fälten.
* Om du vill ta bort ett fält klickar du på papperskorgsikonen bredvid fältet som ska tas bort.
* Om du vill ändra inläsningsordningen klickar eller trycker du och drar handtaget bredvid fältet som ska flyttas.

Mer information om hur du använder bibliotek på klientsidan finns i [Använda bibliotek](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/clientlibs.html)på klientsidan.

>[!CAUTION]
>
>Möjligheten att separat definiera klientbibliotek för sidhuvudet introducerades med huvudkomponentversion 2.2.0.

### Fliken Format {#styles-tab}

Page Component har stöd för AEM [Style System](/help/get-started/authoring.md#component-styling).
