---
title: Adaptiv Forms Core-komponent - datumväljare
description: Använda eller anpassa Core-komponenten för den adaptiva Forms Date-väljaren.
role: Architect, Developer, Admin, User
exl-id: aa9402de-ca57-4c19-8d36-2dd0a78d6806
source-git-commit: 6725784bd4c94d433c91d6bd65d14d03cbefd954
workflow-type: tm+mt
source-wordcount: '2298'
ht-degree: 0%

---


# Datumväljarkomponent{#date-picker-adaptive-forms-core-component}

En datumväljarkomponent i ett adaptivt formulär är ett element i användargränssnittet som gör att användare kan välja ett datum i en kalender eller ange ett datum manuellt i ett visst format. Datumväljarkomponenten kan konfigureras så att den har olika formaterings-, validerings- och standardvärden.

{{traditional-aem}}

**Exempel**

![exempel](/help/adaptive-forms/assets/date-picker.png)

## Användning {#reasons-to-use-drop-date-picker}

Det finns många skäl till att det är bra att ta med en datumväljare i en anpassad form, bland annat:

- **Bekvämlighet**: Med en datumväljarkomponent kan användare enkelt välja ett datum från en kalender utan att behöva ange datumet manuellt i ett textfält. Detta kan spara tid och minska antalet fel.

- **Användarupplevelse**: Datumväljarkomponenten kan användas för att göra formuläret mer användarvänligt genom att tillhandahålla ett tydligt och intuitivt sätt för användarna att välja datum.

- **Dataanalys**: Datumväljarkomponenten kan användas för att samla in data från olika källor och analysera den, eller använda den som indata för vidare bearbetning.

- **Händelsehantering**: Datumväljarkomponenten kan användas på webbplatser för händelsehantering för att välja händelsedatumet.

- **Bokning och reservation**: Datumväljarkomponenten kan användas på webbplatser för bokning och bokning för att välja datum för in- och utcheckning.

- **Datumformat**: Datumväljarkomponenten kan användas för att korrigera det format i vilket datumet visas och anges. Se till att datumformatet är enhetligt i hela formuläret för att säkerställa en konsekvent användarupplevelse.

## Version och kompatibilitet {#version-and-compatibility}

Core Component (kärnkomponent) för den adaptiva Forms-datumväljaren släpptes i februari 2023 som en del av Core Components 2.0.4 för Cloud Service och Core Components 1.1.12 för AEM 6.5.16.0 Forms eller senare. Här är en tabell som visar alla versioner som stöds, kompatibiliteten med AEM och länkar till motsvarande dokumentation:

| Komponentversion | AEM as a Cloud Service | AEM 6.5.16.0 Forms eller senare |
|---|---|---|
| v1 | Kompatibel med <br>[version 2.0.4](/help/adaptive-forms/version.md) och senare | Kompatibel med <br>[version 1.1.12](/help/adaptive-forms/version.md) och senare, men mindre än 2.0.0. |

