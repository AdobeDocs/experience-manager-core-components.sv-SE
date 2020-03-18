---
title: Textkomponent
description: Komponenten Text är en textredigerings- och dispositionskomponent med funktioner för redigering på plats.
translation-type: tm+mt
source-git-commit: fe8a121520000ffd56ae3347469590e89121eaf0

---


# Textkomponent{#text-component}

Core Component Text Component Component Component är en textredigerings- och dispositionskomponent med redigering på plats.

## Användning {#usage}

Textkomponenten har en robust textredigerare som gör det enkelt att redigera text i en förenklad, textbunden redigerare och i ett helskärmsformat.

I [redigeringsdialogrutan](#edit-dialog) finns redigering direkt med begränsade alternativ med full funktionalitet i redigeringsdialogrutan i helskärmsläge. I [designdialogrutan](#design-dialog)kan du konfigurera textformateringsalternativ som rubriker, specialtecken och styckeformat för mallen för innehållsförfattaren.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Text Component är v2, som introducerades i version 2.0.0 av Core Components i januari 2018, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponentversionerna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|---|---|
| v2 | Kompatibel | Kompatibel | Kompatibel | Kompatibel |
| [v1](v1/text-v1.md) | Kompatibel | Kompatibel | Kompatibel | - |

Mer information om Core Component-versioner och -versioner finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill se textkomponenten och exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata, går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_text).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om textkomponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_text_v2).

Mer information om hur du utvecklar kärnkomponenter finns i dokumentationen till [Core Components Developer](/help/developing/overview.md).

## Textkomponenten och RTF-redigeraren {#the-text-component-and-the-rich-text-editor}

