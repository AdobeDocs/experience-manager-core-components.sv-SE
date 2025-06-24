---
title: Adaptiv Forms Core-komponent - lösenordsruta
description: Använda eller anpassa kärnkomponenten i den adaptiva Forms-lösenordsrutan.
role: Architect, Developer, Admin, User
hide: true
hidefromtoc: true
exl-id: 7e70d9e9-b066-4ba3-b7ed-e4aad026c5e0
source-git-commit: 6725784bd4c94d433c91d6bd65d14d03cbefd954
workflow-type: tm+mt
source-wordcount: '1914'
ht-degree: 0%

---


# Lösenordsrutekomponent

<span class="preview"> Den här funktionen är en förhandsversion och kan nås via vår [förhandsutgåva](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/release-notes/prerelease.html#new-features). </span>

Med en lösenordsrutekomponent kan användare ange och redigera känslig information, normalt maskerad för sekretess. Lösenordskomponenten kan konfigureras med olika valideringsregler för att säkerställa att data är korrekta. De lösenordsfält som ofta används i formulär är enkla och förbättrar datasäkerheten.

{{traditional-aem}}

**Exempel**

![exempel på lösenordsruta](/help/adaptive-forms/assets/password.png)

Användaren kan klicka på ögonikonen för att visa den lösenordstext som har angetts. Det förbättrar säkerheten samtidigt som användarna kan ange konfidentiell information korrekt.

## Användning

Det finns flera skäl till att använda lösenordsrutekomponenten i ett adaptivt formulär:

- **Säker datainsamling**: Fältet för lösenordsruta används för att samla in känslig information, t.ex. lösenord, PIN-koder och andra konfidentiella poster, och visa maskerade tecken för sekretess.

- **Användarvänlig**: I lösenordsfältet kan användare ange och redigera information på ett säkert sätt utan att visa den på skärmen.

- **Flexibilitet**: Komponenten för lösenordsruta kan konfigureras för att uppfylla säkerhetskrav, till exempel minsta teckenlängd, specialtecken eller andra anpassade valideringar för att säkerställa starkt dataskydd och precision.

<!--
## Version and Compatibility {#version-and-compatibility}

The Adaptive Forms Password box Core Component was released in Feb 2023 as part of the Core Components 2.0.4 for Cloud Service and Core Components 1.1.12 for AEM 6.5.16.0 Forms or later. Here's a table showing all supported versions, AEM compatibility, and links to corresponding documentation:

|Component Version|AEM as a Cloud Service|AEM 6.5.16.0 Forms or later|
|---|---|---|
|v1|Compatible with<br>[release 2.0.4](/help/adaptive-forms/version.md) and later| Compatible with<br>[release 1.1.12](/help/adaptive-forms/version.md) and later but less than 2.0.0.|

For information on Core Component versions and releases, refer to the [Core Components Versions](/help/adaptive-forms/version.md) document.

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Teknisk information {#technical-details}

Hämta den senaste informationen om kärnkomponenten för det adaptiva Forms-lösenordet i den tekniska dokumentationen för [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/textinput/v1/textinput). Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Du kan enkelt anpassa textinmatningen för besökare med dialogrutan Konfigurera. Du kan också enkelt definiera alternativ för textinmatning för en smidig användarupplevelse.

### fliken Grundläggande

![Grundläggande flik](/help/adaptive-forms/assets/password-basic.png)

- **Namn** - Du kan enkelt identifiera en formulärkomponent med dess unika namn både i formuläret och i regelredigeraren, men namnet får inte innehålla blanksteg eller specialtecken.

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

### Fliken Validering {#validation-tab}

![Fliken Validering](/help/adaptive-forms/assets/password-validation.png)

- **Obligatoriskt** - Välj det här alternativet om du vill visa komponenten i ett adaptivt formulär. När du har valt alternativet måste du ange ett värde innan du fortsätter med en formuläröverföring. Du kan inte välja **Dölj komponent** eller **Inaktivera komponent** på fliken **Grundläggande** när det här alternativet är valt.

- **Felmeddelande** - Med det här alternativet kan du ange ett meddelande som visas om kryssrutan **Obligatorisk** är markerad och fältet lämnas tomt.

- **Skriptvalideringsmeddelande** - Med det här alternativet kan du ange ett meddelande som ska visas om skriptvalideringen misslyckas.

- **Maximalt antal tecken** - Med det här alternativet kan du ange maximalt antal tecken som tillåts i komponenten. Om du anger tecken som är större än det värde som har angetts i **Maximalt antal tecken** visas ett felmeddelande på skärmen. I dialogrutan **Felmeddelande** med maximalt antal tecken kan du lägga till ett anpassat felmeddelande.

- **Felmeddelande med maximalt antal tecken** - I dialogrutan **Felmeddelande med maximalt antal tecken** kan du lägga till ett anpassat felmeddelande om du anger tecken som är större än det värde som har angetts i alternativet **Maximalt antal tecken** .

- **Minsta antal tecken** - Med det här alternativet kan du ange det minsta antalet tecken som tillåts i fältet. Om du anger tecken som är mindre än värdet som anges i **Minsta antal tecken** visas ett felmeddelande på skärmen. I dialogrutan **Felmeddelande för minsta antal tecken** kan du lägga till ett anpassat felmeddelande.

- **Felmeddelande för minsta antal tecken** - I dialogrutan **Felmeddelande för minsta antal tecken** kan du lägga till ett anpassat felmeddelande om du anger tecken som är mindre än det värde som har angetts i alternativet **Minsta antal tecken** .

Med alternativet **Valideringsmönster** kan du ange ett mönster som validerar den angivna texten. Om texten inte kan valideras med det värde som anges i alternativet **Mönster** visas felmeddelandet på skärmen.

- **Mönster** - Med det här alternativet kan du ange tillåtna verifieringsmönster för text. Reguljära uttryck tillåts också.

- **Felmeddelande** - Med det här alternativet kan du ange ett meddelande som visas på skärmen om den angivna texten inte kan valideras med det värde som anges i alternativet **Mönster**

### Fliken Hjälpinnehåll {#help-content-tab}

![Fliken Hjälpinnehåll](/help/adaptive-forms/assets/password-help.png)

- **Kort beskrivning** - En kort beskrivning är en kort textförklaring som ger ytterligare information eller förtydliganden om syftet med ett visst formulärfält. Det hjälper användaren att förstå vilken typ av data som ska anges i fältet och kan ge riktlinjer eller exempel som hjälper till att säkerställa att den angivna informationen är giltig och uppfyller de önskade kriterierna. Som standard är korta beskrivningar dolda. Aktivera alternativet **Visa alltid kort beskrivning** för att visa det under komponenten.

- **Visa alltid kort beskrivning** - Aktivera alternativet att visa den korta beskrivningen under komponenten.

- **Hjälptext** - Hjälptexten hänvisar till ytterligare information eller vägledning som användaren får för att hjälpa dem att fylla i ett formulärfält korrekt. Det visas när användaren klickar på hjälpikonen (i) som finns bredvid komponenten. Hjälptexten ger mer detaljerad information än etiketten eller platshållartexten för ett formulärfält och är utformad för att hjälpa användaren förstå fältets krav eller begränsningar. Den kan också ge förslag eller exempel som gör det enklare och exaktare att fylla i formuläret.

### Fliken Tillgänglighet {#accessibility-tab}

![Fliken Tillgänglighet](/help/adaptive-forms/assets/password-accessibilty.png)

- **Text för skärmläsare** - Text för skärmläsare hänvisar till ytterligare text som är särskilt avsedd att läsas av hjälpmedelstekniker, som skärmläsare, som används av personer med nedsatt syn. Den här texten innehåller en ljudbeskrivning av formulärfältets syfte och kan innehålla information om fältets titel, beskrivning, namn och relevanta meddelanden (anpassad text). Skärmläsartexten ser till att formuläret är tillgängligt för alla användare, även användare med nedsatt syn, och ger dem en fullständig förståelse för formulärfältet och dess krav.
   - **Egen text**: Välj det här alternativet om du vill använda den anpassade texten för ARIA-hjälpmedelsetiketter. Om du väljer det här alternativet visas dialogrutan Egen text. Du kan lägga till relevant information i dialogrutan Egen text.
   - **Beskrivning**: Välj det här alternativet om du vill använda beskrivningen för ARIA-hjälpmedelsetiketter.
   - **Titel**: Välj det här alternativet om du vill använda titeln för ARIA-hjälpmedelsetiketter.
   - **Namn**: Välj det här alternativet om du vill använda namnet på ARIA-hjälpmedelsetiketter.
   - **Inget**: Välj det här alternativet om du inte vill lägga till för hjälpmedelsetiketter för ARIA.

## Designdialogruta {#design-dialog}

Designdialogrutan används för att definiera och hantera CSS-format för textrutekomponenten.

### Fliken Format {#styles-tab}

Fliken används för att definiera och hantera CSS-format för en komponent. Core-komponenten för textrutan Adaptiv Forms har stöd för AEM [Style System](/help/get-started/authoring.md#component-styling).

![Fliken Format](/help/adaptive-forms/assets/datepicker_styletab.png)

- **Standardklasser för CSS**: Du kan ange en standardklass för CSS för kärnkomponenten för den adaptiva Forms-textrutan.

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

* [Create a standalone Adaptive Form](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)

-->

## Relaterade artiklar {#related-articles}

{{more-like-this}}

## Se även {#see-also}

{{see-also}}
