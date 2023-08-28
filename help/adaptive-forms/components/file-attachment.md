---
title: Adaptiv Forms Core-komponent - bifogad fil
description: Använda eller anpassa den adaptiva Forms-filbilagan Core Component.
role: Architect, Developer, Admin, User
exl-id: 64a54fc6-db52-481f-bf5a-60c05122004d
source-git-commit: ad3e3bca5cb46f14e864e4704c90ac3b62779794
workflow-type: tm+mt
source-wordcount: '1580'
ht-degree: 0%

---

# Bifogad fil {#file-attachment-adaptive-forms-core-component}

En bifogad fil i ett adaptivt formulär gör att användarna kan välja och överföra filer från sin lokala dator eller enhet. Komponenten för bifogad fil kan konfigureras så att den tillåter specifika filtyper, storleksbegränsningar och flera bifogade filer.

**Exempel**

![](/help/adaptive-forms/assets/upload-image.png)


## Användning {#reasons-to-use-file-attachment}

Det finns många skäl till att det är bra att ta med en bifogad fil i ett adaptivt format, bland annat:

* **Samlar in ytterligare information**: En bifogad fil gör att användare kan överföra dokument, bilder, videoklipp eller andra typer av filer som en del av formuläröverföringen. Detta kan vara användbart för att samla in ytterligare information som återköp, portföljer eller stöddokumentation.

* **Enkel delning av stora filer**: Komponenten för bifogad fil gör det enkelt att dela stora filer utan att behöva använda externa fildelningstjänster.

* **Bekvämlighet**: Komponenten för bifogad fil gör att användare kan överföra filer från sin lokala dator utan att behöva navigera bort från formuläret eller använda andra verktyg.

* **Dataanalys**: Komponenten för bifogad fil kan användas för att samla in data från olika källor och analysera den, eller använda den som indata för vidare bearbetning.

* **Användarupplevelse**: Komponenten för bifogad fil kan användas för att göra formuläret mer användarvänligt genom att ge användarna ett tydligt och intuitivt sätt att överföra filer.

## Version och kompatibilitet {#version-and-compatibility}

Den adaptiva Forms Accordion Core-komponenten släpptes i februari 2023 som en del av Core Components 2.0.4 för Cloud Service och Core Components 1.1.12 för AEM 6.5.16.0 Forms eller senare. Här är en tabell med alla versioner som stöds, AEM kompatibilitet och länkar till motsvarande dokumentation:

| Komponentversion | AEM as a Cloud Service | AEM 6.5.16.0 Forms eller senare |
|---|---|---|
| v1 | Kompatibel med<br>[version 2.0.4](/help/adaptive-forms/version.md) och senare | Kompatibel med<br>[version 1.1.12](/help/adaptive-forms/version.md) och senare men mindre än 2.0.0. |

