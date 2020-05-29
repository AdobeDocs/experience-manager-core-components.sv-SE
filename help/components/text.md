---
title: Text Component
description: The Text Component is a rich text editing and composing component that features in-place editing.
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '2202'
ht-degree: 0%

---


# Text Component{#text-component}

The Core Component Text Component is a rich text editing and composing component that features in-place editing.

## Användning {#usage}

The Text Component offers a robust rich text editor that allows for easy text editing in a simplified, in-line editor as well as a full screen format.

The [edit dialog](#edit-dialog) features in-line editing with limited options with full functionality available in the full-screen edit dialog. Using the [design dialog](#design-dialog), text formatting options such as headings, special characters, and paragraph styles can be configured for the template for the content author.

## Version och kompatibilitet {#version-and-compatibility}

The current version of the Text Component is v2, which was introduced with release 2.0.0 of the Core Components in January 2018, and is described in this document.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponentversionerna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|---|---|
| v2 | - | Kompatibel | Kompatibel | Kompatibel |
| [v1](v1/text-v1.md) | Kompatibel | Kompatibel | Kompatibel | - |

Mer information om Core Component-versioner och -versioner finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

To experience the Text Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_text).

### Teknisk information {#technical-details}

The latest technical documentation about the Text Component [can be found on GitHub](https://adobe.com/go/aem_cmp_tech_text_v2).

Mer information om hur du utvecklar kärnkomponenter finns i dokumentationen till [Core Components Developer](/help/developing/overview.md).

## Textkomponenten och RTF-redigeraren {#the-text-component-and-the-rich-text-editor}

The Core Components Text Component leverages the AEM Rich Text Editor (RTE). The RTE provides content authors with a wide range of functionality for editing their text content. RTE är mycket flexibelt i sin konfiguration och erbjuder ett antal alternativ. Further details about how the RTE can be configured can be found in the articles [Configure the Rich Text Editor](https://docs.adobe.com/content/help/en/experience-manager-65/administering/operations/rich-text-editor.html) and [Configure the Rich Text Editor plug-ins](https://docs.adobe.com/content/help/en/experience-manager-65/administering/operations/configure-rich-text-editor-plug-ins.html).

The remainder of this article demonstrates the standard configuration of the Core Components Text Component with the out-of-the-box RTE configuration.

>[!NOTE]
>
>Only options enabled by [UI configurations of the RTE](https://docs.adobe.com/content/help/en/experience-manager-65/administering/operations/configure-rich-text-editor-plug-ins.html) are available by in the Text Component.

## Dialogrutan Redigera {#edit-dialog}

The edit dialog offers the standard rich text formatting tools a user would expect to compose text.

![Text Component&#39;s edit dialog](/help/assets/text-edit.png)

### Fet

![Bold icon](/help/assets/text-bold.png)

Används för att formatera text fet eller fet formatera text som skrivs efter markören.

**Ctrl+B** can be used as a keyboard shortcut.

### Kursiv

![Italic icon](/help/assets/text-italic.png)

Used to apply italicized formatting to selected text or italicize text entered after the cursor.

**Ctrl+I** can be used as a keyboard shortcut.

### Understrykning

![Underline icon](/help/assets/text-underline.png)

Used to apply underlined formatting to selected text or underline text entered after the cursor.

**Ctrl+U** kan användas som kortkommando.

### Subscript

![Subscript icon](/help/assets/text-subscript.png)

Används för att formatera markerad text eller text som skrivs efter markören som nedsänkt.

### Upphöjd

![Superscript icon](/help/assets/text-superscript.png)

Used to format selected text or text entered after the cursor as superscript.

### Klistra in som text

![Paste as text icon](/help/assets/text-paste-text.png)

Pastes any copied text as plain text without any formatting.

När du väljer det här alternativet öppnas ett fönster där texten kan klistras in som oformaterad text utan formatering som en förhandsvisning innan den infogas i texten. Acceptera genom att trycka eller klicka på bockmarkeringen, avbryt genom att trycka eller klicka på x.

![Klistra in som textexempel](/help/assets/text-paste-text-example.png)

### Klistra in från Word

![Ikonen Klistra in från Word](/help/assets/text-paste-word.png)

När du väljer det här alternativet öppnas ett fönster där texten kan klistras in med bibehållen formatering som en förhandsvisning innan den infogas i texten. Acceptera genom att trycka eller klicka på bockmarkeringen, avbryt genom att trycka eller klicka på x.

![Klistra in från Word-exempel](/help/assets/text-paste-word-example.png)

### Hyperlänk

![Ikon för hyperlänk](/help/assets/text-hyperlink.png)

Använd det här alternativet om du vill konvertera den markerade texten till en hyperlänk eller ändra en redan definierad länk. Det här alternativet är bara aktivt när text redan är markerad och öppnar ett fönster med ytterligare alternativ för att ange länken.

![Exempel på hyperlänk](/help/assets/text-hyperlink-example.png)

* Ange banan
   * Använd dialogrutan Öppna markering för att välja en bana i AEM
   * Om länken inte finns i AEM anger du den absoluta URL:en
      * Icke-absoluta sökvägar tolkas som relativa till AEM
* Ange alternativ beskrivande text för länken
* Välj länkbeteende
   * Mål
   * Samma flik
   * Ny flik
   * Överordnad ram
   * Övre bildruta
   Tryck eller klicka på bockmarkeringen för att använda länken eller på krysset för att avbryta.

### Bryt länk

![Ikonen Bryt länk](/help/assets/text-unlink.png)

Använd det här alternativet om du vill ta bort en länk som redan används för den markerade texten. Det här alternativet är bara aktivt när en länk redan är markerad.

### Sök

![Ikonen Sök](/help/assets/text-find.png)

Använd det här alternativet om du vill söka efter förekomsten av en angiven textsträng i texten. Om du väljer det här alternativet öppnas ett fönster där du kan ange sökalternativen.

![Sök exempel](/help/assets/text-find-example.png)

Ange texten som du vill söka efter och tryck eller klicka på **Sök** för att påbörja sökningen. Tryck eller klicka på x för att avbryta.
Om du vill göra en exakt matchning utifrån skiftläget, markerar du alternativet **Matcha gemener/VERSALER** innan du startar sökningen.
Om en matchning hittas markeras den och sökdialogrutan är nedtonad. Tryck eller klicka på knappen **Sök** igen i den nedtonade dialogrutan för att söka efter nästa förekomst.

![Sök efter exempel](/help/assets/text-find-example-found.png)

Om inga fler förekomster hittas visas ett meddelande och sökningen startas om från textens början.

![Sök efter exempel på inga fler förekomster](/help/assets/text-find-example-found-end.png)

### Replace

![Ikonen Ersätt](/help/assets/text-replace.png)

Använd det här alternativet om du vill söka efter förekomster av en angiven textsträng och ersätta matchningarna med en annan sträng. Om du väljer det här alternativet öppnas ett fönster där du kan ange alternativ för sökning och ersättning.

![Ersätt exempel](/help/assets/text-replace-example.png)

Ange den text som du vill söka efter samt den text som den ska ersättas med.

* Tryck eller klicka på **Sök** för att påbörja sökningen. Klicka eller tryck på x för att avbryta.
* Om du vill göra en exakt matchning utifrån skiftläget, markerar du alternativet **Matcha gemener/VERSALER** innan du startar sökningen.
* Markera **Ersätt alla** om du vill ersätta alla förekomster av texten samtidigt.

Om en matchning hittas markeras den och sökdialogrutan är nedtonad. Klicka på knappen **Sök** igen i den nedtonade dialogrutan om du vill söka efter nästa förekomst eller markera knappen **Ersätt** om du vill ersätta den markerade, matchade texten. Observera att knappen **Ersätt** bara är aktiv när en matchning har gjorts.

Dialogrutan Sök och ersätt blir genomskinlig när du klickar på Sök och blir ogenomskinlig när du klickar på Ersätt. Detta gör att författaren kan granska texten som författaren ska ersätta.

>[!NOTE]
>
>När du använder funktionen Ersätt bör du ange den ersättningssträng som ska ersättas samtidigt som söksträngen. Du kan dock fortfarande klicka på Sök för att söka efter strängen innan du ersätter den. Om ersättningssträngen anges efter att du klickat på Sök återställs sökningen till början av texten.


### Vänsterjustera text

![Vänsterjusteringsikon](/help/assets/text-left.png)

Används för att justera texten mot vänstermarginalen.

### Centrera text

![Centrera textikon](/help/assets/text-center.png)

Används för att centrera texten.

### Högerjustera text

![Högerjusteringsikon](/help/assets/text-right.png)

Används för att justera texten mot högermarginalen.

### Punkt

![Punktlikon](/help/assets/text-bullet.png)

Används för att formatera den markerade texten som en punktlista eller börja infoga en punktlista efter markören.

Om du vill avsluta en punktlista trycker eller klickar du på knappen **Punkt** en gång till eller anger två radmatningstecken.

### Numrerad

![Ikon för numrerad lista](/help/assets/text-numbered.png)

Används för att formatera den markerade texten som en numrerad lista eller börja infoga en numrerad lista efter markören.

Om du vill avsluta en numrerad lista trycker eller klickar du på knappen **Numrerad** igen eller anger två radmatningstecken.

### Minska indrag

![Ikon för indrag](/help/assets/text-outdent.png)

Används för att minska indragsnivån för den markerade texten eller texten som anges efter markören.

Endast aktivt om markörens markerade text eller position redan är indragen.

### Indrag

![Ikon för indrag](/help/assets/text-outdent.png)

Används för att öka indragsnivån för den markerade texten eller texten som anges efter markören.

### Tabell

![Tabellikon](/help/assets/text-table.png)

Används för att infoga en tabell i texten. Om du väljer det här alternativet öppnas ett fönster där du kan ange tabellinformation.

![Tabellexempel](/help/assets/text-table-example.png)

* **Kolumner** - Antal kolumner i tabellen (obligatoriskt)
* **Rader** - antalet rader i tabellen (obligatoriskt)
* **Bredd** - tabellens bredd
* **Höjd** - tabellens höjd
* **Cellutfyllnad** - Utrymmet runt cellinnehållet
* **Cellavstånd** - Avståndet mellan celler
* **Kant** - vikten på tabellens kantlinjer
   * Om för tabellrubriken:
      * Den första raden ska användas
      * Den första kolumnen ska användas
      * Den första raden och den första kolumnen ska användas
      * Eller så får ingen rubrik användas.
* **Bildtext** - Tabellens bildtext

### Kontrollera stavning

![Kontrollera stavningsikon](/help/assets/text-spellcheck.png)

Används för att kontrollera stavningen i textinnehållet. Eventuella felstavningar stryks under med brutna, röda linjer.

Mer information om stavningskontroll och anpassning av stavningskontrollordlistor finns i dokumentet [Konfigurera plugin-program](https://docs.adobe.com/content/help/en/experience-manager-65/administering/operations/configure-rich-text-editor-plug-ins.html)för textredigeraren.

### Specialtecken {#special-characters}

![Ikon för specialtecken](/help/assets/text-special-characters.png)

Används för att infoga specialtecken i texten. Om du väljer det här alternativet öppnas ett fönster där de tillgängliga tecknen visas.

![Exempel på specialtecken](/help/assets/text-special-characters-example.png)

Tryck eller klicka på det önskade tecknet för att infoga det i texten efter markören. Flera tecken kan infogas. Tryck eller klicka på x för att stänga markeringsfönstret.

### Redigera källa

![Ikon för källredigering](/help/assets/text-source.png)

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

![Ikon för styckeformat](/help/assets/text-paragraph.png)

Används för att tillämpa styckeformatering på den markerade texten eller på text som infogas efter markören. Om du väljer det här alternativet öppnas en listruta där styckeformatet är valt.

![Exempel på styckeformat](/help/assets/text-paragraph-example.png)

### Textbunden redigering {#in-line-editing}

Textkomponenten kan även redigeras textbundet, men på grund av utrymmesbegränsningar är inte alla formateringsalternativ tillgängliga. Om du vill se alla alternativ växlar du till helskärmsläge.

![Exempel på infogad redigering](/help/assets/text-edit-inline-example.png)

### Inställning och ID {#setting-id}

Med det här alternativet kan du styra komponentens unika identifierare i HTML-koden och i [datalagret](/help/developing/data-layer/overview.md).

* Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
* Om ett ID anges är det författarens ansvar att se till att det är unikt.
* Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera vilka textformateringsalternativ som är tillgängliga för innehållsförfattarna.

### Fliken Plugins {#plugins-tab}

Fliken Plugins används för att aktivera och inaktivera olika textformateringsalternativ som är tillgängliga för innehållsförfattarna.

### Funktioner {#features}

![Designdialogfunktioner](/help/assets/text-design-features.png)

Följande funktioner kan aktiveras eller inaktiveras för komponenten.

* Klistra in oformaterad text
* Tidigare från ord
* Sök och ersätt
* Stavningskontroll
* Infogade bildändringsalternativ
* Redigera HTML-källa

### Formatering {#formatting}

![Formatering av designdialogrutor](/help/assets/text-design-formatting.png)

Följande formateringsalternativ kan aktiveras eller inaktiveras för komponenten.

* Tabell
* Listor (punkt, nummer, indrag, indrag)
* Justering (vänster, höger, centrerad)
* Fet, kursiv, understruken
* Länkning (och bryta länkar)
* Sub/superscript

### Styckeformat {#paragraph-styles}

![Styckeformat i designdialogrutan](/help/assets/text-design-paragraph.png)

Styckeformat kan aktiveras eller inaktiveras för komponenten. När det här alternativet är aktiverat kan du definiera vilka format som tillåts.

* Tryck eller klicka på knappen **Lägg till** för att infoga ett nytt format.
* Ange koden för formatet och en beskrivning som ska visas i redigeringsdialogrutan.
* Om du vill ta bort en stil trycker du på eller klickar på **Ta bort** .
* Om du vill ändra ordningen på formaten trycker du eller klickar och drar i handtagen.

### Specialtecken {#configuring-special-characters}

![Specialtecken för designdialogrutor](/help/assets/text-design-special-characters.png)

Alternativet att infoga specialtecken kan aktiveras eller inaktiveras för komponenten. När du aktiverar det här alternativet kan du definiera tillåtna tecken.

* Tryck eller klicka på knappen **Lägg till** för att infoga ett nytt tecken.
* Ange tecknets HTML-kod och en beskrivning som ska visas i redigeringsdialogrutan.
* Om du vill ta bort en teckentryckning eller klickar på knappen **Ta bort** .
* Om du vill ändra ordningen på tecknen trycker du eller klickar och drar i handtagen.

## Fliken Format {#styles-tab}

Textkomponenten har stöd för AEM- [stilsystemet](/help/get-started/authoring.md#component-styling).
