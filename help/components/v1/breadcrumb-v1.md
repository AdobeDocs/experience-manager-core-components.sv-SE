---
title: Breadcrumb-komponent (v1)
description: Komponenten Core Component Breadcrumb är en navigeringskomponent som skapar en rad länkar baserat på sidans plats i innehållshierarkin.
index: n
role: Arkitekt, utvecklare, administratör, affärsansvarig
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '551'
ht-degree: 0%

---


# Breadcrumb Component (v1) {#breadcrumb-component-v}

Komponenten Core Component Breadcrumb är en navigeringskomponent som skapar en rad länkar baserat på sidans plats i innehållshierarkin.

## Användning {#usage}

Komponenten Breadcrumb visar den aktuella sidans position i platshierarkin, vilket gör att sidbesökare kan navigera i sidhierarkin från sin aktuella plats. Detta är ofta integrerat i sidhuvuden och sidfötter.

Tillgängliga alternativ som standardnavigeringsnivån och möjligheten att visa den aktuella sidan eller dolda sidor kan definieras av mallskaparen i [designdialogrutan](#design-dialog). Innehållsredigeraren kan sedan välja om dolda sidor ska visas eller inte och den faktiska navigeringsnivån för komponenten i [redigeringsdialogrutan](#edit-dialog).

## Version och kompatibilitet {#version-and-compatibility}

I det här dokumentet beskrivs v1 av Breadcrumb Component, som ursprungligen introducerades i version 1.0.0 av Core Components med AEM 6.3.

I följande tabell visas kompatibiliteten för v1 för Breadcrumb Component.

| AEM | Breadcrumb Component v1 |
|--- |--- |
| 6.3 | Kompatibel |
| 6.4 | Kompatibel |

>[!CAUTION]
>
>I det här dokumentet beskrivs v1 för Breadcrumb-komponenten.
>Mer information om den aktuella versionen av Breadcrumb Component finns i [Breadcrumb Component](/help/components/breadcrumb.md)-dokumentet.

## Exempelkomponentutdata {#sample-component-output}

Följande är ett exempel från [We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

### Skärmbild {#screenshot}

![](/help/assets/chlimage_1-33.png)

### HTML {#html}

```
<div class="cmp cmp-breadcrumb aem-GridColumn aem-GridColumn--default--12">

<ol class="breadcrumb">
    <li class="breadcrumb-item ">
        <a href="/content/we-retail/us.html">
            United States
        </a>
    </li>

    <li class="breadcrumb-item ">
        <a href="/content/we-retail/us/en.html">
            English
        </a>
    </li>

    <li class="breadcrumb-item active">
        
            Experience
        
    </li>
</ol>
 
</div>
```

### JSON {#json}

```
"breadcrumb": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              ":type": "weretail/components/content/breadcrumb"
            }
```

>[!NOTE]
>
>JSON-export från Core Components kräver version 1.1.0 av Core Components. Mer information finns i [kompatibilitetsinformationen för Core Components v1](/help/versions.md).

## Redigera dialogruta {#edit-dialog}

I redigeringsdialogrutan kan innehållsförfattaren utelämna dolda och aktiva sidor i vägbeskrivningar samt djupet i den hierarki som ska visas.

![](/help/assets/chlimage_1-34.png)

* **Navigeringsnivå att starta**  - Där i hierarkin den synliga sökvägen ska börja gå ned till den aktuella sidan. Exempel i We.Retail:

   * 1 börjar `/content/we-retail`
   * 2 börjar vid `/content/we-retail/<country>`

* **Visa dolda**  - Visa sidor som markerats som dolda i sidutrymmet (som standard visas de inte)
* **Dölj aktuell** - Utelämna den aktuella sidan i sidutrymmet (som standard visas den)

## Designdialog {#design-dialog}

I designdialogrutan kan mallskaparen definiera vilka standardvärden som ska användas för att inaktivera dolda och aktiva sidor i vägbeskrivningarna samt djupet i den hierarki som ska visas.

![](/help/assets/chlimage_1-35.png)

* **Navigeringsnivå att starta**  - Definierar standardvärdet för var i hierarkin den synliga komponenten ska börja gå ned till den aktuella sidan när den synliga komponenten läggs till på en sida.
* **Visa dolda**  - Definierar standardvärdet för alternativet  **Visa** dolda när den synliga komponenten läggs till på en sida.

   * Det aktiverar eller inaktiverar inte alternativet för författaren. Det anger bara standardvärdet.

* **Dölj aktuell**  - Definierar standardvärdet för alternativet  **Dölj** aktuell när den synliga komponenten läggs till på en sida.

   * Det aktiverar eller inaktiverar inte alternativet för författaren. Det anger bara standardvärdet.

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Breadcrumb-komponenten [finns på GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v1/breadcrumb).

Hela kärnkomponentprojektet kan laddas ned från GitHub.

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen till Core Components developer](/help/developing/overview.md).
