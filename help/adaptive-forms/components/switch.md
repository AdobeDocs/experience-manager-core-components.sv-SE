---
title: Adaptiv Forms Core-komponent - switch-komponent
description: Använda eller anpassa den adaptiva kärnkomponenten i Forms-switchen.
role: Architect, Developer, Admin, User
exl-id: 6ff2ca76-1514-42eb-bde3-60259af2d187
source-git-commit: e4274194026c3370b52be17171776847374a86b5
workflow-type: tm+mt
source-wordcount: '1689'
ht-degree: 0%

---

# Växla komponent{#switch-adaptive-forms-core-component}

Switch-komponenten är ett grafiskt användargränssnitt som används i formulär där användarna kan välja mellan två alternativ. Det är vanligtvis en tvålägesväxling som gör att användare kan välja mellan två lägen, vilket aktiverar eller inaktiverar en funktion, inställning eller funktion. Switchkomponenten är utformad för att visuellt representera det aktuella läget och visa om en viss funktion är påslagen eller inte.

Switch-komponenten är ett booleskt kontrollelement som anger värdet till true eller false. Den används till exempel för att växla mellan aktivering och inaktivering av en funktion, som att stänga av eller stänga av ljud, eller aktivera eller inaktivera Bluetooth eller WiFi.

![Exempel på växlingskomponent](/help/adaptive-forms/assets/switch-example.png)

## Användning {#reasons-to-use-switch}

De vanligaste skälen att använda en switch i en adaptiv form är:

- **Användarinteraktion**: Användare kan interagera med switchkomponenten genom att klicka eller trycka på den.

- **Lägen**: Växlingskomponenten har två lägen: PÅ och AV. Växelkomponentens startläge beror på standardinställningen eller den aktuella statusen för funktionen som den styr.

- **Visuell representation**: Växlingskomponenten visar visuellt dess aktuella läge genom att ändra färg eller position.

- **Styr funktionaliteten**: Växlingskomponenten används för att aktivera eller inaktivera vissa funktioner i ett AEM. Användaren kan till exempel aktivera eller inaktivera en funktion.

## Version och kompatibilitet {#version-and-compatibility}

Den adaptiva kärnkomponenten i Forms-switchen släpptes som en del av kärnkomponenterna 2.0.64. Här är en tabell med alla versioner som stöds, AEM kompatibilitet och länkar till motsvarande dokumentation:

|  |  |
|---|---|
| Komponentversion | AEM as a Cloud Service |
| — | — |
| v1 | Kompatibel med<br>[version 2.0.64](/help/adaptive-forms/version.md) och senare | Kompatibel | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i [Huvudkomponentversioner](/help/adaptive-forms/version.md) -dokument.

## Teknisk information {#technical-details}

Den senaste informationen om den adaptiva Forms Switch Core Component finns i den tekniska dokumentationen om [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/switch/v1/switch). Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Med dialogrutan Konfigurera kan du enkelt anpassa hur din switch-komponent fungerar för besökare. Du kan också enkelt definiera alternativ för switchkomponenter för en smidig användarupplevelse.

### Fliken Grundläggande

![fliken Grundläggande](/help/adaptive-forms/assets/switch-basic.png)

- **Namn** - Du kan enkelt identifiera en formulärkomponent med dess unika namn både i formuläret och i regelredigeraren, men namnet får inte innehålla blanksteg eller specialtecken.

- **Titel** - Med dess titel kan du enkelt identifiera en komponent i ett formulär. Som standard visas titeln bredvid komponenten. Om du inte lägger till en titel visas inte komponenten.
<!-- **Allow Rich Text for Title** - This features enables users to format plain text titles, incorporating features like bold, italic, underlined text, various fonts, font sizes, colors, and additional option to enhance visual presentation and customization. It offers greater flexibility and creative control in making titles stand out within documents, websites, or applications.  
    Upon selecting the checkbox for **Allow Rich Text for Title** , formatting options become visible to style the component's title. To access all available formatting options, you can click on the ![Fullscreen icon](/help/adaptive-forms/assets/fullscreen-icon.png) tab.
     
     ![Rich text support](/help/adaptive-forms/assets/richtext-support-title.png)-->

- **Dölj titel** - Välj alternativet om du vill dölja komponentens titel.

