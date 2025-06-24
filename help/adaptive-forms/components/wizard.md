---
title: Adaptiv Forms Core-komponent - guide
description: Använda eller anpassa den adaptiva Forms Wizard Core Component.
role: Architect, Developer, Admin, User
exl-id: fd785cd2-5ed6-4efb-997f-ce9056ed113d
source-git-commit: 6725784bd4c94d433c91d6bd65d14d03cbefd954
workflow-type: tm+mt
source-wordcount: '2186'
ht-degree: 0%

---


# Guidekomponent{#wizard-adaptive-forms-core-component}

En guidelayout i ett adaptivt formulär refererar till ett formulär som är uppdelat i flera steg eller på flera sidor där användaren förflyttar sig i formuläret ett steg i taget. Layouten kallas för en guide eftersom den guidar användaren genom formuläret steg för steg.

Varje steg i guiden innehåller vanligtvis en grupp relaterade formulärfält och en navigeringsmekanism, som knapparna Nästa och Bakåt, som du kan använda för att gå mellan stegen. Användaren kan bara fortsätta till nästa steg när det aktuella steget har slutförts och alla obligatoriska fält har fyllts i.

Guidelayouten är användbar för formulär som innehåller många fält eller information som behöver samlas in, eftersom den delar upp formuläret i mindre, mer hanterbara segment. Det hjälper också användarna att fokusera på en uppsättning fält i taget, vilket kan göra ifyllningsprocessen mindre överväldigande.

Det kan dock även göra formuläret mer komplicerat, eftersom användaren måste gå igenom flera sidor för att fylla i formuläret. Därför är det nödvändigt att utvärdera formulärets krav och användarens behov innan man bestämmer sig för att använda en guidelayout.
Du kan använda huvudkomponenten för guidelayouten i ett adaptivt formulär för att skapa en guidelayout.

{{traditional-aem}}

**Exempel**

![exempel](/help/adaptive-forms/assets/wizard.png)

## Användning {#reasons-to-use-wizard-in-an-adaptive-form}

Det finns flera skäl till att det kan vara bra att använda en guidelayout i anpassad form:

- **Enkelhet**: Om du delar upp ett formulär i flera steg blir det lättare för användarna att förstå och slutföra, eftersom de kan fokusera på en uppsättning fält i taget.

- **Organisation**: Med en guidelayout kan du ordna formulär efter ämne eller syfte, och du kan också gruppera relaterade fält tillsammans, vilket kan göra ifyllningsprocessen mer logisk och effektiv.

- **Validering**: Med en guidelayout kan du stegvis validera, vilket kan hjälpa användare att identifiera och korrigera fel när de går, i stället för att vänta tills formuläret är slut.

- **Förloppsindikator**: En guidelayout kan visa förloppet för formuläret, vilket kan hjälpa användaren att förstå hur mycket av formuläret som återstår att slutföra.

- **Långa formulär**: Om formuläret innehåller många fält kan det vara överväldigande för användaren att se alla samtidigt, så att det blir mindre skrämmande om användaren bryter ned dem i mindre, mer hanterbara segment.

- **Undvik övergivande**: En guidelayout kan också bidra till att minska antalet formuläröverläggningar, eftersom användarna oftare fyller i ett formulär om de kan se förloppet och förstå hur mycket som återstår att göra.

- **Mobile Experience**: En guidelayout kan också vara bra för formulär som öppnas på mobila enheter, eftersom det gör det möjligt att läsa in mindre sidor snabbare och enklare att navigera på.

Generellt sett kan en guidelayout göra det enklare och effektivare att fylla i formulär, men det är viktigt att tänka på hur komplext formuläret är och användarens behov innan du bestämmer dig för att använda den här typen av layout.

## Version och kompatibilitet {#version-and-compatibility}

Kärnkomponenten i den adaptiva Forms-guiden Layout släpptes i februari 2023 som en del av kärnkomponenterna 2.0.4. Här är en tabell som visar alla versioner som stöds, kompatibiliteten med AEM och länkar till motsvarande dokumentation:

