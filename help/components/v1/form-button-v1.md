---
title: Komponent för formulärknapp (v1)
description: Komponenten Core Component Form Hidden gör det möjligt att inkludera ett dolt fält i ett formulär.
index: n
role: Architect, Developer, Admin, User
exl-id: 2c06a942-7ac5-4847-9d11-7bbcd0ea51bd
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 0%

---


# Komponent för formulärknapp (v1) {#form-button-component-v}

Komponenten Core Component Form Button gör det möjligt att inkludera ett knappfält i ett formulär för att utlösa en åtgärd.

## Användning {#usage}

Komponenten Core Component Form Button gör det möjligt att skapa knappfält, ofta för att utlösa att formuläret skickas och är avsedd att användas tillsammans med [formulärbehållarkomponenten](form-container-v1.md).

Knappegenskaperna kan definieras av innehållsredigeraren i dialogrutan [Konfigurera](#configure-dialog).

## Version och kompatibilitet {#version-and-compatibility}

I det här dokumentet beskrivs v1 för komponenten Form Button, som ursprungligen introducerades i version 1.0.0 av Core Components med AEM 6.3.

I följande tabell visas kompatibiliteten för v1 för komponenten Formulärknapp.

| AEM Version | Komponent för formulärknapp v1 |
|--- |--- |
| 6,3 | Kompatibel |
| 6,4 | Kompatibel |

>[!CAUTION]
>
>I det här dokumentet beskrivs v1 för komponenten Form Button.
>
>Mer information om den aktuella versionen av komponenten Formulärknapp finns i dokumentet [Komponent för formulärknapp](/help/components/forms/form-button.md).

## Exempel på komponentutdata {#sample-component-output}

Följande är ett exempel från [We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

### Skärmbild {#screenshot}

![](/help/assets/chlimage_1-48.png)

### HTML {#html}

```
<div class="cmp cmp-button aem-GridColumn aem-GridColumn--default--12">
    <div class="cmp cmp-button">
        <button type="BUTTON" class="btn btn-action btn-primary" name="loveToast" value="ILoveToast">
            Click here if you love toast!
        </button>
    </div>
</div>
```

### JSON {#json}

```
"container": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              "columnCount": 12,
              "gridClassNames": "aem-Grid aem-Grid--12 aem-Grid--default--12",
              ":items": {
                "button": {
                  "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
                  ":type": "weretail/components/form/button",
                  "name": "loveToast",
                  "jcr:title": "Click here if you love toast!",
                  "type": "submit",
                  "value": "ILoveToast"
                }
              },
              ":itemsOrder": [
                "button"
              ],
              ":type": "weretail/components/form/container"
            }
```

>[!NOTE]
>
>JSON-export från Core Components kräver version 1.1.0 av Core Components. Mer information finns i [kompatibilitetsinformationen för kärnkomponenter v1](/help/versions.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera knappens parametrar.

![](/help/assets/chlimage_1-49.png)

* **Typ**
   * **Knapp**
   * **Skicka**

* **Titel** - Texten som visas på knappen
   * Om inget anges används knapptypen som standard

* **Namn** - Namnet på knappen som skickas med formulärdata
* **Värde** - Värdet på knappen som skickas med formulärdata

## Designdialogruta {#design-dialog}

Det finns ingen designdialogruta för komponenten Formulärknapp.

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Form Button-komponenten [ finns på GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/button/v1/button).

Hela kärnkomponentprojektet kan hämtas från GitHub.

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).
