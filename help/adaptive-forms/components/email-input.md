---
title: Adaptiv Forms Core-komponent - e-postindata
description: Använda eller anpassa den adaptiva Forms E-postindatakomponenten.
role: Architect, Developer, Admin, User
source-git-commit: 945e1793ae4e959f83960db46d2de4257916fe32
workflow-type: tm+mt
source-wordcount: '1776'
ht-degree: 0%

---


# E-postindata {#Email-input-adaptive-forms-core-component}

Kärnkomponenten för indata för e-post med adaptiv form används för att samla in e-postadresser från användare. I e-postinmatningsfältet kan webbläsaren validera att de angivna data är ett giltigt e-postadressformat. Den representeras vanligtvis som en textruta och har mönstervalideringar som godkänner endast giltiga e-postadresser. E-postinmatningsfältet kan anpassas ytterligare med attribut som&quot;required&quot;,&quot;placeholder&quot; och&quot;pattern&quot; för att ange valideringar för inmatningsdata.

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

Det finns många skäl till att det är bra att ta med en e-postindatakomponent i ett anpassat formulär, bland annat:

* **Användarbekvämlighet**: En e-postinmatning gör det enklare för användare att ange sina e-postadresser eftersom det ger en tydlig indikation på de data som förväntas i fältet.

* **Personlig kommunikation**: Genom att samla in e-postadresser från användare via ett formulär kan du kommunicera på ett personligt sätt, till exempel skicka bekräftelsemeddelanden via e-post eller nyhetsbrev.

* **Generering av leads**: Genom att samla in e-postadresser via ett formulär kan företag skapa sin e-postlista och använda den för att generera leads.

* **Användarautentisering**: E-postadresser kan användas som ett sätt att autentisera åtkomst till begränsat innehåll eller begränsade tjänster.

* **Feedback Collection**: Med e-postindata i ett feedbackformulär kan företaget kommunicera med användaren för uppföljning eller förtydligande av deras feedback.

## Version och kompatibilitet {#version-and-compatibility}

Kärnkomponenten i den adaptiva e-postinmatningen från Forms släpptes i februari 2023 som en del av kärnkomponenterna 2.0.4. Här är en tabell med alla versioner som stöds, AEM kompatibilitet och länkar till motsvarande dokumentation:

|  |  |
|---|---|
| Komponentversion | AEM as a Cloud Service |
| — | --- |
| v1 | Kompatibel med<br>[version 2.0.4](/help/versions.md) och senare | Kompatibel | Kompatibel |