Komponenten Core Components Text använder AEM Rich Text Editor (RTE). RTE ger innehållsförfattare ett stort antal funktioner för att redigera textinnehåll. RTE är mycket flexibelt i sin konfiguration och erbjuder ett antal alternativ. Mer information om hur textredigeraren kan konfigureras finns i artiklarna [Konfigurera textredigeraren](https://docs.adobe.com/content/help/en/experience-manager-65/administering/operations/rich-text-editor.html) och [Konfigurera plugin-programmen](https://docs.adobe.com/content/help/en/experience-manager-65/administering/operations/configure-rich-text-editor-plug-ins.html)för textredigeraren.

Resten av den här artikeln demonstrerar standardkonfigurationen för textkomponenten för kärnkomponenter med RTE-konfigurationen som är klar att användas.

>[!NOTE]
>
>Endast alternativ som aktiveras av [gränssnittskonfigurationer för textredigeraren](https://docs.adobe.com/content/help/en/experience-manager-65/administering/operations/configure-rich-text-editor-plug-ins.html) är tillgängliga i textkomponenten.

## Dialogrutan Redigera {#edit-dialog}

I redigeringsdialogrutan finns de standardverktyg för RTF-formatering som en användare kan förvänta sig att skapa text.

![](/help/assets/screen_shot_2018-01-11at143025.png)

### Fet

![](/help/assets/screen_shot_2018-01-11at125602.png)

Används för att formatera text fet eller fet formatera text som skrivs efter markören.

**Ctrl+B** kan användas som kortkommando.

### Kursiv

![](/help/assets/screen_shot_2018-01-11at125609.png)

Används för att tillämpa kursiv formatering på markerad text eller kursiv om text som anges efter markören.

**Ctrl+I** kan användas som kortkommando.

### Understrykning

![](/help/assets/screen_shot_2018-01-11at125615.png)

Används för att tillämpa understruken formatering på markerad text eller understruken text som anges efter markören.

**Ctrl+U** kan användas som kortkommando.

### Nedsänkt

![](/help/assets/screen_shot_2018-01-11at125703.png)

Används för att formatera markerad text eller text som skrivs efter markören som nedsänkt.

### Upphöjd

![](/help/assets/screen_shot_2018-01-11at125708.png)

Används för att formatera markerad text eller text som skrivs efter markören som upphöjd text.

### Klistra in som text

![](/help/assets/screen_shot_2018-01-11at125713.png)

Klistrar in kopierad text som oformaterad text utan formatering.

När du väljer det här alternativet öppnas ett fönster där texten kan klistras in som oformaterad text utan formatering som en förhandsvisning innan den infogas i texten. Acceptera genom att trycka eller klicka på bockmarkeringen, avbryt genom att trycka eller klicka på x.

![](/help/assets/screen_shot_2018-01-11at143234.png)

### Klistra in från Word

![](/help/assets/screen_shot_2018-01-11at125717.png)

När du väljer det här alternativet öppnas ett fönster där texten kan klistras in med bibehållen formatering som en förhandsvisning innan den infogas i texten. Acceptera genom att trycka eller klicka på bockmarkeringen, avbryt genom att trycka eller klicka på x.

![](/help/assets/screen_shot_2018-01-11at143250.png)

### Hyperlänk

![](/help/assets/screen_shot_2018-01-11at125839.png)

Använd det här alternativet om du vill konvertera den markerade texten till en hyperlänk eller ändra en redan definierad länk. Det här alternativet är bara aktivt när text redan är markerad och öppnar ett fönster med ytterligare alternativ för att ange länken.

![](/help/assets/screen_shot_2018-01-11at130003.png)

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

### Bryt länk

![](/help/assets/screen_shot_2018-01-11at125901.png)

Använd det här alternativet om du vill ta bort en länk som redan används för den markerade texten. Det här alternativet är bara aktivt när en länk redan är markerad.

### Sök

![](/help/assets/screen_shot_2018-01-11at125906.png)

Använd det här alternativet om du vill söka efter förekomsten av en angiven textsträng i texten. Om du väljer det här alternativet öppnas ett fönster där du kan ange sökalternativen.

![](/help/assets/screen_shot_2018-01-11at130107.png)

Ange texten som du vill söka efter och tryck eller klicka på **Sök** för att påbörja sökningen. Tryck eller klicka på x för att avbryta.
Om du vill göra en exakt matchning utifrån skiftläget, markerar du alternativet **Matcha gemener/VERSALER** innan du startar sökningen.
Om en matchning hittas markeras den och sökdialogrutan är nedtonad. Tryck eller klicka på knappen **Sök** igen i den nedtonade dialogrutan för att söka efter nästa förekomst.

![](/help/assets/screen_shot_2018-01-11at130145.png)

Om inga fler förekomster hittas visas ett meddelande och sökningen startas om från textens början.

![](/help/assets/screen_shot_2018-01-11at130241.png)

### Replace

![](/help/assets/screen_shot_2018-01-11at125910.png)

Använd det här alternativet om du vill söka efter förekomster av en angiven textsträng och ersätta matchningarna med en annan sträng. Om du väljer det här alternativet öppnas ett fönster där du kan ange alternativ för sökning och ersättning.

![](/help/assets/screen_shot_2018-01-11at130441.png)

Ange den text som du vill söka efter samt den text som den ska ersättas med.

Tryck eller klicka på **Sök** för att påbörja sökningen. Klicka eller tryck på x för att avbryta.

Om du vill göra en exakt matchning utifrån skiftläget, markerar du alternativet **Matcha gemener/VERSALER** innan du startar sökningen.

Om en matchning hittas markeras den och sökdialogrutan är nedtonad. Klicka på knappen **Sök** igen i den nedtonade dialogrutan om du vill söka efter nästa förekomst eller markera knappen **Ersätt** om du vill ersätta den markerade, matchade texten. Observera att knappen **Ersätt** bara är aktiv när en matchning har gjorts.

Markera **Ersätt alla** om du vill ersätta alla förekomster av texten samtidigt.

### Vänsterjustera text

![](/help/assets/screen_shot_2018-01-11at142012.png)

Används för att justera texten mot vänstermarginalen.

### Centrera text

![](/help/assets/screen_shot_2018-01-11at142017.png)

Används för att centrera texten.

### Högerjustera text

![](/help/assets/screen_shot_2018-01-11at142021.png)

Används för att justera texten mot högermarginalen.

### Punkt

![](/help/assets/screen_shot_2018-01-11at142025.png)

Används för att formatera den markerade texten som en punktlista eller börja infoga en punktlista efter markören.

Om du vill avsluta en punktlista trycker eller klickar du på knappen **Punkt** en gång till eller anger två radmatningstecken.

### Numrerad

![](/help/assets/screen_shot_2018-01-11at142030.png)

Används för att formatera den markerade texten som en numrerad lista eller börja infoga en numrerad lista efter markören.

Om du vill avsluta en numrerad lista trycker eller klickar du på knappen **Numrerad** igen eller anger två radmatningstecken.

### Minska indrag

![](/help/assets/screen_shot_2018-01-11at141917.png)

Används för att minska indragsnivån för den markerade texten eller texten som anges efter markören.

Endast aktivt om markörens markerade text eller position redan är indragen.

### Indrag

![](/help/assets/screen_shot_2018-01-11at141922.png)

Används för att öka indragsnivån för den markerade texten eller texten som anges efter markören.

### Tabell

![](/help/assets/screen_shot_2018-01-11at141928.png)

Används för att infoga en tabell i texten. Om du väljer det här alternativet öppnas ett fönster där du kan ange tabellinformation.

![](/help/assets/screen_shot_2018-01-11at142405.png)

* **Kolumner** Antalet kolumner i tabellen (obligatoriskt)
* **Rader** Antalet rader i tabellen (obligatoriskt)
* **Bredd** Tabellens bredd
* **Höjd** Tabellens höjd
* **Cellutfyllnad** Utrymmet runt cellinnehållet
* **Cellavstånd** Avståndet mellan celler
* **Kant** Bredden på tabellens kantlinjer
* Om för tabellrubriken:
   * Den första raden ska användas
   * Den första kolumnen ska användas
   * Den första raden och den första kolumnen ska användas
   * Eller så får ingen rubrik användas.
* **Bildtext** Tabellens bildtext

### Kontrollera stavning

![](/help/assets/screen_shot_2018-01-11at141935.png)

Används för att kontrollera stavningen i textinnehållet. Eventuella felstavningar stryks under med brutna, röda linjer.

Mer information om stavningskontroll och anpassning av stavningskontrollordlistor finns i dokumentet [Konfigurera plugin-program](https://docs.adobe.com/content/help/en/experience-manager-65/administering/operations/configure-rich-text-editor-plug-ins.html)för textredigeraren.

### Specialtecken {#special-characters}

![](/help/assets/screen_shot_2018-01-11at142600.png)

Används för att infoga specialtecken i texten. Om du väljer det här alternativet öppnas ett fönster där de tillgängliga tecknen visas.

![](/help/assets/screen_shot_2018-01-11at142635.png)

Tryck eller klicka på det önskade tecknet för att infoga det i texten efter markören. Flera tecken kan infogas. Tryck eller klicka på x för att stänga markeringsfönstret.

### Redigera källa

![](/help/assets/screen_shot_2018-01-11at142746.png)

Används för att visa och ändra textens HTML-källa.

Tryck eller klicka på ikonen **Källredigering** om du vill ändra textens innehåll från den formaterade vyn för att visa rå HTML-kod. I det här läget är alla andra formateringsalternativ inaktiverade. Tryck eller klicka på ikonen **Källredigering** igen för att gå tillbaka till den formaterade vyn.

>[!CAUTION]
>
>Som alltid när du har åtkomst till rå HTML måste du vara försiktig när du använder alternativet **Källredigering** !
>
>HTML som anges via **Källredigering** genomsöks efter XSS-risker och eventuella infogade skript tas bort och visas inte på den resulterande sidan. Felformaterad HTML som angetts i **Källredigering** kan emellertid bryta sidans mall, vilket resulterar i oväntad formatering eller återgivning av den resulterande sidan som inte kan användas.

>[!NOTE]
>
>Eftersom HTML som anges via **Källredigering** genomsöks efter XSS-risker och eventuella skript och automatiskt tar bort dem som hittas, kan det faktiska innehållet som behålls variera från vad som angetts i **Källredigering**. Om du vill spara ändringar som gjorts med **Källredigering** måste du därför först avsluta **Källredigering** för att visa texten i den vanliga redigeraren innan du sparar.

### Styckeformat

![](/help/assets/screen_shot_2018-01-11at142752.png)

Används för att tillämpa styckeformatering på den markerade texten eller på text som infogas efter markören. Om du väljer det här alternativet öppnas en listruta där styckeformatet är valt.

![](/help/assets/screen_shot_2018-01-11at142828.png)

Textkomponenten kan även redigeras textbundet, men på grund av utrymmesbegränsningar är inte alla formateringsalternativ tillgängliga. Om du vill se alla alternativ växlar du till helskärmsläge.

![](/help/assets/screen_shot_2018-01-11at142921.png)

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera vilka textformateringsalternativ som är tillgängliga för innehållsförfattarna.

### Fliken Plugins {#plugins-tab}

Fliken Plugins används för att aktivera och inaktivera olika textformateringsalternativ som är tillgängliga för innehållsförfattarna.

### Funktioner {#features}

![](/help/assets/chlimage_1-28.png)

Följande funktioner kan aktiveras eller inaktiveras för komponenten.

* Klistra in oformaterad text
* Tidigare från ord
* Sök och ersätt
* Stavningskontroll
* Källredigering

### Formatering {#formatting}

![](/help/assets/chlimage_1-29.png)

Följande formateringsalternativ kan aktiveras eller inaktiveras för komponenten.

* Tabell
* Listor
* Justering
* Fet, kursiv, understruken
* Länkar
* Sub/superscript

### Styckeformat {#paragraph-styles}

![](/help/assets/chlimage_1-30.png)

Styckeformat kan aktiveras eller inaktiveras för komponenten. När det här alternativet är aktiverat kan du definiera vilka format som tillåts.

* Tryck eller klicka på knappen **Lägg till** för att infoga ett nytt format.
* Ange koden för formatet och en beskrivning som ska visas i redigeringsdialogrutan.
* Om du vill ta bort en stil trycker du på eller klickar på **Ta bort** .
* Om du vill ändra ordningen på formaten trycker du eller klickar och drar i handtagen.

### Konfigurera specialtecken {#configuring-special-characters}

![](/help/assets/chlimage_1-31.png)

Alternativet att infoga specialtecken kan aktiveras eller inaktiveras för komponenten. När du aktiverar det här alternativet kan du definiera tillåtna tecken.

* Tryck eller klicka på knappen **Lägg till** för att infoga ett nytt tecken.
* Ange tecknets HTML-kod och en beskrivning som ska visas i redigeringsdialogrutan.
* Om du vill ta bort en teckentryckning eller klickar på knappen **Ta bort** .
* Om du vill ändra ordningen på tecknen trycker du eller klickar och drar i handtagen.

## Fliken Format {#styles-tab}

Textkomponenten har stöd för AEM- [stilsystemet](/help/get-started/authoring.md#component-styling).
