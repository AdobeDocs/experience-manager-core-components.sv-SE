---
title: Formulärtextkomponent (v1)
description: Med komponenten Core Component Form Text kan du skriva in formulärtext.
index: n
role: Architect, Developer, Admin, User
exl-id: d6fbc596-cb42-4478-8a3c-aa5aead3be0a
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 0%

---

# Formulärtextkomponent (v1) {#form-text-component-v}

Med komponenten Core Component Form Text kan du skriva in formulärtext.

## Användning {#usage}

Med Form Text Component kan du skicka olika typer av text och den är avsedd att användas tillsammans med [formulärbehållarkomponenten](form-container-v1.md).

Typen av textvalidering, etiketter och hjälpmeddelanden kan definieras av innehållsredigeraren i dialogrutan [Konfigurera](#configure-dialog).

## Version och kompatibilitet {#version-and-compatibility}

I det här dokumentet beskrivs v1 av Form Text Component, som ursprungligen introducerades i version 1.0.0 av Core Components med AEM 6.3.

I följande tabell visas kompatibiliteten för v1 för Form Text Component.

| AEM | Formulärtextkomponent v1 |
|--- |--- |
| 6,3 | Kompatibel |
| 6,4 | Kompatibel |

>[!CAUTION]
>
>I det här dokumentet beskrivs v1 för Form Text Component.
>
>Information om den aktuella versionen av formulärtextkomponenten finns i dokumentet [Formulärtextkomponent](/help/components/forms/form-text.md) .

## Exempel på komponentutdata {#sample-component-output}

Följande är ett exempel från [We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

### Skärmbild {#screenshot}

![](/help/assets/chlimage_1-22.png)

### HTML {#html}

```
<div class="cmp cmp-form aem-GridColumn aem-GridColumn--default--12">
 <form method="POST" action="/content/we-retail/us/en/experience.html" id="new_form" name="new_form" enctype="multipart/form-data" class="aem-Grid aem-Grid--12 aem-Grid--default--12 ">
     <input type="hidden" name=":formstart" value="/content/we-retail/us/en/experience/jcr:content/root/responsivegrid/container">
     <div class="cmp cmp-form-field aem-GridColumn aem-GridColumn--default--12">
   <div class="form-group">
       <label for="form-text-978484744">How many pieces of toast would you like?</label>
          <input type="number" id="form-text-978484744" name="pieces">
   </div>
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
                "text": {
                  "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
                  ":type": "weretail/components/form/text",
                  "name": "piecesOfToast",
                  "jcr:title": "How many pieces of toast would you like?",
                  "type": "number",
                  "rows": "2"
                }
              },
              ":itemsOrder": [
                "text"
              ],
              ":type": "weretail/components/form/container"
            }
```

>[!NOTE]
>
>JSON-export från Core Components kräver version 1.1.0 av Core Components. Mer information finns i [kompatibilitetsinformationen för kärnkomponenter v1](/help/versions.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera vilken typ av text som ska anges samt standardvärden och etiketter.

### Huvud {#main}

![](/help/assets/chlimage_1-23.png)

* **Begränsning** - Den typ av text som ska anges och valideras mot

   * **Text**
   * **Textområde**
   * **E-post**
   * **Tel**
   * **Datum**
   * **Number**
   * **Lösenord**

* **Textrader** - Antal rader som ska visas i textområdet (visas bara när **Begränsning** är inställt på **Textområde**)

* **Etikett** - Etiketten som ska visas för fältet
* **Dölj etiketten så att den inte visas** - Behövs om etiketten endast är nödvändig för hjälpmedelssyften och inte tillför någon ytterligare visuell information om fältet
* **Elementnamn** - Namnet på fältet som skickas med formulärdata
* **Värde** - Standardvärde som är förifyllt i fältet

### Om {#about}

![](/help/assets/chlimage_1-24.png)

* **Hjälpmeddelande** - Ett tips till användaren om vad som kan anges i fältet
* **Visa hjälpmeddelandet som platshållare** - Om du vill visa hjälpmeddelandet i formulärindata när det är tomt och inte i fokus

### Begränsningar {#constraints}

![](/help/assets/chlimage_1-25.png)

* **Begränsningsmeddelande**

   * Meddelande som visas som verktygstips när formuläret skickas om värdet inte validerar vald typ
   * Visas inte för begränsningstyperna **Text** och **Textområde**

* **Obligatoriskt** - Om det här alternativet är markerat måste användaren fylla i ett värde innan formuläret skickas
* **Gör skrivskyddad** - Om det här alternativet är markerat kan användaren inte ändra fältets värde

## Designdialogruta {#design-dialog}

Det finns ingen designdialogruta för komponenten Formulärtext.

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Form Text Component [finns på GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/text/v1/text).

Hela kärnkomponentprojektet kan hämtas från GitHub.

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).
