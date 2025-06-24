---
title: Adaptiv Forms Core-komponent - e-postindata
description: Använda eller anpassa den adaptiva Forms E-postindatakomponenten.
role: Architect, Developer, Admin, User
exl-id: f6a2974b-991e-4cea-9ef8-0b03e8975eeb
source-git-commit: 6725784bd4c94d433c91d6bd65d14d03cbefd954
workflow-type: tm+mt
source-wordcount: '2111'
ht-degree: 0%

---


# E-postkomponent {#Email-input-adaptive-forms-core-component}

Kärnkomponenten för indata för e-post med adaptiv form används för att samla in e-postadresser från användare. I e-postinmatningsfältet kan webbläsaren validera att de angivna data är ett giltigt e-postadressformat. Den representeras vanligtvis som en textruta och har mönstervalideringar som godkänner endast giltiga e-postadresser. E-postinmatningsfältet kan anpassas ytterligare med attribut som&quot;required&quot;,&quot;placeholder&quot; och&quot;pattern&quot; för att ange valideringar för inmatningsdata.

{{traditional-aem}}

**Exempel**

![exempel](/help/adaptive-forms/assets/emailid-example.png)

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

Det finns många skäl till att det är bra att ta med en e-postindatakomponent i ett anpassat formulär, bland annat:

- **Användarvänlighet**: En e-postinmatning gör det enklare för användare att ange sina e-postadresser eftersom den ger en tydlig indikation på de data som förväntas i fältet.

- **Anpassad kommunikation**: Om du samlar in e-postadresser från användare via ett formulär kan du kommunicera på ett personligt sätt, till exempel skicka bekräftelsemeddelanden via e-post eller nyhetsbrev.

- **Leadgenerering**: Genom att samla in e-postadresser via ett formulär kan företag skapa sin e-postlista och använda den för leadgenerering.

- **Användarautentisering**: E-postadresser kan användas som ett sätt att autentisera åtkomst till begränsat innehåll eller begränsade tjänster.

- **Feedback Collection**: Med e-postindata i ett feedbackformulär kan företaget kommunicera med användaren för uppföljning eller förtydligande av deras feedback.

## Version och kompatibilitet {#version-and-compatibility}

Den adaptiva e-postkärnkomponenten för Forms släpptes i februari 2023 som en del av Core Components 2.0.4 för Cloud Service och Core Components 1.1.12 för AEM 6.5.16.0 Forms eller senare. Här är en tabell som visar alla versioner som stöds, kompatibiliteten med AEM och länkar till motsvarande dokumentation:

| Komponentversion | AEM as a Cloud Service | AEM 6.5.16.0 Forms eller senare |
|---|---|---|
| v1 | Kompatibel med <br>[version 2.0.4](/help/adaptive-forms/version.md) och senare | Kompatibel med <br>[version 1.1.12](/help/adaptive-forms/version.md) och senare, men mindre än 2.0.0. |

