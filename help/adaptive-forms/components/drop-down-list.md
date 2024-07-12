---
title: Adaptiv Forms Core-komponent - nedrullningsbar lista
description: Använda eller anpassa den adaptiva Forms-nedrullningsbara kärnkomponenten.
role: Architect, Developer, Admin, User
exl-id: 9d59d0d2-d38f-4ed5-8b43-984c45f26f27
source-git-commit: 4c510b8fe59f4be6e1b329ee4257ab1b780fbf22
workflow-type: tm+mt
source-wordcount: '2185'
ht-degree: 0%

---

# Komponent för nedrullningsbar lista{#drop-down-list-adaptive-forms-core-component}

Med en nedrullningsbar lista i ett adaptivt formulär kan användarna välja ett eller flera alternativ i en lista med fördefinierade alternativ. Alternativen kan vara av typen String, Number eller Boolean. Dessutom kan den nedrullningsbara listkomponenten konfigureras så att den har olika validerings- och standardvärden.

**Exempel**
![example](/help/adaptive-forms/assets/drop-down-list.png)

## Användning {#reasons-to-use-drop-down-list}

Det finns många skäl till att det är bra att ta med en nedrullningsbar lista i en anpassad form, bland annat:

- **Lång lista med alternativ**: Nedrullningsbara listor är användbara i situationer där det finns en lång lista med alternativ för ett fält. De tar mindre plats i formuläret än en lista med alternativknappar eller kryssrutor och kan vara mindre överväldigande för användarna.

- **Konsekvens**: Listrutor ger en konsekvent design och layout av formuläret, vilket gör det mer intuitivt och enkelt för användarna att navigera.

- **Klarhet**: Med nedrullningsbara listor kan du göra formuläret tydligare och lättare att förstå genom att tillhandahålla en tydlig och kortfattad lista med alternativ.

- **Användarupplevelse**: Nedrullningsbara listor kan användas för att göra formuläret mer användarvänligt genom att tillhandahålla ett tydligt och intuitivt sätt för användarna att välja alternativ.

- **Dataanalys**: Nedrullningsbara listor kan användas för att samla in data från olika källor och analysera dem, eller för att använda dem som indata för vidare bearbetning.

**Dialogrutan Egenskaper**

Dialogrutan ![egenskaper](/help/adaptive-forms/assets/drop-down-list-properties.png)

I det här exemplet används elementet Alternativ för att definiera listobjekten. Elementet **Visningstext** används för att tillhandahålla en etikett för listobjekt och **Datavärde** används för att ange det värde som skickas till servern när formuläret skickas.

Varje alternativ i listrutan har ett unikt datavärde och attributet Visa text. Om en användare väljer alternativet &quot;Rött&quot; skickas motsvarande datavärde till servern när formuläret skickas. Dessa data kan sedan bearbetas av ett skript på servern för att avgöra vilka alternativ som har valts av användaren och kan användas för olika åtgärder, som att uppdatera andra fält i formuläret eller skicka formulärdata till ett skript på servern för vidare bearbetning.

Listrutan kan dessutom konfigureras att ha olika bearbetningsvärden för varje alternativ, och detta kan ställas in med Adaptiv Forms regelredigerare.

## Version och kompatibilitet {#version-and-compatibility}

Den adaptiva Forms Accordion Core-komponenten släpptes i februari 2023 som en del av Core Components 2.0.4 för Cloud Service och Core Components 1.1.12 för AEM 6.5.16.0 Forms eller senare. Här är en tabell med alla versioner som stöds, AEM kompatibilitet och länkar till motsvarande dokumentation:

| Komponentversion | AEM as a Cloud Service | AEM 6.5.16.0 Forms eller senare |
|---|---|---|
| v1 | Kompatibel med <br>[version 2.0.4](/help/adaptive-forms/version.md) och senare | Kompatibel med <br>[version 1.1.12](/help/adaptive-forms/version.md) och senare, men mindre än 2.0.0. |

