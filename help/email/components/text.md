---
title: E-posttextkomponent
description: E-posttextkomponenten är en textredigerings- och dispositionskomponent med funktioner för redigering på plats.
role: Architect, Developer, Admin, User
exl-id: 4aa192f6-8314-40e7-8732-c6626d647986
source-git-commit: 3abc29e0c186a84f079d5938b8b716f4c7378d65
workflow-type: tm+mt
source-wordcount: '2261'
ht-degree: 0%

---


# E-posttextkomponent {#email-text-component}

E-posttextkomponenten är en textredigerings- och dispositionskomponent med funktioner för redigering på plats.

## Användning {#usage}

E-posttextkomponenten är en robust textredigerare som gör det enkelt att redigera text i en förenklad, textbunden redigerare och i ett helskärmsformat.

* Dialogrutan [Redigera](#edit-dialog) innehåller redigeringsfunktioner i rad med begränsade alternativ med full funktionalitet i redigeringsdialogrutan i helskärmsläge.
* Med hjälp av designdialogrutan [kan ](#design-dialog)-textformateringsalternativ som rubriker, specialtecken och styckeformat konfigureras för mallen för innehållsförfattaren.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av e-posttextkomponenten är v1, som introducerades i version X av e-postkärnkomponenterna i oktober 2022, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | Kompatibel | - |

Mer information om Core Component-versioner och -versioner finns i dokumentet [Email Core Components Versions.](/help/email/versions.md)

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om e-posttextkomponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_email_text_v1).

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).

## E-posttextkomponenten och RTF-redigeraren {#the-text-component-and-the-rich-text-editor}

Komponenten för e-posttext använder AEM RTF-redigeraren. RTE ger innehållsförfattare ett stort antal funktioner för att redigera textinnehåll. RTE är flexibelt i sin konfiguration och erbjuder ett antal alternativ. Mer information om hur textredigeraren kan konfigureras finns i artiklarna [Konfigurera textredigeraren](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/configuring-and-extending/rich-text-editor.html) och [Konfigurera plugin-programmen för textredigeraren](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/configuring-and-extending/configure-rich-text-editor-plug-ins.html).

Resten av det här dokumentet demonstrerar standardkonfigurationen för e-posttextkomponenten med den färdiga RTE-konfigurationen.

>[!NOTE]
>
>Endast alternativ som har aktiverats av [gränssnittskonfigurationer för RTE](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/configuring-and-extending/configure-rich-text-editor-plug-ins.html) är tillgängliga i e-posttextkomponenten.

## Dialogrutan Redigera {#edit-dialog}

![Textkomponentens redigeringsdialogruta](/help/email/assets/email-text-edit.png)

### Formateringsalternativ {#options}

I redigeringsdialogrutan finns de standardverktyg för RTF-formatering som en användare kan förvänta sig att komponera text.

#### Fet

![Fet ikon](/help/assets/text-bold.png)

Används för att formatera text fet eller fet formatera text som skrivs efter markören.

**Ctrl+B** kan användas som kortkommando.

#### Kursiv

![Kursiv ikon](/help/assets/text-italic.png)

Används för att tillämpa kursiv formatering på markerad text eller kursiv om text som anges efter markören.

**Ctrl+I** kan användas som kortkommando.

#### Understruken

![Understrykningsikon](/help/assets/text-underline.png)

Används för att tillämpa understruken formatering på markerad text eller understruken text som anges efter markören.

**Ctrl+U** kan användas som kortkommando.

#### Nedsänkt

![Ikon för nedsänkt text](/help/assets/text-subscript.png)

Används för att formatera markerad text eller text som skrivs efter markören som nedsänkt.

#### Upphöjd

![Upphöjd ikon](/help/assets/text-superscript.png)

Används för att formatera markerad text eller text som skrivs efter markören som upphöjd text.

#### Klistra in som text

![Ikonen Klistra in som text](/help/assets/text-paste-text.png)

Klistrar in kopierad text som oformaterad text utan formatering.

När du väljer det här alternativet öppnas ett fönster där texten kan klistras in som oformaterad text utan formatering som en förhandsvisning innan den infogas i texten. Acceptera genom att trycka eller klicka på bockmarkeringen, avbryt genom att trycka eller klicka på x.

![Exempel på inklistring som text](/help/assets/text-paste-text-example.png)

#### Klistra in från Word

![Ikonen Klistra in från Word](/help/assets/text-paste-word.png)

