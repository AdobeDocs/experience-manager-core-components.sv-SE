---
title: Adaptiv Forms Core-komponent - villkor
description: Använda eller anpassa den adaptiva kärnkomponenten i Forms Terms and Conditions.
role: Architect, Developer, Admin, User
exl-id: c607d554-ad2d-4434-856d-91e174ef3149
source-git-commit: 6725784bd4c94d433c91d6bd65d14d03cbefd954
workflow-type: tm+mt
source-wordcount: '3253'
ht-degree: 0%

---


# Villkor - komponent

En **Terms and Conditions** -komponent refererar till ett avsnitt i ett formulär som anger de villkor som användare måste godkänna eller uppfylla när de använder en tjänst eller använder innehåll.

Komponenten **Villkor** är en sammansatt komponent som består av komponenterna Text, Checkbox och Link. Textkomponenten innehåller en titel tillsammans med en kort översikt över syftet med och omfattningen av villkoren. Den innehåller även en kryssruta som används för att få användarens uttryckliga medgivande. Du kan också ersätta en medgivandetext med länkar.

>[!NOTE]
>
> För AEM 6.5 Forms introducerades den här komponenten med AEM 6.5 Forms Service Pack 19 (6.5.19.0). Om du vill aktivera den här komponenten kontrollerar du att de nödvändiga versionerna av både Forms Core Components och WCM Core Components är installerade. Mer information om de olika versionerna av adaptiva Forms Core-komponenter finns i [Adaptiva Forms Core-komponentreleaser](/help/adaptive-forms/version.md)

{{traditional-aem}}

**Exempel**

![Villkor](/help/adaptive-forms/assets/terms-and-conditions.png)

