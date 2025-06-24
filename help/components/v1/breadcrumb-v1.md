---
title: Breadcrumb-komponent (v1)
description: Komponenten Core Component Breadcrumb är en navigeringskomponent som skapar en rad länkar baserat på sidans plats i innehållshierarkin.
index: n
role: Architect, Developer, Admin, User
exl-id: 4845e649-033a-43a8-b5ee-892a3f2a8b98
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 0%

---


# Breadcrumb-komponent (v1) {#breadcrumb-component-v}

Komponenten Core Component Breadcrumb är en navigeringskomponent som skapar en rad länkar baserat på sidans plats i innehållshierarkin.

## Användning {#usage}

Komponenten Breadcrumb visar positionen för den aktuella sidan i platshierarkin, vilket gör att sidbesökare kan navigera i sidhierarkin från sin aktuella plats. Detta är ofta integrerat i sidhuvuden och sidfötter.

Tillgängliga alternativ som standardnavigeringsnivån och möjligheten att visa den aktuella sidan eller dolda sidor kan definieras av mallförfattaren i [designdialogrutan](#design-dialog). Innehållsredigeraren kan sedan välja om dolda sidor ska visas eller inte och den faktiska navigeringsnivån för komponenten i [redigeringsdialogrutan](#edit-dialog).

## Version och kompatibilitet {#version-and-compatibility}

I det här dokumentet beskrivs v1 av Breadcrumb Component, som ursprungligen introducerades i version 1.0.0 av Core Components med AEM 6.3.

I följande tabell visas kompatibiliteten för v1 för Breadcrumb Component.

| AEM Version | Breadcrumb Component v1 |
|--- |--- |
| 6,3 | Kompatibel |
| 6,4 | Kompatibel |

>[!CAUTION]
>
>I det här dokumentet beskrivs v1 för Breadcrumb-komponenten.
>&#x200B;>Information om den aktuella versionen av Breadcrumb-komponenten finns i dokumentet [Breadcrumb Component](/help/components/breadcrumb.md) .

## Exempel på komponentutdata {#sample-component-output}

Följande är ett exempel från [We.Retail](https://helpx.adobe.com/se/experience-manager/6-4/sites/developing/using/we-retail.html).

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
>JSON-export från Core Components kräver version 1.1.0 av Core Components. Mer information finns i [kompatibilitetsinformationen för kärnkomponenter v1](/help/versions.md).

## Dialogrutan Redigera {#edit-dialog}

I redigeringsdialogrutan kan innehållsförfattaren utelämna dolda och aktiva sidor i vägbeskrivningar samt djupet i den hierarki som ska visas.

![](/help/assets/chlimage_1-34.png)

* **Navigeringsnivå till start** - Där i hierarkin den synliga komponenten ska börja gå ned till den aktuella sidan. I t.ex. We.Retail:

   * 1 börjar `/content/we-retail`
   * 2 börjar `/content/we-retail/<country>`

* **Visa dolda** - Visa sidor som markerats som dolda i vägbeskrivningsfilen (som standard visas de inte)
* **Dölj aktuell**- Utelämna den aktuella sidan i den synliga sökvägen (som standard visas den)

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera vilka standardvärden som ska användas för att inaktivera dolda och aktiva sidor i vägbeskrivningar samt djupet i den hierarki som ska visas.

![](/help/assets/chlimage_1-35.png)

* **Navigeringsnivå att starta** - Definierar standardvärdet för var i hierarkin den synliga komponenten ska börja gå ned till den aktuella sidan när den synliga komponenten läggs till på en sida.
* **Visa dolda** - Definierar standardvärdet för alternativet **Visa dolda** när den synliga komponenten läggs till på en sida.

   * Det aktiverar eller inaktiverar inte alternativet för författaren. Det anger bara standardvärdet.

* **Dölj aktuell** - Definierar standardvärdet för alternativet **Dölj aktuell** när den synliga komponenten läggs till på en sida.

   * Det aktiverar eller inaktiverar inte alternativet för författaren. Det anger bara standardvärdet.

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Breadcrumb-komponenten [ finns på GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v1/breadcrumb).

Hela kärnkomponentprojektet kan hämtas från GitHub.

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).