När du väljer det här alternativet öppnas ett fönster där texten kan klistras in med bibehållen formatering som en förhandsvisning innan den infogas i texten. Acceptera genom att trycka eller klicka på bockmarkeringen, avbryt genom att trycka eller klicka på x.

![Exempel på Klistra in från Word](/help/assets/text-paste-word-example.png)

#### Hyperlänk

![Hyperlänkikon](/help/assets/text-hyperlink.png)

Använd det här alternativet om du vill konvertera den markerade texten till en hyperlänk eller ändra en redan definierad länk. Med det här alternativet öppnas ett fönster med ytterligare alternativ för att ange länken.

![Exempel på hyperlänk](/help/assets/text-hyperlink-example.png)

* Ange banan
   * Använd dialogrutan **Öppna markering** för att välja en bana i AEM
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

#### Bryt länk

![Ikonen Bryt länk](/help/assets/text-unlink.png)

Använd det här alternativet om du vill ta bort en länk som redan har tillämpats på den markerade texten. Det här alternativet är bara aktivt när en länk redan är markerad.

#### Ankarpunkt {#anchor}

![Ankarikon](/help/email/assets/anchor.png)

Använd det här alternativet om du vill infoga en ankarpunkt i texten.

#### Sök

![Ikonen Sök](/help/assets/text-find.png)

Använd det här alternativet om du vill söka efter förekomsten av en angiven textsträng i texten. Om du väljer det här alternativet öppnas ett fönster där du kan ange sökalternativen.

![Sök exempel](/help/assets/text-find-example.png)

Ange den text som du vill söka efter och tryck eller klicka på **Sök** för att påbörja sökningen. Tryck eller klicka på x för att avbryta.
Om du vill göra en exakt matchning utifrån skiftläget, markerar du alternativet **Matcha skiftläge** innan du startar sökningen.
Om en matchning hittas markeras den och sökdialogrutan är nedtonad. Tryck eller klicka på knappen **Sök** igen i den nedtonade dialogrutan för att söka efter nästa förekomst.

![Exempel på sökning hittades](/help/assets/text-find-example-found.png)

Om inga fler förekomster hittas visas ett meddelande och sökningen startas om från textens början.

![Sök efter exempel på inga fler förekomster](/help/assets/text-find-example-found-end.png)

#### Ersätt

![Ikonen Ersätt](/help/assets/text-replace.png)

Använd det här alternativet om du vill söka efter förekomster av en angiven textsträng och ersätta matchningarna med en annan sträng. Om du väljer det här alternativet öppnas ett fönster där du kan ange alternativ för sökning och ersättning.

![Ersätt exempel](/help/assets/text-replace-example.png)

Ange den text som du vill söka efter samt den text som den ska ersättas med.

* Tryck eller klicka på **Sök** för att påbörja sökningen. Klicka eller tryck på x för att avbryta.
* Om du vill göra en exakt matchning utifrån skiftläget, markerar du alternativet **Matcha skiftläge** innan du startar sökningen.
* Välj **Ersätt alla** om du vill ersätta alla förekomster av texten samtidigt.

Om en matchning hittas markeras den och sökdialogrutan är nedtonad. Klicka på knappen **Sök** igen i den nedtonade dialogrutan om du vill söka efter nästa förekomst, eller välj knappen **Ersätt** om du vill ersätta den markerade, matchade texten. Knappen **Ersätt** är bara aktiv när en matchning har gjorts.

Dialogrutan Sök och ersätt blir genomskinlig när du klickar på Sök och blir ogenomskinlig när du klickar på Ersätt. Detta gör att författaren kan granska texten som författaren ska ersätta.

>[!NOTE]
>
>När du använder ersättningsfunktionen ska strängen som ska ersättas anges samtidigt som strängen som ska hittas. Du kan dock fortfarande klicka på Sök för att söka efter strängen innan du ersätter den. Om ersättningssträngen anges efter att du klickat på Sök återställs sökningen till början av texten.

#### Ångra

![Ångra-ikon](/help/email/assets/undo.png)

Används för att ångra den senaste redigeringen i RTF-redigeraren.

#### Gör om

![Ikonen Gör om](/help/email/assets/redo.png)

Används för att ångra en redigering som ångrats med ikonen Ångra.

#### Vänsterjustera text

![Ikonen Vänsterjustera](/help/assets/text-left.png)

Används för att justera texten mot vänstermarginalen.

#### Centrera text

