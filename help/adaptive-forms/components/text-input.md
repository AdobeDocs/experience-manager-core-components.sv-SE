---
title: Adaptiv Forms Core-komponent - textinmatning (textruta)
description: Använda eller anpassa den adaptiva kärnkomponenten i Forms-textinmatning.
role: Architect, Developer, Admin, User
exl-id: 49d9fe69-0578-4489-beaa-a18cdb14add7
source-git-commit: be630c4d0a10ebaa679b77419b901fac818addb1
workflow-type: tm+mt
source-wordcount: '1786'
ht-degree: 0%

---

# Textinmatning (textruta) {#text-input-adaptive-forms-core-component}

Med en textinmatningskomponent (textruta) kan användaren ange och redigera en eller flera rader med text, beroende på inmatningselementets type-attribut. Textindatakomponenten kan placeras i ett formulär och är vanligtvis märkt med en användbar text som lätt identifierar dess syfte. Dessa är ett grundläggande element i alla typer av formulär som ofta används för att samla in olika typer av data från användarna, de är enkla, flexibla och kan konfigureras för att validera indata och förbättra informationsinsamlingen.


**Exempel**

![](/help/adaptive-forms/assets/text-input.png)


## Användning {#reasons-to-use-text-input-field}

Det finns flera skäl till att använda textinmatningskomponenten i ett adaptivt formulär:

* **Datainsamling**: Textinmatningsfält är ett av de vanligaste formulärelementen som används för att samla in en mängd olika typer av information från användare, till exempel namn, e-postadresser, telefonnummer och andra typer av textdata.

* **Användarvänlig**: Textinmatningsfält är enkla och enkla att använda, vilket gör det enkelt för användarna att ange och redigera text.

* **Flexibilitet**: Textinmatningsfält kan användas för att samla in en mängd olika typer av information, från korta textinmatningar med en rad till längre textinmatningar med flera rader.

## Version och kompatibilitet {#version-and-compatibility}

Den adaptiva Forms Accordion Core-komponenten släpptes i februari 2023 som en del av Core Components 2.0.4 för Cloud Service och Core Components 1.1.12 för AEM 6.5.16.0 Forms eller senare. Här är en tabell med alla versioner som stöds, AEM kompatibilitet och länkar till motsvarande dokumentation:

| Komponentversion | AEM as a Cloud Service | AEM 6.5.16.0 Forms eller senare |
|---|---|---|
| v1 | Kompatibel med<br>[version 2.0.4](/help/adaptive-forms/version.md) och senare | Kompatibel med<br>[version 1.1.12](/help/adaptive-forms/version.md) och senare men mindre än 2.0.0. |

