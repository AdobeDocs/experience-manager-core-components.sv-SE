---
title: Breadcrumb-komponent
description: Komponenten Core Component Breadcrumb är en navigeringskomponent som skapar en rad länkar baserat på sidans plats i innehållshierarkin.
role: Architect, Developer, Admin, User
exl-id: 19d65b9d-a407-4f50-9c55-8de0f12222ed
source-git-commit: 16930ccaa281f9d9c4ddbb890d4222e128557580
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 1%

---

# Breadcrumb-komponent{#breadcrumb-component}

Komponenten Core Component Breadcrumb är en navigeringskomponent som skapar en rad länkar baserat på sidans plats i innehållshierarkin.

## Användning {#usage}

Komponenten Breadcrumb visar den aktuella sidans position i platshierarkin, vilket gör att sidbesökare kan navigera i sidhierarkin från sin aktuella plats. Detta är ofta integrerat i sidhuvuden och sidfötter.

Tillgängliga alternativ, t.ex. standardnavigeringsnivån och möjligheten att visa den aktuella sidan eller dolda sidor, kan definieras av mallskaparen i dialogrutan [designdialogruta](#design-dialog). Innehållsredigeraren kan sedan välja om dolda sidor ska visas eller inte och den faktiska navigeringsnivån för komponenten i [redigeringsdialogruta](#edit-dialog).

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Breadcrumb Component är v3, som introducerades i version 2.18.0 av Core Components i februari 2022, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- | --- |--- |---|
| v3 | - | Kompatibel | Kompatibel |
| [v2](v2/breadcrumb.md) | Kompatibel | Kompatibel | Kompatibel |
| [v1](v1/breadcrumb-v1.md) | Kompatibel | Kompatibel | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Huvudkomponentversioner](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill visa Breadcrumb Component och se exempel på dess konfigurationsalternativ samt HTML och JSON-utdata går du till [Komponentbibliotek](https://adobe.com/go/aem_cmp_library_breadcrumb).

>[!NOTE]
>
>Från och med Core Components version 2.1.0 stöder Breadcrumb Components [schema.org, mikrodata](https://schema.org/BreadcrumbList).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Breadcrumb-komponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_breadcrumb_v2).

Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Dialogrutan Redigera {#edit-dialog}

I redigeringsdialogrutan kan innehållsförfattaren utelämna dolda och aktiva sidor i vägbeskrivningar samt djupet i den hierarki som ska visas.

## Fliken Egenskaper {#properties-tab}

![Dialogruta för redigering av komponenten Breadcrumb](/help/assets/breadcrumb-edit.png)

* **Startnivå för navigering** - Där i hierarkin den synliga komponenten ska börja gå ned till den aktuella sidan. Till exempel:

   * 0 börjar vid `/content`
   * 1 börjar vid `/content/<yourSite>`
   * 2 börjar vid `/content/<yourSite>/<country>`

* **Visa dolda navigeringsobjekt** - Visa sidor som markerats som dolda i sidutrymmet (som standard visas de inte)
* **Dölj aktuell sida** - Utelämna den aktuella sidan i sidutrymmet (som standard visas den)
* **Inaktivera skuggning** - Om sidan i hierarkin är en omdirigering visas namnet på omdirigeringssidan i stället för målet. Se [Stöd för Shadow Site Structure](navigation.md#shadow-structure) i navigeringskomponenten för mer information.
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [Datalager](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

### Fliken Format {#styles-tab-edit}

![Fliken Format i redigeringsdialogrutan för komponenten Breadcrumb List](/help/assets/breadcrumb-edit-styles.png)

Breadcrumb-komponenten stöder AEM [Formatsystem.](/help/get-started/authoring.md#component-styling).

Använd listrutan för att välja de format som du vill använda på komponenten. Markeringar som görs i redigeringsdialogrutan har samma effekt som de som väljs i komponentverktygsfältet.

Format måste konfigureras för den här komponenten i [designdialogruta](#design-dialog) för att den nedrullningsbara menyn ska vara tillgänglig.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera vilka standardvärden som ska användas för att inaktivera dolda och aktiva sidor i vägbeskrivningarna samt djupet i den hierarki som ska visas.

### Huvudflik {#main-tab}

![](/help/assets/breadcrumb-design.png)

* **Startnivå för navigering** - Definierar standardvärdet för var i hierarkin den ledande komponenten ska börja gå ned till den aktuella sidan när den synliga komponenten läggs till på en sida.
* **Visa dolda navigeringsobjekt** - Definierar standardvärdet för **Visa dolda navigeringsobjekt** när den synliga komponenten läggs till på en sida.

   * Det aktiverar eller inaktiverar inte alternativet för författaren. Det anger bara standardvärdet.

* **Dölj aktuell sida**- Definierar standardvärdet för **Dölj aktuell sida** när den synliga komponenten läggs till på en sida.

   * Det aktiverar eller inaktiverar inte alternativet för författaren. Det anger bara standardvärdet.

* **Inaktivera skuggning** - Definierar standardvärdet för **Inaktivera skuggning** när den synliga komponenten läggs till på en sida.

### Fliken Format {#styles-tab}

Breadcrumb-komponenten stöder AEM [Formatsystem](/help/get-started/authoring.md#component-styling).

## Adobe-klientdatalager {#data-layer}

Komponenten Breadcrumb har stöd för [Adobe Client Data Layer.](/help/developing/data-layer/overview.md)
