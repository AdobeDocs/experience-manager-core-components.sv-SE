---
title: Adaptiv Forms Core-komponent - talindata
description: Använda eller anpassa den adaptiva kärnkomponenten Forms Number.
role: Architect, Developer, Admin, User
source-git-commit: 945e1793ae4e959f83960db46d2de4257916fe32
workflow-type: tm+mt
source-wordcount: '1780'
ht-degree: 0%

---


# Nummerindata {#number-input-adaptive-forms-core-component}

En Number Input-komponent i ett adaptivt formulär är en typ av formulärfält där användarna kan ange numeriska värden. Komponenten representeras vanligtvis av ett textfält med upp- och nedpilar som ökar och minskar talet.

Den kan också användas med attribut som min, max, step, value med mera. Dessa attribut kan användas för att ange de lägsta och högsta värden som tillåts i fältet, stegintervallet för att öka eller minska talet och fältets standardvärde.

Den här komponenten kan användas för att samla in numeriska data som ålder, kvantitet med mera. och kan även användas för att utföra matematiska operationer som addition och subtraktion. Den här komponenten kan också användas för att validera numeriska data som anges av användaren.

För hjälpmedel är det viktigt att ange &quot;label&quot; som beskriver syftet med talinmatningsfältet och vilken typ av inmatning som förväntas.

**Exempel**

![](/help/adaptive-forms/assets/numeric-stepper.png)

## Användning {#reasons-to-use-number-input-numeric-stepper}

Det finns flera skäl till att det är bra att ta med en numerisk indatakomponent i en adaptiv form, bland annat:

* **Matematiska operationer**: Numeriska fält kan användas för att utföra matematiska operationer som addition, subtraktion, multiplikation och division.

* **Dataområde**: Numeriska fält kan användas för att ange ett intervall med giltiga värden genom att använda attributen min, max och step.

* **Dynamiskt innehåll**: En numerisk komponent kan användas för att visa dynamiska data baserat på formulärfälten.


## Version och kompatibilitet {#version-and-compatibility}

Core-komponenten för indata för adaptiva Forms Number släpptes i februari 2023 som en del av Core Components 2.0.4. Här är en tabell med alla versioner som stöds, AEM kompatibilitet och länkar till motsvarande dokumentation:

|  |  |
|---|---|
| Komponentversion | AEM as a Cloud Service |
| — | --- |
| v1 | Kompatibel med<br>[version 2.0.4](/help/versions.md) och senare | Kompatibel | Kompatibel |

Information om versioner och versioner av kärnkomponenter finns i [Huvudkomponentversioner](/help/versions.md) -dokument.


