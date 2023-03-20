---
title: Adaptiv Forms Core-komponent - datumväljare
description: Använda eller anpassa Core-komponenten för den adaptiva Forms Date-väljaren.
role: Architect, Developer, Admin, User
exl-id: aa9402de-ca57-4c19-8d36-2dd0a78d6806
source-git-commit: d2a6108f17f6e0c6b91bec84893d64a8bd48effd
workflow-type: tm+mt
source-wordcount: '1666'
ht-degree: 0%

---

# Datumväljaren {#date-picker-adaptive-forms-core-component}

En datumväljarkomponent i ett adaptivt formulär är ett element i användargränssnittet som gör att användare kan välja ett datum i en kalender eller ange ett datum manuellt i ett visst format. Datumväljarkomponenten kan konfigureras så att den har olika formaterings-, validerings- och standardvärden.

**Exempel**

![](/help/adaptive-forms/assets/date-picker.png)

## Användning {#reasons-to-use-drop-date-picker}

Det finns många skäl till att det är bra att ta med en datumväljare i en anpassad form, bland annat:

* **Bekvämlighet**: Med en datumväljarkomponent kan användare enkelt välja ett datum i en kalender utan att behöva ange datumet manuellt i ett textfält. Detta kan spara tid och minska antalet fel.

* **Användarupplevelse**: Datumväljarkomponenten kan användas för att göra formuläret mer användarvänligt genom att tillhandahålla ett tydligt och intuitivt sätt för användarna att välja datum.

* **Dataanalys**: Datumväljarkomponenten kan användas för att samla in data från olika källor och analysera den, eller använda den som indata för vidare bearbetning.

* **Händelsehantering**: Datumväljarkomponenten kan användas på händelsehanteringswebbplatser för att välja händelsemedatum.

* **Bokning och bokning**: Datumväljarkomponenten kan användas på boknings- och reservationswebbplatser för att välja datum för in- och utcheckning.

* **Datumformat**: Datumväljarkomponenten kan användas för att korrigera det format i vilket datumet visas och anges. Se till att datumformatet är enhetligt i hela formuläret för att säkerställa en konsekvent användarupplevelse.

## Version och kompatibilitet {#version-and-compatibility}

Den adaptiva Forms Accordion Core-komponenten släpptes i februari 2023 som en del av Core Components 2.0.4 för Cloud Service och Core Components 1.1.12 för AEM 6.5.16.0 Forms eller senare. Här är en tabell med alla versioner som stöds, AEM kompatibilitet och länkar till motsvarande dokumentation:

| Komponentversion | AEM as a Cloud Service | AEM 6.5.16.0 Forms eller senare |
|---|---|---|
| v1 | Kompatibel med<br>[version 2.0.4](/help/adaptive-forms/version.md) och senare | Kompatibel med<br>[version 1.1.12](/help/adaptive-forms/version.md) och senare men mindre än 2.0.0. |

Information om versioner och versioner av kärnkomponenter finns i [Huvudkomponentversioner](/help/adaptive-forms/version.md) -dokument.

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->


## Teknisk information {#technical-details}

Hämta den senaste informationen om Core Component-komponenten för den adaptiva Forms Date-väljaren i den tekniska dokumentationen om [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/datepicker/v1/datepicker). Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Med dialogrutan Konfigurera kan du enkelt anpassa din datumväljarupplevelse för besökare. Du kan också enkelt definiera datumväljaralternativ för en smidig användarupplevelse.

### Fliken Grundläggande {#basic-tab}

![Fliken Grundläggande](/help/adaptive-forms/assets/datepicker_basictab.png)

* **Namn** - Namnet identifierar komponenten i regelredigeraren unikt. Specialtecken och mellanslag är inte tillåtna i namnsträngarna.

* **Titel** - Titel är en sträng som visas högst upp i en komponent i ett adaptivt format. En unik titel identifierar komponenten i trädstrukturen i ett adaptivt formulär. Om du inte lägger till en titel visas komponentens namn i stället för titeltexten.

* **Dölj titel** - Välj det här alternativet om du vill dölja rubriken för komponenttypen i ett adaptivt formulär.

* **Platshållartext** - Platshållartext i en formulärkomponent refererar till en kort etikett eller en fråga som visas i ett inmatningsfält som ett tips till användaren om vilken typ av information som förväntas anges i det fältet. Platshållartext försvinner när användaren börjar skriva i fältet och visas igen om fältet lämnas tomt. Den ger användaren en visuell referens, men fungerar inte som en permanent etikett eller ett permanent värde för fältet.

* **Dölj komponent** - Välj alternativet att dölja komponenten från formuläret. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren. Detta är användbart när du behöver lagra information som inte behöver visas eller ändras direkt av användaren.
* **Inaktivera komponent** - Välj alternativet att inaktivera komponenten. Den inaktiverade komponenten är inte aktiv eller redigerbar av slutanvändaren. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.
* **Skrivskyddad** - Välj alternativet att göra komponenten icke-redigerbar. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.
* **Standarddatum** - Med det här alternativet kan du lägga till ett datum i formulärfältet. Det angivna datumet visas som standard i stället för komponenten. Om inget datum anges av användaren skickas det här värdet när formuläret skickas. Om **Inaktiverad komponent** eller **Skrivskyddad komponent** är markerat visas standarddatumet på skärmen och skickas när formuläret skickas.


### Fliken Validering {#validation-tab}

![Fliken Validering](/help/adaptive-forms/assets/datepicker_validation.png)

* **Obligatoriskt** - Välj det här alternativet om du vill visa komponenten i ett adaptivt formulär. Du kan inte välja **Dölj komponent** eller **Inaktivera komponent** i **Grundläggande** när det här alternativet är markerat.

