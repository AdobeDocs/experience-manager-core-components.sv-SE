---
title: Adaptiv Forms Core-komponent - klok signatur
description: Använda eller anpassa den adaptiva Forms Scribble Signature Core-komponenten.
role: Architect, Developer, Admin, User
source-git-commit: 246a608e4c23a9075813a64691d583584164578c
workflow-type: tm+mt
source-wordcount: '1761'
ht-degree: 0%

---


# Skriptsignaturkomponent

<span>Komponenten Scribble Signature finns under Tidigt Adobe-program. Du kan skriva till `aem-forms-ea@adobe.com` från ditt officiella e-post-id för att gå med i det tidiga adopterprogrammet och begära åtkomst till funktionen.</span>

En komponent för klottersignatur i ett adaptivt formulär är ett element i användargränssnittet som gör att användare kan rita sin **signatur** direkt i formuläret med hjälp av en mus, penna eller pekskärm. Det säkerställer korrekt inhämtning av handskrivet samtycke, godkännanden och verifiering i digitala arbetsflöden.

**Exempel**

![exempel](/help/adaptive-forms/assets/scribble-signature.png){width=50%,align-center}

**Olika alternativ finns i signaturfönstret**

- **A:** Klicka på ikonen **Rita** för att rita din signatur på arbetsytan.
- **B:** Klicka på ikonen **Rensa** för att rensa signaturen på arbetsytan.
- **C:** Klicka på ikonen **Geolocation** för att lägga till geopositionering tillsammans med signaturen.
- **D:** Klicka på ikonen **Tangentbord** för att skriva ditt namn på arbetsytan.

När du har markerat ikonen **Spara** i fönstret Klottsignatur kan du inte redigera signaturen. Om du vill redigera signaturen måste du bortse från den aktuella signaturen och signera igen med alternativet Målningspensel/Tangentbord ovan.

>[!NOTE]
>
> Signaturer sparas alltid i PNG-format.

## Användning {#reasons-to-use-scribble-signature}

Det finns flera orsaker till varför det är bra att inkludera ett fält för skriptsignatur i ett formulär, bland annat:

- **Digitalt samtycke**: Tillåter användare att tillhandahålla juridiskt giltiga signaturer elektroniskt.
- **Förbättrad användarupplevelse**: Tillhandahåller ett naturligt sätt att signera direkt på enheter utan skanning eller överföring.
- **Papperslösa arbetsflöden**: Eliminerar behovet av att skriva ut, signera och skanna om dokument.
- **Autentisering**: Fungerar som ett ytterligare lager av bekräftelse och godkännande.
- **Datakvalitet**: Säkerställer korrekt inhämtning av signerarens handskrivna indata i digitalt format.

## Version och kompatibilitet {#version-and-compatibility}

Kärnkomponenten för adaptiv Forms Scribble-signatur släpptes **augusti 2025** som en del av **Core Components 2.24.6** för Cloud Service och senare.

| Komponentversion | AEM as a Cloud Service | AEM 6.5.16.0 Forms eller senare |
|---|---|---|
| v1 | Kompatibel med <br>[version 2.24.6](/help/adaptive-forms/version.md) och senare | |

Mer information om versioner finns i [Huvudkomponentversioner](/help/adaptive-forms/version.md).

## Teknisk information {#technical-details}