<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Teknisk information {#technical-details}

Hämta den senaste informationen om den adaptiva kärnkomponenten Forms Number i den tekniska dokumentationen om [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/numberinput/v1/numberinput). Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Med dialogrutan Konfigurera kan du enkelt anpassa din talinmatning för besökare. Du kan också enkelt definiera talinmatningsalternativ för en smidig användarupplevelse.

### Fliken Grundläggande {#basic-tab}

![Fliken Grundläggande](/help/adaptive-forms/assets/numberinput_basictab.png)

* **Namn** - Du kan enkelt identifiera en formulärkomponent med dess unika namn både i formuläret och i regelredigeraren, men namnet får inte innehålla blanksteg eller specialtecken.

* **Titel** - Med dess titel kan du enkelt identifiera en komponent i ett formulär. Som standard visas titeln ovanpå komponenten. Om du inte lägger till en titel visas komponentens namn i stället för titeltexten.

* **Dölj titel** - Välj alternativet om du vill dölja komponentens titel.

* **Platshållartext** - Platshållartext i en formulärkomponent refererar till en kort etikett eller en fråga som visas i ett inmatningsfält som ett tips till användaren om vilken typ av information som förväntas anges i det fältet. Platshållartext försvinner när användaren börjar skriva i fältet och visas igen om fältet lämnas tomt. Den ger användaren en visuell referens, men fungerar inte som en permanent etikett eller ett permanent värde för fältet.
* **Bindningsreferens** - En bind referens är en referens till ett dataelement som lagras i en extern datakälla och används i ett formulär. Med den binda referensen kan du binda data dynamiskt till formulärfält så att formuläret kan visa de senaste data från datakällan. En bindningsreferens kan till exempel användas för att visa en kunds namn och adress i ett formulär baserat på kundens ID som anges i formuläret. Bindningsreferensen kan också användas för att uppdatera datakällan med data som anges i formuläret. På så sätt kan AEM Forms skapa formulär som interagerar med externa datakällor, vilket ger en smidig användarupplevelse för att samla in och hantera data.
* **Dölj komponent** - Välj alternativet att dölja komponenten från formuläret. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren. Detta är användbart när du behöver lagra information som inte behöver visas eller ändras direkt av användaren.
* **Inaktivera komponent** - Välj alternativet att inaktivera komponenten. Den inaktiverade komponenten är inte aktiv eller redigerbar av slutanvändaren. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.
* **Skrivskyddad** - Välj alternativet för att göra komponenten icke-redigerbar Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.
* **Nummertyp** - Med det här alternativet kan du välja vilken typ av numeriska värden &#x200B; &#x200B; som tillåts i formulärfältet. Du kan välja antingen Decimal- eller Integer-typer i listrutan.
* **Standardvärde** - Med det här alternativet kan du lägga till ett standardvärde i ett formulärfält. If **Inaktiverad komponent** eller **Skrivskyddad komponent** är markerat visas standardvärdet på skärmen. Om användaren inte anger något värde i formulärfältet skickas det här värdet när formuläret skickas

### Fliken Validering {#validation-tab}

![Fliken Validering](/help/adaptive-forms/assets/numberinput_validationtab.png)

* **Obligatoriskt** - Välj det här alternativet om du vill visa komponenten i ett adaptivt formulär. Du kan inte välja **Dölj komponent** eller **Inaktivera komponent**  i **Grundläggande** när det här alternativet är markerat.

* **Felmeddelande** - Med det här alternativet kan du ange ett meddelande som visas om **Obligatoriskt** är markerad och fältet lämnas tomt.

* **Skriptverifieringsmeddelande** - Med det här alternativet kan du ange ett meddelande som ska visas om skriptvalideringen misslyckas.

* **Lägsta tal/Minsta tal** - Använd det här alternativet om du vill välja det minsta tillåtna talet som ska anges i formulärfältet. Om värdet är mindre än talet som anges i **Lägsta tal/Minsta tal** om du anger ett alternativ i formulärfältet visas felmeddelandet.

* **Minsta felmeddelande** - Med det här alternativet kan du ange ett felmeddelande som visas när användaren anger ett värde som är mindre än det som anges i **Minsta antal/minsta antal** alternativ.

* **Uteslut minimivärde** - Markera den här kryssrutan om du inte vill ha det minimivärde som anges i **Lägsta tal/Minsta tal** som ska inkluderas i det &#x200B; värdeintervallet som ska anges i formulärfältet.

* **Högsta tal/största tal** - Använd det här alternativet om du vill välja det högsta tillåtna talet som ska anges i formulärfältet. Om talet är större än talet som anges i **Högsta tal/största tal** om du anger ett alternativ i formulärfältet visas felmeddelandet.

* **Högsta felmeddelande** - Med det här alternativet kan du ange ett felmeddelande som visas när användaren anger ett värde som är större än det som anges i **Högsta tal/största tal** alternativ.

* **Uteslut högsta värde** - Markera den här kryssrutan om du inte vill ha det maximala värde som anges i **Högsta tal/största tal** som ska inkluderas i det värdeintervall som ska anges i formulärfältet.

### Fliken Hjälpinnehåll {#help-content}

![Fliken Hjälpinnehåll](/help/adaptive-forms/assets/numberinput_helptab.png)

* **Kort beskrivning** - En kort beskrivning är en kort textförklaring som ger ytterligare information eller förtydliganden om syftet med ett visst formulärfält. Det hjälper användaren att förstå vilken typ av data som ska anges i fältet och kan ge riktlinjer eller exempel som hjälper till att säkerställa att den angivna informationen är giltig och uppfyller de önskade kriterierna. Som standard är korta beskrivningar dolda. Aktivera **Visa alltid kort beskrivning** för att visa den under komponenten.

* **Visa alltid kort beskrivning** - Aktivera alternativet att visa den korta beskrivningen under komponenten.

* **Hjälptext** - Hjälptexten hänvisar till ytterligare information eller vägledning som användaren får för att hjälpa sig fylla i ett formulärfält på rätt sätt. Det visas när användaren klickar på hjälpikonen (i) som finns bredvid komponenten. Hjälptexten ger mer detaljerad information än etiketten eller platshållartexten för ett formulärfält och är utformad för att hjälpa användaren förstå fältets krav eller begränsningar. Den kan också ge förslag eller exempel som gör det enklare och exaktare att fylla i formuläret.

### Fliken Tillgänglighet {#accessibility}

![Fliken Tillgänglighet](/help/adaptive-forms/assets/numberinput_accessibility.png)

* **Text för skärmläsare** - Text för skärmläsare avser text som är avsedd att läsas av hjälpmedelstekniker, t.ex. skärmläsare, som används av personer med nedsatt syn. Den här texten innehåller en ljudbeskrivning av formulärfältets syfte och kan innehålla information om fältets titel, beskrivning, namn och relevanta meddelanden (anpassad text). Skärmläsartexten ser till att formuläret är tillgängligt för alla användare, även användare med nedsatt syn, och ger dem en fullständig förståelse för formulärfältet och dess krav.

### Fliken Format {#formats-tab}

![Fliken Tillgänglighet](/help/adaptive-forms/assets/numberinput_formattab.png)


* **Visningsformat** - Med det här alternativet kan du välja alternativ från olika numeriska heltalsformat för visning. När användaren väljer något alternativ på menyn **Typ** nedrullningsbar meny, **Format** visas på panelen. Du kan välja ett specifikt format där tal visas för användaren.

* **Antal siffror före decimaltecknet (1234,000)** - Använd det här alternativet om du vill ange antalet siffror som ska visas före decimalkommat.

* **Antal siffror efter decimaltecknet (1234,000)** - Använd det här alternativet om du vill ange antalet siffror som ska visas efter decimalkommat.

## Designdialogruta {#design-dialog}

Designdialogrutan används för att definiera och hantera CSS-format för indatakomponenten Number.


### Fliken Format {#styles-tab}

Designdialogrutan används för att definiera och hantera CSS-format för en komponent. Den adaptiva kärnkomponenten Forms Number har stöd för AEM [Formatsystem](/help/get-started/authoring.md#component-styling).

**CSS-standardklasser**: Du kan ange en standard-CSS-klass för indatakomponenten Adaptive Forms Number.

**Tillåtna format**: Du kan definiera format genom att ange ett namn och den CSS-klass som representerar formatet. Du kan till exempel skapa ett format med namnet&quot;bold text&quot; och ge CSS-klassen&quot;font-weight: fet&quot;. Du kan använda eller tillämpa dessa format på ett adaptivt formulär i den adaptiva Forms-redigeraren. Om du vill använda ett format väljer du den komponent du vill använda formatet på i Adaptiv Forms-redigerare, navigerar till egenskapsdialogrutan och väljer önskat format i dialogrutan **Stilar** nedrullningsbar lista. Om du behöver uppdatera eller ändra formaten går du tillbaka till designdialogrutan, uppdaterar formaten på formatfliken och sparar ändringarna.

### Fliken Format {#format-tab}

På fliken Format kan du ange standardtalformat och anpassade talformat.