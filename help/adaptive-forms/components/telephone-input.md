---
title: Adaptiv Forms Core-komponent - telefoninmatning
description: Använda eller anpassa den adaptiva kärnkomponenten för telefoninmatning från Forms.
role: Architect, Developer, Admin, User
source-git-commit: 945e1793ae4e959f83960db46d2de4257916fe32
workflow-type: tm+mt
source-wordcount: '1698'
ht-degree: 0%

---


# Telefonindata {#telephone-input-adaptive-forms-core-component}

Med den adaptiva formulärens telefoningång Core Component kan användare ange ett telefonnummer. I fältet för telefonindata visas tangentbord i mobila enheter som är relevanta för telefonnummer. Den kan anpassas med ytterligare attribut som &quot;pattern&quot; och &quot;placeholder&quot; för att ange telefonnumrets format och beskrivning.

Telefoninmatningsfältet används ofta i kontaktformulär, registreringsformulär och andra formulär där ett telefonnummer krävs som kontaktmetod. Telefoninmatningsfältet kan också användas för att säkerställa att användaren anger ett giltigt telefonnummer, eftersom webbläsaren kan tillämpa vissa begränsningar, t.ex. telefonnumrets längd och format, baserat på mönsterattributet.

## Användning {#reasons-to-use-telephone-input}

De vanligaste skälen till att använda ett telefoninmatningsfält i en adaptiv form är:

* **Kontaktinformation**: Ett telefoninmatningsfält används vanligtvis för att samla in en användares telefonnummer som kontaktmetod.

* **Förbättrad datakvalitet**: Genom att använda ett telefoninmatningsfält kan formuläret begränsa telefonnumrets format, vilket kan säkerställa att de data som matas in är korrekta och fullständiga.

* **Bättre användarupplevelser**: Ett telefoninmatningsfält är ett tydligt och intuitivt sätt för användare att ange sitt telefonnummer och kan förbättra användarupplevelsen genom att användarna snabbt och enkelt kan ange sin kontaktinformation.

## Version och kompatibilitet {#version-and-compatibility}

Kärnkomponenten för adaptiv Forms telefoninmatning släpptes i februari 2023 som en del av kärnkomponenterna 2.0.4. Här är en tabell med alla versioner som stöds, AEM kompatibilitet och länkar till motsvarande dokumentation:

|  |  |
|---|---|
| Komponentversion | AEM as a Cloud Service |
| — | --- |
| v1 | Kompatibel med<br>[version 2.0.4](/help/versions.md) och senare | Kompatibel | Kompatibel |