Hämta den senaste tekniska informationen om den adaptiva Forms Scribble Signature Core-komponenten på [GitHub](https://github.com/adobe/aem-core-forms-components). Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för grundkomponentsutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan du anpassa komponenten Skriptsignatur.

### Fliken Grundläggande {#basic-tab}

![Fliken Grundläggande](/help/adaptive-forms/assets/scribble-signature-basictab.png)

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

- **Titel för signaturdialogruta**: I signaturdialogrutans titel definieras den text som visas högst upp i dialogrutan för signaturhämtning. Det fungerar som en uppmaning eller instruktion för användaren när de måste ange en signatur. Texten hjälper användaren genom signeringsprocessen och gör interaktionen tydlig och intuitiv.

### Fliken Validering

![valideringsflik](/help/adaptive-forms/assets/scribble-signature-validation.png)

- **Obligatoriskt** - Välj det här alternativet om du vill visa komponenten i ett adaptivt formulär. När du har valt alternativet måste du göra ett val innan du kan fortsätta med en formuläröverföring. Du kan inte välja **Dölj komponent** eller **Inaktivera komponent** på fliken **Grundläggande** när det här alternativet är valt.

- **Felmeddelande** - Med det här alternativet kan du ange ett meddelande som visas om kryssrutan **Obligatorisk** är markerad och formulärfältet lämnas tomt.

- **Skriptvalideringsmeddelande** - Med det här alternativet kan du ange ett meddelande som ska visas om skriptvalideringen misslyckas.

### Fliken Hjälpinnehåll {#help-content-tab}

![Fliken Hjälpinnehåll](/help/adaptive-forms/assets/scribble-signature-helptab.png)

- **Kort beskrivning** - En kort beskrivning är en kort textförklaring som ger ytterligare information eller förtydliganden om syftet med ett visst formulärfält. Det hjälper användaren att förstå vilken typ av data som ska anges i fältet och kan ge riktlinjer eller exempel som hjälper till att säkerställa att den angivna informationen är giltig och uppfyller de önskade kriterierna. Som standard är korta beskrivningar dolda. Aktivera alternativet **Visa alltid kort beskrivning** för att visa det under komponenten.

- **Visa alltid kort beskrivning** - Aktivera alternativet att visa den korta beskrivningen under komponenten.

- **Hjälptext** - Hjälptexten hänvisar till ytterligare information eller vägledning som användaren får för att hjälpa dem att fylla i ett formulärfält korrekt. Det visas när användaren klickar på hjälpikonen (i) som finns bredvid komponenten. Hjälptexten ger mer detaljerad information än etiketten eller platshållartexten för ett formulärfält och är utformad för att hjälpa användaren förstå fältets krav eller begränsningar. Den kan också ge förslag eller exempel som gör det enklare och exaktare att fylla i formuläret.

### Fliken Tillgänglighet {#accessibility-tab}

![Fliken Tillgänglighet](/help/adaptive-forms/assets/scribble-signature-accessibilitytab.png)

- **Text för skärmläsare** - Text för skärmläsare hänvisar till ytterligare text som är särskilt avsedd att läsas av hjälpmedelstekniker, som skärmläsare, som används av personer med nedsatt syn. Den här texten innehåller en ljudbeskrivning av formulärfältets syfte och kan innehålla information om fältets titel, beskrivning, namn och relevanta meddelanden (anpassad text). Skärmläsartexten ser till att formuläret är tillgängligt för alla användare, även användare med nedsatt syn, och ger dem en fullständig förståelse för formulärfältet och dess krav.
   - **Egen text**: Välj det här alternativet om du vill använda den anpassade texten för ARIA-hjälpmedelsetiketter. Om du väljer det här alternativet visas dialogrutan Egen text. Du kan lägga till relevant information i dialogrutan Egen text.
   - **Beskrivning**: Välj det här alternativet om du vill använda beskrivningen för ARIA-hjälpmedelsetiketter.
   - **Titel**: Välj det här alternativet om du vill använda titeln för ARIA-hjälpmedelsetiketter.
   - **Namn**: Välj det här alternativet om du vill använda namnet på ARIA-hjälpmedelsetiketter.
   - **Inget**: Välj det här alternativet om du inte vill lägga till för hjälpmedelsetiketter för ARIA.

## Designdialogruta {#design-dialog}

Designdialogrutan används för att definiera och hantera CSS-format för komponenten Klottsignatur.

### Fliken Format {#styles-tab}

Fliken används för att definiera och hantera CSS-format för en komponent. Kärnkomponenten för adaptiv Forms Scribble-signatur stöder AEM [Style System](/help/get-started/authoring.md#component-styling).

![Designdialogrutan](/help/adaptive-forms/assets/checkbox-style.png)

- **Standardklasser för CSS**: Du kan ange en standardklass för CSS för den adaptiva kärnkomponenten för Forms Scribble Signature.

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
