---
title: Adaptiv Forms Core-komponent - alternativknapp
description: Använda eller anpassa den adaptiva Forms Radio button Core Component.
role: Architect, Developer, Admin, User
exl-id: 86b5e9ec-58ac-4cd5-9c7c-4269247ec34f
source-git-commit: c3401da271efd930d1a2711bcab25c29f763f38e
workflow-type: tm+mt
source-wordcount: '2080'
ht-degree: 0%

---

# Alternativknappskomponent {#radio-button-adaptive-forms-core-component}

<span class="preview"> Den här artikeln innehåller innehåll om  **Tillåt RTF-text för rubrik**  och  **Tillåt RTF för alternativ**   funktioner, förhandsversioner. Förhandsversionen är bara tillgänglig via vår [kanal för förhandsversion](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/release-notes/prerelease.html#new-features).</span>

En alternativknapp i ett adaptivt formulär är en typ av indataelement som gör att en användare kan välja ett alternativ från en grupp med relaterade alternativ. Den representeras av en liten cirkulär knapp som antingen är fylld eller tom för att ange om alternativet är markerat eller inte. När en användare markerar en alternativknapp avmarkeras de andra i gruppen. Alternativknappar används vanligtvis när det finns flera alternativ som utesluter varandra och bara ett alternativ kan markeras åt gången.

**Exempel**

![exempel](/help/adaptive-forms/assets/radio-button.png)

**Dialogrutan Egenskaper**

![exempel](/help/adaptive-forms/assets/radio-button-properties.png)

I det här exemplet används elementet Alternativ för att gruppera alternativknapparna. The **Visa text** -elementet används för att ange en etikett för ett objekt och **Datavärde** används för att ange det värde som skickas till servern när formuläret skickas.

Varje alternativknappsalternativ har ett unikt datavärde och attributet Display Text. Om en användare väljer &quot;1-10&quot; skickas motsvarande datavärde till servern när formuläret skickas. Dessa data kan sedan bearbetas av ett skript på servern för att avgöra vilka alternativ som har valts av användaren och kan användas för olika åtgärder, som att uppdatera andra fält i formuläret eller skicka formulärdata till ett skript på servern för vidare bearbetning.

Dessutom kan varje alternativknapp konfigureras att ha olika bearbetningsvärden för varje alternativ, och detta kan ställas in med hjälp av den adaptiva Forms regelredigeraren

## Användning {#reasons-to-use-radio-button}

Det finns flera skäl att använda alternativknappar i ett formulär, bland annat:

- **Begränsade alternativ**: Alternativknappar används för att visa en lista med fördefinierade alternativ som användaren kan välja mellan, och endast ett alternativ kan väljas åt gången. Detta är användbart när antalet alternativ är begränsat och ömsesidigt uteslutande.

- **Rensa representation**: Alternativknappar är tydliga och lättbegripliga, vilket gör det enkelt för användarna att veta vad de väljer.

- **Konsekvens**: Användning av alternativknappar ger ett konsekvent och standardiserat sätt att presentera alternativ för användarna, vilket gör det enklare för dem att förstå och interagera med formuläret.

- **Lättanvänd**: Alternativknappar är enkla att använda, särskilt för användare som inte känner till teknik eller som har begränsad mobilitet.

## Version och kompatibilitet {#version-and-compatibility}

Den adaptiva Forms Accordion Core-komponenten släpptes i februari 2023 som en del av Core Components 2.0.4 för Cloud Service och Core Components 1.1.12 för AEM 6.5.16.0 Forms eller senare. Här är en tabell med alla versioner som stöds, AEM kompatibilitet och länkar till motsvarande dokumentation:

| Komponentversion | AEM as a Cloud Service | AEM 6.5.16.0 Forms eller senare |
|---|---|---|
| v1 | Kompatibel med<br>[version 2.0.4](/help/adaptive-forms/version.md) och senare | Kompatibel med<br>[version 1.1.12](/help/adaptive-forms/version.md) och senare men mindre än 2.0.0. |

Mer information om versioner och versioner av kärnkomponenter finns i [Huvudkomponentversioner](/help/adaptive-forms/version.md) -dokument.

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Teknisk information {#technical-details}

Den senaste informationen om den adaptiva Forms Radio button Core Component finns i den tekniska dokumentationen om [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/radiobutton/v1/radiobutton). Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Du kan enkelt anpassa din alternativknappsupplevelse för besökare med dialogrutan Konfigurera. Du kan också enkelt definiera alternativknappar för en smidig användarupplevelse.

![fliken Grundläggande](/help/adaptive-forms/assets/radiobutton_basictab.png)

- **Namn** - Du kan enkelt identifiera en formulärkomponent med dess unika namn både i formuläret och i regelredigeraren, men namnet får inte innehålla blanksteg eller specialtecken.

- **Titel** - Med dess titel kan du enkelt identifiera en komponent i ett formulär. Som standard visas titeln ovanpå komponenten. Om du inte lägger till en titel visas komponentens namn i stället för rubriktexten.
- **Tillåt RTF-text för rubrik** - Med den här funktionen kan användare formatera vanliga texttitlar med funktioner som fet, kursiv, understruken text, olika teckensnitt, teckenstorlekar, färger och ytterligare alternativ för att förbättra visuell presentation och anpassning. Det ger större flexibilitet och kreativ kontroll när det gäller att få titlar att sticka ut i dokument, på webbplatser och i tillämpningar.\
  När du markerar kryssrutan för **Tillåt RTF-text för rubrik** blir formateringsalternativen synliga för att formatera komponentens titel. Om du vill visa alla tillgängliga formateringsalternativ klickar du på ![Helskärmsikon](/help/adaptive-forms/assets/fullscreen-icon.png) -fliken.

  ![Stöd för RTF](/help/adaptive-forms/assets/richtext-support-title.png)

- **Dölj titel** - Välj alternativet om du vill dölja komponentens titel.

- **Alternativ** - Du kan lägga till datavärden och visa textpar med **Lägg till** -knappen.\
  När ett nytt alternativ har lagts till kan följande åtgärder utföras:
   - **Datavärde** - Med det här alternativet kan du ange det innehåll som ska skickas när ett alternativ har valts.
   - **Visa text** - Med det här alternativet kan du ange det innehåll som ska visas i ett adaptivt formulär.
   - **Ta bort** - Tryck eller klicka för att ta bort alternativet för en alternativknapp.
   - **Ordna om** - Tryck eller klicka och dra för att ändra ordningen på alternativen.
Du kan också formatera alternativen för alternativknappsgruppen med **Tillåt RTF för alternativ**.

  ![RTF-stöd för olika alternativ](/help/adaptive-forms/assets/richtext-for-options.png)

  När du har markerat kryssrutan för **Tillåt RTF för alternativ** formateringsalternativen blir synliga när du vill formatera komponentens alternativ. Om du vill visa alla tillgängliga formateringsalternativ klickar du på `Fullscreen` ![Helskärmsikon](/help/adaptive-forms/assets/fullscreen-icon.png) -fliken.

  ![RTF-stöd för olika alternativ](/help/adaptive-forms/assets/richtextoptions-support.png)

- **Bindningsreferens** - En bind referens är en referens till ett dataelement som lagras i en extern datakälla och används i ett formulär. Med den binda referensen kan du binda data dynamiskt till formulärfält så att formuläret kan visa de senaste data från datakällan. En bindningsreferens kan till exempel användas för att visa en kunds namn och adress i ett formulär baserat på kundens ID som anges i formuläret. Bindningsreferensen kan också användas för att uppdatera datakällan med data som anges i formuläret. På så sätt kan AEM Forms skapa formulär som interagerar med externa datakällor, vilket ger en smidig användarupplevelse för att samla in och hantera data.

- **Markera som obundet formulärelement**: Välj alternativet att konfigurera ett formulärfält som inte är länkat till något schema. Med det här alternativet kan du spara data utan att uppdatera datakällan. Det gör det också möjligt att hantera data på ett anpassat sätt, skilt från standarddatabasintegrering.

- **Datatyp för skickat värde** - Det här alternativet anger datatypen för det värde som skickas när något alternativ är markerat. Om **datatyp för skickat värde** är inställd på `Number` och du lägger till strängdata i **Datavärde** &#x200B; &#x200B; på **Alternativ** visas en `Value type mismatch` felmeddelande.

- **Standardalternativ** - Med det här alternativet kan du lägga till förvalda standardvärden när formuläret läses in. Om **datatyp för skickat värde** är inställd på `Number` och du lägger till strängdata i **Standardalternativ** visas en `Value type mismatch` felmeddelande.

- **Visningsalternativ** - Det här alternativet används för att ange den visuella justeringen för alternativknappar i ett adaptivt format. Följande två alternativ stöds:
   - **Vågrät** - När det här alternativet är markerat visas alternativknappar från vänster till höger i ett adaptivt formulär.
   - **Lodrätt** - När det här alternativet är markerat visas alternativknappar uppifrån och ned i ett adaptivt formulär.
- **Dölj komponent** - Välj alternativet att dölja komponenten från formuläret. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren. Detta är användbart när du behöver lagra information som inte behöver visas eller ändras direkt av användaren.
- **Inaktivera komponent** - Välj alternativet att inaktivera komponenten. Den inaktiverade komponenten är inte aktiv eller redigerbar av slutanvändaren. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.
- **Skrivskyddad** - Välj alternativet att göra komponenten icke-redigerbar. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.

### Fliken Validering {#validation-tab}

![Fliken Validering](/help/adaptive-forms/assets/radiobutton_validationtab.png)

- **Obligatoriskt** - Välj det här alternativet om du vill visa komponenten i ett adaptivt formulär. När du har valt alternativet måste du göra ett val innan du kan fortsätta med en formuläröverföring. Du kan inte välja **Dölj komponent** eller **Inaktivera komponent**  i **Grundläggande** när det här alternativet är markerat.
- **Felmeddelande** - Med det här alternativet kan du ange ett meddelande som visas om **Obligatoriskt** kryssrutan är markerad och formulärfältet är tomt.

- **Skriptverifieringsmeddelande** - Med det här alternativet kan du ange ett meddelande som ska visas om skriptvalideringen misslyckas.

### Fliken Hjälpinnehåll {#helpcontent-tab}

![Fliken Hjälpinnehåll](/help/adaptive-forms/assets/radiobutton_helptab.png)

- **Kort beskrivning** - En kort beskrivning är en kort textförklaring som ger ytterligare information eller förtydliganden om syftet med ett visst formulärfält. Det hjälper användaren att förstå vilken typ av data som ska anges i fältet och kan ge riktlinjer eller exempel som hjälper till att säkerställa att den angivna informationen är giltig och uppfyller de önskade kriterierna. Som standard är korta beskrivningar dolda. Aktivera **Visa alltid kort beskrivning** för att visa den under komponenten.

- **Visa alltid kort beskrivning** - Aktivera alternativet att visa den korta beskrivningen under komponenten.

- **Hjälptext** - Hjälptexten hänvisar till ytterligare information eller vägledning som användaren får för att hjälpa sig fylla i ett formulärfält på rätt sätt. Det visas när användaren klickar på hjälpikonen (i) som finns bredvid komponenten. Hjälptexten ger mer detaljerad information än etiketten eller platshållartexten för ett formulärfält och är utformad för att hjälpa användaren förstå fältets krav eller begränsningar. Den kan också ge förslag eller exempel som gör det enklare och exaktare att fylla i formuläret.

### Fliken Tillgänglighet {#accessibility-tab}

![Fliken Tillgänglighet](/help/adaptive-forms/assets/radiobutton_accessibilitytab.png)

**Text för skärmläsare** - Text för skärmläsare avser text som är avsedd att läsas av hjälpmedelstekniker, t.ex. skärmläsare, som används av personer med nedsatt syn. Den här texten innehåller en ljudbeskrivning av formulärfältets syfte och kan innehålla information om fältets titel, beskrivning, namn och relevanta meddelanden (anpassad text). Skärmläsartexten ser till att formuläret är tillgängligt för alla användare, även användare med nedsatt syn, och ger dem en fullständig förståelse för formulärfältet och dess krav.

## Designdialogruta {#design-dialog}

Designdialogrutan används för att definiera och hantera CSS-format för komponenten Radio button.


### Fliken Format {#styles-tab}

Fliken används för att definiera och hantera CSS-format för en komponent. Core-komponenten för den adaptiva Forms-alternativknappen har stöd för AEM [Formatsystem](/help/get-started/authoring.md#component-styling).

![Designdialogruta](/help/adaptive-forms/assets/checkbox-style.png)

- **CSS-standardklasser**: Du kan ange en standard-CSS-klass för den adaptiva Forms-alternativknappens Core-komponent.

- **Tillåtna format**: Du kan definiera format genom att ange ett namn och den CSS-klass som representerar formatet. Du kan till exempel skapa ett format med namnet&quot;bold text&quot; och ge CSS-klassen&quot;font-weight: bold&quot;. Du kan använda eller tillämpa dessa format på ett adaptivt formulär i en anpassad Forms-redigerare. Om du vill använda ett format väljer du den komponent du vill använda formatet på i Adaptiv Forms-redigerare, navigerar till egenskapsdialogrutan och väljer önskat format i dialogrutan **Stilar** listruta. Om du behöver uppdatera eller ändra formaten går du tillbaka till designdialogrutan, uppdaterar formaten på formatfliken och sparar ändringarna.

### Anpassade egenskaper

![Dialogrutan Anpassade egenskaper](/help/adaptive-forms/assets/checkbox-customproperties.png)

Med anpassade egenskaper kan du koppla anpassade attribut (nyckelvärdepar) till en anpassad formulärets kärnkomponent med hjälp av formulärmallen. De anpassade egenskaperna återspeglas i egenskapsavsnittet i den headless-renderingen av komponenten. Det gör att du kan skapa dynamiskt formulärbeteende som anpassas baserat på anpassade attributvärden. Utvecklare kan till exempel utforma olika renderingar av en Headless Forms-komponent för mobiler, datorer eller webbplattformar, vilket avsevärt förbättrar användarupplevelsen på en mängd olika enheter.

- **Gruppnamn**: Du kan ange ett namn som identifierar den anpassade egenskapsgruppen. Du kan lägga till, ta bort eller ordna om flera anpassade egenskapsgrupper. När du har lagt till den anpassade egenskapsgruppen kan du se följande alternativ:

   - **Nyckelvärdepar**: Du kan lägga till flera anpassade egenskapsnamn och anpassade egenskapsvärden genom att klicka på **Lägg till** för varje anpassad egenskapsgrupp.

   - **Ta bort**: Tryck eller klicka för att ta bort det anpassade egenskapsnamnet och det anpassade egenskapsvärdet.

   - **Ordna om**: Tryck eller klicka och dra för att ändra ordningen på det anpassade egenskapsnamnet och det anpassade egenskapsvärdet.

## Relaterade artiklar {#related-articles}

{{more-like-this}}

## Se även {#see-also}

{{see-also}}
