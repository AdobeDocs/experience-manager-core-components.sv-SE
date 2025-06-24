---
title: Komponent för dolt formulär (v1)
description: Komponenten Core Component Form Hidden gör det möjligt att visa ett dolt fält.
index: n
role: Architect, Developer, Admin, User
exl-id: 8e30dac0-5b4b-4fc7-af99-5791c98c90bf
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 0%

---


# Komponent för dolt formulär (v1) {#form-hidden-component-v}

Komponenten Core Component Form Hidden gör det möjligt att visa ett dolt fält.

## Användning {#usage}

Med den dolda komponenten för kärnkomponentformulär kan du skapa dolda fält som skickar information om den aktuella sidan tillbaka till AEM och som ska användas tillsammans med [formulärbehållarkomponenten](form-container-v1.md).

Fältegenskaperna kan definieras av innehållsredigeraren i dialogrutan [Konfigurera](#configure-dialog).

## Version och kompatibilitet {#version-and-compatibility}

I det här dokumentet beskrivs v1 i Form Hidden Component, som ursprungligen introducerades i version 1.0.0 av Core Components med AEM 6.3.

I följande tabell visas kompatibiliteten för v1 för komponenten Form Hidden.

| AEM Version | Formulärets dolda komponent v1 |
|--- |--- |
| 6,3 | Kompatibel |
| 6,4 | Kompatibel |

>[!CAUTION]
>
>I det här dokumentet beskrivs v1 för komponenten Form Hidden.
>
>Mer information om den aktuella versionen av den dolda formulärkomponenten finns i dokumentet [Dold formulärkomponent](/help/components/forms/form-hidden.md).

## Exempel på komponentutdata {#sample-component-output}

Följande är ett exempel från [We.Retail](https://helpx.adobe.com/se/experience-manager/6-4/sites/developing/using/we-retail.html).

### HTML {#html}

```
<div class="cmp cmp-form aem-GridColumn aem-GridColumn--default--12">
 <form method="POST" action="/content/we-retail/us/en/experience.html" id="new_form" name="new_form" enctype="multipart/form-data" class="aem-Grid aem-Grid--12 aem-Grid--default--12 ">
  <input type="hidden" name=":formstart" value="/content/we-retail/us/en/experience/jcr:content/root/responsivegrid/container">
   <div class="visible aem-GridColumn aem-GridColumn--default--12">
    <input type="hidden" id="ghostToast" name="Invisible Toast" value="ghostToast">
   </div>
 </form>
</div>
```

### JSON {#json}

```
"container": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              "columnCount": 12,
              "gridClassNames": "aem-Grid aem-Grid--12 aem-Grid--default--12",
              ":items": {
                "hidden": {
                  "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
                  ":type": "weretail/components/form/hidden",
                  "name": "Invisible Toast",
                  "id": "ghostToast",
                  "value": "ghostToast"
                }
              },
              ":itemsOrder": [
                "hidden"
              ],
              ":type": "weretail/components/form/container"
            }
```

>[!NOTE]
>
>JSON-export från Core Components kräver version 1.1.0 av Core Components. Mer information finns i [kompatibilitetsinformationen för kärnkomponenter v1](/help/versions.md#release-history-and-compatibility).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera parametrarna för det dolda fältet.

![](/help/assets/chlimage_1-26.png)

* **Namn** - Namnet på fältet som skickas med formulärdata
* **Värde** - Fältets värde, som skickas med formulärdata
* **Identifierare** - Identifieraren ska vara unik på sidan och kan användas för att binda skript till det här formulärfältet

## Designdialogruta {#design-dialog}

Det finns ingen designdialogruta för komponenten Formulär-dold.

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om den dolda formulärkomponenten [ finns på GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/hidden/v1/hidden).

Hela kärnkomponentprojektet kan hämtas från GitHub.

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).
