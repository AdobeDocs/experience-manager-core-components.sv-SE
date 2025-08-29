---
title: Adaptiv Forms Core-komponent - datum och tid
description: Använda eller anpassa den adaptiva Forms Core-komponenten för datum och tid.
role: Architect, Developer, Admin, User
source-git-commit: daeabccaff39e255c111c6af2540ca4d5be0c709
workflow-type: tm+mt
source-wordcount: '1898'
ht-degree: 0%

---


# Datum- och tidskomponent

En datum- och tidskomponent i ett adaptivt formulär är ett element i användargränssnittet som gör att användare kan välja både **datum och tid** med hjälp av ett kalender- och klockgränssnitt, eller genom att ange värden manuellt i ett visst format. Det säkerställer korrekta, standardiserade indata för användning där både datum och tid är viktiga.

**Exempel**

![exempel](/help/adaptive-forms/assets/date-time-picker.png)

## Användning {#reasons-to-use-date-time-picker}

Det finns många skäl till att det är bra att ta med en datum- och tidväljare i ett formulär, bland annat:

- **Praktisk**: Används för att enkelt välja både ett datum och en tid utan att användaren behöver ange värden manuellt.
- **Konsekvens**: Tillämpar ett standardformat för datum- och tidsinmatningar i hela formuläret.
- **Förbättrad användarupplevelse**: Tillhandahåller ett intuitivt användargränssnitt med kalender- och tidsväljare.
- **Händelseplanering**: Användbart i formulär för bokning av möten, intervjuer eller schemaläggning av möten.
- **Resor och reservationer**: Låter användarna välja datum och tid för in- och utcheckning.
- **Datakvalitet**: Minskar indatafel jämfört med fritextinmatning.

## Version och kompatibilitet {#version-and-compatibility}

Den adaptiva Forms Core-komponenten för datum och tid släpptes **augusti 2025** som en del av **Core Components 2.24.6** för Cloud Service och senare.

| Komponentversion | AEM as a Cloud Service | AEM 6.5.16.0 Forms eller senare |
|---|---|---|
| v1 | Kompatibel med <br>[version 2.24.6](/help/adaptive-forms/version.md) och senare | |

Mer information om versioner finns i [Huvudkomponentversioner](/help/adaptive-forms/version.md).

## Teknisk information {#technical-details}

