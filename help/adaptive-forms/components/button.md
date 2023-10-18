---
title: Adaptiv Forms Core-komponent - knapp
description: Använda eller anpassa den adaptiva Forms-knappens kärnkomponent.
role: Architect, Developer, Admin, User
exl-id: cb75929b-8c86-49d1-b51a-368f5b80b1a9
source-git-commit: 0026734a2e43c51c7f5af2b37492d61e8f779ac7
workflow-type: tm+mt
source-wordcount: '1443'
ht-degree: 0%

---

# Button-komponent {#button-component-adaptive-forms-core-component}

En knapp i ett adaptivt formulär är ett gränssnittselement som gör att användare kan initiera en åtgärd när de klickar på den. Knappelementet kan användas för att skicka ett formulär, återställa ett formulär eller utföra andra åtgärder som att navigera till en annan sida eller utlösa anpassad kod. Knappen kan skapas med komponenten Button Core.

Med den adaptiva Forms-regelredigeraren kan användare ange olika åtgärder för knappkomponenten. Dessa åtgärder kan bland annat vara att öppna en webbplats, visa eller dölja formulärkomponenter, lägga till en instans av en panel eller komponent, skicka eller återställa ett formulär.

Adaptiv Forms har olika komponenter för [Skicka-knapp](/help/adaptive-forms/components/submit-button.md) och [Knappen Återställ](/help/adaptive-forms/components/reset-button.md), vilket gör det enkelt för användarna att skicka eller återställa ett formulär. Button-komponenten kan konfigureras flexibelt för att köra dessa åtgärder baserat på specifika behov.

Användare kan komma åt den fullständiga listan över åtgärder som stöds för knappkomponenten med den adaptiva Forms-regelredigeraren. Med regelredigeraren kan användare skapa regler som aktiveras av olika händelser, till exempel när användaren klickar på en knapp, när ett formulär läses in eller när ett fältvärde ändras. Dessa regler kan sedan användas för att utföra olika åtgärder, som att visa eller dölja komponenter, ange fältvärden eller skicka formuläret.

## Användning {#reasons-to-use-button}

Det finns många skäl till att det är bra att ta med en knapp i en adaptiv form, bland annat:

* **Inlämning av formulär**: En knapp används vanligtvis för att skicka ett formulär, vilket gör att användare kan skicka data som de har angett till servern för bearbetning.

* **Formuläråterställning**: Knappar kan också användas för att återställa ett formulär och för att rensa alla data som användaren anger.

* **Navigering**: Knappar kan användas för att navigera mellan olika avsnitt i ett formulär eller olika sidor på en webbplats.

* **Händelsehantering**: Knappar kan användas för att utlösa olika händelser, som att öppna en webbplats, visa/dölja komponenter, lägga till en instans av en panel eller komponent till knappen.

* **Interaktivitet**: Knappar kan användas för att skapa interaktiva formulär. En knapp kan till exempel användas för att öppna en modal dialogruta eller för att växla mellan olika avsnitt i formuläret.

## Version och kompatibilitet {#version-and-compatibility}

Den adaptiva Forms Accordion Core-komponenten släpptes i februari 2023 som en del av Core Components 2.0.4 för Cloud Service och Core Components 1.1.12 för AEM 6.5.16.0 Forms eller senare. Här är en tabell med alla versioner som stöds, AEM kompatibilitet och länkar till motsvarande dokumentation:

| Komponentversion | AEM as a Cloud Service | AEM 6.5.16.0 Forms eller senare |
|---|---|---|
| v1 | Kompatibel med<br>[version 2.0.4](/help/adaptive-forms/version.md) och senare | Kompatibel med<br>[version 1.1.12](/help/adaptive-forms/version.md) och senare men mindre än 2.0.0. |