|  |  |
|---|---|
| Komponentversion | AEM as a Cloud Service |
| — | — |
| v1 | Kompatibel med <br>[version 2.0.4](/help/adaptive-forms/version.md) och senare | Kompatibel | Kompatibel |

Information om versioner och versioner av kärnkomponenter finns i dokumentet [Core Components Versions](/help/adaptive-forms/version.md) .

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Teknisk information {#technical-details}

Hämta den senaste informationen om kärnkomponenten i den adaptiva Forms-guiden i den tekniska dokumentationen för [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/wizard/v1/wizard). Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Du kan enkelt anpassa guideupplevelsen för besökare med dialogrutan Konfigurera. Du kan också enkelt definiera guidealternativ för en smidig användarupplevelse.

### Fliken Grundläggande {#basic-tab}

![Fliken Grundläggande](/help/adaptive-forms/assets/wizard-basic.png)

- **Namn** - Du kan enkelt identifiera en formulärkomponent med dess unika namn både i formuläret och i regelredigeraren, men namnet får inte innehålla blanksteg eller specialtecken.

- **Titel** - Med titeln kan du enkelt identifiera en komponent i ett formulär. Som standard visas titeln ovanpå komponenten.

- **Dölj titel** - Välj alternativet för att dölja komponentens titel.

- **Gruppera underordnade komponenters data för formuläröverföring (kapsla in data i objekt)** - När alternativet är markerat kapslas data från dess underordnade komponenter in i den överordnade komponentens JSON-objekt. Om alternativet inte är markerat har inskickade JSON-data en platt struktur utan objekt för den överordnade komponenten. Till exempel:

   - När alternativet är markerat kapslas data från de underordnade komponenterna (till exempel Street, City och Zip Code) in i den överordnade komponenten (Address) som ett JSON-objekt. Detta skapar en hierarkisk struktur och data ordnas under den överordnade komponenten.

     Struktur på inlämnade uppgifter:

     ```JSON
     { "Address":
     
     { "Street": "123 Main Street", "City": "New York", "Zip Code": "12345" }
     
     }
     ```

   - När alternativet inte är markerat har skickade JSON-data en platt struktur utan objekt för den överordnade komponenten (adress). Alla data finns på samma nivå, utan någon hierarkisk organisation.


     Struktur på inlämnade uppgifter:

     ```JSON
        { "Street": "123 Main Street", "City": "New York", "Zip Code": "12345" }
     ```

<!--   **Wrap data in an object** - Choose "Wrap data in an object" to put the field data from the Wizard inside a JSON object. If not chosen, the submit data JSON has a flat structure for the Wizard's fields.

-   **Layout** - You can have either a fixed layout (Simple) or a flexible layout (Responsive Grid) for your wizard. The Simple layout keeps everything fixed in the place, while the Responsive Grid allows you to adjust the position of components to suit your needs. For example, use Responsive Grid to align "First Name", "Middle Name" and "Last Name" in a form in a single row.  -->

- **Bindningsreferens** - En bindningsreferens är en referens till ett dataelement som lagras i en extern datakälla och används i ett formulär. Med den binda referensen kan du binda data dynamiskt till formulärfält så att formuläret kan visa de senaste data från datakällan. En bindningsreferens kan till exempel användas för att visa en kunds namn och adress i ett formulär baserat på kundens ID som anges i formuläret. Bindningsreferensen kan också användas för att uppdatera datakällan med data som anges i formuläret. På så sätt kan du med AEM Forms skapa formulär som interagerar med externa datakällor, vilket ger en smidig användarupplevelse för att samla in och hantera data.

- **Dölj komponent** - Välj alternativet att dölja komponenten från formuläret. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren. Detta är användbart när du behöver lagra information som inte behöver visas eller ändras direkt av användaren.

- **Inaktivera komponent** - Välj alternativet att inaktivera komponenten. Den inaktiverade komponenten är inte aktiv eller redigerbar av slutanvändaren. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.

- **Skrivskyddad** - Välj alternativet för att göra komponenten icke-redigerbar. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.

### Fliken Repeat Wizard {#repeat-wizard-tab}

![Upprepa guide](/help/adaptive-forms/assets/wizard-repeat.png)

Du kan använda alternativen för upprepning för att duplicera guiden och dess underordnade komponenter, definiera ett minsta och högsta antal upprepningar och underlätta replikering av liknande avsnitt i ett formulär. När du interagerar med Wizard-komponenten och använder dess inställningar visas följande alternativ:

- **Gör guiden repeterbar**: En växlingsfunktion som gör att användare kan aktivera eller inaktivera repeteringsfunktionen.
- **Minsta antal upprepningar**: Anger det minsta antal gånger som guidepanelen kan upprepas. Värdet noll anger att guidepanelen inte upprepas. Standardvärdet är noll.
- **Maximalt antal upprepningar**: Anger maximalt antal gånger som guidepanelen kan upprepas. Som standard är det här värdet obegränsat.

Om du effektivt vill hantera repeterbara avsnitt i guiden följer du stegen i artikeln [Skapa formulär med repeterbara avsnitt](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/create-forms-repeatable-sections.html?lang=sv-SE) .

### Fliken Objekt {#items-tab}

![Fliken Objekt](/help/adaptive-forms/assets/wizard_itemstab.png)

Med det här alternativet kan du lägga till adaptiva formulärkomponenter genom att klicka på knappen Lägg till, som visas som standard när guiden läggs till i redigeringsläge.

### Fliken Hjälp {#help-tab}

![Fliken Hjälp](/help/adaptive-forms/assets/wizard_helptab.png)

- **Kort beskrivning** - En kort beskrivning är en kort textförklaring som ger ytterligare information eller förtydliganden om syftet med ett visst formulärfält. Det hjälper användaren att förstå vilken typ av data som ska anges i fältet och kan ge riktlinjer eller exempel som hjälper till att säkerställa att den angivna informationen är giltig och uppfyller de önskade kriterierna. Som standard är korta beskrivningar dolda. Aktivera alternativet **Visa alltid kort beskrivning** för att visa det under komponenten.

- **Visa alltid kort beskrivning** - Aktivera alternativet att visa den korta beskrivningen under komponenten.

- **Hjälptext** - Hjälptexten hänvisar till ytterligare information eller vägledning som användaren får för att hjälpa dem att fylla i ett formulärfält korrekt. Det visas när användaren klickar på hjälpikonen (i) som finns bredvid komponenten. Hjälptexten ger mer detaljerad information än etiketten eller platshållartexten för ett formulärfält och är utformad för att hjälpa användaren förstå fältets krav eller begränsningar. Den kan också ge förslag eller exempel som gör det enklare och exaktare att fylla i formuläret.


### Fliken Tillgänglighet {#accessibility}

![Fliken Hjälpmedel](/help/adaptive-forms/assets/wizard_accessibiltytab.png)

- **Text för skärmläsare** - Text för skärmläsare hänvisar till ytterligare text som är särskilt avsedd att läsas av hjälpmedelstekniker, som skärmläsare, som används av personer med nedsatt syn. Den här texten innehåller en ljudbeskrivning av formulärfältets syfte och kan innehålla information om fältets titel, beskrivning, namn och relevanta meddelanden (anpassad text). Skärmläsartexten ser till att formuläret är tillgängligt för alla användare, även användare med nedsatt syn, och ger dem en fullständig förståelse för formulärfältet och dess krav.
   - **Egen text**: Välj det här alternativet om du vill använda den anpassade texten för ARIA-hjälpmedelsetiketter. Om du väljer det här alternativet visas dialogrutan Egen text. Du kan lägga till relevant information i dialogrutan Egen text.
   - **Beskrivning**: Välj det här alternativet om du vill använda beskrivningen för ARIA-hjälpmedelsetiketter.
   - **Titel**: Välj det här alternativet om du vill använda titeln för ARIA-hjälpmedelsetiketter.
   - **Namn**: Välj det här alternativet om du vill använda namnet på ARIA-hjälpmedelsetiketter.
   - **Inget**: Välj det här alternativet om du inte vill lägga till för hjälpmedelsetiketter för ARIA.

- **HTML-roll för skärmläsare som ska tillkännages** - HTML-rollen är ett attribut som används för att ange syftet med ett HTML-element för hjälpmedelstekniker som skärmläsare. Rollattributet används för att ge ytterligare kontext och semantisk innebörd till ett element, vilket gör det enklare för skärmläsare att tolka och meddela innehållet till användaren. I AEM Forms kan till exempel etiketten för ett formulärfält ha rollen&quot;label&quot;, och inmatningsfältet kan ha rollen&quot;texbox&quot;. Detta gör att skärmläsaren förstår förhållandet mellan etiketten och inmatningsfältet och kan meddela användaren dem på rätt sätt.


## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskapare styra hur saker visas som standard. För den adaptiva Forms-guidekomponenten kan du ange följande:

- Huvudkomponenterna som en formulärskapare kan lägga till i guiden i Adaptive Forms Editor
- Enkla namn på format (CSS-klasser) som kan användas i egenskapsdialogrutan för komponenten Wizard i den adaptiva Forms-redigeraren.

Detta gör det enklare och effektivare att skapa och anpassa formulär.

### Fliken Tillåtna komponenter {#allowed-components-tab}

![Fliken Tillåtna komponenter](/help/adaptive-forms/assets/tabs-allowed-component.png)

På fliken **Tillåtna komponenter** kan mallredigeraren ange vilka komponenter som kan läggas till som objekt på panelerna i guidekomponenten i den adaptiva Forms-redigeraren.

### Fliken Format {#styles-tab}

Designdialogrutan används för att definiera och hantera CSS-format för en komponent. Core-komponenten för den adaptiva Forms-guiden stöder AEM [Style System](/help/get-started/authoring.md#component-styling).

![Fliken Format](/help/adaptive-forms/assets/tabs-styles-tab.png)

- **Standardklasser för CSS**: Du kan ange en standardklass för CSS för den adaptiva kärnkomponenten i Forms-guiden.

- **Tillåtna format**: Du kan definiera format genom att ange ett namn och den CSS-klass som representerar formatet. Du kan till exempel skapa ett format med namnet&quot;bold text&quot; och ge CSS-klassen&quot;font-weight: bold&quot;. Du kan använda eller tillämpa dessa format på ett adaptivt formulär i en anpassad Forms-redigerare. Om du vill använda ett format väljer du den komponent du vill använda formatet på i Adaptiv Forms-redigerare, navigerar till egenskapsdialogrutan och väljer önskat format i listrutan **Format**. Om du behöver uppdatera eller ändra formaten går du tillbaka till designdialogrutan, uppdaterar formaten på formatfliken och sparar ändringarna.

### Fliken Anpassade egenskaper

![Fliken Anpassade egenskaper](/help/adaptive-forms/assets/tabs-custom-properties.png)

Med anpassade egenskaper kan du koppla anpassade attribut (nyckelvärdepar) till en anpassad formulärets kärnkomponent med hjälp av formulärmallen. De anpassade egenskaperna återspeglas i egenskapsavsnittet i den headless-renderingen av komponenten. Det gör att du kan skapa dynamiskt formulärbeteende som anpassas baserat på anpassade attributvärden. Utvecklare kan till exempel utforma olika renderingar av en Headless Forms-komponent för mobiler, datorer eller webbplattformar, vilket avsevärt förbättrar användarupplevelsen på en mängd olika enheter.

- **Gruppnamn**: Du kan ange ett namn som identifierar den anpassade egenskapsgruppen. Du kan lägga till, ta bort eller ordna om flera anpassade egenskapsgrupper. När du har lagt till den anpassade egenskapsgruppen kan du se följande alternativ:

   - **Nyckelvärdepar**: Du kan lägga till flera anpassade egenskapsnamn och anpassade egenskapsvärden genom att klicka på knappen **Lägg till** för varje anpassad egenskapsgrupp.

   - **Ta bort**: Tryck eller klicka för att ta bort det anpassade egenskapsnamnet och det anpassade egenskapsvärdet.

   - **Ordna om**: Tryck eller klicka och dra för att ändra ordningen på det anpassade egenskapsnamnet och det anpassade egenskapsvärdet.

## Relaterade artiklar {#related-articles}

{{more-like-this}}

## Se även {#see-also}

{{see-also}}