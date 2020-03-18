---
title: Breadcrumb-komponent
description: Komponenten Core Component Breadcrumb är en navigeringskomponent som skapar en rad länkar baserat på sidans plats i innehållshierarkin.
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# Breadcrumb-komponent{#breadcrumb-component}

Komponenten Core Component Breadcrumb är en navigeringskomponent som skapar en rad länkar baserat på sidans plats i innehållshierarkin.

## Användning {#usage}

Komponenten Breadcrumb visar den aktuella sidans position i platshierarkin, vilket gör att sidbesökare kan navigera i sidhierarkin från sin aktuella plats. Detta är ofta integrerat i sidhuvuden och sidfötter.

Tillgängliga alternativ, t.ex. standardnavigeringsnivån och möjligheten att visa den aktuella sidan eller dolda sidor, kan definieras av mallskaparen i [designdialogrutan](#design-dialog). Innehållsredigeraren kan sedan välja om dolda sidor ska visas eller inte och den faktiska navigeringsnivån för komponenten i [redigeringsdialogrutan](#edit-dialog).

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Breadcrumb Component är v2, som introducerades i version 2.0.0 av Core Components i januari 2018, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponentversionerna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |--- |---|
| v2 | Kompatibel | Kompatibel | Kompatibel | Kompatibel |
| [v1](v1/breadcrumb-v1.md) | Kompatibel | Kompatibel | Kompatibel | - |

Mer information om Core Component-versioner och -versioner finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill visa Breadcrumb Component (Breadcrumb-komponenten) och se exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_breadcrumb).

>[!NOTE]
>
>Från och med Core Components version 2.1.0 stöder Breadcrumb-komponenten [schema.org-mikrodata](https://schema.org/BreadcrumbList).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Breadcrumb Component [finns på GitHub](https://adobe.com/go/aem_cmp_tech_breadcrumb_v2).

Mer information om hur du utvecklar kärnkomponenter finns i dokumentationen till [Core Components Developer](/help/developing/overview.md).

## Dialogrutan Redigera {#edit-dialog}

I redigeringsdialogrutan kan innehållsförfattaren utelämna dolda och aktiva sidor i vägbeskrivningar samt djupet i den hierarki som ska visas.

![](/help/assets/screen_shot_2018-01-12at124250.png)

* **Startnivå** för navigering - Där i hierarkin den synliga komponenten ska börja gå ned till den aktuella sidan. Exempel i We.Retail:

   * 0 börjar vid `/content`
   * 1 börjar vid `/content/we-retail`
   * 2 börjar vid `/content/we-retail/<country>`

* **Visa dolda navigeringsobjekt** - Visa sidor som är markerade som dolda i navigeringsfältet (som standard visas de inte)
* **Dölj aktuell sida**- Utelämna den aktuella sidan i sidutrymmet (som standard visas den)

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera vilka standardvärden som ska användas för att inaktivera dolda och aktiva sidor i vägbeskrivningarna samt djupet i den hierarki som ska visas.

### Huvudflik {#main-tab}

![](/help/assets/screen_shot_2018-01-12at124437.png)

* **Startnivå** för navigering - Definierar standardvärdet för var i hierarkin den synliga komponenten ska börja gå ned till den aktuella sidan när den synliga komponenten läggs till på en sida.
* **Visa dolda navigeringsobjekt** - Definierar standardvärdet för alternativet **Visa dolda navigeringsobjekt** när den synliga komponenten läggs till på en sida.

   * Det aktiverar eller inaktiverar inte alternativet för författaren. Det anger bara standardvärdet.

* **Dölj aktuell sida**- Definierar standardvärdet för alternativet **Dölj aktuell sida** när den synliga komponenten läggs till på en sida.

   * Det aktiverar eller inaktiverar inte alternativet för författaren. Det anger bara standardvärdet.

### Fliken Format {#styles-tab}

Komponenten Breadcrumb har stöd för AEM [Style System](/help/get-started/authoring.md#component-styling).