Mer information om versioner och versioner av kärnkomponenter finns i [Huvudkomponentversioner](/help/adaptive-forms/version.md) -dokument.

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Teknisk information {#technical-details}

Hämta den senaste informationen om den adaptiva Forms-kärnkomponenten för bifogade filer i den tekniska dokumentationen om [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/fileinput/v1/fileinput). Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Med dialogrutan Konfigurera kan du enkelt anpassa den bifogade filen för besökare. Du kan också enkelt definiera alternativ för bifogade filer för en smidig användarupplevelse.

### Fliken Grundläggande {#basic-tab}

![fliken Grundläggande](/help/adaptive-forms/assets/fileattachement_basictab.png)

* **Namn** - Du kan enkelt identifiera en formulärkomponent med dess unika namn både i formuläret och i regelredigeraren, men namnet får inte innehålla blanksteg eller specialtecken.

* **Titel** - Med dess titel kan du enkelt identifiera en komponent i ett formulär. Som standard visas titeln ovanpå komponenten. Om du inte lägger till en titel visas komponentens namn i stället för rubriktexten.

* **Dölj titel** - Välj alternativet om du vill dölja komponentens titel.

* **Knapptitel** - Det här alternativet används för att ange etiketten för knappen som visas i ett adaptivt formulär.

* **Bindningsreferens** - En bind referens är en referens till ett dataelement som lagras i en extern datakälla och används i ett formulär. Med den binda referensen kan du binda data dynamiskt till formulärfält så att formuläret kan visa de senaste data från datakällan. En bindningsreferens kan till exempel användas för att visa en kunds namn och adress i ett formulär baserat på kundens ID som anges i formuläret. Bindningsreferensen kan också användas för att uppdatera datakällan med data som anges i formuläret. På så sätt kan AEM Forms skapa formulär som interagerar med externa datakällor, vilket ger en smidig användarupplevelse för att samla in och hantera data.
* **Dölj komponent** - Välj alternativet att dölja komponenten från formuläret. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren. Detta är användbart när du behöver lagra information som inte behöver visas eller ändras direkt av användaren.
* **Inaktivera komponent** - Välj alternativet att inaktivera komponenten. Den inaktiverade komponenten är inte aktiv eller redigerbar av slutanvändaren. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.
* **Skrivskyddad** - Välj alternativet att göra komponenten icke-redigerbar. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.
* **Tillåt flera bifogade filer** - Välj det här alternativet om du vill överföra flera bifogade filer med **Bifogad fil** -knappen.

### Fliken Validering {#validation-tab}

![Fliken Validering](/help/adaptive-forms/assets/fileattachment_validationtab.png)

* **Obligatoriskt** - Välj det här alternativet om du vill visa komponenten i ett adaptivt formulär. Du kan inte välja **Dölj komponent** eller **Inaktivera komponent**  i **Grundläggande** när det här alternativet är markerat.

* **Felmeddelande** - Med det här alternativet kan du ange ett meddelande som visas om **Obligatoriskt** kryssrutan är markerad och fältet lämnas tomt.

* **Skriptverifieringsmeddelande** - Med det här alternativet kan du ange ett meddelande som ska visas om skriptvalideringen misslyckas.

* **Felmeddelande för minsta antal filer** - Det här alternativet används för att ange ett felmeddelande som visas om du överför filer som är mindre än det angivna minsta antalet filer.

* **Felmeddelande för maximalt antal filer** - Det här alternativet används för att ange ett felmeddelande som visas om du överför filer som är större än det angivna maximala antalet filer.

* **Maximal filstorlek (MB)** - Med det här alternativet kan du ange en maximal filstorlek. Filstorlekar anges i MB.

* **Felmeddelande för maximal filstorlek** - Det här alternativet används för att ange ett felmeddelande som visas om du överför filer som är större än den filstorlek som anges i **Maximal filstorlek (MB)** alternativ.

* **Tillåtna filtyper** - Olika typer av filer som kan överföras med **Bifogad fil** här läggs knappen till. Du kan också lägga till ett nytt filformat genom att klicka på **Lägg till** -knappen. Filformat som stöds är: ljud, video, bild, text eller PDF. Du kan också ta bort eller ordna om tillåtna filtyper med:
   * **Ta bort** - Tryck eller klicka för att ta bort specifika filtyper.
   * **Ordna om** - Tryck eller klicka och dra för att ändra ordningen på tillåtna filtyper.

* **Felmeddelande för filtyp** - Med det här alternativet kan du ange ett felmeddelande som visas när du överför andra filformat än de som listas i **Tillåtna filtyper** alternativ.

### Fliken Hjälpinnehåll {#help-content-tab}

![Fliken Hjälpinnehåll](/help/adaptive-forms/assets/fileattachement_helpcontenttab.png)

* **Kort beskrivning** - En kort beskrivning är en kort textförklaring som ger ytterligare information eller förtydliganden om syftet med ett visst formulärfält. Det hjälper användaren att förstå vilken typ av data som ska anges i fältet och kan ge riktlinjer eller exempel som hjälper till att säkerställa att den angivna informationen är giltig och uppfyller de önskade kriterierna. Som standard är korta beskrivningar dolda. Aktivera **Visa alltid kort beskrivning** för att visa den under komponenten.

* **Visa alltid kort beskrivning** - Aktivera alternativet att visa den korta beskrivningen under komponenten.

* **Hjälptext** - Hjälptexten hänvisar till ytterligare information eller vägledning som användaren får för att hjälpa sig fylla i ett formulärfält på rätt sätt. Det visas när användaren klickar på hjälpikonen (i) som finns bredvid komponenten. Hjälptexten ger mer detaljerad information än etiketten eller platshållartexten för ett formulärfält och är utformad för att hjälpa användaren förstå fältets krav eller begränsningar. Den kan också ge förslag eller exempel som gör det enklare och exaktare att fylla i formuläret.

### Fliken Tillgänglighet {#accessibility-tab}


![Fliken Tillgänglighet](/help/adaptive-forms/assets/fileattachement_accessibilitytab.png)

* **Text för skärmläsare** - Text för skärmläsare avser text som är avsedd att läsas av hjälpmedelstekniker, t.ex. skärmläsare, som används av personer med nedsatt syn. Den här texten innehåller en ljudbeskrivning av formulärfältets syfte och kan innehålla information om fältets titel, beskrivning, namn och relevanta meddelanden (anpassad text). Skärmläsartexten ser till att formuläret är tillgängligt för alla användare, även användare med nedsatt syn, och ger dem en fullständig förståelse för formulärfältet och dess krav.


## Designdialogruta {#design-dialog}

Designdialogrutan används för att definiera och hantera CSS-format för komponenten för bifogade filer.

### Fliken Format {#styles-tab}

Kärnkomponenten för adaptiv bifogad Forms-fil stöder AEM [Formatsystem](/help/get-started/authoring.md#component-styling).

![Designdialogruta för bifogade filer](/help/adaptive-forms/assets/fileattachment_designdialog.png)

* **CSS-standardklasser**: Du kan ange en standard-CSS-klass för den adaptiva Forms-kärnkomponenten för bifogade filer.

* **Tillåtna format**: Du kan definiera format genom att ange ett namn och den CSS-klass som representerar formatet. Du kan till exempel skapa ett format med namnet&quot;bold text&quot; och ge CSS-klassen&quot;font-weight: bold&quot;. Du kan använda eller tillämpa dessa format på ett adaptivt formulär i en anpassad Forms-redigerare. Om du vill använda ett format väljer du den komponent du vill använda formatet på i Adaptiv Forms-redigerare, navigerar till egenskapsdialogrutan och väljer önskat format i dialogrutan **Stilar** listruta. Om du behöver uppdatera eller ändra formaten går du tillbaka till designdialogrutan, uppdaterar formaten på formatfliken och sparar ändringarna.

## Relaterad artikel {#related-article}

* [Skapa ett anpassat formulär i AEM Sites Page eller Experience Fragment](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html)

* [Skapa ett fristående anpassat formulär](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)


## Se även {#see-also}

* [Dragspel](/help/adaptive-forms/components/accordion.md)
* [Knapp](/help/adaptive-forms/components/button.md)
* [Kryssrutegrupp](/help/adaptive-forms/components/checkbox-group.md)
* [Datumväljaren](/help/adaptive-forms/components/date-picker.md)
* [Nedrullningsbar lista](/help/adaptive-forms/components/drop-down.md)
* [E-postinmatning](/help/adaptive-forms/components/email-input.md)
* [Formulärbehållare](/help/adaptive-forms/components/form-container.md)
* [Sidfot](/help/adaptive-forms/components/footer.md)
* [Sidhuvud](/help/adaptive-forms/components/header.md)
* [Vågräta flikar](/help/adaptive-forms/components/horizontal-tabs.md)
* [Bild](/help/adaptive-forms/components/image.md)
* [Nummerindata](/help/adaptive-forms/components/number-input.md)
* [Panelbehållare](/help/adaptive-forms/components/panel-container.md)
* [Alternativknapp](/help/adaptive-forms/components/radio-button.md)
* [Återställ knapp](/help/adaptive-forms/components/reset-button.md)
* [Skicka-knapp](/help/adaptive-forms/components/submit-button.md)
* [Telefonindata](/help/adaptive-forms/components/telephone-input.md)
* [Textindata](/help/adaptive-forms/components/text-input.md)
* [Text](/help/adaptive-forms/components/text.md)
* [Titel](/help/adaptive-forms/components/title.md)
* [guide](/help/adaptive-forms/components/wizard.md)