Information om versioner och versioner av kärnkomponenter finns i [Huvudkomponentversioner](/help/versions.md) -dokument.

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Teknisk information {#technical-details}

Få den senaste informationen om den adaptiva Forms telefonindatakärnkomponenten i den tekniska dokumentationen om [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/telephoneinput/v1/telephoneinput). Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Du kan enkelt anpassa telefoninmatningen för besökare med dialogrutan Konfigurera. Du kan också enkelt definiera telefoninmatningsalternativ för en smidig användarupplevelse.

![Fliken Grundläggande](/help/adaptive-forms/assets/telephoneinput_basictab.png)

* **Namn** - Du kan enkelt identifiera en formulärkomponent med dess unika namn både i formuläret och i regelredigeraren, men namnet får inte innehålla blanksteg eller specialtecken.

* **Titel** - Med dess titel kan du enkelt identifiera en komponent i ett formulär. Som standard visas titeln ovanpå komponenten. Om du inte lägger till en titel visas komponentens namn i stället för titeltexten.

* **Dölj titel** - Välj alternativet om du vill dölja komponentens titel.

* **Platshållartext** - Platshållartext i en formulärkomponent refererar till en kort etikett eller en fråga som visas i ett inmatningsfält som ett tips till användaren om vilken typ av information som förväntas anges i det fältet. Platshållartext försvinner när användaren börjar skriva i fältet och visas igen om fältet lämnas tomt. Den ger användaren en visuell referens, men fungerar inte som en permanent etikett eller ett permanent värde för fältet.

* **Bindningsreferens** - En bind referens är en referens till ett dataelement som lagras i en extern datakälla och används i ett formulär. Med den binda referensen kan du binda data dynamiskt till formulärfält så att formuläret kan visa de senaste data från datakällan. En bindningsreferens kan till exempel användas för att visa en kunds namn och adress i ett formulär baserat på kundens ID som anges i formuläret. Bindningsreferensen kan också användas för att uppdatera datakällan med data som anges i formuläret. På så sätt kan AEM Forms skapa formulär som interagerar med externa datakällor, vilket ger en smidig användarupplevelse för att samla in och hantera data.

* **Dölj komponent** - Välj alternativet att dölja komponenten från formuläret. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren. Detta är användbart när du behöver lagra information som inte behöver visas eller ändras direkt av användaren.

* **Inaktivera komponent** - Välj alternativet att inaktivera komponenten. Den inaktiverade komponenten är inte aktiv eller redigerbar av slutanvändaren. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.

* **Skrivskyddad** - Välj alternativet att göra komponenten icke-redigerbar. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.

* **Standardvärde** - Med det här alternativet kan du lägga till ett standardvärde i ett formulärfält. If **Inaktiverad komponent** eller **Skrivskyddad komponent** är markerat visas standardvärdet på skärmen. Om användaren inte anger något värde i formulärfältet skickas det här värdet när formuläret skickas

### Fliken Validering {#validation-tab}

![Fliken Validering](/help/adaptive-forms/assets/telephoneinput_validationtab.png)

* **Obligatoriskt** - Välj det här alternativet om du vill visa komponenten i ett adaptivt formulär. Du kan inte välja **Dölj komponent** eller **Inaktivera komponent**  i **Grundläggande** när det här alternativet är markerat.

* **Felmeddelande** - Med det här alternativet kan du ange ett meddelande som visas om **Obligatoriskt** är markerad och fältet lämnas tomt.

* **Skriptverifieringsmeddelande** - Med det här alternativet kan du ange ett meddelande som ska visas om skriptvalideringen misslyckas.

* **Maximalt antal tecken** - Med det här alternativet kan du ange det maximala antalet tecken som tillåts i komponenten. Om du anger tecken som är större än det värde som anges i **Maximalt antal tecken** visas ett felmeddelande på skärmen. The **Felmeddelande för högsta antal tecken** kan du lägga till ett eget felmeddelande.

* **Felmeddelande för högsta antal tecken** - **Felmeddelande för högsta antal tecken** kan du lägga till ett anpassat felmeddelande om du anger tecken som är större än värdet som anges i **Maximalt antal tecken** alternativ.

* **Minsta antal tecken** - Med det här alternativet kan du ange det minsta antalet tecken som tillåts i fältet. Om du anger tecken som är mindre än det värde som anges i **Minsta antal tecken** visas ett felmeddelande på skärmen. The **Felmeddelande för minsta antal tecken** kan du lägga till ett eget felmeddelande.

* *Felmeddelande för minsta antal tecken** - **Felmeddelande för minsta antal tecken** kan du lägga till ett anpassat felmeddelande om du anger tecken som är mindre än värdet som anges i **Minsta antal tecken** alternativ.

The **Valideringsmönster** kan du ange ett mönster för att validera det angivna telefonnumret. Det angivna telefonnumret valideras mot det värde som anges i **Mönster** alternativ. Om telefonnumret inte kan valideras med det värde som anges i **Mönster** visas felmeddelandet på skärmen.

* **Mönster** - Med det här alternativet kan du ange tillåtna verifieringsmönster för telefonnummer. Reguljära uttryck tillåts också.

* **Felmeddelande** - Med det här alternativet kan du ange ett meddelande som visas på skärmen om det angivna telefonnumret inte kan valideras med det värde som anges i **Mönster** option

### Fliken Hjälpinnehåll {#help-content-tab}

![Fliken Hjälpinnehåll](/help/adaptive-forms/assets/telephoneinput_helptab.png)

* **Kort beskrivning** - En kort beskrivning är en kort textförklaring som ger ytterligare information eller förtydliganden om syftet med ett visst formulärfält. Det hjälper användaren att förstå vilken typ av data som ska anges i fältet och kan ge riktlinjer eller exempel som hjälper till att säkerställa att den angivna informationen är giltig och uppfyller de önskade kriterierna. Som standard är korta beskrivningar dolda. Aktivera **Visa alltid kort beskrivning** för att visa den under komponenten.

* **Visa alltid kort beskrivning** - Aktivera alternativet att visa den korta beskrivningen under komponenten.

* **Hjälptext** - Hjälptexten hänvisar till ytterligare information eller vägledning som användaren får för att hjälpa sig fylla i ett formulärfält på rätt sätt. Det visas när användaren klickar på hjälpikonen (i) som finns bredvid komponenten. Hjälptexten ger mer detaljerad information än etiketten eller platshållartexten för ett formulärfält och är utformad för att hjälpa användaren förstå fältets krav eller begränsningar. Den kan också ge förslag eller exempel som gör det enklare och exaktare att fylla i formuläret.

### Fliken Tillgänglighet {#accessibility-tab}

![Fliken Tillgänglighet](/help/adaptive-forms/assets/telephoneinput_accessibilitytab.png)

* **Text för skärmläsare** - Text för skärmläsare avser text som är avsedd att läsas av hjälpmedelstekniker, t.ex. skärmläsare, som används av personer med nedsatt syn. Den här texten innehåller en ljudbeskrivning av formulärfältets syfte och kan innehålla information om fältets titel, beskrivning, namn och relevanta meddelanden (anpassad text). Skärmläsartexten ser till att formuläret är tillgängligt för alla användare, även användare med nedsatt syn, och ger dem en fullständig förståelse för formulärfältet och dess krav.


## Designdialogruta {#design-dialog}

Designdialogrutan används för att definiera och hantera CSS-format för telefonindatakomponenten.

### Fliken Format {#styles-tab}

Designdialogrutan används för att definiera och hantera CSS-format för en komponent. Kärnkomponenten för adaptiv telefoninmatning från Forms stöder AEM [Formatsystem](/help/get-started/authoring.md#component-styling).

**CSS-standardklasser**: Du kan ange en standard-CSS-klass för den adaptiva Forms telefonindatakomponenten.

**Tillåtna format**: Du kan definiera format genom att ange ett namn och den CSS-klass som representerar formatet. Du kan till exempel skapa ett format med namnet&quot;bold text&quot; och ge CSS-klassen&quot;font-weight: fet&quot;. Du kan använda eller tillämpa dessa format på ett adaptivt formulär i den adaptiva Forms-redigeraren. Om du vill använda ett format väljer du den komponent du vill använda formatet på i Adaptiv Forms-redigerare, navigerar till egenskapsdialogrutan och väljer önskat format i dialogrutan **Stilar** nedrullningsbar lista. Om du behöver uppdatera eller ändra formaten går du tillbaka till designdialogrutan, uppdaterar formaten på formatfliken och sparar ändringarna.

### Fliken Format {#format-tab}

På fliken Format kan du ange standardtalformat och anpassade talformat.
