---
title: Textkomponent (v1)
description: Komponenten Text är en textredigerings- och dispositionskomponent med funktioner för redigering på plats.
index: n
role: Architect, Developer, Admin, User
exl-id: c9fe3052-a33d-412e-9456-52c9a0cea292
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: tm+mt
source-wordcount: '1639'
ht-degree: 0%

---


# Textkomponent (v1) {#text-component-v}

Komponenten Text är en textredigerings- och dispositionskomponent med funktioner för redigering på plats.

## Användning {#usage}

Textkomponenten har en robust textredigerare som gör det enkelt att redigera text i en förenklad, textbunden redigerare och i ett helskärmsformat.

Dialogrutan [Redigera](#edit-dialog) innehåller redigeringsfunktioner i rad med begränsade alternativ med full funktionalitet i redigeringsdialogrutan i helskärmsläge. Med hjälp av [designdialogrutan](#design-dialog) kan textformateringsalternativ som rubriker, specialtecken och styckeformat konfigureras för mallen för innehållsförfattaren.

## Version och kompatibilitet {#version-and-compatibility}

I det här dokumentet beskrivs v1 av textkomponenten, som ursprungligen introducerades i version 1.0.0 av kärnkomponenterna med AEM 6.3.

I följande tabell visas kompatibiliteten för v1 för textkomponenten.

| AEM Version | Textkomponent v1 |
|--- |--- |
| 6,3 | Kompatibel |
| 6,4 | Kompatibel |

>[!CAUTION]
>
>Det här dokumentet beskriver v1 för textkomponenten.
>
>Information om den aktuella versionen av textkomponenten finns i dokumentet [Textkomponent](/help/components/text.md).

## Exempel på komponentutdata {#sample-component-output}

Följande är ett exempel från [We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html).

### Skärmbild {#screenshot}

![](/help/assets/chlimage_1-27.png)

### HTML {#html}

```
<div class="cmp cmp-text aem-GridColumn aem-GridColumn--default--12">
<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer porttitor ante a tortor volutpat maximus. Donec eu porta eros. Aenean sit amet eleifend arcu, eu vestibulum magna. Fusce eget nisi tincidunt, tristique felis quis, tincidunt est. Aliquam consequat aliquam quam non eleifend. Phasellus ut magna luctus, aliquam risus eget, fermentum augue. Aliquam lobortis accumsan magna, quis efficitur enim dictum eu. Pellentesque iaculis felis eget felis commodo, non euismod dolor euismod. Quisque nec arcu rutrum, mollis tortor non, sollicitudin odio. Sed dictum nulla mauris, eu pretium dui vulputate a. Maecenas lacus massa, egestas vitae tincidunt eu, interdum et magna. Lorem ipsum dolor sit amet, consectetur adipiscing elit. In eleifend ex lacus, in consectetur nunc interdum et. Donec interdum mi vitae dolor pretium mattis. In quis arcu sapien. Phasellus at metus vitae nisi tincidunt varius.<br />
</p>
</div>
```

### JSON {#json}

```
"text": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              "text": "<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer porttitor ante a tortor volutpat maximus. Donec eu porta eros. Aenean sit amet eleifend arcu, eu vestibulum magna. Fusce eget nisi tincidunt, tristique felis quis, tincidunt est. Aliquam consequat aliquam quam non eleifend. Phasellus ut magna luctus, aliquam risus eget, fermentum augue. Aliquam lobortis accumsan magna, quis efficitur enim dictum eu. Pellentesque iaculis felis eget felis commodo, non euismod dolor euismod. Quisque nec arcu rutrum, mollis tortor non, sollicitudin odio. Sed dictum nulla mauris, eu pretium dui vulputate a. Maecenas lacus massa, egestas vitae tincidunt eu, interdum et magna. Lorem ipsum dolor sit amet, consectetur adipiscing elit. In eleifend ex lacus, in consectetur nunc interdum et. Donec interdum mi vitae dolor pretium mattis. In quis arcu sapien. Phasellus at metus vitae nisi tincidunt varius.</p>\n",
              "richText": true,
              ":type": "weretail/components/content/text"
            }
```

>[!NOTE]
>
>JSON-export från Core Components kräver version 1.1.0 av Core Components. Mer information finns i [kompatibilitetsinformationen för kärnkomponenter v1](/help/versions.md).

## Dialogrutan Redigera {#edit-dialog}

I redigeringsdialogrutan finns de standardverktyg för RTF-formatering som en användare kan förvänta sig att skapa text.

![](/help/assets/chlimage_1-52.png)

* Fet

  ![](/help/assets/chlimage_1-53.png)

  Används för att formatera text fet eller fet formatera text som skrivs efter markören.

  **Ctrl+B** kan användas som kortkommando.

* Kursiv

  ![](/help/assets/chlimage_1-54.png)

  Används för att tillämpa kursiv formatering på markerad text eller kursiv om text som anges efter markören.

  **Ctrl+I** kan användas som kortkommando.

* Understruken

  ![](/help/assets/chlimage_1-55.png)

  Används för att tillämpa understruken formatering på markerad text eller understruken text som anges efter markören.

  **Ctrl+U** kan användas som kortkommando.

* Nedsänkt

  ![](/help/assets/chlimage_1-56.png)

  Används för att formatera markerad text eller text som skrivs efter markören som nedsänkt.

* Upphöjd

  ![](/help/assets/chlimage_1-57.png)

  Används för att formatera markerad text eller text som skrivs efter markören som upphöjd text.

* Klistra in som text

  ![](/help/assets/chlimage_1-58.png)

  Klistrar in kopierad text som oformaterad text utan formatering.

  När du väljer det här alternativet öppnas ett fönster där texten kan klistras in som oformaterad text utan formatering som en förhandsvisning innan den infogas i texten. Acceptera genom att trycka eller klicka på bockmarkeringen, avbryt genom att trycka eller klicka på x.

  ![](/help/assets/chlimage_1-59.png)

* Klistra in från Word

  ![](/help/assets/chlimage_1-60.png)

  När du väljer det här alternativet öppnas ett fönster där texten kan klistras in med bibehållen formatering som en förhandsvisning innan den infogas i texten. Acceptera genom att trycka eller klicka på bockmarkeringen, avbryt genom att trycka eller klicka på x.

  ![](/help/assets/chlimage_1-61.png)

* Hyperlänk

  ![](/help/assets/chlimage_1-62.png)

  Använd det här alternativet om du vill konvertera den markerade texten till en hyperlänk eller ändra en redan definierad länk. Det här alternativet är bara aktivt när text redan är markerad och öppnar ett fönster med ytterligare alternativ för att ange länken.

  ![](/help/assets/chlimage_1-63.png)

   * Ange platsen

      * Använd dialogrutan Öppna markering för att välja en bana i AEM
      * Om länken inte finns i AEM anger du den absoluta URL:en (icke-absoluta sökvägar tolkas som relativa till AEM)

   * Ange alternativ beskrivande text för länken
   * Välj länkbeteende

      * Mål
      * Samma flik
      * Ny flik
      * Överordnad ram
      * Övre bildruta

  Tryck eller klicka på bockmarkeringen för att använda länken eller på krysset för att avbryta.

* Bryt länk

  ![](/help/assets/chlimage_1-64.png)

  Använd det här alternativet om du vill ta bort en länk som redan har tillämpats på den markerade texten. Det här alternativet är bara aktivt när en länk redan är markerad.

* Sök

  ![](/help/assets/chlimage_1-65.png)

  Använd det här alternativet om du vill söka efter förekomster av en angiven textsträng i texten. Om du väljer det här alternativet öppnas ett fönster där du kan ange sökalternativen.

  ![](/help/assets/chlimage_1-66.png)

  Ange den text som du vill söka efter och tryck eller klicka på **Sök** för att påbörja sökningen. Tryck eller klicka på x för att avbryta.

  Om du vill göra en exakt matchning utifrån skiftläget, markerar du alternativet **Matcha skiftläge** innan du startar sökningen.

  Om en matchning hittas markeras den och sökdialogrutan är nedtonad. Tryck eller klicka på knappen **Sök** igen i den nedtonade dialogrutan för att söka efter nästa förekomst.

  ![](/help/assets/chlimage_1-67.png)

  Om inga fler förekomster hittas visas ett meddelande och sökningen startas om från textens början.

  ![](/help/assets/chlimage_1-68.png)

* Ersätt

  ![](/help/assets/chlimage_1-69.png)

  Använd det här alternativet om du vill söka efter förekomster av en angiven textsträng och ersätta matchningarna med en annan sträng. Om du väljer det här alternativet öppnas ett fönster där du kan ange alternativ för sökning och ersättning.

  ![](/help/assets/chlimage_1-70.png)

  Ange den text som du vill söka efter samt den text som den ska ersättas med.

  Tryck eller klicka på **Sök** för att påbörja sökningen. Klicka eller tryck på x för att avbryta.

  Om du vill göra en exakt matchning utifrån skiftläget, markerar du alternativet **Matcha skiftläge** innan du startar sökningen.

  Om en matchning hittas markeras den och sökdialogrutan är nedtonad. Klicka på knappen **Sök** igen i den nedtonade dialogrutan om du vill söka efter nästa förekomst, eller välj knappen **Ersätt** om du vill ersätta den markerade, matchade texten. Observera att knappen **Ersätt** bara är aktiv när en matchning har gjorts.

  Välj **Ersätt alla** om du vill ersätta alla förekomster av texten samtidigt.

* Vänsterjustera text

  ![](/help/assets/chlimage_1-71.png)

  Används för att justera texten mot vänstermarginalen.

* Centrera text

  ![](/help/assets/chlimage_1-72.png)

  Används för att centrera texten.

* Högerjustera text

  ![](/help/assets/chlimage_1-73.png)

  Används för att justera texten mot högermarginalen.

* Punkt

  ![](/help/assets/chlimage_1-74.png)

  Används för att formatera den markerade texten som en punktlista eller börja infoga en punktlista efter markören.

  Om du vill avsluta en punktlista trycker eller klickar du på knappen **Bullet** igen eller anger två vagnreturer.

* Numrerad

  ![](/help/assets/chlimage_1-75.png)

  Används för att formatera den markerade texten som en numrerad lista eller börja infoga en numrerad lista efter markören.

  Om du vill avsluta en numrerad lista trycker eller klickar du på knappen **Numrerad** igen eller anger två radmatningar.

* Minska indrag

  ![](/help/assets/chlimage_1-76.png)

  Används för att minska indragsnivån för den markerade texten eller texten som anges efter markören.

  Endast aktivt om markörens markerade text eller position redan är indragen.

* Indrag

  ![](/help/assets/chlimage_1-77.png)

  Används för att öka indragsnivån för den markerade texten eller texten som anges efter markören.

* Tabell

  ![](/help/assets/chlimage_1-78.png)

  Används för att infoga en tabell i texten. Om du väljer det här alternativet öppnas ett fönster där du kan ange tabellinformation.

  ![](/help/assets/chlimage_1-79.png)

   * **Kolumner** - Antal kolumner i tabellen (obligatoriskt)
   * **Rader** - antalet rader i tabellen (obligatoriskt)
   * **Bredd** - Tabellens bredd
   * **Höjd** - tabellens höjd
   * **Cellfyllnad** g - Utrymmet runt cellinnehållet
   * **Cellmellanrum** - Mellanrummet mellan celler
   * **Kant** - vikten på tabellens kantlinjer
   * Om för tabellrubriken:

      * Den första raden ska användas
      * Den första kolumnen ska användas
      * Den första raden och den första kolumnen ska användas
      * Eller så får ingen rubrik användas.

   * **Beskrivning** - Tabellens beskrivning

* Kontrollera stavning

  ![](/help/assets/chlimage_1-80.png)

  Används för att kontrollera stavningen i textinnehållet. Eventuella felstavningar stryks under med brutna, röda linjer.

* Specialtecken

  ![](/help/assets/chlimage_1-81.png)

  Används för att infoga specialtecken i texten. Om du väljer det här alternativet öppnas ett fönster där de tillgängliga tecknen visas.

  ![](/help/assets/chlimage_1-82.png)

  Tryck eller klicka på det önskade tecknet för att infoga det i texten efter markören. Det går att infoga flera tecken. Tryck eller klicka på x för att stänga markeringsfönstret.

* Source Edit

  ![](/help/assets/chlimage_1-83.png)

  Används för att visa och ändra textens HTML-källa.

  Tryck eller klicka på ikonen **Source Edit** om du vill ändra textens innehåll från den formaterade vyn så att du kan visa HTML i Raw-format. I det här läget är alla andra formateringsalternativ inaktiverade. Tryck eller klicka på ikonen **Source Edit** igen för att återgå till den formaterade vyn.

  >[!CAUTION]
  >
  >Som alltid när du har åtkomst till rå HTML måste du vara försiktig när du använder alternativet **Source Edit**!
  >
  >
  >HTML som angetts via **Source Edit** genomsöks efter XSS-risker och eventuella infogade skript tas bort och visas inte på den resulterande sidan. Felaktigt formaterade HTML som angavs i **Source Edit** kan emellertid bryta sidans mall, vilket kan leda till oväntad formatering eller oanvändbar återgivning av den resulterande sidan.

* Styckeformat

  ![](/help/assets/chlimage_1-84.png)

  Används för att tillämpa styckeformatering på den markerade texten eller på text som infogas efter markören. Om du väljer det här alternativet öppnas en listruta där styckeformatet är valt.

  ![](/help/assets/chlimage_1-85.png)

Textkomponenten kan även redigeras textbundet, men på grund av utrymmesbegränsningar är inte alla formateringsalternativ tillgängliga. Om du vill se alla alternativ växlar du till helskärmsläge.

![](/help/assets/chlimage_1-86.png)

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera vilka textformateringsalternativ som är tillgängliga för innehållsförfattarna.

### Funktioner {#features}

![](/help/assets/chlimage_1-28.png)

Följande funktioner kan aktiveras eller inaktiveras för komponenten.

* Klistra in oformaterad text
* Tidigare från ord
* Sök och ersätt
* Stavningskontroll
* Source-redigering

### Formatering {#formatting}

![](/help/assets/chlimage_1-29.png)

Följande formateringsalternativ kan aktiveras eller inaktiveras för komponenten.

* Tabell
* Listor
* Justering
* Fet, kursiv, understruken
* Länkar
* Under/upphöjd

### Styckeformat {#paragraph-styles}

![](/help/assets/chlimage_1-30.png)

Styckeformat kan aktiveras eller inaktiveras för komponenten. När det här alternativet är aktiverat kan du definiera vilka format som tillåts.

* Tryck eller klicka på knappen **Lägg till** för att infoga ett nytt format.
* Ange koden för formatet och en beskrivning som ska visas i redigeringsdialogrutan.
* Om du vill ta bort en formatknapp eller klickar på knappen **Ta bort** .
* Om du vill ändra ordningen på formaten trycker du eller klickar och drar i handtagen.

### Specialtecken {#special-characters}

![](/help/assets/chlimage_1-31.png)

Alternativet att infoga specialtecken kan aktiveras eller inaktiveras för komponenten. När det här alternativet är aktiverat kan du definiera tillåtna tecken.

* Tryck eller klicka på knappen **Lägg till** för att infoga ett nytt tecken.
* Ange HTML-koden för tecknet och en beskrivning som visas i redigeringsdialogrutan.
* Om du vill ta bort en teckentryckning eller klicka på knappen **Ta bort** .
* Om du vill ändra ordningen på tecknen trycker du eller klickar och drar i handtagen.

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om textkomponenten [finns på GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/text/v1/text).

Hela kärnkomponentprojektet kan hämtas från GitHub.

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).
