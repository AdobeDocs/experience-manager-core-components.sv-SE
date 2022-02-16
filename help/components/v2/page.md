---
title: Sidkomponent (v2)
description: Page Component (Sidkomponent) är en utökningsbar sidkomponent som är avsedd att fungera tillsammans med mallredigeraren och som gör att sidhuvud/sidfot och strukturkomponenter kan monteras tillsammans med mallredigeraren.
role: Architect, Developer, Admin, User
source-git-commit: e5251010ca41025eb2bb56b66164ecf4cc0145c8
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 0%

---


# Sidkomponent (v2) {#page-component}

Sidkomponenten är en utökningsbar sidkomponent som är avsedd att fungera med [mallredigerare](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html) och gör att sidhuvud/sidfot och strukturkomponenter kan sättas ihop med mallredigeraren.

## Användning {#usage}

Page Component (Sidkomponent) utgör grunden för alla sidor som utformats med Core Components (kärnkomponenter) samt redigerbara mallar. Med hjälp av sidkomponenten kan sidhuvuden, sidfötter och sidstrukturen definieras som en mall med hjälp av de andra kärnkomponenterna.

Använda [designdialogruta](#design-dialog)kan anpassade klientbibliotek definieras för sidan. Till skillnad från andra komponenter som har en redigeringsdialogruta som är tillgänglig direkt från komponenten, eftersom sidkomponenten är själva sidan, är [redigeringsdialogruta](#edit-dialog) för Page Component (Sidkomponent) är sidegenskapsfönstret.

## Version och kompatibilitet {#version-and-compatibility}

I det här dokumentet beskrivs v2 av Page Component, som introducerades i version 2.0.0 av Core Components i januari 2018.

>[!CAUTION]
>
>I det här dokumentet beskrivs v2 för sidkomponenten.
>
>Information om den aktuella versionen av sidkomponenten finns i [Sidkomponent](/help/components/page.md) -dokument.

## Progressivt stöd för webbappar {#pwa-support}

I version 2.15.0 av Core Components introducerades stöd för AEM as a Cloud Service inbyggda [Progressiva webbprogram (PWA) - funktioner.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/enable-pwa.html) Med en enkel konfiguration på webbplatsnivå kan du omvandla din AEM till en PWA!

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Page Component [finns på GitHub](https://adobe.com/go/aem_cmp_tech_page_v2).

Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Dialogrutan Redigera {#edit-dialog}

Eftersom komponenten representerar hela sidan, finns de inställningar som normalt skulle finnas i en redigeringsdialogruta i [Sidegenskaper](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html) -fönstret.

## Designdialogruta {#design-dialog}

Eftersom komponenten representerar hela sidan öppnas designdialogrutan via **Sidinformation -> Sidprofil** när du redigerar sidmallen.

![Sidprofil](/help/assets/page-policy.png)

>[!NOTE]
>
>I tidigare versioner av AEM **Sidprofil** anropades **Siddesign**.

### Fliken Egenskaper {#properties-tab}

I fönstret Siddesign kan du definiera vilka klientbibliotek som ska läsas in samt webbresursbiblioteket för sidan.

* **Klientbibliotek** - Detta definierar de klientbibliotekskategorier som ska läsas in. JavaScript läggs till i innehållsslutet och CSS läggs till i sidhuvudet.
* **Client Libraries JavaScript Page Head** - Detta definierar de JavaScript-bibliotekskategorier som ska läsas in i sidhuvudet.
   * Kategorier som definieras här och som också finns i **Klientbibliotek** ska JavaScript läsas in i sidhuvudet i stället för i slutet.
   * Ingen CSS läses in såvida inte kategorin också finns i **Klientbibliotek** fält.

* **Klientbibliotek för webbresurser** - Klientbibliotekskategorin som används för webbresurser som till exempel favoritikoner.

* **Gå till elementväljaren för huvudinnehåll** - Används som hjälpmedelsfunktion för att hoppa direkt till huvudinnehållet på sidan

![Designdialogruta för sidkomponent](/help/assets/page-design.png)

Bibliotek kan konfigureras för båda **Klientbibliotek** och **Client Libraries JavaScript Page Head** fält enligt följande:

* Om du vill lägga till ett nytt fält klickar du på **Lägg till** knappen under fälten.
* Om du vill ta bort ett fält klickar du på papperskorgsikonen bredvid fältet som ska tas bort.
* Om du vill ändra inläsningsordningen klickar eller trycker du och drar handtaget bredvid fältet som ska flyttas.

Mer information om hur du använder klientbibliotek finns i [Använda bibliotek på klientsidan](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/clientlibs.html).

>[!CAUTION]
>
>Möjligheten att separat definiera klientbibliotek för sidhuvudet introducerades med huvudkomponentversion 2.2.0.

### Fliken Format {#styles-tab}

Page Component har stöd för AEM [Formatsystem](/help/get-started/authoring.md#component-styling).

## Adobe-klientdatalager {#data-layer}

Page Component har stöd för [Adobe Client Data Layer.](/help/developing/data-layer/overview.md)