Information om versioner och versioner av kärnkomponenter finns i dokumentet [Core Components Versions](/help/adaptive-forms/version.md) .

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Teknisk information {#technical-details}

Hämta den senaste informationen om den adaptiva Forms-kärnkomponenten för e-postindata i den tekniska dokumentationen för [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/emailinput/v1/emailinput). Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Du kan enkelt anpassa e-postinmatningen för besökare med dialogrutan Konfigurera. Du kan också enkelt definiera alternativ för e-postinmatning för en smidig användarupplevelse.

### Fliken Grundläggande {#basic-tab}

![Fliken Grundläggande](/help/adaptive-forms/assets/email_basictab.png)

- **Namn** - Namnet identifierar komponenten i regelredigeraren unikt. Specialtecken och blanksteg tillåts inte i namnsträngarna.

- **Titel** - Med titeln kan du enkelt identifiera en komponent i ett formulär. Som standard visas titeln ovanpå komponenten. Om du inte lägger till en titel visas komponentens namn i stället för rubriktexten.
- **Tillåt RTF-text för rubrik** - Med den här funktionen kan användare formatera oformaterad text med funktioner som fet, kursiv, understruken text, olika teckensnitt, teckenstorlekar, färger och ytterligare alternativ för att förbättra visuell presentation och anpassning. Det ger större flexibilitet och kreativ kontroll när det gäller att få titlar att sticka ut i dokument, på webbplatser och i tillämpningar.\
  När du markerar kryssrutan för **Tillåt RTF-text för titel** visas formateringsalternativ som formaterar komponentens titel. Om du vill visa alla tillgängliga formateringsalternativ klickar du på fliken ![Helskärmsikon](/help/adaptive-forms/assets/fullscreen-icon.png) .

  ![RTF-stöd](/help/adaptive-forms/assets/richtext-support-title.png)

- **Dölj titel** - Välj alternativet för att dölja komponentens titel.

- **Platshållartext** - Platshållartext i en formulärkomponent refererar till en kort etikett eller en fråga som visas i ett inmatningsfält som ett tips till användaren om vilken typ av information som förväntas anges i det fältet. Platshållartext försvinner när användaren börjar skriva i fältet och visas igen om fältet lämnas tomt. Den ger användaren en visuell referens, men fungerar inte som en permanent etikett eller ett permanent värde för fältet.
- **Bindningsreferens** - En bindningsreferens är en referens till ett dataelement som lagras i en extern datakälla och används i ett formulär. Med den binda referensen kan du binda data dynamiskt till formulärfält så att formuläret kan visa de senaste data från datakällan. En bindningsreferens kan till exempel användas för att visa en kunds namn och adress i ett formulär baserat på kundens ID som anges i formuläret. Bindningsreferensen kan också användas för att uppdatera datakällan med data som anges i formuläret. På så sätt kan AEM Forms skapa formulär som interagerar med externa datakällor, vilket ger en smidig användarupplevelse för att samla in och hantera data.
- **Markera som obundet formulärelement**: Välj alternativet att konfigurera ett formulärfält som inte är länkat till något schema. Med det här alternativet kan du spara data utan att uppdatera datakällan. Det gör det också möjligt att hantera data på ett anpassat sätt, skilt från standarddatabasintegrering.
- **Dölj komponent** - Välj alternativet att dölja komponenten från formuläret. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren. Detta är användbart när du behöver lagra information som inte behöver visas eller ändras direkt av användaren.
- **Inaktivera komponent** - Välj alternativet att inaktivera komponenten. Den inaktiverade komponenten är inte aktiv eller redigerbar av slutanvändaren. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.
- **Skrivskyddad** - Välj alternativet för att göra komponenten icke-redigerbar. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.

- **Standardvärde** - Med det här alternativet kan du lägga till ett standardvärde i ett formulärfält. Om **Inaktiverad komponent** eller **skrivskyddad komponent** har valts visas standardvärdet på skärmen. Om användaren inte anger något värde i formulärfältet skickas värdet när formuläret skickas
- **Attribut för automatisk ifyllning**: Med det här alternativet kan användare ange ett värde som fylls i automatiskt i formulärfältet baserat på den lagrade informationen.

### Fliken Validering {#validation-tab}

![Fliken Validering](/help/adaptive-forms/assets/email_validationtab.png)

- **Obligatoriskt** - Välj det här alternativet om du vill visa komponenten i ett adaptivt formulär. När du har valt alternativet måste du ange ett värde innan du fortsätter med en formuläröverföring. Du kan inte välja **Dölj komponent** eller **Inaktivera komponent** på fliken **Grundläggande** när det här alternativet är valt.

- **Felmeddelande** - Med det här alternativet kan du ange ett meddelande som visas om kryssrutan **Obligatorisk** är markerad och formulärfältet lämnas tomt.

- **Skriptvalideringsmeddelande** - Med det här alternativet kan du ange ett meddelande som ska visas om skriptvalideringen misslyckas.

- **Maximalt antal tecken** - Med det här alternativet kan du ange maximalt antal tecken i fältet. Om du anger tecken som är större än det värde som har angetts i **Maximalt antal tecken** visas ett felmeddelande på skärmen. I dialogrutan **Felmeddelande** med maximalt antal tecken kan du lägga till ett anpassat felmeddelande.

- **Felmeddelande med maximalt antal tecken** - I dialogrutan **Felmeddelande med maximalt antal tecken** kan du lägga till ett anpassat felmeddelande om du anger tecken som är större än det värde som har angetts i alternativet **Maximalt antal tecken** .

- **Minsta antal tecken** - Med det här alternativet kan du ange det minsta antalet tecken som tillåts i fältet. Om du anger tecken som är mindre än värdet som anges i **Minsta antal tecken** visas ett felmeddelande på skärmen. I dialogrutan **Felmeddelande för minsta antal tecken** kan du lägga till ett anpassat felmeddelande.

- **Felmeddelande för minsta antal tecken** - I dialogrutan **Felmeddelande för minsta antal tecken** kan du lägga till ett anpassat felmeddelande om du anger tecken som är mindre än det värde som har angetts i alternativet **Minsta antal tecken** .
<br>

Med alternativet **Valideringsmönster** kan du ange ett mönster för att validera det angivna e-post-ID:t. Om e-post-ID:t inte kan valideras med det värde som anges i alternativet **Mönster** visas felmeddelandet på skärmen.

- **Mönster** - Med det här alternativet kan du ange tillåtna verifieringsmönster för e-post. Reguljära uttryck tillåts också.
- **Felmeddelande** - Med det här alternativet kan du ange ett meddelande som visas på skärmen om e-post-ID:t inte kan valideras med det värde som anges i alternativet **Mönster**

### Fliken Hjälpinnehåll {#help-content-tab}

![Fliken Hjälpinnehåll](/help/adaptive-forms/assets/email_helptab.png)

- **Kort beskrivning** - En kort beskrivning är en kort textförklaring som ger ytterligare information eller förtydliganden om syftet med ett visst formulärfält. Det hjälper användaren att förstå vilken typ av data som ska anges i fältet och kan ge riktlinjer eller exempel som hjälper till att säkerställa att den angivna informationen är giltig och uppfyller de önskade kriterierna. Som standard är korta beskrivningar dolda. Aktivera alternativet **Visa alltid kort beskrivning** för att visa det under komponenten.

- **Visa alltid kort beskrivning** - Aktivera alternativet att visa den korta beskrivningen under komponenten.

- **Hjälptext** - Hjälptexten hänvisar till ytterligare information eller vägledning som användaren får för att hjälpa dem att fylla i ett formulärfält korrekt. Det visas när användaren klickar på hjälpikonen (i) som finns bredvid komponenten. Hjälptexten ger mer detaljerad information än etiketten eller platshållartexten för ett formulärfält och är utformad för att hjälpa användaren förstå fältets krav eller begränsningar. Den kan också ge förslag eller exempel som gör det enklare och exaktare att fylla i formuläret.

### Fliken Tillgänglighet {#accessibility-tab}

![Fliken Tillgänglighet](/help/adaptive-forms/assets/email_accessibilitytab.png)

- **Text för skärmläsare** - Text för skärmläsare hänvisar till ytterligare text som är särskilt avsedd att läsas av hjälpmedelstekniker, som skärmläsare, som används av personer med nedsatt syn. Den här texten innehåller en ljudbeskrivning av formulärfältets syfte och kan innehålla information om fältets titel, beskrivning, namn och relevanta meddelanden (anpassad text). Skärmläsartexten ser till att formuläret är tillgängligt för alla användare, även användare med nedsatt syn, och ger dem en fullständig förståelse för formulärfältet och dess krav.

   - **Egen text**: Välj det här alternativet om du vill använda den anpassade texten för ARIA-hjälpmedelsetiketter. Om du väljer det här alternativet visas dialogrutan Egen text. Du kan lägga till relevant information i dialogrutan Egen text.
   - **Beskrivning**: Välj det här alternativet om du vill använda beskrivningen för ARIA-hjälpmedelsetiketter.
   - **Titel**: Välj det här alternativet om du vill använda titeln för ARIA-hjälpmedelsetiketter.
   - **Namn**: Välj det här alternativet om du vill använda namnet på ARIA-hjälpmedelsetiketter.
   - **Inget**: Välj det här alternativet om du inte vill lägga till för hjälpmedelsetiketter för ARIA.

## Designdialogruta {#design-dialog}

Designdialogrutan används för att definiera och hantera CSS-format för e-postindatakomponenten.

### Fliken Format {#styles-tab}

Fliken används för att definiera och hantera CSS-format för en komponent. Kärnkomponenten för anpassade Forms-indata via e-post stöder AEM [Style System](/help/get-started/authoring.md#component-styling).

![Fliken Format](/help/adaptive-forms/assets/datepicker_styletab.png)

- **Standardklasser för CSS**: Du kan ange en standardklass för CSS för den adaptiva kärnkomponenten för e-postindata från Forms.

- **Tillåtna format**: Du kan definiera format genom att ange ett namn och den CSS-klass som representerar formatet. Du kan till exempel skapa ett format med namnet&quot;bold text&quot; och ge CSS-klassen&quot;font-weight: bold&quot;. Du kan använda eller tillämpa dessa format på ett adaptivt formulär i en anpassad Forms-redigerare. Om du vill använda ett format väljer du den komponent du vill använda formatet på i Adaptiv Forms-redigerare, navigerar till egenskapsdialogrutan och väljer önskat format i listrutan **Format**. Om du behöver uppdatera eller ändra formaten går du tillbaka till designdialogrutan, uppdaterar formaten på formatfliken och sparar ändringarna.

### Anpassade egenskaper

![Dialogrutan Anpassade egenskaper](/help/adaptive-forms/assets/datepicker_customproperties.png)

Med anpassade egenskaper kan du koppla anpassade attribut (nyckelvärdepar) till en anpassad formulärets kärnkomponent med hjälp av formulärmallen. De anpassade egenskaperna återspeglas i egenskapsavsnittet i den headless-renderingen av komponenten. Det gör att du kan skapa dynamiskt formulärbeteende som anpassas baserat på anpassade attributvärden. Utvecklare kan till exempel utforma olika renderingar av en Headless Forms-komponent för mobiler, datorer eller webbplattformar, vilket avsevärt förbättrar användarupplevelsen på en mängd olika enheter.

- **Gruppnamn**: Du kan ange ett namn som identifierar den anpassade egenskapsgruppen. Du kan lägga till, ta bort eller ordna om flera anpassade egenskapsgrupper. När du har lagt till den anpassade egenskapsgruppen kan du se följande alternativ:

   - **Nyckelvärdepar**: Du kan lägga till flera anpassade egenskapsnamn och anpassade egenskapsvärden genom att klicka på knappen **Lägg till** för varje anpassad egenskapsgrupp.

   - **Ta bort**: Tryck eller klicka för att ta bort det anpassade egenskapsnamnet och det anpassade egenskapsvärdet.

   - **Ordna om**: Tryck eller klicka och dra för att ändra ordningen på det anpassade egenskapsnamnet och det anpassade egenskapsvärdet.

### Fliken Format {#formats-tab}

På fliken Format kan du ange standardformat och anpassade datumformat.

![Formateringsflik](/help/adaptive-forms/assets/emailinput_formattab.png)

<!--

## Related article {#related-article}

* [Create a standalone Adaptive Form](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html?lang=sv-SE)

-->

## Relaterade artiklar {#related-articles}

{{more-like-this}}

## Se även {#see-also}

{{see-also}}
