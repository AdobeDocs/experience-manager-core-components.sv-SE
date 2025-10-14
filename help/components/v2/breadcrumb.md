---
title: Breadcrumb-komponent (v2)
description: Komponenten Core Component Breadcrumb är en navigeringskomponent som skapar en rad länkar baserat på sidans plats i innehållshierarkin.
role: Architect, Developer, Admin, User
exl-id: 5f2e6fef-e2f6-48e2-8dac-008db3131044
index: n
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: tm+mt
source-wordcount: '673'
ht-degree: 0%

---


# Breadcrumb-komponent (v2) {#breadcrumb-component}

Komponenten Core Component Breadcrumb är en navigeringskomponent som skapar en rad länkar baserat på sidans plats i innehållshierarkin.

## Användning {#usage}

Komponenten Breadcrumb visar positionen för den aktuella sidan i platshierarkin, vilket gör att sidbesökare kan navigera i sidhierarkin från sin aktuella plats. Detta är ofta integrerat i sidhuvuden och sidfötter.

Tillgängliga alternativ, till exempel standardnavigeringsnivån och möjligheten att visa den aktuella sidan eller dolda sidor, kan definieras av mallskaparen i [designdialogrutan](#design-dialog). Innehållsredigeraren kan sedan välja om dolda sidor ska visas eller inte och den faktiska navigeringsnivån för komponenten i [redigeringsdialogrutan](#edit-dialog).

## Version och kompatibilitet {#version-and-compatibility}

I det här dokumentet beskrivs v2 av Breadcrumb Component, som introducerades i version 2.0.0 av Core Components i januari 2018.

>[!CAUTION]
>
>I det här dokumentet beskrivs v2 för Breadcrumb-komponenten.
>
>Information om den aktuella versionen av Breadcrumb-komponenten finns i dokumentet [Breadcrumb Component](/help/components/breadcrumb.md) .

## Exempel på komponentutdata {#sample-component-output}

Om du vill visa Breadcrumb-komponenten och se exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_breadcrumb).

>[!NOTE]
>
>Från och med Core Components version 2.1.0 stöder Breadcrumb-komponenten [schema.org &#x200B;](https://schema.org/BreadcrumbList).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Breadcrumb-komponenten [&#x200B; finns på GitHub](https://adobe.com/go/aem_cmp_tech_breadcrumb_v2).

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).

## Dialogrutan Redigera {#edit-dialog}

I redigeringsdialogrutan kan innehållsförfattaren utelämna dolda och aktiva sidor i vägbeskrivningar samt djupet i den hierarki som ska visas.

![Dialogrutan Redigera komponent vid spreadcrumb](/help/assets/breadcrumb-edit.png)

* **Navigeringsstartnivå** - Där i hierarkin den synliga komponenten ska börja gå ned till den aktuella sidan. Till exempel:

   * 0 börjar `/content`
   * 1 börjar `/content/<yourSite>`
   * 2 börjar `/content/<yourSite>/<country>`

* **Visa dolda navigeringsobjekt** - Visa sidor som markerats som dolda i navigeringsfältet (som standard visas de inte)
* **Dölj aktuell sida** - Utelämna den aktuella sidan i den synliga sökvägen (som standard visas den)
* **Inaktivera skuggning** - Om sidan i hierarkin är en omdirigering visas namnet på omdirigeringssidan i stället för målet. Mer information finns i [Stöd för skuggplatsstruktur](../v1/navigation.md#shadow-structure) för navigeringskomponenten.
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [datalagret](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera vilka standardvärden som ska användas för att inaktivera dolda och aktiva sidor i vägbeskrivningar samt djupet i den hierarki som ska visas.

### Huvudflik {#main-tab}

![](/help/assets/breadcrumb-design.png)

* **Navigeringsstartnivå** - Definierar standardvärdet för var i hierarkin den synliga komponenten ska börja gå ned till den aktuella sidan när den synliga komponenten läggs till på en sida.
* **Visa dolda navigeringsobjekt** - Definierar standardvärdet för alternativet **Visa dolda navigeringsobjekt** när den synliga komponenten läggs till på en sida.

   * Det aktiverar eller inaktiverar inte alternativet för författaren. Det anger bara standardvärdet.

* **Dölj aktuell sida**- Definierar standardvärdet för alternativet **Dölj aktuell sida** när den synliga komponenten läggs till på en sida.

   * Det aktiverar eller inaktiverar inte alternativet för författaren. Det anger bara standardvärdet.

* **Inaktivera skuggning** - Definierar standardvärdet för alternativet **Inaktivera skuggning** när den synliga komponenten läggs till på en sida.

### Fliken Format {#styles-tab}

Breadcrumb-komponenten stöder AEM [Style System](/help/get-started/authoring.md#component-styling).

## Adobe Client Data Layer {#data-layer}

Breadcrumb-komponenten stöder [Adobe Client Data Layer.](/help/developing/data-layer/overview.md)
