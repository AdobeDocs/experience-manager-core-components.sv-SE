---
title: Breadcrumb-komponent
description: Komponenten Core Component Breadcrumb är en navigeringskomponent som skapar en rad länkar baserat på sidans plats i innehållshierarkin.
role: Architect, Developer, Administrator, Business Practitioner
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 1%

---


# Breadcrumb-komponent{#breadcrumb-component}

Komponenten Core Component Breadcrumb är en navigeringskomponent som skapar en rad länkar baserat på sidans plats i innehållshierarkin.

## Användning {#usage}

Komponenten Breadcrumb visar den aktuella sidans position i platshierarkin, vilket gör att sidbesökare kan navigera i sidhierarkin från sin aktuella plats. Detta är ofta integrerat i sidhuvuden och sidfötter.

Tillgängliga alternativ, till exempel standardnavigeringsnivån och möjligheten att visa den aktuella sidan eller dolda sidor, kan definieras av mallskaparen i [designdialogrutan](#design-dialog). Innehållsredigeraren kan sedan välja om dolda sidor ska visas eller inte och den faktiska navigeringsnivån för komponenten i [redigeringsdialogrutan](#edit-dialog).

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Breadcrumb Component är v2, som introducerades i version 2.0.0 av Core Components i januari 2018, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- | --- |--- |---|
| v2 | Kompatibel | Kompatibel | Kompatibel |
| [v1](v1/breadcrumb-v1.md) | Kompatibel | Kompatibel | - |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempelkomponentutdata {#sample-component-output}

Om du vill visa Breadcrumb-komponenten och se exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_breadcrumb).

>[!NOTE]
>
>Från och med Core Components version 2.1.0 stöder Breadcrumb Component [schema.org mikrodata](https://schema.org/BreadcrumbList).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Breadcrumb-komponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_breadcrumb_v2).

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen till Core Components developer](/help/developing/overview.md).

## Redigera dialogruta {#edit-dialog}

I redigeringsdialogrutan kan innehållsförfattaren utelämna dolda och aktiva sidor i vägbeskrivningar samt djupet i den hierarki som ska visas.

![Dialogruta för redigering av komponenten Breadcrumb](/help/assets/breadcrumb-edit.png)

* **Startnivå**  för navigering - Där i hierarkin den synliga komponenten ska börja gå ned till den aktuella sidan. Till exempel:

   * 0 börjar vid `/content`
   * 1 börjar `/content/<yourSite>`
   * 2 börjar vid `/content/<yourSite>/<country>`

* **Visa dolda navigeringsobjekt** - Visa sidor som är markerade som dolda i navigeringsfältet (som standard visas de inte)
* **Dölj aktuell sida** - Utelämna den aktuella sidan i sidutrymmet (som standard visas den)
* **Inaktivera skuggning**  - Om sidan i hierarkin är en omdirigering visas namnet på omdirigeringssidan i stället för målet. Mer information finns i [Stöd för skuggplatsstruktur](navigation.md#shadow-structure) för navigeringskomponenten.
* **ID**  - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i  [datalagret](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

## Designdialog {#design-dialog}

I designdialogrutan kan mallskaparen definiera vilka standardvärden som ska användas för att inaktivera dolda och aktiva sidor i vägbeskrivningarna samt djupet i den hierarki som ska visas.

### Huvudflik {#main-tab}

![](/help/assets/breadcrumb-design.png)

* **Startnivå**  för navigering - Definierar standardvärdet för var i hierarkin den synliga komponenten ska börja gå ned till den aktuella sidan när den synliga komponenten läggs till på en sida.
* **Visa dolda navigeringsobjekt**  - Definierar standardvärdet för alternativet  **Visa dolda** navigeringsobjekt när den synliga komponenten läggs till på en sida.

   * Det aktiverar eller inaktiverar inte alternativet för författaren. Det anger bara standardvärdet.

* **Dölj aktuell sida** - Definierar standardvärdet för alternativet  **Dölj aktuell** sida när den synliga komponenten läggs till på en sida.

   * Det aktiverar eller inaktiverar inte alternativet för författaren. Det anger bara standardvärdet.

* **Inaktivera skuggning**  - Definierar standardvärdet för alternativet  **Inaktivera** skuggning när den synliga komponenten läggs till på en sida.

### Fliken Format {#styles-tab}

Breadcrumb-komponenten stöder AEM [Style System](/help/get-started/authoring.md#component-styling).

## Adobe-klientdatalagret {#data-layer}

Breadcrumb-komponenten stöder [Adobe-klientdatalagret.](/help/developing/data-layer/overview.md)