Information om versioner och versioner av kärnkomponenter finns i [Huvudkomponentversioner](/help/versions.md) -dokument.

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Teknisk information {#technical-details}

Hämta den senaste informationen om den adaptiva Forms E-postindatakärnkomponenten i den tekniska dokumentationen om [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/emailinput/v1/emailinput). Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Du kan enkelt anpassa e-postinmatningen för besökare med dialogrutan Konfigurera. Du kan också enkelt definiera alternativ för e-postinmatning för en smidig användarupplevelse.

### Fliken Grundläggande {#basic-tab}

![Fliken Grundläggande](/help/adaptive-forms/assets/email_basictab.png)

* **Namn** - Namnet identifierar komponenten i regelredigeraren unikt. Specialtecken och mellanslag är inte tillåtna i namnsträngarna.

* **Titel** - Med dess titel kan du enkelt identifiera en komponent i ett formulär. Som standard visas titeln ovanpå komponenten. Om du inte lägger till en titel visas komponentens namn i stället för titeltexten.

* **Dölj titel** - Välj alternativet om du vill dölja komponentens titel.

* **Platshållartext** - Platshållartext i en formulärkomponent refererar till en kort etikett eller en fråga som visas i ett inmatningsfält som ett tips till användaren om vilken typ av information som förväntas anges i det fältet. Platshållartext försvinner när användaren börjar skriva i fältet och visas igen om fältet lämnas tomt. Den ger användaren en visuell referens, men fungerar inte som en permanent etikett eller ett permanent värde för fältet.

* **Bindningsreferens** - En bind referens är en referens till ett dataelement som lagras i en extern datakälla och används i ett formulär. Med den binda referensen kan du binda data dynamiskt till formulärfält så att formuläret kan visa de senaste data från datakällan. En bindningsreferens kan till exempel användas för att visa en kunds namn och adress i ett formulär baserat på kundens ID som anges i formuläret. Bindningsreferensen kan också användas för att uppdatera datakällan med data som anges i formuläret. På så sätt kan AEM Forms skapa formulär som interagerar med externa datakällor, vilket ger en smidig användarupplevelse för att samla in och hantera data.
* **Dölj komponent** - Välj alternativet att dölja komponenten från formuläret. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren. Detta är användbart när du behöver lagra information som inte behöver visas eller ändras direkt av användaren.
* **Inaktivera komponent** - Välj alternativet att inaktivera komponenten. Den inaktiverade komponenten är inte aktiv eller redigerbar av slutanvändaren. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.
* **Skrivskyddad** - Välj alternativet att göra komponenten icke-redigerbar. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.

* **Standardvärde** - Med det här alternativet kan du lägga till ett standardvärde i ett formulärfält. If **Inaktiverad komponent** eller **Skrivskyddad komponent** är markerat visas standardvärdet på skärmen. Om användaren inte anger något värde i formulärfältet skickas det här värdet när formuläret skickas


### Fliken Validering {#validation-tab}

![Fliken Validering](/help/adaptive-forms/assets/email_validationtab.png)

* **Obligatoriskt** - Välj det här alternativet om du vill visa komponenten i ett adaptivt formulär. Du kan inte välja **Dölj komponent** eller **Inaktivera komponent**  i **Grundläggande** när det här alternativet är markerat.

* **Felmeddelande** - Med det här alternativet kan du ange ett meddelande som visas om **Obligatoriskt** kryssrutan är markerad och formulärfältet är tomt.

* **Skriptverifieringsmeddelande** - Med det här alternativet kan du ange ett meddelande som ska visas om skriptvalideringen misslyckas.

* **Maximalt antal tecken** - Med det här alternativet kan du ange det maximala antalet tecken som tillåts i fältet. Om du anger tecken som är större än det värde som anges i **Maximalt antal tecken** visas ett felmeddelande på skärmen. The **Felmeddelande för högsta antal tecken** kan du lägga till ett eget felmeddelande.

* **Felmeddelande för högsta antal tecken** - **Felmeddelande för högsta antal tecken** kan du lägga till ett anpassat felmeddelande om du anger tecken som är större än värdet som anges i **Maximalt antal tecken** alternativ.

* **Minsta antal tecken** - Med det här alternativet kan du ange det minsta antalet tecken som tillåts i fältet. Om du anger tecken som är mindre än det värde som anges i **Minsta antal tecken** visas ett felmeddelande på skärmen. The **Felmeddelande för minsta antal tecken** kan du lägga till ett eget felmeddelande.

* **Felmeddelande för minsta antal tecken** - **Felmeddelande för minsta antal tecken** kan du lägga till ett anpassat felmeddelande om du anger tecken som är mindre än värdet som anges i **Minsta antal tecken** alternativ.

<br>

    Med alternativet **Valideringsmönster** kan du ange ett mönster som validerar det angivna e-post-ID:t. Om e-post-ID:t inte kan valideras med det värde som anges i alternativet **Pattern** visas felmeddelandet på skärmen.
    * **Mönster** - Med det här alternativet kan du ange tillåtna verifieringsmönster för e-post. Reguljära uttryck tillåts också.
    * **Felmeddelande** - Med det här alternativet kan du ange ett meddelande som visas på skärmen om e-post-ID:t inte kan valideras med det värde som anges i alternativet **Pattern**

### Fliken Hjälpinnehåll {#help-content-tab}

![Fliken Hjälpinnehåll](/help/adaptive-forms/assets/email_helptab.png)

* **Kort beskrivning** - En kort beskrivning är en kort textförklaring som ger ytterligare information eller förtydliganden om syftet med ett visst formulärfält. Det hjälper användaren att förstå vilken typ av data som ska anges i fältet och kan ge riktlinjer eller exempel som hjälper till att säkerställa att den angivna informationen är giltig och uppfyller de önskade kriterierna. Som standard är korta beskrivningar dolda. Aktivera **Visa alltid kort beskrivning** för att visa den under komponenten.

* **Visa alltid kort beskrivning** - Aktivera alternativet att visa den korta beskrivningen under komponenten.

* **Hjälptext** - Hjälptexten hänvisar till ytterligare information eller vägledning som användaren får för att hjälpa sig fylla i ett formulärfält på rätt sätt. Det visas när användaren klickar på hjälpikonen (i) som finns bredvid komponenten. Hjälptexten ger mer detaljerad information än etiketten eller platshållartexten för ett formulärfält och är utformad för att hjälpa användaren förstå fältets krav eller begränsningar. Den kan också ge förslag eller exempel som gör det enklare och exaktare att fylla i formuläret.

### Fliken Tillgänglighet {#accessibility-tab}

![Fliken Tillgänglighet](/help/adaptive-forms/assets/email_accessibilitytab.png)

På **Tillgänglighet** tabb, värden anges för [Tillgänglighet för ARIA](https://www.w3.org/WAI/standards-guidelines/aria/) -etiketter för komponenten. Det finns olika alternativ för att använda texten för skärmläsare:

* **Text för skärmläsare** - Text för skärmläsare avser text som är avsedd att läsas av hjälpmedelstekniker, t.ex. skärmläsare, som används av personer med nedsatt syn. Den här texten innehåller en ljudbeskrivning av formulärfältets syfte och kan innehålla information om fältets titel, beskrivning, namn och relevanta meddelanden (anpassad text). Skärmläsartexten ser till att formuläret är tillgängligt för alla användare, även användare med nedsatt syn, och ger dem en fullständig förståelse för formulärfältet och dess krav.


   * **Egen text**: Välj det här alternativet om du vill använda den anpassade texten för ARIA-hjälpmedelsetiketter. Om du väljer det här alternativet visas dialogrutan Egen text. Du kan lägga till relevant information i dialogrutan Egen text.
   * **Beskrivning**: Välj det här alternativet om du vill använda beskrivningen för hjälpmedelsetiketter för ARIA.
   * **Titel**: Välj det här alternativet om du vill använda titeln för ARIA-hjälpmedelsetiketter.
   * **Namn**: Välj det här alternativet om du vill använda namnet på ARIA-hjälpmedelsetiketter.
   * **Ingen**: Välj det här alternativet om du inte vill lägga till hjälpmedelsetiketter för ARIA.


## Designdialogruta {#design-dialog}

Designdialogrutan används för att definiera och hantera CSS-format för e-postindatakomponenten.


### Fliken Format {#styles-tab}

Designdialogrutan används för att definiera och hantera CSS-format för en komponent. Kärnkomponenten för anpassade e-postindata från Forms stöder AEM [Formatsystem](/help/get-started/authoring.md#component-styling).

**CSS-standardklasser**: Du kan ange en standard-CSS-klass för den adaptiva kärnkomponenten för e-postindata från Forms.

**Tillåtna format**: Du kan definiera format genom att ange ett namn och den CSS-klass som representerar formatet. Du kan till exempel skapa ett format med namnet&quot;bold text&quot; och ge CSS-klassen&quot;font-weight: fet&quot;. Du kan använda eller tillämpa dessa format på ett adaptivt formulär i den adaptiva Forms-redigeraren. Om du vill använda ett format väljer du den komponent du vill använda formatet på i Adaptiv Forms-redigerare, navigerar till egenskapsdialogrutan och väljer önskat format i dialogrutan **Stilar** nedrullningsbar lista. Om du behöver uppdatera eller ändra formaten går du tillbaka till designdialogrutan, uppdaterar formaten på formatfliken och sparar ändringarna.

### Fliken Format {#format-tab}

På fliken Format kan du ange standardformat och anpassade datumformat.