- **Bevara omarkerat lägesvärde** - Om du väljer det här alternativet kan du ange vilket värde som ska returneras när växlingskomponenten inte är markerad.
- **Alternativ** - Ange datavärdet och visa text för varje alternativ.
   - **På datavärde** - Ange det värde som ska skickas när växeln aktiveras i ett adaptivt format.
   - **I visningstext** - Ange den text som ska visas som etikett när växeln är aktiverad i ett adaptivt format.
   - **Av datavärde** - Ange det värde som ska skickas när växeln inte är aktiverad i ett adaptivt format. Det här alternativet visas bara om **Bevara omarkerat lägesvärde** växeln är aktiverad.
   - **Text utanför visning** - Ange den text som ska visas som etikett när växeln inte är aktiverad i ett adaptivt format. Det här alternativet visas bara om **Bevara omarkerat lägesvärde** växeln är aktiverad.

<!-- You can also format the options for switch using **Allow Rich Text for Options**. 
  
     ![Rich text support for options](/help/adaptive-forms/assets/switch-optipn-rich-text.png)

    Once you select the checkbox for **Allow Rich Text for options** formatting options become visible to style the component's options. To access all available formatting options, you can click on the `Fullscreen` ![Fullscreen icon](/help/adaptive-forms/assets/fullscreen-icon.png) tab.
    
    ![Rich text support for options](/help/adaptive-forms/assets/switch-richtext-for-display.png) -->

- **Bindningsreferens** - En bind referens är en referens till ett dataelement som lagras i en extern datakälla och används i ett formulär. Med den binda referensen kan du binda data dynamiskt till formulärfält så att formuläret kan visa de senaste data från datakällan. En bindningsreferens kan till exempel användas för att visa en kunds namn och adress i ett formulär baserat på kundens ID som anges i formuläret. Bindningsreferensen kan också användas för att uppdatera datakällan med data som anges i formuläret. På så sätt kan du med AEM Forms skapa formulär som interagerar med externa datakällor, vilket ger en smidig användarupplevelse för att samla in och hantera data.
- **Markera som obundet formulärelement**: Välj alternativet att konfigurera ett formulärfält som inte är länkat till något schema. Med det här alternativet kan du spara data utan att uppdatera datakällan. Det gör det också möjligt att hantera data på ett anpassat sätt, skilt från standarddatabasintegrering.

- **Datatyp för skickat värde**: Det här alternativet anger datatypen för det värde som skickas när något alternativ är markerat. Om **datatyp för skickat värde** är inställd på `Number` och du lägger till strängdata i **Datavärde** &#x200B; &#x200B; på **Alternativ** visas en `Value type mismatch` felmeddelande.
- **Dölj komponent** - Välj alternativet att dölja komponenten från formuläret. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren. Detta är användbart när du behöver lagra information som inte behöver visas eller ändras direkt av användaren.

- **Inaktivera komponent** - Välj alternativet att inaktivera eller låsa komponenten. Den inaktiverade komponenten är inte aktiv eller redigerbar av slutanvändaren. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.

- **Standardvärde**: Med det här alternativet kan du lägga till ett standardvärde i ett formulärfält. If **Inaktiverad komponent** eller **Skrivskyddad komponent** är markerat visas standardvärdet på skärmen. Om användaren inte anger något värde i formulärfältet skickas det här värdet när formuläret skickas.

### Fliken Validering {#validation-tab}

![Fliken Validering](/help/adaptive-forms/assets/switch-validation.png)

- **Obligatoriskt** - Välj det här alternativet om du vill visa komponenten i ett adaptivt formulär. När du har valt alternativet måste du göra ett val innan du kan fortsätta med en formuläröverföring. Du kan inte välja **Dölj komponent** eller **Inaktivera komponent**  i **Grundläggande** när det här alternativet är markerat.

- **Felmeddelande** - Med det här alternativet kan du ange ett meddelande som visas om **Obligatoriskt** kryssrutan är markerad och formulärfältet är tomt.

- **Skriptverifieringsmeddelande** - Med det här alternativet kan du ange ett meddelande som ska visas om skriptvalideringen misslyckas.

### Fliken Hjälpinnehåll {#helpcontent-tab}

![Fliken Hjälpinnehåll](/help/adaptive-forms/assets/switch-help.png)

- **Kort beskrivning** - En kort beskrivning är en kort textförklaring som ger ytterligare information eller förtydliganden om syftet med ett visst formulärfält. Det hjälper användaren att förstå vilken typ av data som ska anges i fältet och kan ge riktlinjer eller exempel som hjälper till att säkerställa att den angivna informationen är giltig och uppfyller de önskade kriterierna. Som standard är korta beskrivningar dolda. Aktivera **Visa alltid kort beskrivning** för att visa den under komponenten.