Hämta den senaste tekniska informationen om den adaptiva Forms Core-komponenten för datum och tid på [GitHub](https://github.com/adobe/aem-core-forms-components). Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för grundkomponentsutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan du anpassa datum och tid.

### Fliken Grundläggande {#basic-tab}

![Fliken Grundläggande](/help/adaptive-forms/assets/datetime_basictab.png)

- **Namn** - Namnet identifierar komponenten i regelredigeraren unikt. Specialtecken och mellanslag är inte tillåtna i namnsträngarna.

- **Titel** - Titel är en sträng som visas högst upp i en komponent i ett anpassat formulär. En unik titel identifierar komponenten i trädstrukturen i ett adaptivt formulär. Om du inte lägger till en titel visas komponentens namn i stället för rubriktexten.
- **Tillåt RTF-text för rubrik** - Med den här funktionen kan användare formatera oformaterad text med funktioner som fet, kursiv, understruken text, olika teckensnitt, teckenstorlekar, färger och ytterligare alternativ för att förbättra visuell presentation och anpassning. Det ger större flexibilitet och kreativ kontroll när det gäller att få titlar att sticka ut i dokument, på webbplatser och i tillämpningar.\
  När du markerar kryssrutan för **Tillåt RTF-text för titel** visas formateringsalternativ som formaterar komponentens titel. Om du vill visa alla tillgängliga formateringsalternativ klickar du på fliken ![Helskärmsikon](/help/adaptive-forms/assets/fullscreen-icon.png) .

  ![RTF-stöd](/help/adaptive-forms/assets/richtext-support-title.png)

- **Dölj titel** - Välj det här alternativet om du vill dölja titeln för komponenttypen i ett adaptivt formulär.

- **Platshållartext** - Platshållartext i en formulärkomponent refererar till en kort etikett eller en fråga som visas i ett inmatningsfält som ett tips till användaren om vilken typ av information som förväntas anges i det fältet. Platshållartext försvinner när användaren börjar skriva i fältet och visas igen om fältet lämnas tomt. Den ger användaren en visuell referens, men fungerar inte som en permanent etikett eller ett permanent värde för fältet.
- **Bindningsreferens** - En bindningsreferens är en referens till ett dataelement som lagras i en extern datakälla och används i ett formulär. Med den binda referensen kan du binda data dynamiskt till formulärfält så att formuläret kan visa de senaste data från datakällan. En bindningsreferens kan till exempel användas för att visa en kunds namn och adress i ett formulär baserat på kundens ID som anges i formuläret. Bindningsreferensen kan också användas för att uppdatera datakällan med data som anges i formuläret. På så sätt kan du med AEM Forms skapa formulär som interagerar med externa datakällor, vilket ger en smidig användarupplevelse för att samla in och hantera data.

- **Markera som obundet formulärelement**: Välj alternativet att konfigurera ett formulärfält som inte är länkat till något schema. Med det här alternativet kan du spara data utan att uppdatera datakällan. Det gör det också möjligt att hantera data på ett anpassat sätt, skilt från standarddatabasintegrering.

- **Dölj komponent** - Välj alternativet att dölja komponenten från formuläret. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren. Detta är användbart när du behöver lagra information som inte behöver visas eller ändras direkt av användaren.
- **Inaktivera komponent** - Välj alternativet att inaktivera komponenten. Den inaktiverade komponenten är inte aktiv eller redigerbar av slutanvändaren. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.
- **Skrivskyddad** - Välj alternativet för att göra komponenten icke-redigerbar. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.
- **Standarddatum och standardtid** - Med det här alternativet kan du lägga till ett datum och en tid i formulärfältet. Det angivna datumet visas som standard i stället för komponenten. Om användaren inte anger något datum eller ingen tid skickas värdet när formuläret skickas. Om **Inaktiverad komponent** eller **skrivskyddad komponent** väljs visas standarddatum och -tid på skärmen och skickas när formuläret skickas.

### Fliken Validering {#validation-tab}

![Fliken Validering](/help/adaptive-forms/assets/datetime_validation.png)

- **Obligatoriskt** - Välj det här alternativet om du vill visa komponenten i ett adaptivt formulär. När du har valt alternativet måste du göra ett val innan du kan fortsätta med en formuläröverföring. Du kan inte välja **Dölj komponent** eller **Inaktivera komponent** på fliken **Grundläggande** när det här alternativet är valt.

- **Felmeddelande** - Med det här alternativet kan du ange ett meddelande som visas om kryssrutan **Obligatorisk** är markerad och formulärfältet lämnas tomt.

- **Skriptvalideringsmeddelande** - Med det här alternativet kan du ange ett meddelande som ska visas om skriptvalideringen misslyckas.

- **Minimidatum** - Med det här alternativet kan du ange det minsta obligatoriska datumet. Om du anger ett datum som är tidigare än det som anges i Minimidatum och tid visas ett felmeddelande på skärmen. I dialogrutan **Minimalt felmeddelande** kan du lägga till ett eget felmeddelande.

- **Minimalt felmeddelande** - I dialogrutan **Minimalt felmeddelande** kan du lägga till ett anpassat felmeddelande som ska visas om du anger ett datum eller en tid som är tidigare än det datum eller den tid som anges i alternativet **Minimalt datum** .

- **Maximalt datum** - Med det här alternativet kan du ange maximalt datum och tid som krävs. Om du anger ett datum eller en tid som är senare än det datum eller den tid som anges i Maximalt datum visas ett felmeddelande på skärmen. I dialogrutan **Maximalt felmeddelande** kan du lägga till ett anpassat felmeddelande.

- **Maximalt felmeddelande** - I dialogrutan **Maximalt felmeddelande** kan du lägga till ett anpassat felmeddelande som ska visas om du anger ett datum eller en tid senare än det datum eller den tid som anges i alternativet **Maximalt datum** .

### Fliken Hjälpinnehåll {#help-content-tab}

![Fliken Hjälpinnehåll](/help/adaptive-forms/assets/datetime_helptab.png)

- **Kort beskrivning** - En kort beskrivning är en kort textförklaring som ger ytterligare information eller förtydliganden om syftet med ett visst formulärfält. Det hjälper användaren att förstå vilken typ av data som ska anges i fältet och kan ge riktlinjer eller exempel som hjälper till att säkerställa att den angivna informationen är giltig och uppfyller de önskade kriterierna. Som standard är korta beskrivningar dolda. Aktivera alternativet **Visa alltid kort beskrivning** för att visa det under komponenten.

- **Visa alltid kort beskrivning** - Aktivera alternativet att visa den korta beskrivningen under komponenten.

- **Hjälptext** - Hjälptexten hänvisar till ytterligare information eller vägledning som användaren får för att hjälpa dem att fylla i ett formulärfält korrekt. Det visas när användaren klickar på hjälpikonen (i) som finns bredvid komponenten. Hjälptexten ger mer detaljerad information än etiketten eller platshållartexten för ett formulärfält och är utformad för att hjälpa användaren förstå fältets krav eller begränsningar. Den kan också ge förslag eller exempel som gör det enklare och exaktare att fylla i formuläret.


### Fliken Tillgänglighet {#accessibility-tab}

![Fliken Tillgänglighet](/help/adaptive-forms/assets/datetime_accessibilitytab.png)

- **Text för skärmläsare** - Text för skärmläsare hänvisar till ytterligare text som är särskilt avsedd att läsas av hjälpmedelstekniker, som skärmläsare, som används av personer med nedsatt syn. Den här texten innehåller en ljudbeskrivning av formulärfältets syfte och kan innehålla information om fältets titel, beskrivning, namn och relevanta meddelanden (anpassad text). Skärmläsartexten ser till att formuläret är tillgängligt för alla användare, även användare med nedsatt syn, och ger dem en fullständig förståelse för formulärfältet och dess krav.
   - **Egen text**: Välj det här alternativet om du vill använda den anpassade texten för ARIA-hjälpmedelsetiketter. Om du väljer det här alternativet visas dialogrutan Egen text. Du kan lägga till relevant information i dialogrutan Egen text.
   - **Beskrivning**: Välj det här alternativet om du vill använda beskrivningen för ARIA-hjälpmedelsetiketter.
   - **Titel**: Välj det här alternativet om du vill använda titeln för ARIA-hjälpmedelsetiketter.
   - **Namn**: Välj det här alternativet om du vill använda namnet på ARIA-hjälpmedelsetiketter.
   - **Inget**: Välj det här alternativet om du inte vill lägga till för hjälpmedelsetiketter för ARIA.

<!--
### Formats Tab {#format-tab}

![Formats tab](/help/adaptive-forms/assets/datepicker_formattab.png)

-   **Display Format** - It represents the date format that is displayed to the user. The **Type** option allows the user to select the date format. You can also customize the date format using the **Custom** option in the **Type** dropdown menu.

-   **Edit Format** - It represents a date format in which the user can edit the date. The **Type** option allows the user to select the date format. You can also customize the date format using the **Custom** option in the **Type** dropdown menu.
-  **Format error message** - This option allows you to enter the message displayed on the screen when the entered date is not in the correct format.
- **Language** - This feature is used for formatting the specific field. When a user selects any language option from the **Type** drop-down menu, the **IETF BCP 47 language tag** option appears in the panel. You can choose the language for field formatting when translating an Adaptive Form into a specific language.
  
The set of languages is not visible by default, but users can input a custom **IETF BCP 47 language tag** by updating the template policy:

  1. Open the corresponding template associated with an Adaptive Form in the template editor.
  2. Select the existing policy as `datepicker-default-policy` from the drop-down menu.
   
        ![Date Picker template Policy](/help/adaptive-forms/assets/date-picker-template-policy.png)

  3. Click **Done**.

        >[!NOTE]
        >
        > For further information on how to translate an Adaptive Form to a specific locale, [click here](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/supporting-new-language-localization-core-components).
-->

## Designdialogruta {#design-dialog}

Designdialogrutan används för att definiera och hantera CSS-format för komponenten Datum och Tid.

### Fliken Format {#styles-tab}

Fliken används för att definiera och hantera CSS-format för en komponent. Den adaptiva Forms Core-komponenten för datum och tid stöder AEM [Style System](/help/get-started/authoring.md#component-styling).

![Fliken Format](/help/adaptive-forms/assets/datepicker_styletab.png)

- **Standardklasser för CSS**: Du kan ange en standardklass för CSS för den adaptiva kärnkomponenten Forms Date and Time.

- **Tillåtna format**: Du kan definiera format genom att ange ett namn och den CSS-klass som representerar formatet. Du kan till exempel skapa ett format med namnet&quot;bold text&quot; och ge CSS-klassen&quot;font-weight: bold&quot;. Du kan använda eller tillämpa dessa format på ett adaptivt formulär i en anpassad Forms-redigerare. Om du vill använda ett format väljer du den komponent du vill använda formatet på i Adaptiv Forms-redigerare, navigerar till egenskapsdialogrutan och väljer önskat format i listrutan **Format**. Om du behöver uppdatera eller ändra formaten går du tillbaka till designdialogrutan, uppdaterar formaten på formatfliken och sparar ändringarna.

### Anpassade egenskaper

![Dialogrutan Anpassade egenskaper](/help/adaptive-forms/assets/datepicker_customproperties.png)

Med anpassade egenskaper kan du koppla anpassade attribut (nyckelvärdepar) till en anpassad formulärets kärnkomponent med hjälp av formulärmallen. De anpassade egenskaperna återspeglas i egenskapsavsnittet i den headless-renderingen av komponenten. Det gör att du kan skapa dynamiskt formulärbeteende som anpassas baserat på anpassade attributvärden. Utvecklare kan till exempel utforma olika renderingar av en Headless Forms-komponent för mobiler, datorer eller webbplattformar, vilket avsevärt förbättrar användarupplevelsen på en mängd olika enheter.

- **Gruppnamn**: Du kan ange ett namn som identifierar den anpassade egenskapsgruppen. Du kan lägga till, ta bort eller ordna om flera anpassade egenskapsgrupper. När du har lagt till den anpassade egenskapsgruppen kan du se följande alternativ:

   - **Nyckelvärdepar**: Du kan lägga till flera anpassade egenskapsnamn och anpassade egenskapsvärden genom att klicka på knappen **Lägg till** för varje anpassad egenskapsgrupp.

   - **Ta bort**: Tryck eller klicka för att ta bort det anpassade egenskapsnamnet och det anpassade egenskapsvärdet.

   - **Ordna om**: Tryck eller klicka och dra för att ändra ordningen på det anpassade egenskapsnamnet och det anpassade egenskapsvärdet.

<!--
### Formats Tab {#formats-tab}

The formats tab allows you to specify default and custom date formats.

![Formattab](/help/adaptive-forms/assets/datepicker_formatpolicy.png)



## Related article {#related-article}

* [Create a standalone Adaptive Form](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html?lang=sv-SE)

-->

## Relaterade artiklar {#related-articles}

{{more-like-this}}

## Se även {#see-also}

{{see-also}}