Mer information om versioner och versioner av kärnkomponenter finns i [Huvudkomponentversioner](/help/adaptive-forms/version.md) -dokument.

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Teknisk information {#technical-details}

Få den senaste informationen om de adaptiva Forms-flikarna i Top Core-komponenten i den tekniska dokumentationen om [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/textinput/v1/textinput). Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Du kan enkelt anpassa textinmatningen för besökare med dialogrutan Konfigurera. Du kan också enkelt definiera alternativ för textinmatning för en smidig användarupplevelse.

![Fliken Grundläggande](/help/adaptive-forms/assets/textinput_basictab.png)

* **Namn** - Du kan enkelt identifiera en formulärkomponent med dess unika namn både i formuläret och i regelredigeraren, men namnet får inte innehålla blanksteg eller specialtecken.

* **Titel** - Med dess titel kan du enkelt identifiera en komponent i ett formulär. Som standard visas titeln ovanpå komponenten. Om du inte lägger till en titel visas komponentens namn i stället för rubriktexten.

* **Dölj titel** - Välj alternativet om du vill dölja komponentens titel.

* **Platshållartext** - Platshållartext i en formulärkomponent refererar till en kort etikett eller en fråga som visas i ett inmatningsfält som ett tips till användaren om vilken typ av information som förväntas anges i det fältet. Platshållartext försvinner när användaren börjar skriva i fältet och visas igen om fältet lämnas tomt. Den ger användaren en visuell referens, men fungerar inte som en permanent etikett eller ett permanent värde för fältet.

* **Bindningsreferens** - En bind referens är en referens till ett dataelement som lagras i en extern datakälla och används i ett formulär. Med den binda referensen kan du binda data dynamiskt till formulärfält så att formuläret kan visa de senaste data från datakällan. En bindningsreferens kan till exempel användas för att visa en kunds namn och adress i ett formulär baserat på kundens ID som anges i formuläret. Bindningsreferensen kan också användas för att uppdatera datakällan med data som anges i formuläret. På så sätt kan AEM Forms skapa formulär som interagerar med externa datakällor, vilket ger en smidig användarupplevelse för att samla in och hantera data.

* **Dölj komponent** - Välj alternativet att dölja komponenten från formuläret. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren. Detta är användbart när du behöver lagra information som inte behöver visas eller ändras direkt av användaren.

* **Inaktivera komponent** - Välj alternativet att inaktivera komponenten. Den inaktiverade komponenten är inte aktiv eller redigerbar av slutanvändaren. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.

* **Skrivskyddad** - Välj alternativet att göra komponenten icke-redigerbar. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.

* **Standardvärde** - Med det här alternativet kan du lägga till ett standardvärde i ett formulärfält. Texten försvinner när användaren börjar skriva i fältet. If **Inaktiverad komponent** eller **Skrivskyddad komponent** är markerat visas standardvärdet på skärmen. Om användaren inte anger något värde i formulärfältet skickas det här värdet när formuläret skickas.

* **Tillåt flera rader** - Med det här alternativet kan användaren ange flera rader i ett formulärfält.

* **Tillåt RTF** - I redigeringsdialogrutan finns standardverktyg för formatering av RTF-text som användaren kan använda för att formatera text.

* **Autofyll attribut** - Fyll i automatiskt fyller i formulärfält enligt ett mönster eller text som redan har angetts. När användaren börjar skriva text i formulärfältet visas förslag i en nedrullningsbar lista där han/hon kan välja lämpligt alternativ.

### Fliken Validering {#validation-tab}

![Fliken Validering](/help/adaptive-forms/assets/textinput_validationtab.png)

* **Obligatoriskt** - Välj det här alternativet om du vill visa komponenten i ett adaptivt formulär. Du kan inte välja **Dölj komponent** eller **Inaktivera komponent**  i **Grundläggande** när det här alternativet är markerat.

* **Felmeddelande** - Med det här alternativet kan du ange ett meddelande som visas om **Obligatoriskt** kryssrutan är markerad och fältet lämnas tomt.

* **Skriptverifieringsmeddelande** - Med det här alternativet kan du ange ett meddelande som ska visas om skriptvalideringen misslyckas.

* **Maximalt antal tecken** - Med det här alternativet kan du ange det maximala antalet tecken som tillåts i komponenten. Om du anger tecken som är större än det värde som anges i **Maximalt antal tecken** visas ett felmeddelande på skärmen. The **Felmeddelande för högsta antal tecken** kan du lägga till ett eget felmeddelande.

* **Felmeddelande för högsta antal tecken** - **Felmeddelande för högsta antal tecken** kan du lägga till ett anpassat felmeddelande om du anger tecken som är större än värdet som anges i **Maximalt antal tecken** alternativ.

* **Minsta antal tecken** - Med det här alternativet kan du ange det minsta antalet tecken som tillåts i fältet. Om du anger tecken som är mindre än det värde som anges i **Minsta antal tecken** visas ett felmeddelande på skärmen. The **Felmeddelande för minsta antal tecken** kan du lägga till ett eget felmeddelande.

* **Felmeddelande för minsta antal tecken** - **Felmeddelande för minsta antal tecken** kan du lägga till ett anpassat felmeddelande om du anger tecken som är mindre än värdet som anges i **Minsta antal tecken** alternativ.

The **Valideringsmönster** kan du ange ett mönster för att validera den angivna texten. Om texten inte kan valideras med det värde som anges i **Mönster** visas felmeddelandet på skärmen.

* **Mönster** - Med det här alternativet kan du ange tillåtna verifieringsmönster för text. Reguljära uttryck tillåts också.

* **Felmeddelande** - Med det här alternativet kan du ange ett meddelande som visas på skärmen om den angivna texten inte kan valideras med det värde som anges i **Mönster** option

### Fliken Hjälpinnehåll {#help-content-tab}

![Fliken Hjälpinnehåll](/help/adaptive-forms/assets/textinput_helptab.png)

* **Kort beskrivning** - En kort beskrivning är en kort textförklaring som ger ytterligare information eller förtydliganden om syftet med ett visst formulärfält. Det hjälper användaren att förstå vilken typ av data som ska anges i fältet och kan ge riktlinjer eller exempel som hjälper till att säkerställa att den angivna informationen är giltig och uppfyller de önskade kriterierna. Som standard är korta beskrivningar dolda. Aktivera **Visa alltid kort beskrivning** för att visa den under komponenten.

* **Visa alltid kort beskrivning** - Aktivera alternativet att visa den korta beskrivningen under komponenten.

* **Hjälptext** - Hjälptexten hänvisar till ytterligare information eller vägledning som användaren får för att hjälpa sig fylla i ett formulärfält på rätt sätt. Det visas när användaren klickar på hjälpikonen (i) som finns bredvid komponenten. Hjälptexten ger mer detaljerad information än etiketten eller platshållartexten för ett formulärfält och är utformad för att hjälpa användaren förstå fältets krav eller begränsningar. Den kan också ge förslag eller exempel som gör det enklare och exaktare att fylla i formuläret.

### Fliken Tillgänglighet {#accessibility-tab}

![Fliken Tillgänglighet](/help/adaptive-forms/assets/textinput_accessibiltytab.png)

**Text för skärmläsare** - Text för skärmläsare avser text som är avsedd att läsas av hjälpmedelstekniker, t.ex. skärmläsare, som används av personer med nedsatt syn. Den här texten innehåller en ljudbeskrivning av formulärfältets syfte och kan innehålla information om fältets titel, beskrivning, namn och relevanta meddelanden (anpassad text). Skärmläsartexten ser till att formuläret är tillgängligt för alla användare, även användare med nedsatt syn, och ger dem en fullständig förståelse för formulärfältet och dess krav.

## Designdialogruta {#design-dialog}

Designdialogrutan används för att definiera och hantera CSS-format för textrutekomponenten.

### Fliken Format {#styles-tab}

Fliken används för att definiera och hantera CSS-format för en komponent. Kärnkomponenten i den adaptiva Forms-textrutan stöder AEM [Formatsystem](/help/get-started/authoring.md#component-styling).

![Designdialogruta](/help/adaptive-forms/assets/telephoneinput_designdialog.png)

* **CSS-standardklasser**: Du kan ange en standard-CSS-klass för Core-komponenten för textrutan Adaptiv Forms.

* **Tillåtna format**: Du kan definiera format genom att ange ett namn och den CSS-klass som representerar formatet. Du kan till exempel skapa ett format med namnet&quot;bold text&quot; och ge CSS-klassen&quot;font-weight: bold&quot;. Du kan använda eller tillämpa dessa format på ett adaptivt formulär i en anpassad Forms-redigerare. Om du vill använda ett format väljer du den komponent du vill använda formatet på i Adaptiv Forms-redigerare, navigerar till egenskapsdialogrutan och väljer önskat format i dialogrutan **Stilar** listruta. Om du behöver uppdatera eller ändra formaten går du tillbaka till designdialogrutan, uppdaterar formaten på formatfliken och sparar ändringarna.

### Fliken Format {#format-tab}

På fliken Format kan du ange standardtalformat och anpassade talformat.

![Fliken Format](/help/adaptive-forms/assets/telephoneinput_format.png)


<!--

## Related article {#related-article}

* [Create a standalone Adaptive Form](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)

-->

>[!MORELIKETHIS]
>
>* [Dragspel](/help/adaptive-forms/components/accordion.md)
>* [Knapp](/help/adaptive-forms/components/button.md)
>* [Kryssrutegrupp](/help/adaptive-forms/components/checkbox-group.md)
>* [Datumväljaren](/help/adaptive-forms/components/date-picker.md)
>* [Nedrullningsbar lista](/help/adaptive-forms/components/drop-down.md)
>* [E-postinmatning](/help/adaptive-forms/components/email-input.md)
>* [Formulärbehållare](/help/adaptive-forms/components/form-container.md)
>* [Bifogad fil](/help/adaptive-forms/components/file-attachment.md)
>* [Sidfot](/help/adaptive-forms/components/footer.md)
>* [Sidhuvud](/help/adaptive-forms/components/header.md)
>* [Vågräta flikar](/help/adaptive-forms/components/horizontal-tabs.md)
>* [Bild](/help/adaptive-forms/components/image.md)
>* [Nummerindata](/help/adaptive-forms/components/number-input.md)
>* [Panelbehållare](/help/adaptive-forms/components/panel-container.md)
>* [Alternativknapp](/help/adaptive-forms/components/radio-button.md)
>* [Återställ knapp](/help/adaptive-forms/components/reset-button.md)
>* [Skicka-knapp](/help/adaptive-forms/components/submit-button.md)
>* [Telefonindata](/help/adaptive-forms/components/telephone-input.md)
>* [Text](/help/adaptive-forms/components/text.md)
>* [Titel](/help/adaptive-forms/components/title.md)
>* [guide](/help/adaptive-forms/components/wizard.md)

## Se även {#see-also}

{{see-also}}