![Centrera textikon](/help/assets/text-center.png)

Används för att centrera texten.

#### Högerjustera text

![Högerjustera ikon](/help/assets/text-right.png)

Används för att justera texten mot högermarginalen.

#### Punkt

![Bullet icon](/help/assets/text-bullet.png)

Används för att formatera den markerade texten som en punktlista eller börja infoga en punktlista efter markören.

Om du vill avsluta en punktlista trycker eller klickar du på knappen **Bullet** igen eller anger två vagnreturer.

#### Numrerad

![Ikon för numrerad lista](/help/assets/text-numbered.png)

Används för att formatera den markerade texten som en numrerad lista eller börja infoga en numrerad lista efter markören.

Om du vill avsluta en numrerad lista trycker eller klickar du på knappen **Numrerad** igen eller anger två radmatningar.

#### Minska indrag

![Ikon för indrag](/help/assets/text-outdent.png)

Används för att minska indragsnivån för den markerade texten eller texten som anges efter markören.

Endast aktivt om markörens markerade text eller position redan är indragen.

#### Indrag

![Ikon för indrag](/help/assets/text-indent.png)

Används för att öka indragsnivån för den markerade texten eller texten som anges efter markören.

#### Tabell

![Tabellikon](/help/assets/text-table.png)

Används för att infoga en tabell i texten. Om du väljer det här alternativet öppnas ett fönster där du kan ange tabellinformation.

![Exempel på tabell](/help/assets/text-table-example.png)

* **Kolumner** - Antal kolumner i tabellen (obligatoriskt)
* **Rader** - antalet rader i tabellen (obligatoriskt)
* **Bredd** - Tabellens bredd
* **Höjd** - tabellens höjd
* **Cellutfyllnad** - Utrymmet runt cellinnehållet
* **Cellmellanrum** - Mellanrummet mellan celler
* **Kant** - vikten på tabellens kantlinjer
   * Om för tabellrubriken:
      * Den första raden ska användas
      * Den första kolumnen ska användas
      * Den första raden och den första kolumnen ska användas
      * Eller så får ingen rubrik användas.
* **Beskrivning** - Tabellens beskrivning

#### Bild

![Bildikon](/help/email/assets/image-icon.png)

Används för att justera en infogad bild.

#### Kontrollera stavning

![Kontrollera stavningsikon](/help/assets/text-spellcheck.png)

Används för att kontrollera stavningen i textinnehållet. Eventuella felstavningar stryks under med brutna, röda linjer.

Mer information om stavningskontroll och anpassning av stavningskontrollordlistor finns i dokumentet [Konfigurera plugin-program för textredigeraren](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/configuring-and-extending/configure-rich-text-editor-plug-ins.html).

#### Specialtecken {#special-characters}

![Ikon för specialtecken](/help/assets/text-special-characters.png)

Används för att infoga specialtecken i texten. Om du väljer det här alternativet öppnas ett fönster där de tillgängliga tecknen visas.

![Exempel på specialtecken](/help/assets/text-special-characters-example.png)

Tryck eller klicka på det önskade tecknet för att infoga det i texten efter markören. Det går att infoga flera tecken. Tryck eller klicka på x för att stänga markeringsfönstret.

#### Source Edit

![Source redigeringsikon](/help/assets/text-source.png)

Används för att visa och ändra textens HTML-källa.

Tryck eller klicka på ikonen **Source Edit** om du vill ändra textens innehåll från den formaterade vyn så att du kan visa HTML i Raw-format. I det här läget är alla andra formateringsalternativ inaktiverade. Tryck eller klicka på ikonen **Source Edit** igen för att återgå till den formaterade vyn.

>[!CAUTION]
>
>Som alltid när du har åtkomst till Raw-HTML måste du vara försiktig när du använder alternativet **Source Edit**!
>
>HTML som anges via **Source Edit** genomsöks efter XSS-risker och eventuella infogade skript tas bort och visas inte på den resulterande sidan. Felformaterad HTML som angetts i **Source Edit** kan emellertid bryta sidans mall, vilket resulterar i oväntad formatering eller oanvändbar återgivning av den resulterande sidan.

>[!NOTE]
>
>Eftersom HTML som anges via **Source Edit** genomsöks efter XSS-risker och eventuella skript och automatiskt tar bort dem som hittas, kan det faktiska innehållet som behålls variera från det som angavs i **Source Edit**. Om du vill spara ändringar som gjorts med **Source Edit** måste du därför först avsluta **Source Edit** och visa texten i den vanliga redigeraren innan du sparar.

