---
title: Adaptiv Forms Core-komponent - skicka-knapp
description: Använda eller anpassa den adaptiva Forms Submit-knappens kärnkomponent.
role: Architect, Developer, Admin, User
exl-id: e4b8e475-79b9-4c4d-9f11-a125a424d32b
source-git-commit: e0ed415bd7f45fdca6fbbb8ba409604d9e82a647
workflow-type: tm+mt
source-wordcount: '1380'
ht-degree: 0%

---

# Skicka-knapp {#submit-button}

En Skicka-knapp i ett adaptivt formulär är en knapp som gör att användare kan skicka formulärdata till en server för bearbetning. När användaren klickar på knappen Skicka skickas formulärdata till servern, där de kan lagras, bearbetas eller användas i olika syften, som att skicka ett e-postmeddelande eller uppdatera en databas.

Knappen Skicka är vanligtvis det sista steget i ifyllningsprocessen och används för att initiera processen att skicka formulärdata till servern.

**Exempel**

![Exempel på knapp](/help/adaptive-forms/assets/example-button.png)

## Användning {#reasons-to-use-submit-button}

Skälen till att du använder en skicka-knapp i en adaptiv form är:

- **Inlämning av data**: Skicka-knappen är den primära mekanismen för att skicka formulärdata till en server för bearbetning.

- **Förbättrad användarupplevelse**: En väldesignad Skicka-knapp kan förbättra användarupplevelsen genom att ge tydlig feedback på formulärinlämningsprocessen och ange när formuläret har skickats in.

- **Dataverifiering**: Knappen Skicka kan användas för att aktivera datavalideringskontroller, vilket säkerställer att formulärdata är fullständiga och korrekta innan de skickas till servern.


## Version och kompatibilitet {#version-and-compatibility}

Den adaptiva Forms Accordion Core-komponenten släpptes i februari 2023 som en del av Core Components 2.0.4 för Cloud Service och Core Components 1.1.12 för AEM 6.5.16.0 Forms eller senare. Här är en tabell med alla versioner som stöds, AEM kompatibilitet och länkar till motsvarande dokumentation:

| Komponentversion | AEM as a Cloud Service | AEM 6.5.16.0 Forms eller senare |
|---|---|---|
| v1 | Kompatibel med<br>[version 2.0.4](/help/adaptive-forms/version.md) och senare | Kompatibel med<br>[version 1.1.12](/help/adaptive-forms/version.md) och senare men mindre än 2.0.0. |