Mer information om versioner och versioner av kärnkomponenter finns i [Huvudkomponentversioner](/help/adaptive-forms/version.md) -dokument.

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Teknisk information {#technical-details}

Den senaste informationen om den adaptiva Forms Button Core-komponenten finns i den tekniska dokumentationen om [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/button/v1/button). Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Du kan enkelt anpassa knappupplevelsen för besökare med dialogrutan Konfigurera. Du kan också enkelt definiera knappegenskaper för en smidig användarupplevelse.

### Fliken Grundläggande {#basic-tab}

![Fliken Grundläggande](/help/adaptive-forms/assets/button_basictab.png)

* **Namn** - Du kan enkelt identifiera en formulärkomponent med dess unika namn både i formuläret och i regelredigeraren, men namnet får inte innehålla blanksteg eller specialtecken.

* **Titel** - Med dess titel kan du enkelt identifiera en komponent i ett formulär. Som standard visas titeln ovanpå komponenten. Om du inte lägger till en titel visas komponentens namn i stället för rubriktexten.

* **Bindningsreferens** - En bind referens är en referens till ett dataelement som lagras i en extern datakälla och används i ett formulär. Med den binda referensen kan du binda data dynamiskt till formulärfält så att formuläret kan visa de senaste data från datakällan. En bindningsreferens kan till exempel användas för att visa en kunds namn och adress i ett formulär baserat på kundens ID som anges i formuläret. Bindningsreferensen kan också användas för att uppdatera datakällan med data som anges i formuläret. På så sätt kan AEM Forms skapa formulär som interagerar med externa datakällor, vilket ger en smidig användarupplevelse för att samla in och hantera data.

* **Bindningsreferens för dokument** - Med det här alternativet kan du koppla ett adaptivt formulärfält till fältet Dokument för post. När användaren anger ett värde i ett länkat fält i ett adaptivt formulär visas det värdet också i det länkade fältet i motsvarande postdokument. En dokumentbindningsreferens kan t.ex. användas för att visa en kunds namn och adress i ett arkivdokument, baserat på kundens ID som anges i formuläret. På så sätt kan AEM Forms generera ett dokument för inspelning och erbjuder en smidig användarupplevelse för insamling och hantering av data.

* **Dölj komponent** - Välj alternativet att dölja komponenten från formuläret. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren. Detta är användbart när du behöver lagra information som inte behöver visas eller ändras direkt av användaren.
* **Inaktivera komponent** - Välj alternativet att inaktivera komponenten. Den inaktiverade komponenten är inte aktiv eller redigerbar av slutanvändaren. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.
* **Skrivskyddad** - Välj alternativet att göra komponenten icke-redigerbar. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.

### Fliken Hjälpinnehåll {#help-content}

![Fliken Hjälpinnehåll](/help/adaptive-forms/assets/button_helptab.png)

* **Kort beskrivning** - En kort beskrivning är en kort textförklaring som ger ytterligare information eller förtydliganden om syftet med ett visst formulärfält. Det hjälper användaren att förstå vilken typ av data som ska anges i fältet och kan ge riktlinjer eller exempel som hjälper till att säkerställa att den angivna informationen är giltig och uppfyller de önskade kriterierna. Som standard är korta beskrivningar dolda. Aktivera **Visa alltid kort beskrivning** för att visa den under komponenten.

* **Visa alltid kort beskrivning** - Aktivera alternativet att visa den korta beskrivningen under komponenten.

* **Hjälptext** - Hjälptexten hänvisar till ytterligare information eller vägledning som användaren får för att hjälpa sig fylla i ett formulärfält på rätt sätt. Det visas när användaren klickar på hjälpikonen (i) som finns bredvid komponenten. Hjälptexten ger mer detaljerad information än etiketten eller platshållartexten för ett formulärfält och är utformad för att hjälpa användaren förstå fältets krav eller begränsningar. Den kan också ge förslag eller exempel som gör det enklare och exaktare att fylla i formuläret.

### Tillgänglighet {#accessibility}

![Fliken Tillgänglighet](/help/adaptive-forms/assets/button_accessibilitytab.png)


* **Text för skärmläsare** - Text för skärmläsare avser text som är avsedd att läsas av hjälpmedelstekniker, t.ex. skärmläsare, som används av personer med nedsatt syn. Den här texten innehåller en ljudbeskrivning av formulärfältets syfte och kan innehålla information om fältets titel, beskrivning, namn och relevanta meddelanden (anpassad text). Skärmläsartexten ser till att formuläret är tillgängligt för alla användare, även användare med nedsatt syn, och ger dem en fullständig förståelse för formulärfältet och dess krav.

## Designdialogruta {#design-dialog}

Designdialogrutan används för att definiera och hantera CSS-format för knappkomponenten.

### Fliken Format {#styles-tab}

Den adaptiva Forms Button Core-komponenten stöder AEM [Formatsystem](/help/get-started/authoring.md#component-styling).

![designdialogruta](/help/adaptive-forms/assets/button_designdialog.png)

* **CSS-standardklasser**: Du kan ange en standard-CSS-klass för den adaptiva Forms Button Core-komponenten.

* **Tillåtna format**: Du kan definiera format genom att ange ett namn och den CSS-klass som representerar formatet. Du kan till exempel skapa ett format med namnet&quot;bold text&quot; och ge CSS-klassen&quot;font-weight: bold&quot;. Du kan använda eller tillämpa dessa format på ett adaptivt formulär i en anpassad Forms-redigerare. Om du vill använda ett format väljer du den komponent du vill använda formatet på i Adaptiv Forms-redigerare, navigerar till egenskapsdialogrutan och väljer önskat format i dialogrutan **Stilar** listruta. Om du behöver uppdatera eller ändra formaten går du tillbaka till designdialogrutan, uppdaterar formaten på formatfliken och sparar ändringarna.

<!--

## Related article {#related-article}

* [Create a standalone Adaptive Form](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)

-->

>[!MORELIKETHIS]
>
>* [Dragspel](/help/adaptive-forms/components/accordion.md)
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
>* [Textindata](/help/adaptive-forms/components/text-input.md)
>* [Text](/help/adaptive-forms/components/text.md)
>* [Titel](/help/adaptive-forms/components/title.md)
>* [guide](/help/adaptive-forms/components/wizard.md)


## Se även {#see-also}

{{see-also}}