Mer information om olika komponenter i villkorskomponenten finns i avsnittet [Underkomponenter i villkorskomponenten](#sub-component).

## Användning {#reasons-to-use-termsandconditions}

- **Användaravtal**: Komponenten fungerar som ett avtal mellan tjänsteleverantören och användaren. Användarna måste bekräfta och godkänna villkoren innan de kan komma åt tjänsten eller innehållet.

- **Juridisk efterlevnad**: Den säkerställer regelefterlevnad och skydd för tjänsteleverantören genom att ange båda parters rättigheter, ansvar och ansvar.

- **Registreringsprocesser**: Registrerings- eller registreringsformulären innehåller komponenten **Villkor** som kräver att användarna uttryckligen godkänner villkoren innan de skapar ett konto eller använder en tjänst.

- **E-handelstransaktioner**: Onlinewebbplatser innehåller komponenten **Villkor** så att användare uppmanas att godkänna villkoren som en del av utcheckningsprocessen innan de gör köp online.

- **Säkerhets- och sekretessavtal**: Komponenten **Villkor** innehåller information om hur användardata samlas in, lagras och används, som ofta kompletteras av en separat sekretesspolicy

## Version och kompatibilitet {#version-and-compatibility}

Kärnkomponenten för villkor för adaptiva Forms lanserades i februari 2023 som en del av kärnkomponenterna 2.0.62 för Cloud Service och Core Components 1.1.28 för AEM 6.5.16.0 Forms eller senare. Här är en tabell som visar alla versioner som stöds, kompatibiliteten med AEM och länkar till motsvarande dokumentation:

| Komponentversion | AEM as a Cloud Service | AEM 6.5.16.0 Forms eller senare |
|---|---|---|
| v1 | Kompatibel med <br>[version 2.0.62](/help/adaptive-forms/version.md) och senare | Kompatibel med <br>[version 1.1.28](/help/adaptive-forms/version.md) och senare, men mindre än 2.0.0. |

Information om versioner och versioner av kärnkomponenter finns i dokumentet [Core Components Versions](/help/adaptive-forms/version.md) .

## Teknisk information {#technical-details}

Hämta den senaste informationen om kärnkomponenten för villkor för adaptiva Forms i den tekniska dokumentationen för [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/checkboxgroup/v1/checkboxgroup). Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Med dialogrutan Konfigurera kan du enkelt anpassa dina villkor och komponentupplevelser för besökare. Du kan också enkelt definiera villkor för en smidig användarupplevelse.

### Fliken Grundläggande

![Fliken Grundläggande](/help/adaptive-forms/assets/terms-and-conditions-basic-tab.png)

- **Namn** - Namnet identifierar komponenten i regelredigeraren unikt. Specialtecken och mellanslag är inte tillåtna i namnsträngarna.

- **Titel** - Med titeln kan du enkelt identifiera en komponent i ett formulär. Som standard visas titeln ovanpå komponenten. Om du inte lägger till en titel visas komponentens namn i stället för rubriktexten.
- **Tillåt RTF-text för rubrik** - Med den här funktionen kan användare formatera oformaterad text med funktioner som fet, kursiv, understruken text, olika teckensnitt, teckenstorlekar, färger och ytterligare alternativ för att förbättra visuell presentation och anpassning. Det ger större flexibilitet och kreativ kontroll när det gäller att få titlar att sticka ut i dokument, på webbplatser och i tillämpningar.\
  När du markerar kryssrutan för **Tillåt RTF-text för titel** visas formateringsalternativ som formaterar komponentens titel. Om du vill visa alla tillgängliga formateringsalternativ klickar du på fliken ![Helskärmsikon](/help/adaptive-forms/assets/fullscreen-icon.png) .

  ![RTF-stöd](/help/adaptive-forms/assets/richtext-support-title.png)

- **Visa alternativ för godkännande** - Markera alternativet för att visa kryssrutan för godkännande som används för att få explicit samtycke från användaren.

- **Visa som ett popup-fönster** - Välj alternativet för att visa villkorskomponenten i ett popup-fönster.

- **Ersätt medgivande-text med webblänkar**: Välj alternativet att ersätta en medgivande-text med en webblänk.  Om alternativet inte är markerat visas den medföljande texten som standard.

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

- **Bindningsreferens** - En bindningsreferens är en referens till ett dataelement som lagras i en extern datakälla och används i ett formulär. Med den binda referensen kan du binda data dynamiskt till formulärfält så att formuläret kan visa de senaste data från datakällan. En bindningsreferens kan till exempel användas för att visa en kunds namn och adress i ett formulär baserat på kundens ID som anges i formuläret. Bindningsreferensen kan också användas för att uppdatera datakällan med data som anges i formuläret. På så sätt kan AEM Forms skapa formulär som interagerar med externa datakällor, vilket ger en smidig användarupplevelse för att samla in och hantera data.

- **Dölj komponent** - Välj alternativet att dölja komponenten från formuläret. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren. Detta är användbart när du behöver lagra information som inte behöver visas eller ändras direkt av användaren.
- **Inaktivera komponent** - Välj alternativet att inaktivera komponenten. Den inaktiverade komponenten är inte aktiv eller redigerbar av slutanvändaren. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.
- **Skrivskyddad** - Välj alternativet för att göra komponenten icke-redigerbar. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.

### Fliken Hjälpinnehåll {#help-content-tab}

![Fliken Hjälpinnehåll](/help/adaptive-forms/assets/terms-and-conditions-help-tab.png)

- **Kort beskrivning** - En kort beskrivning är en kort textförklaring som ger ytterligare information eller förtydliganden om syftet med ett visst formulärfält. Det hjälper användaren att förstå vilken typ av data som ska anges i fältet och kan ge riktlinjer eller exempel som hjälper till att säkerställa att den angivna informationen är giltig och uppfyller de önskade kriterierna. Som standard är korta beskrivningar dolda. Aktivera alternativet **Visa alltid kort beskrivning** för att visa det under komponenten.

- **Visa alltid kort beskrivning** - Aktivera alternativet att visa den korta beskrivningen under komponenten.

- **Hjälptext** - Hjälptexten hänvisar till ytterligare information eller vägledning som användaren får för att hjälpa dem att fylla i ett formulärfält korrekt. Det visas när användaren klickar på hjälpikonen (i) som finns bredvid komponenten. Hjälptexten ger mer detaljerad information än etiketten eller platshållartexten för ett formulärfält och är utformad för att hjälpa användaren förstå fältets krav eller begränsningar. Den kan också ge förslag eller exempel som gör det enklare och exaktare att fylla i formuläret.

### Fliken Tillgänglighet

![Fliken Tillgänglighet](/help/adaptive-forms/assets/terms-and-conditions-accessibility-tab.png)

- **Text för skärmläsare** - Text för skärmläsare hänvisar till ytterligare text som är särskilt avsedd att läsas av hjälpmedelstekniker, som skärmläsare, som används av personer med nedsatt syn. Den här texten innehåller en ljudbeskrivning av formulärfältets syfte och kan innehålla information om fältets titel, beskrivning, namn och relevanta meddelanden (anpassad text). Skärmläsartexten ser till att formuläret är tillgängligt för alla användare, även användare med nedsatt syn, och ger dem en fullständig förståelse för formulärfältet och dess krav.
   - **Egen text**: Välj det här alternativet om du vill använda den anpassade texten för ARIA-hjälpmedelsetiketter. Om du väljer det här alternativet visas dialogrutan Egen text. Du kan lägga till relevant information i dialogrutan Egen text.
   - **Beskrivning**: Välj det här alternativet om du vill använda beskrivningen för ARIA-hjälpmedelsetiketter.
   - **Titel**: Välj det här alternativet om du vill använda titeln för ARIA-hjälpmedelsetiketter.
   - **Namn**: Välj det här alternativet om du vill använda namnet på ARIA-hjälpmedelsetiketter.
   - **Inget**: Välj det här alternativet om du inte vill lägga till för hjälpmedelsetiketter för ARIA.
- **HTML-roll för skärmläsare som ska tillkännages** - HTML-rollen är ett attribut som används för att ange syftet med ett HTML-element för hjälpmedelstekniker som skärmläsare. Rollattributet används för att ge ytterligare kontext och semantisk innebörd till ett element, vilket gör det enklare för skärmläsare att tolka och meddela innehållet till användaren. I AEM Forms kan till exempel etiketten för ett formulärfält ha rollen&quot;label&quot;, och inmatningsfältet kan ha rollen&quot;texbox&quot;. Detta gör att skärmläsaren förstår förhållandet mellan etiketten och inmatningsfältet och kan meddela användaren dem på rätt sätt.

## Designdialogruta {#design-dialog}

Designdialogrutan används för att definiera och hantera CSS-format för villkorskomponenten.


### Fliken Format {#styles-tab}

Fliken används för att definiera och hantera CSS-format för en komponent. Kärnkomponenten för villkor för adaptiva Forms stöder AEM [Style System](/help/get-started/authoring.md#component-styling).

![Designdialogrutan](/help/adaptive-forms/assets/checkbox-style.png)

- **Standardklasser för CSS**: Du kan ange en standardklass för CSS för kärnkomponenten Adaptive Forms Terms and Conditions.

- **Tillåtna format**: Du kan definiera format genom att ange ett namn och den CSS-klass som representerar formatet. Du kan till exempel skapa ett format med namnet&quot;bold text&quot; och ge CSS-klassen&quot;font-weight: bold&quot;. Du kan använda eller tillämpa dessa format på ett adaptivt formulär i en anpassad Forms-redigerare. Om du vill använda ett format väljer du den komponent du vill använda formatet på i Adaptiv Forms-redigerare, navigerar till egenskapsdialogrutan och väljer önskat format i listrutan **Format**. Om du behöver uppdatera eller ändra formaten går du tillbaka till designdialogrutan, uppdaterar formaten på formatfliken och sparar ändringarna.

### Anpassade egenskaper

![Dialogrutan Anpassade egenskaper](/help/adaptive-forms/assets/checkbox-customproperties.png)

Med anpassade egenskaper kan du koppla anpassade attribut (nyckelvärdepar) till en anpassad formulärets kärnkomponent med hjälp av formulärmallen. De anpassade egenskaperna återspeglas i egenskapsavsnittet i den headless-renderingen av komponenten. Det gör att du kan skapa dynamiskt formulärbeteende som anpassas baserat på anpassade attributvärden. Utvecklare kan till exempel utforma olika renderingar av en Headless Forms-komponent för mobiler, datorer eller webbplattformar, vilket avsevärt förbättrar användarupplevelsen på en mängd olika enheter.

- **Gruppnamn**: Du kan ange ett namn som identifierar den anpassade egenskapsgruppen. Du kan lägga till, ta bort eller ordna om flera anpassade egenskapsgrupper. När du har lagt till den anpassade egenskapsgruppen kan du se följande alternativ:

   - **Nyckelvärdepar**: Du kan lägga till flera anpassade egenskapsnamn och anpassade egenskapsvärden genom att klicka på knappen **Lägg till** för varje anpassad egenskapsgrupp.

   - **Ta bort**: Tryck eller klicka för att ta bort det anpassade egenskapsnamnet och det anpassade egenskapsvärdet.

   - **Ordna om**: Tryck eller klicka och dra för att ändra ordningen på det anpassade egenskapsnamnet och det anpassade egenskapsvärdet.

## Delkomponenter i villkorskomponenten {#sub-component}

**Villkor** är en sammansatt komponent som omfattar följande underkomponenter:
- [Länkkomponent](#link)
- [Textkomponent](#text)
- [Kryssrutekomponent](#checkbox)

### Länkkomponent{#link}

Den här komponenten ersätter en medgivandetext med en webblänk eller länkar. Det används i ett scenario där användaren avser att erbjuda referenser till särskilda avsnitt, ytterligare information eller externa dokument. Du kan enkelt anpassa komponenten **Link** individuellt för besökare med dialogrutan Konfigurera.

#### Fliken Grundläggande

![Fliken Grundläggande](/help/adaptive-forms/assets/link-basic-tab.png)

- **Namn** - Namnet identifierar komponenten i regelredigeraren unikt. Specialtecken och mellanslag är inte tillåtna i namnsträngarna.

- **Titel** - Med titeln kan du enkelt identifiera en komponent i ett formulär. Som standard visas titeln ovanpå komponenten. Om du inte lägger till en titel visas komponentens namn i stället för rubriktexten.
- **Tillåt RTF-text för rubrik** - Med den här funktionen kan användare formatera titlar med alternativ som fet, kursiv, teckensnittsformat, färger och justering, vilket förbättrar visuell presentation och anpassning. Det ger större flexibilitet och kreativ kontroll när det gäller att få titlar att sticka ut i dokument, på webbplatser och i tillämpningar.\
  När du markerar kryssrutan för **Tillåt RTF-text för titel** visas formateringsalternativ som formaterar komponentens titel. Om du vill visa alla tillgängliga formateringsalternativ klickar du på fliken ![Helskärmsikon](/help/adaptive-forms/assets/fullscreen-icon.png) .

  ![RTF-stöd](/help/adaptive-forms/assets/richtext-support-title.png)

- **Dölj titel** - Välj alternativet för att dölja komponentens titel.

- **Länkar** - Ange länken och motsvarande visningstext som används i stället för den godkända texten. Du kan lägga till flera länkar genom att klicka på knappen **Lägg till** .
När ett nytt alternativ har lagts till kan följande åtgärder utföras:
   - **Länk** - Med det här alternativet kan du ange URL:en för omdirigering när ett alternativ har valts.
   - **Visa text** - Med det här alternativet kan du ange det innehåll som ska visas i ett anpassat formulär.
   - **Ta bort** - Tryck eller klicka för att ta bort alternativet för en alternativknapp.
   - **Ordna om** - Tryck eller klicka och dra för att ordna om alternativen.

  Du kan också formatera alternativen för kryssrutegruppen med **Tillåt RTF för alternativ**. När du har markerat kryssrutan för formateringsalternativen **Tillåt RTF för alternativ** visas för att formatera komponentens alternativ. Om du vill visa alla tillgängliga formateringsalternativ klickar du på fliken `Fullscreen` ![Helskärmsikon](/help/adaptive-forms/assets/fullscreen-icon.png) .

  ![RTF-stöd för alternativ](/help/adaptive-forms/assets/link-options.png)

- **Bindningsreferens** - En bindningsreferens är en referens till ett dataelement som lagras i en extern datakälla och används i ett formulär. Med den binda referensen kan du binda data dynamiskt till formulärfält så att formuläret kan visa de senaste data från datakällan. En bindningsreferens kan till exempel användas för att visa en kunds namn och adress i ett formulär baserat på kundens ID som anges i formuläret. Bindningsreferensen kan också användas för att uppdatera datakällan med data som anges i formuläret. På så sätt kan du med AEM Forms skapa formulär som interagerar med externa datakällor, vilket ger en smidig användarupplevelse för att samla in och hantera data.

- **Markera som obundet formulärelement**: Välj alternativet att konfigurera ett formulärfält som inte är länkat till något schema. Med det här alternativet kan du spara data utan att uppdatera datakällan. Det gör det också möjligt att hantera data på ett anpassat sätt, skilt från standarddatabasintegrering.
- **Dölj komponent** - Välj alternativet att dölja komponenten från formuläret. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren. Detta är användbart när du behöver lagra information som inte behöver visas eller ändras direkt av användaren.

- **Inaktivera komponent** - Välj alternativet att inaktivera eller låsa komponenten. Den inaktiverade komponenten är inte aktiv eller redigerbar av slutanvändaren. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.
- **Skrivskyddad** - Välj alternativet för att göra komponenten icke-redigerbar. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.

#### Fliken Validering

![Fliken Validering](/help/adaptive-forms/assets/link-validation-tab.png)

- **Obligatoriskt** - Välj det här alternativet om du vill visa komponenten i ett adaptivt formulär. När du har valt alternativet måste du göra ett val innan du kan fortsätta med en formuläröverföring. Du kan inte välja **Dölj komponent** eller **Inaktivera komponent** på fliken **Grundläggande** när det här alternativet är valt.

- **Felmeddelande** - Med det här alternativet kan du ange ett meddelande som visas om kryssrutan **Obligatorisk** är markerad och formulärfältet lämnas tomt.

- **Skriptvalideringsmeddelande** - Med det här alternativet kan du ange ett meddelande som ska visas om skriptvalideringen misslyckas.

### Fliken Hjälpinnehåll {#helpcontent-tab}

![Fliken Hjälpinnehåll](/help/adaptive-forms/assets/link-help-tab.png)

- **Kort beskrivning** - En kort beskrivning är en kort textförklaring som ger ytterligare information eller förtydliganden om syftet med ett visst formulärfält. Det hjälper användaren att förstå vilken typ av data som ska anges i fältet och kan ge riktlinjer eller exempel som hjälper till att säkerställa att den angivna informationen är giltig och uppfyller de önskade kriterierna. Som standard är korta beskrivningar dolda. Aktivera alternativet **Visa alltid kort beskrivning** för att visa det under komponenten.

- **Visa alltid kort beskrivning** - Aktivera alternativet att visa den korta beskrivningen under komponenten.

- **Hjälptext** - Hjälptexten hänvisar till ytterligare information eller vägledning som användaren får för att hjälpa dem att fylla i ett formulärfält korrekt. Det visas när användaren klickar på hjälpikonen (i) som finns bredvid komponenten. Hjälptexten ger mer detaljerad information än etiketten eller platshållartexten för ett formulärfält och är utformad för att hjälpa användaren förstå fältets krav eller begränsningar. Den kan också ge förslag eller exempel som gör det enklare och exaktare att fylla i formuläret.

### Fliken Tillgänglighet

![Fliken Tillgänglighet](/help/adaptive-forms/assets/link-accessibilty-tab.png)

- **Text för skärmläsare** - Text för skärmläsare hänvisar till ytterligare text som är särskilt avsedd att läsas av hjälpmedelstekniker, som skärmläsare, som används av personer med nedsatt syn. Den här texten innehåller en ljudbeskrivning av formulärfältets syfte och kan innehålla information om fältets titel, beskrivning, namn och relevanta meddelanden (anpassad text). Skärmläsartexten ser till att formuläret är tillgängligt för alla användare, även användare med nedsatt syn, och ger dem en fullständig förståelse för formulärfältet och dess krav.
   - **Egen text**: Välj det här alternativet om du vill använda den anpassade texten för ARIA-hjälpmedelsetiketter. Om du väljer det här alternativet visas dialogrutan Egen text. Du kan lägga till relevant information i dialogrutan Egen text.
   - **Beskrivning**: Välj det här alternativet om du vill använda beskrivningen för ARIA-hjälpmedelsetiketter.
   - **Titel**: Välj det här alternativet om du vill använda titeln för ARIA-hjälpmedelsetiketter.
   - **Namn**: Välj det här alternativet om du vill använda namnet på ARIA-hjälpmedelsetiketter.
   - **Inget**: Välj det här alternativet om du inte vill lägga till för hjälpmedelsetiketter för ARIA.

### Textkomponent {#text}

Komponenten **Text** visar textinnehållet som ger information till användarna. Den här komponenten innehåller de faktiska villkoren, det juridiska språket eller annan relevant textinformation.

Du kan enkelt anpassa [textkomponenten](/help/adaptive-forms/components/text.md) individuellt för besökare med dialogrutan Konfigurera. Använd dialogrutan [Konfigurera för textkomponenten](/help/adaptive-forms/components/text.md#configure-dialog) för att enkelt definiera textalternativ för en sömlös användarupplevelse.


### Kryssrutekomponent {#checkbox}

En kryssruta används för att få användarens samtycke eller godkännande. Det fungerar som en visuell indikator på att användaren har läst och godkänt villkoren som anges. Du måste markera kryssrutan för att ange användarens samtycke.

Du kan enkelt anpassa [kryssrutekomponenten](/help/adaptive-forms/components/checkbox.md) individuellt för besökare med dialogrutan Konfigurera. Om du vill definiera egenskaperna för kryssrutan för en sömlös användarupplevelse använder du dialogrutan [Konfigurera för kryssrutekomponenten](/help/adaptive-forms/components/checkbox.md#configure-dialog).


## Relaterade artiklar {#related-articles}

{{more-like-this}}

## Se även {#see-also}

{{see-also}}