Mer information om versioner och versioner av kärnkomponenter finns i [Huvudkomponentversioner](/help/adaptive-forms/version.md) -dokument.

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Teknisk information {#technical-details}

Hämta den senaste informationen om den adaptiva Forms-knappen Core Component (Skicka) i den tekniska dokumentationen om [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/button/v1/button). Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Med dialogrutan Konfigurera kan du enkelt anpassa din sändningsknapp för besökare. Du kan också enkelt definiera alternativ för Skicka-knappen för en smidig användarupplevelse.

### Fliken Grundläggande {#basic-tab}

![Fliken Grundläggande](/help/adaptive-forms/assets/button_basictab.png)

- **Namn** - Du kan enkelt identifiera en formulärkomponent med dess unika namn både i formuläret och i regelredigeraren, men namnet får inte innehålla blanksteg eller specialtecken.

- **Titel** - Med dess titel kan du enkelt identifiera en komponent i ett formulär. Som standard visas titeln ovanpå komponenten. Om du inte lägger till en titel visas komponentens namn i stället för rubriktexten.

- **Bindningsreferens** - En bind referens är en referens till ett dataelement som lagras i en extern datakälla och används i ett formulär. Med den binda referensen kan du binda data dynamiskt till formulärfält så att formuläret kan visa de senaste data från datakällan. En bindningsreferens kan till exempel användas för att visa en kunds namn och adress i ett formulär baserat på kundens ID som anges i formuläret. Bindningsreferensen kan också användas för att uppdatera datakällan med data som anges i formuläret. På så sätt kan AEM Forms skapa formulär som interagerar med externa datakällor, vilket ger en smidig användarupplevelse för att samla in och hantera data.
- **Markera som obundet formulärelement**: Välj alternativet att konfigurera ett formulärfält som inte är länkat till något schema. Med det här alternativet kan du spara data utan att uppdatera datakällan. Det gör det också möjligt att hantera data på ett anpassat sätt, skilt från standarddatabasintegrering.

- **Dölj komponent** - Välj alternativet att dölja komponenten från formuläret. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren. Detta är användbart när du behöver lagra information som inte behöver visas eller ändras direkt av användaren.
- **Inaktivera komponent** - Välj alternativet att inaktivera komponenten. Den inaktiverade komponenten är inte aktiv eller redigerbar av slutanvändaren. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.
- **Skrivskyddad** - Välj alternativet att göra komponenten icke-redigerbar. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.

### Fliken Hjälpinnehåll {#help-content}

![Fliken Hjälpinnehåll](/help/adaptive-forms/assets/button_helptab.png)

- **Kort beskrivning** - En kort beskrivning är en kort textförklaring som ger ytterligare information eller förtydliganden om syftet med ett visst formulärfält. Det hjälper användaren att förstå vilken typ av data som ska anges i fältet och kan ge riktlinjer eller exempel som hjälper till att säkerställa att den angivna informationen är giltig och uppfyller de önskade kriterierna. Som standard är korta beskrivningar dolda. Aktivera **Visa alltid kort beskrivning** för att visa den under komponenten.

- **Visa alltid kort beskrivning** - Aktivera alternativet att visa den korta beskrivningen under komponenten.

- **Hjälptext** - Hjälptexten hänvisar till ytterligare information eller vägledning som användaren får för att hjälpa sig fylla i ett formulärfält på rätt sätt. Det visas när användaren klickar på hjälpikonen (i) som finns bredvid komponenten. Hjälptexten ger mer detaljerad information än etiketten eller platshållartexten för ett formulärfält och är utformad för att hjälpa användaren förstå fältets krav eller begränsningar. Den kan också ge förslag eller exempel som gör det enklare och exaktare att fylla i formuläret.

### Tillgänglighet {#accessibility}

![Fliken Tillgänglighet](/help/adaptive-forms/assets/button_accessibilitytab.png)

**Text för skärmläsare** - Text för skärmläsare avser text som är avsedd att läsas av hjälpmedelstekniker, t.ex. skärmläsare, som används av personer med nedsatt syn. Den här texten innehåller en ljudbeskrivning av formulärfältets syfte och kan innehålla information om fältets titel, beskrivning, namn och relevanta meddelanden (anpassad text). Skärmläsartexten ser till att formuläret är tillgängligt för alla användare, även användare med nedsatt syn, och ger dem en fullständig förståelse för formulärfältet och dess krav.

## Designdialogruta {#design-dialog}

Designdialogrutan används för att definiera och hantera CSS-format för komponenten Skicka.

### Fliken Format {#styles-tab}

Fliken används för att definiera och hantera CSS-format för en komponent. Kärnkomponenten för den adaptiva Forms-knappen stöder AEM [Formatsystem](/help/get-started/authoring.md#component-styling).

![Designdialogruta](/help/adaptive-forms/assets/checkbox-style.png)

- **CSS-standardklasser**: Du kan ange en standard-CSS-klass för den adaptiva Forms Checkbox Group Core Component.

- **Tillåtna format**: Du kan definiera format genom att ange ett namn och den CSS-klass som representerar formatet. Du kan till exempel skapa ett format med namnet&quot;bold text&quot; och ge CSS-klassen&quot;font-weight: bold&quot;. Du kan använda eller tillämpa dessa format på ett adaptivt formulär i en anpassad Forms-redigerare. Om du vill använda ett format väljer du den komponent du vill använda formatet på i Adaptiv Forms-redigerare, navigerar till egenskapsdialogrutan och väljer önskat format i dialogrutan **Stilar** listruta. Om du behöver uppdatera eller ändra formaten går du tillbaka till designdialogrutan, uppdaterar formaten på formatfliken och sparar ändringarna.

### Anpassade egenskaper

![Dialogrutan Anpassade egenskaper](/help/adaptive-forms/assets/checkbox-customproperties.png)

Med anpassade egenskaper kan du koppla anpassade attribut (nyckelvärdepar) till en anpassad formulärets kärnkomponent med hjälp av formulärmallen. De anpassade egenskaperna återspeglas i egenskapsavsnittet i den headless-renderingen av komponenten. Det gör att du kan skapa dynamiskt formulärbeteende som anpassas baserat på anpassade attributvärden. Utvecklare kan till exempel utforma olika renderingar av en Headless Forms-komponent för mobiler, datorer eller webbplattformar, vilket avsevärt förbättrar användarupplevelsen på en mängd olika enheter.

- **Gruppnamn**: Du kan ange ett namn som identifierar den anpassade egenskapsgruppen. Du kan lägga till, ta bort eller ordna om flera anpassade egenskapsgrupper. När du har lagt till den anpassade egenskapsgruppen kan du se följande alternativ:

   - **Nyckelvärdepar**: Du kan lägga till flera anpassade egenskapsnamn och anpassade egenskapsvärden genom att klicka på **Lägg till** för varje anpassad egenskapsgrupp.

   - **Ta bort**: Tryck eller klicka för att ta bort det anpassade egenskapsnamnet och det anpassade egenskapsvärdet.

   - **Ordna om**: Tryck eller klicka och dra för att ändra ordningen på det anpassade egenskapsnamnet och det anpassade egenskapsvärdet.

## Relaterade artiklar {#related-articles}

{{more-like-this}}


## Se även {#see-also}

{{see-also}}