- **Visa alltid kort beskrivning** - Aktivera alternativet att visa den korta beskrivningen under komponenten.

- **Hjälptext** - Hjälptexten hänvisar till ytterligare information eller vägledning som användaren får för att hjälpa sig fylla i ett formulärfält på rätt sätt. Det visas när användaren klickar på hjälpikonen (i) som finns bredvid komponenten. Hjälptexten ger mer detaljerad information än etiketten eller platshållartexten för ett formulärfält och är utformad för att hjälpa användaren förstå fältets krav eller begränsningar. Den kan också ge förslag eller exempel som gör det enklare och exaktare att fylla i formuläret.

### Fliken Tillgänglighet {#accessibility-tab}

![Fliken Tillgänglighet](/help/adaptive-forms/assets/switch-accessibility.png)

**Text för skärmläsare** - Text för skärmläsare avser text som är avsedd att läsas av hjälpmedelstekniker, t.ex. skärmläsare, som används av personer med nedsatt syn. Den här texten innehåller en ljudbeskrivning av formulärfältets syfte och kan innehålla information om fältets titel, beskrivning, namn och relevanta meddelanden (anpassad text). Skärmläsartexten ser till att formuläret är tillgängligt för alla användare, även användare med nedsatt syn, och ger dem en fullständig förståelse för formulärfältet och dess krav.

### Fliken Format {#styles-tab}

![Fliken Format](/help/adaptive-forms/assets/switch-styles.png)

- **Dölj etiketter** - Välj det här alternativet om du vill dölja etiketterna för switchkomponenten.

- **Visa etiketter** - Välj det här alternativet om du vill visa växelkomponentens etiketter.

## Designdialogruta {#design-dialog}

Designdialogrutan används för att definiera och hantera CSS-format för komponenten Switch.

### Fliken Format {#styles-design-tab}

Den adaptiva kärnkomponenten i Forms-switchen stöder AEM [Formatsystem](/help/get-started/authoring.md#component-styling).

![Designdialogruta](/help/adaptive-forms/assets/checkbox-style.png)

- **CSS-standardklasser**: Du kan ange en standard-CSS-klass för den adaptiva Forms Switch Group Core Component.

- **Tillåtna format**: Du kan definiera format genom att ange ett namn och den CSS-klass som representerar formatet. Du kan till exempel skapa ett format med namnet&quot;bold text&quot; och ge CSS-klassen&quot;font-weight: bold&quot;. Du kan använda eller tillämpa dessa format på ett adaptivt formulär i en anpassad Forms-redigerare. Om du vill använda ett format väljer du den komponent du vill använda formatet på i Adaptiv Forms-redigerare, navigerar till egenskapsdialogrutan och väljer önskat format i dialogrutan **Stilar** listruta. Om du behöver uppdatera eller ändra formaten går du tillbaka till designdialogrutan, uppdaterar formaten på formatfliken och sparar ändringarna.

### Anpassade egenskaper

![Dialogrutan Anpassade egenskaper](/help/adaptive-forms/assets/checkbox-customproperties.png)

Med anpassade egenskaper kan du associera anpassade attribut (nyckelvärdepar) till en huvudkomponent för adaptiva formulär med hjälp av formulärmallen. De anpassade egenskaperna återspeglas i egenskapsavsnittet i den headless-renderingen av komponenten. Det gör att du kan skapa dynamiskt formulärbeteende som anpassas baserat på anpassade attributvärden. Utvecklare kan till exempel utforma olika renderingar av en Headless Forms-komponent för mobiler, datorer eller webbplattformar, vilket avsevärt förbättrar användarupplevelsen på en mängd olika enheter.

- **Gruppnamn**: Du kan ange ett namn som identifierar den anpassade egenskapsgruppen. Du kan lägga till, ta bort eller ordna om flera anpassade egenskapsgrupper. När du har lagt till den anpassade egenskapsgruppen kan du se följande alternativ:

   - **Nyckelvärdepar**: Du kan lägga till flera anpassade egenskapsnamn och anpassade egenskapsvärden genom att klicka på **Lägg till** för varje anpassad egenskapsgrupp.

   - **Ta bort**: Tryck eller klicka för att ta bort det anpassade egenskapsnamnet och det anpassade egenskapsvärdet.

   - **Ordna om**: Tryck eller klicka och dra för att ändra ordningen på det anpassade egenskapsnamnet och det anpassade egenskapsvärdet.

## Relaterade artiklar {#related-articles}

{{more-like-this}}

## Se även {#see-also}

{{see-also}}