* **Felmeddelande** - Med det här alternativet kan du ange ett meddelande som visas om **Obligatoriskt** kryssrutan är markerad och formulärfältet är tomt.

* **Skriptverifieringsmeddelande** - Med det här alternativet kan du ange ett meddelande som ska visas om skriptvalideringen misslyckas.

* **Minsta datum** - Med det här alternativet kan du ange det minsta obligatoriska datumet. Om du anger ett datum som är tidigare än det som anges i Minimidatum visas ett felmeddelande på skärmen. The **Minsta felmeddelande** kan du lägga till ett eget felmeddelande.

* **Minsta felmeddelande** - **Minsta felmeddelande** kan du lägga till ett eget felmeddelande som ska visas om du anger ett datum som är tidigare än det som anges i **Minsta datum** alternativ.

* **Högsta datum** - Med det här alternativet kan du ange maximalt obligatoriskt datum. Om du anger ett datum som är senare än det som anges i Maximalt datum visas ett felmeddelande på skärmen. The **Högsta felmeddelande** kan du lägga till ett eget felmeddelande.

* **Högsta felmeddelande** - **Högsta felmeddelande** kan du lägga till ett eget felmeddelande som ska visas om du anger ett datum som är senare än det som anges i **Högsta datum** alternativ.


### Fliken Hjälpinnehåll {#help-content-tab}

![Fliken Hjälpinnehåll](/help/adaptive-forms/assets/datepicker_helptab.png)

* **Kort beskrivning** - En kort beskrivning är en kort textförklaring som ger ytterligare information eller förtydliganden om syftet med ett visst formulärfält. Det hjälper användaren att förstå vilken typ av data som ska anges i fältet och kan ge riktlinjer eller exempel som hjälper till att säkerställa att den angivna informationen är giltig och uppfyller de önskade kriterierna. Som standard är korta beskrivningar dolda. Aktivera **Visa alltid kort beskrivning** för att visa den under komponenten.

* **Visa alltid kort beskrivning**- Aktivera alternativet att visa den korta beskrivningen under komponenten.

* **Hjälptext** - Hjälptexten hänvisar till ytterligare information eller vägledning som användaren får för att hjälpa sig fylla i ett formulärfält på rätt sätt. Det visas när användaren klickar på hjälpikonen (i) som finns bredvid komponenten. Hjälptexten ger mer detaljerad information än etiketten eller platshållartexten för ett formulärfält och är utformad för att hjälpa användaren förstå fältets krav eller begränsningar. Den kan också ge förslag eller exempel som gör det enklare och exaktare att fylla i formuläret.


### Fliken Tillgänglighet {#accessibility-tab}

![Fliken Tillgänglighet](/help/adaptive-forms/assets/datepicker_accessibilitytab.png)

**Text för skärmläsare** - Text för skärmläsare avser text som är avsedd att läsas av hjälpmedelstekniker, t.ex. skärmläsare, som används av personer med nedsatt syn. Den här texten innehåller en ljudbeskrivning av formulärfältets syfte och kan innehålla information om fältets titel, beskrivning, namn och relevanta meddelanden (anpassad text). Skärmläsartexten ser till att formuläret är tillgängligt för alla användare, även användare med nedsatt syn, och ger dem en fullständig förståelse för formulärfältet och dess krav.

### Fliken Format {#format-tab}

![Fliken Format](/help/adaptive-forms/assets/datepicker_formattab.png)

* **Visningsformat** - Det representerar det datumformat som visas för användaren. The **Typ** gör att användaren kan välja datumformat. Du kan också anpassa datumformatet med **Egen** i **Typ** nedrullningsbar meny.

* **Redigera format** - Det representerar ett datumformat där användaren kan redigera datumet. The **Typ** gör att användaren kan välja datumformat. Du kan också anpassa datumformatet med **Egen** i **Typ** nedrullningsbar meny.

* **Visningsformat** - Det representerar det datumformat som visas för användaren. Med alternativet Typ kan användaren välja datumformat. Du kan också anpassa datumformatet med **Egen** i **Typ** nedrullningsbar meny.

* **Redigera format** - Det representerar ett datumformat där användaren redigerar datumet. Med alternativet Typ kan användaren välja datumformat. Du kan också anpassa datumformatet med **Egen** i **Typ** nedrullningsbar meny.

## Designdialogruta {#design-dialog}

Designdialogrutan används för att definiera och hantera CSS-format för komponenten Date-Picker.

### Fliken Format {#styles-tab}

Fliken används för att definiera och hantera CSS-format för en komponent. Core-komponenten för datumväljaren i den adaptiva Forms stöder AEM [Formatsystem](/help/get-started/authoring.md#component-styling).

![Fliken Format](/help/adaptive-forms/assets/datepicker_styletab.png)

* **CSS-standardklasser**: Du kan ange en standard-CSS-klass för den adaptiva Forms Date-picker Core Component.

* **Tillåtna format**: Du kan definiera format genom att ange ett namn och den CSS-klass som representerar formatet. Du kan till exempel skapa ett format med namnet&quot;bold text&quot; och ge CSS-klassen&quot;font-weight: fet&quot;. Du kan använda eller tillämpa dessa format på ett adaptivt formulär i den adaptiva Forms-redigeraren. Om du vill använda ett format väljer du den komponent du vill använda formatet på i Adaptiv Forms-redigerare, navigerar till egenskapsdialogrutan och väljer önskat format i dialogrutan **Stilar** nedrullningsbar lista. Om du behöver uppdatera eller ändra formaten går du tillbaka till designdialogrutan, uppdaterar formaten på formatfliken och sparar ändringarna.

### Fliken Format {#formats-tab}

På fliken Format kan du ange standardformat och anpassade datumformat.

![Formatera](/help/adaptive-forms/assets/datepicker_formatpolicy.png)