#### Styckeformat

![Ikon för styckeformat](/help/assets/text-paragraph.png)

Används för att tillämpa styckeformatering på den markerade texten eller på text som infogas efter markören. Om du väljer det här alternativet öppnas en listruta där styckeformatet är valt.

![Exempel på styckeformat](/help/assets/text-paragraph-example.png)

#### Välj Adobe Campaign-variabel

![Välj Adobe Campaign-variabelikon](/help/email/assets/select-adobe-campaign-variable-icon.png)

Öppnar dialogrutan [Välj Adobe Campaign-variabel](/help/email/campaign-variables.md) där du kan infoga dynamiskt innehåll från Adobe Campaign.

### Textbunden redigering {#in-line-editing}

Textkomponenten kan även redigeras online. Om du vill redigera textbunden markerar du E-posttextkomponenten på innehållssidan.

![Välj e-posttextkomponent](/help/email/assets/email-text-select-component.png)

Tryck eller klicka sedan på ikonen **Redigera** i verktygsfältet som visas över komponenten. Verktygsfältet ändras och visar begränsade textformateringsalternativ (inklusive åtkomst till alternativet **Välj Adobe Campaign-variabel** ), och du kan redigera texten textbundet.

![Exempel på infogad redigering](/help/email/assets/email-text-edit-inline-example.png)

Tryck eller klicka på bockmarkeringen i verktygsfältet för att spara dina ändringar eller på X för att ta bort.

På grund av utrymmesbegränsningar är inte alla formateringsalternativ tillgängliga. Om du vill se alla alternativ växlar du till helskärmsläge.

### Ange ett ID {#setting-id}

Med det här alternativet kan du kontrollera den unika identifieraren för komponenten i HTM.

* Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
* Om ett ID anges är det författarens ansvar att se till att det är unikt.
* Om du ändrar ID:t kan det påverka CSS.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera vilka textformateringsalternativ som är tillgängliga för innehållsförfattarna.

### Fliken Plugins {#plugins-tab}

Fliken **Plugins** används för att aktivera och inaktivera olika textformateringsalternativ som är tillgängliga för innehållsförfattarna.

### Funktioner {#features}

![Designdialogfunktioner](/help/assets/text-design-features.png)

Följande funktioner kan aktiveras eller inaktiveras för komponenten.

* Klistra in oformaterad text
* Tidigare från ord
* Sök och ersätt
* Ångra och göra om
* Stavningskontroll
* Infogade bildändringsalternativ
* HTML källredigering

### Formatering {#formatting}

![Formatering i designdialogrutan](/help/assets/text-design-formatting.png)

Följande formateringsalternativ kan aktiveras eller inaktiveras för komponenten.

* Tabell
* Listor (punkt, nummer, indrag, indrag)
* Justering (vänster, höger, centrerad)
* Fet, kursiv, understruken
* Länkning (och bryta länkar)
* Under/upphöjd

### Styckeformat {#paragraph-styles}

![Styckeformat i designdialogrutan](/help/assets/text-design-paragraph.png)

Styckeformat kan aktiveras eller inaktiveras för komponenten. När det här alternativet är aktiverat kan du definiera vilka format som tillåts.

* Tryck eller klicka på knappen **Lägg till** för att infoga ett nytt format.
* Ange koden för formatet och en beskrivning som ska visas i redigeringsdialogrutan.
* Om du vill ta bort en stil trycker du på eller klickar på knappen **Ta bort** .
* Om du vill ändra ordningen på formaten trycker eller klickar du och drar i handtagen.

### Specialtecken {#configuring-special-characters}

![Specialtecken i designdialogrutan](/help/assets/text-design-special-characters.png)

Alternativet att infoga specialtecken kan aktiveras eller inaktiveras för komponenten. När det här alternativet är aktiverat kan du definiera tillåtna tecken.

* Tryck eller klicka på knappen **Lägg till** för att infoga ett nytt tecken.
* Ange HTML-koden för tecknet och en beskrivning som ska visas i redigeringsdialogrutan.
* Om du vill ta bort ett tecken trycker du på eller klickar på knappen **Ta bort** .
* Om du vill ändra ordningen på tecknen trycker du eller klickar och drar i handtagen.

## Fliken Format {#styles-tab}

Komponenten för e-posttext har stöd för AEM [style system](/help/get-started/authoring.md#component-styling).