Information om versioner och versioner av kärnkomponenter finns i dokumentet [Core Components Versions](/help/adaptive-forms/version.md) .

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Teknisk information {#technical-details}

Hämta den senaste informationen om Core-komponenten för datumväljaren för adaptiv Forms i den tekniska dokumentationen för [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/datepicker/v1/datepicker). Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Med dialogrutan Konfigurera kan du enkelt anpassa din datumväljarupplevelse för besökare. Du kan också enkelt definiera datumväljaralternativ för en smidig användarupplevelse.

### Fliken Grundläggande {#basic-tab}

![Fliken Grundläggande](/help/adaptive-forms/assets/datepicker_basictab.png)

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
- **Standarddatum** - Med det här alternativet kan du lägga till ett datum i formulärfältet. Det angivna datumet visas som standard i stället för komponenten. Om inget datum anges av användaren skickas det här värdet när formuläret skickas. Om **Inaktiverad komponent** eller **skrivskyddad komponent** väljs visas standarddatumet på skärmen och skickas när formuläret skickas.


### Fliken Validering {#validation-tab}

![Fliken Validering](/help/adaptive-forms/assets/datepicker_validation.png)

- **Obligatoriskt** - Välj det här alternativet om du vill visa komponenten i ett adaptivt formulär. När du har valt alternativet måste du göra ett val innan du kan fortsätta med en formuläröverföring. Du kan inte välja **Dölj komponent** eller **Inaktivera komponent** på fliken **Grundläggande** när det här alternativet är valt.

- **Felmeddelande** - Med det här alternativet kan du ange ett meddelande som visas om kryssrutan **Obligatorisk** är markerad och formulärfältet lämnas tomt.

- **Skriptvalideringsmeddelande** - Med det här alternativet kan du ange ett meddelande som ska visas om skriptvalideringen misslyckas.

- **Minimidatum** - Med det här alternativet kan du ange det minsta obligatoriska datumet. Om du anger ett datum som är tidigare än det som anges i Minimidatum visas ett felmeddelande på skärmen. I dialogrutan **Minimalt felmeddelande** kan du lägga till ett eget felmeddelande.

- **Minimalt felmeddelande** - I dialogrutan **Minimalt felmeddelande** kan du lägga till ett anpassat felmeddelande som ska visas om du anger ett datum som infaller före det datum som anges i alternativet **Minimidatum**.
- **Undanta minimidatum** - Det här alternativet tillåter att minimidatum utelämnas i ett visst intervall eller en viss datumuppsättning.

- **Maximalt datum** - Med det här alternativet kan du ange maximalt obligatoriskt datum. Om du anger ett datum som är senare än det som anges i Maximalt datum visas ett felmeddelande på skärmen. I dialogrutan **Maximalt felmeddelande** kan du lägga till ett anpassat felmeddelande.

- **Maximalt felmeddelande** - I dialogrutan **Maximalt felmeddelande** kan du lägga till ett anpassat felmeddelande som ska visas om du anger ett datum som infaller senare än det datum som anges i alternativet **Maximalt datum**.

- **Uteslut maximalt datum** - Med det här alternativet kan du utelämna maximalt datum i ett visst intervall eller en viss datumuppsättning.

### Fliken Hjälpinnehåll {#help-content-tab}

![Fliken Hjälpinnehåll](/help/adaptive-forms/assets/datepicker_helptab.png)

- **Kort beskrivning** - En kort beskrivning är en kort textförklaring som ger ytterligare information eller förtydliganden om syftet med ett visst formulärfält. Det hjälper användaren att förstå vilken typ av data som ska anges i fältet och kan ge riktlinjer eller exempel som hjälper till att säkerställa att den angivna informationen är giltig och uppfyller de önskade kriterierna. Som standard är korta beskrivningar dolda. Aktivera alternativet **Visa alltid kort beskrivning** för att visa det under komponenten.

- **Visa alltid kort beskrivning** - Aktivera alternativet att visa den korta beskrivningen under komponenten.

- **Hjälptext** - Hjälptexten hänvisar till ytterligare information eller vägledning som användaren får för att hjälpa dem att fylla i ett formulärfält korrekt. Det visas när användaren klickar på hjälpikonen (i) som finns bredvid komponenten. Hjälptexten ger mer detaljerad information än etiketten eller platshållartexten för ett formulärfält och är utformad för att hjälpa användaren förstå fältets krav eller begränsningar. Den kan också ge förslag eller exempel som gör det enklare och exaktare att fylla i formuläret.


### Fliken Tillgänglighet {#accessibility-tab}

![Fliken Tillgänglighet](/help/adaptive-forms/assets/datepicker_accessibilitytab.png)

- **Text för skärmläsare** - Text för skärmläsare hänvisar till ytterligare text som är särskilt avsedd att läsas av hjälpmedelstekniker, som skärmläsare, som används av personer med nedsatt syn. Den här texten innehåller en ljudbeskrivning av formulärfältets syfte och kan innehålla information om fältets titel, beskrivning, namn och relevanta meddelanden (anpassad text). Skärmläsartexten ser till att formuläret är tillgängligt för alla användare, även användare med nedsatt syn, och ger dem en fullständig förståelse för formulärfältet och dess krav.
   - **Egen text**: Välj det här alternativet om du vill använda den anpassade texten för ARIA-hjälpmedelsetiketter. Om du väljer det här alternativet visas dialogrutan Egen text. Du kan lägga till relevant information i dialogrutan Egen text.
   - **Beskrivning**: Välj det här alternativet om du vill använda beskrivningen för ARIA-hjälpmedelsetiketter.
   - **Titel**: Välj det här alternativet om du vill använda titeln för ARIA-hjälpmedelsetiketter.
   - **Namn**: Välj det här alternativet om du vill använda namnet på ARIA-hjälpmedelsetiketter.
   - **Inget**: Välj det här alternativet om du inte vill lägga till för hjälpmedelsetiketter för ARIA.

### Fliken Format {#format-tab}

![Fliken Format](/help/adaptive-forms/assets/datepicker_formattab.png)

- **Visningsformat** - Det representerar det datumformat som visas för användaren. Med alternativet **Typ** kan användaren välja datumformat. Du kan också anpassa datumformatet med alternativet **Egen** i listrutan **Typ** .

- **Redigera format** - Det representerar ett datumformat där användaren kan redigera datumet. Med alternativet **Typ** kan användaren välja datumformat. Du kan också anpassa datumformatet med alternativet **Egen** i listrutan **Typ** .
- **Formatfelmeddelande** - Med det här alternativet kan du ange meddelandet som visas på skärmen när det angivna datumet inte har rätt format.
- **Språk** - Den här funktionen används för att formatera det specifika fältet. När en användare väljer ett språkalternativ i listrutan **Typ** visas alternativet **IETF BCP 47-språktagg** på panelen. Du kan välja språk för fältformatering när du översätter ett adaptivt formulär till ett visst språk.

Språkuppsättningen är inte synlig som standard, men användare kan ange en anpassad **IETF BCP 47-språktagg** genom att uppdatera mallprincipen:

1. Öppna motsvarande mall som är kopplad till ett adaptivt formulär i mallredigeraren.
2. Välj den befintliga profilen som `datepicker-default-policy` på den nedrullningsbara menyn.

   ![Mallprincip för datumväljare](/help/adaptive-forms/assets/date-picker-template-policy.png)

3. Klicka på **Klar**.

   >[!NOTE]
   >
   > [Klicka här](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/supporting-new-language-localization-core-components) om du vill ha mer information om hur du översätter ett anpassat formulär till en viss språkinställning.

## Designdialogruta {#design-dialog}

Designdialogrutan används för att definiera och hantera CSS-format för komponenten Date-Picker.

### Fliken Format {#styles-tab}

Fliken används för att definiera och hantera CSS-format för en komponent. Core-komponenten för datumväljaren i den adaptiva Forms stöder AEM [Style System](/help/get-started/authoring.md#component-styling).

![Fliken Format](/help/adaptive-forms/assets/datepicker_styletab.png)

- **Standard-CSS-klasser**: Du kan ange en standard-CSS-klass för den adaptiva Forms Date-picker-kärnkomponenten.

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

![Formateringsflik](/help/adaptive-forms/assets/datepicker_formatpolicy.png)

<!--

## Related article {#related-article}

* [Create a standalone Adaptive Form](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html?lang=sv-SE)

-->

## Relaterade artiklar {#related-articles}

{{more-like-this}}

## Se även {#see-also}

{{see-also}}


