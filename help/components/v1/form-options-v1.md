---
title: Formuläralternativkomponent (v1)
description: Alternativkomponenten Core Component Form gör att du kan välja bland fördefinierade alternativ i olika format.
index: n
role: Architect, Developer, Admin, User
exl-id: a5e8656b-eddd-48ec-876b-39bbaa70edf6
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 0%

---


# Formuläralternativkomponent (v1) {#form-options-component-v}

Alternativkomponenten Core Component Form gör att du kan välja bland fördefinierade alternativ i olika format.

## Användning {#usage}

Komponenten Core Component Form Options gör det möjligt att skicka olika typer av alternativ som presenteras på många olika sätt och är avsedd att användas tillsammans med [formulärbehållarkomponenten](form-container-v1.md).

Presentationen av alternativ, etiketter och enskilda alternativ kan definieras av innehållsredigeraren i dialogrutan [Konfigurera](#configure-dialog).

## Version och kompatibilitet {#version-and-compatibility}

I det här dokumentet beskrivs v1 i Form Options Component, som ursprungligen introducerades i version 1.0.0 av Core Components med AEM 6.3.

I följande tabell visas kompatibiliteten för v1 för komponenten Formuläralternativ.

| Komponentversion | AEM 6.3 | AEM 6.4 |
|--- |--- |--- |
| v2 | Kompatibel | Kompatibel |
| v1 | Kompatibel | Kompatibel |

>[!CAUTION]
>
>I det här dokumentet beskrivs v1 för komponenten Formuläralternativ.
>
>Mer information om den aktuella versionen av formuläralternativskomponenten finns i dokumentet [Formuläralternativkomponent](/help/components/forms/form-options.md).

## Exempel på komponentutdata {#sample-component-output}

Följande är ett exempel från [We.Retail](https://helpx.adobe.com/se/experience-manager/6-4/sites/developing/using/we-retail.html).

### Skärmbild {#screenshot}

![](/help/assets/chlimage_1-89.png)

### HTML {#html}

```
<div class="cmp cmp-form aem-GridColumn aem-GridColumn--default--12">
<form method="POST" action="/content/we-retail/us/en/experience.html" id="new_form" name="new_form" enctype="multipart/form-data" class="aem-Grid aem-Grid--12 aem-Grid--default--12 ">
    <input type="hidden" name=":formstart" value="/content/we-retail/us/en/experience/jcr:content/root/responsivegrid/container">
    
    <div class="cmp cmp-options aem-GridColumn aem-GridColumn--default--12">

    <fieldset class="form-group checkbox">
        <legend>What is your favorite type of toast?</legend>
        
        <div class="checkbox-item">
            <label>
              <input type="checkbox" name="toasttypes" value="dry">
              Plain dry toast
            </label>
        </div>
<div class="checkbox-item">
            <label>
              <input type="checkbox" name="toasttypes" value="french">
              French toast
            </label>
        </div>
<div class="checkbox-item">
            <label>
              <input type="checkbox" name="toasttypes" value="texas">
              Texas toast
            </label>
        </div>

    </fieldset>
    
</div>
    
</form></div>
```

### JSON {#json}

```
"container": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              "columnCount": 12,
              "gridClassNames": "aem-Grid aem-Grid--12 aem-Grid--default--12",
              ":items": {
                "options": {
                  "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
                  ":type": "weretail/components/form/options",
                  "name": "toastTypes",
                  "jcr:title": "What is your favorite type of toast?",
                  "source": "local",
                  "type": "checkbox"
                }
              },
              ":itemsOrder": [
                "options"
              ],
              ":type": "weretail/components/form/container"
            }
```

>[!NOTE]
>
>JSON-export från Core Components kräver version 1.1.0 av Core Components. Mer information finns i [kompatibilitetsinformationen för kärnkomponenter v1](/help/versions.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera vilken typ av alternativ som ska visas, etiketter och vilka alternativ som är tillgängliga.

![](/help/assets/chlimage_1-90.png)

* **Typer**
Hur alternativen presenteras

   * **Kryssrutor**
   * **Alternativknappar**
   * **Listruta**
   * **Listruta för flera val**

* **Titel** - Den rubrik som ska visas som etikett för alternativen
* **Namn** - Namnet på fältet som skickats med formulärdata
* **Source** - Där alternativen har definierats

   * **Lokal** - definieras i komponenten
      * Tryck eller klicka på knappen **Lägg till** för att lägga till ett värde, **Ta bort** för att ta bort ett värde
      * **Värde** - Det värde som sparas när det alternativet väljs när formuläret skickas
      * **Text** - Etiketten för alternativet som visas i formuläret
      * **Aktiv** - Alternativet markeras som markerat när formuläret läses in
      * **Inaktiverad** - Alternativet kan inte markeras men visas ändå
      * **Lista** - En statisk lista som definierats någon annanstans i AEM används för alternativet
         * **Lista** - Sökvägen till den statiska listan i AEM
            * Använd knappen Bläddra för att hitta listresursen
      * **Datakälla** - En datakälla används för alternativen
         * **Datakälla** - datakällans resurstyp
* **Hjälpmeddelande** - Ett tips för användaren om vad som kan anges i fältet

## Designdialogruta {#design-dialog}

Det finns ingen designdialogruta för komponenten Formuläralternativ.

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Form Options-komponenten [finns på GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/options/v1/options).

Hela kärnkomponentprojektet kan hämtas från GitHub.

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).
