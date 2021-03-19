---
title: Komponent för formulärknapp (v1)
description: Komponenten Core Component Form Hidden gör det möjligt att inkludera ett dolt fält i ett formulär.
index: n
role: Arkitekt, utvecklare, administratör, affärsansvarig
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 2%

---


# Komponent för formulärknapp (v1) {#form-button-component-v}

Komponenten Core Component Form Button gör det möjligt att inkludera ett knappfält i ett formulär för att utlösa en åtgärd.

## Användning {#usage}

Komponenten Core Component Form Button gör det möjligt att skapa knappfält, ofta för att utlösa att formuläret skickas och är avsedd att användas tillsammans med [formulärbehållarkomponenten](form-container-v1.md).

Knappegenskaperna kan definieras av innehållsredigeraren i [konfigurationsdialogrutan](#configure-dialog).

## Version och kompatibilitet {#version-and-compatibility}

I det här dokumentet beskrivs v1 för komponenten Form Button, som ursprungligen introducerades i version 1.0.0 av Core Components med AEM 6.3.

I följande tabell visas kompatibiliteten för v1 för komponenten Formulärknapp.

| AEM | Komponent för formulärknapp v1 |
|--- |--- |
| 6.3 | Kompatibel |
| 6.4 | Kompatibel |

>[!CAUTION]
>
>I det här dokumentet beskrivs v1 för komponenten Form Button.
>
>Mer information om den aktuella versionen av komponenten Formulärknapp finns i dokumentet [Komponent för formulärknapp](/help/components/forms/form-button.md).

## Exempelkomponentutdata {#sample-component-output}

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
>JSON-export från Core Components kräver version 1.1.0 av Core Components. Mer information finns i [kompatibilitetsinformationen för Core Components v1](/help/versions.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera knappens parametrar.

![](/help/assets/chlimage_1-49.png)

* **Typ**
   * **Knapp**
   * **Skicka**

* **Titel**  - Texten som visas på knappen
   * Om inget anges används knapptypen som standard

* **Namn** - Namnet på knappen som skickas med formulärdata
* **Värde**  - Värdet på knappen som skickas in tillsammans med formulärdata

## Designdialog {#design-dialog}

Det finns ingen designdialogruta för komponenten Formulärknapp.

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Form Button-komponenten [finns på GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/button/v1/button).

Hela kärnkomponentprojektet kan laddas ned från GitHub.

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen till Core Components developer](/help/developing/overview.md).