Information om versioner och versioner av kärnkomponenter finns i dokumentet [Core Components Versions](/help/adaptive-forms/version.md) .

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Teknisk information {#technical-details}

Hämta den senaste informationen om Core-komponenten för listrutan Adaptiv Forms i den tekniska dokumentationen för [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/dropdown/v1/dropdown). Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Du kan enkelt anpassa den nedrullningsbara listan för besökare med dialogrutan Konfigurera. Du kan också enkelt definiera alternativ för nedrullningsbara listor för en smidig användarupplevelse.

![Fliken Grundläggande](/help/adaptive-forms/assets/dropdown_basictab.png)

- **Namn** - Du kan enkelt identifiera en formulärkomponent med dess unika namn både i formuläret och i regelredigeraren, men namnet får inte innehålla blanksteg eller specialtecken.

- **Titel** - Med titeln kan du enkelt identifiera en komponent i ett formulär. Som standard visas titeln ovanpå komponenten. Om du inte lägger till en titel visas komponentens namn i stället för rubriktexten.
- **Tillåt RTF-text för rubrik** - Med den här funktionen kan användare formatera oformaterad text med funktioner som fet, kursiv, understruken text, olika teckensnitt, teckenstorlekar, färger och ytterligare alternativ för att förbättra visuell presentation och anpassning. Det ger större flexibilitet och kreativ kontroll när det gäller att få titlar att sticka ut i dokument, på webbplatser och i tillämpningar.\
  När du markerar kryssrutan för **Tillåt RTF-text för titel** visas formateringsalternativ som formaterar komponentens titel. Om du vill visa alla tillgängliga formateringsalternativ klickar du på fliken ![Helskärmsikon](/help/adaptive-forms/assets/fullscreen-icon.png) .

  ![RTF-stöd](/help/adaptive-forms/assets/richtext-support-title.png)

- **Dölj titel** - Välj alternativet för att dölja komponentens titel.

- **Tillåt flera markeringar** - Välj det här alternativet om du vill välja flera alternativ i en nedrullningsbar lista.
- **Spara värde som** - Det här alternativet anger datatypen för det värde som skickas när något alternativ har valts. Om värdet **Spara som** är inställt på `Number` och du lägger till strängdata i &#x200B; **Datavärde** på fliken **Alternativ** visas ett `Value type mismatch`-felmeddelande.

  På fliken **Alternativ** kan du lägga till datavärden och visa textpar med knappen **Lägg till** . När ett nytt alternativ har lagts till utförs följande åtgärder:

   - **Datavärde** - Med det här alternativet kan du ange det innehåll som ska skickas när ett alternativ har valts.
   - **Visa text** - Med det här alternativet kan du ange det innehåll som ska visas i ett anpassat formulär.
   - **Ta bort** - Tryck eller klicka för att ta bort alternativet för en nedrullningsbar meny.
   - **Ordna om** - Tryck eller klicka och dra för att ändra ordningen för alternativet i en nedrullningsbar meny.

- **Standardalternativ** - Med det här alternativet kan du lägga till standardvärden. Använd ikonen Ta bort för att ta bort det tillagda alternativet. Om värdet **Spara som** är `Number` och du lägger till strängdata i **Standardalternativ** visas ett `Value type mismatch`-felmeddelande på skärmen.

- **Platshållartext** - Platshållartext i en formulärkomponent refererar till en kort etikett eller en fråga som visas i ett inmatningsfält som ett tips till användaren om vilken typ av information som förväntas anges i det fältet. Platshållartext försvinner när användaren börjar skriva i fältet och visas igen om fältet lämnas tomt. Den ger användaren en visuell referens, men fungerar inte som en permanent etikett eller ett permanent värde för fältet.

- **Alternativ** - Du kan lägga till datavärden och visa textpar med knappen **Lägg till** .  När ett nytt alternativ har lagts till kan följande åtgärder utföras:
   - **Datavärde** - Med det här alternativet kan du ange det innehåll som ska skickas när ett alternativ har valts.
   - **Visa text** - Med det här alternativet kan du ange det innehåll som ska visas i ett anpassat formulär.
   - **Ta bort** - Tryck eller klicka för att ta bort alternativet för en kryssruta.
   - **Ordna om** - Tryck eller klicka och dra för att ordna om panelerna.

- **Bindningsreferens** - En bindningsreferens är en referens till ett dataelement som lagras i en extern datakälla och används i ett formulär. Med den binda referensen kan du binda data dynamiskt till formulärfält så att formuläret kan visa de senaste data från datakällan. En bindningsreferens kan till exempel användas för att visa en kunds namn och adress i ett formulär baserat på kundens ID som anges i formuläret. Bindningsreferensen kan också användas för att uppdatera datakällan med data som anges i formuläret. På så sätt kan AEM Forms skapa formulär som interagerar med externa datakällor, vilket ger en smidig användarupplevelse för att samla in och hantera data.
- **Markera som obundet formulärelement**: Välj alternativet att konfigurera ett formulärfält som inte är länkat till något schema. Med det här alternativet kan du spara data utan att uppdatera datakällan. Det gör det också möjligt att hantera data på ett anpassat sätt, skilt från standarddatabasintegrering.

- **Dölj komponent** - Välj alternativet att dölja komponenten från formuläret. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren. Detta är användbart när du behöver lagra information som inte behöver visas eller ändras direkt av användaren.
- **Inaktivera komponent** - Välj alternativet att inaktivera komponenten. Den inaktiverade komponenten är inte aktiv eller redigerbar av slutanvändaren. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.
- **Skrivskyddad** - Välj alternativet för att göra komponenten icke-redigerbar. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.

### Fliken Validering {#validation-tab}

![Fliken Validering](/help/adaptive-forms/assets/dropdown_validationtab.png)

- **Obligatoriskt** - Välj det här alternativet om du vill visa komponenten i ett adaptivt formulär. När du har valt alternativet måste du göra ett val innan du kan fortsätta med en formuläröverföring. Du kan inte välja **Dölj komponent** eller **Inaktivera komponent** på fliken **Grundläggande** när det här alternativet är valt.

- **Felmeddelande** - Med det här alternativet kan du ange ett meddelande som visas om kryssrutan **Obligatorisk** är markerad och formulärfältet lämnas tomt.

- **Skriptvalideringsmeddelande** - Med det här alternativet kan du ange ett meddelande som ska visas om skriptvalideringen misslyckas.

### Fliken Hjälpinnehåll {#help-content-tab}

![Fliken Hjälpinnehåll](/help/adaptive-forms/assets/dropdown_helptab.png)

- **Kort beskrivning** - En kort beskrivning är en kort textförklaring som ger ytterligare information eller förtydliganden om syftet med ett visst formulärfält. Det hjälper användaren att förstå vilken typ av data som ska anges i fältet och kan ge riktlinjer eller exempel som hjälper till att säkerställa att den angivna informationen är giltig och uppfyller de önskade kriterierna. Som standard är korta beskrivningar dolda. Aktivera alternativet **Visa alltid kort beskrivning** för att visa det under komponenten.

- **Visa alltid kort beskrivning** - Aktivera alternativet att visa den korta beskrivningen under komponenten.

- **Hjälptext** - Hjälptexten hänvisar till ytterligare information eller vägledning som användaren får för att hjälpa dem att fylla i ett formulärfält korrekt. Det visas när användaren klickar på hjälpikonen (i) som finns bredvid komponenten. Hjälptexten ger mer detaljerad information än etiketten eller platshållartexten för ett formulärfält och är utformad för att hjälpa användaren förstå fältets krav eller begränsningar. Den kan också ge förslag eller exempel som gör det enklare och exaktare att fylla i formuläret.

### Fliken Tillgänglighet {#accessibility-tab}

![Fliken Tillgänglighet](/help/adaptive-forms/assets/dropdown_accessibilitytab.png)


- **Text för skärmläsare** - Text för skärmläsare hänvisar till ytterligare text som är särskilt avsedd att läsas av hjälpmedelstekniker, som skärmläsare, som används av personer med nedsatt syn. Den här texten innehåller en ljudbeskrivning av formulärfältets syfte och kan innehålla information om fältets titel, beskrivning, namn och relevanta meddelanden (anpassad text). Skärmläsartexten ser till att formuläret är tillgängligt för alla användare, även användare med nedsatt syn, och ger dem en fullständig förståelse för formulärfältet och dess krav.

   - **Egen text**: Välj det här alternativet om du vill använda den anpassade texten för ARIA-hjälpmedelsetiketter. Om du väljer det här alternativet visas dialogrutan Egen text. Du kan lägga till relevant information i dialogrutan Egen text.
   - **Beskrivning**: Välj det här alternativet om du vill använda beskrivningen för ARIA-hjälpmedelsetiketter.
   - **Titel**: Välj det här alternativet om du vill använda titeln för ARIA-hjälpmedelsetiketter.
   - **Namn**: Välj det här alternativet om du vill använda namnet på ARIA-hjälpmedelsetiketter.
   - **Inget**: Välj det här alternativet om du inte vill lägga till för hjälpmedelsetiketter för ARIA.

## Designdialogruta {#design-dialog}

Designdialogrutan används för att definiera och hantera CSS-format för den nedrullningsbara listkomponenten.

### Fliken Format {#styles-tab}

Fliken används för att definiera och hantera CSS-format för en komponent. Core Component (Core-komponent) för den adaptiva Forms-listrutan stöder AEM [Style System](/help/get-started/authoring.md#component-styling).

![Designdialogrutan](/help/adaptive-forms/assets/checkbox-style.png)

- **Standardklass för CSS-klasser**: Du kan ange en standardklass för CSS för den anpassade nedrullningsbara huvudkomponenten för Forms.

- **Tillåtna format**: Du kan definiera format genom att ange ett namn och den CSS-klass som representerar formatet. Du kan till exempel skapa ett format med namnet&quot;bold text&quot; och ge CSS-klassen&quot;font-weight: bold&quot;. Du kan använda eller tillämpa dessa format på ett adaptivt formulär i en anpassad Forms-redigerare. Om du vill använda ett format väljer du den komponent du vill använda formatet på i Adaptiv Forms-redigerare, navigerar till egenskapsdialogrutan och väljer önskat format i listrutan **Format**. Om du behöver uppdatera eller ändra formaten går du tillbaka till designdialogrutan, uppdaterar formaten på formatfliken och sparar ändringarna.

### Anpassade egenskaper

![Dialogrutan Anpassade egenskaper](/help/adaptive-forms/assets/checkbox-customproperties.png)

Med anpassade egenskaper kan du koppla anpassade attribut (nyckelvärdepar) till en anpassad formulärets kärnkomponent med hjälp av formulärmallen. De anpassade egenskaperna återspeglas i egenskapsavsnittet i den headless-renderingen av komponenten. Det gör att du kan skapa dynamiskt formulärbeteende som anpassas baserat på anpassade attributvärden. Utvecklare kan till exempel utforma olika renderingar av en Headless Forms-komponent för mobiler, datorer eller webbplattformar, vilket avsevärt förbättrar användarupplevelsen på en mängd olika enheter.

- **Gruppnamn**: Du kan ange ett namn som identifierar den anpassade egenskapsgruppen. Du kan lägga till, ta bort eller ordna om flera anpassade egenskapsgrupper. När du har lagt till den anpassade egenskapsgruppen kan du se följande alternativ:

   - **Nyckelvärdepar**: Du kan lägga till flera anpassade egenskapsnamn och anpassade egenskapsvärden genom att klicka på knappen **Lägg till** för varje anpassad egenskapsgrupp.

   - **Ta bort**: Tryck eller klicka för att ta bort det anpassade egenskapsnamnet och det anpassade egenskapsvärdet.

   - **Ordna om**: Tryck eller klicka och dra för att ändra ordningen på det anpassade egenskapsnamnet och det anpassade egenskapsvärdet.

## Relaterade artiklar {#related-articles}

{{more-like-this}}

## Se även {#see-also}

{{see-also}}
