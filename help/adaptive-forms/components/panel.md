---
title: Adaptiv Forms Core-komponent - panelbehållare
description: Använda eller anpassa Core-komponenten för den adaptiva Forms-panelbehållaren.
role: Architect, Developer, Admin, User
exl-id: 104836fe-8325-47de-978d-1ff2d6a9dd15
source-git-commit: 6725784bd4c94d433c91d6bd65d14d03cbefd954
workflow-type: tm+mt
source-wordcount: '2225'
ht-degree: 0%

---


# Panelkomponent{#panel-container-adaptive-forms-core-component}

I ett adaptivt formulär är en panel ett behållarelement som kan användas för att gruppera relaterade formulärelement. Det gör att du kan gruppera och ordna olika formulärelement på ett logiskt och meningsfullt sätt. Detta kan förbättra formulärets övergripande struktur och läsbarhet, vilket gör det lättare för användarna att förstå och navigera.

Paneler kan också användas för att skapa komprimerbara avsnitt, vilket kan vara användbart för att dölja komplexa eller mindre ofta använda formulärfält, vilket gör formuläret enkelt och lätt att använda. Du kan även inkludera andra komponenter som text, kryssrutor, knappar och så vidare.

Den kan också användas för att ange olika regelbaserade åtgärder som att skicka formulär, öppna en webbplats, visa/dölja komponenter eller lägga till en instans av en panel.

{{traditional-aem}}

**Exempel**

![exempel](/help/adaptive-forms/assets/panel-container.png)

## Användning {#reasons-to-use-panel-container}

Det finns flera skäl att använda en panel i ett formulär, bland annat:

- **Organisera formulärelement**: En panel kan användas för att gruppera relaterade formulärelement, vilket gör det enklare för användarna att förstå och navigera i formuläret.

- **Förbättra formulärstrukturen**: Genom att gruppera formulärelement i paneler kan det förbättra formulärets övergripande struktur och läsbarhet, vilket gör det lättare att förstå.

- **Skapa komprimerbara avsnitt**: Paneler kan användas för att skapa komprimerbara avsnitt, vilket kan vara användbart för att dölja komplexa eller mindre ofta använda formulärfält, vilket gör formuläret enkelt och lätt att använda.

- **Förbättrad användbarhet**: Genom att använda paneler för att ordna formulärelement kan det göra formuläret mer användarvänligt och lättare att använda, vilket kan leda till högre slutförandegrad.

## Version och kompatibilitet {#version-and-compatibility}

Core-komponenten för den adaptiva Forms-panelbehållaren släpptes i februari 2023 som en del av Core Components 2.0.4. Här är en tabell som visar alla versioner som stöds, kompatibiliteten med AEM och länkar till motsvarande dokumentation:

|  |  |
|---|---|
| Komponentversion | AEM as a Cloud Service |
| — | — |
| v1 | Kompatibel med <br>[version 2.0.4](/help/adaptive-forms/version.md) och senare | Kompatibel | Kompatibel |

Information om versioner och versioner av kärnkomponenter finns i dokumentet [Core Components Versions](/help/adaptive-forms/version.md) .

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Teknisk information {#technical-details}

Hämta den senaste informationen om kärnkomponenten för den adaptiva Forms-panelbehållaren i den tekniska dokumentationen för [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/panelcontainer/v1/panelcontainer). Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Du kan enkelt anpassa panelbehållarupplevelsen för besökare med dialogrutan Konfigurera. Du kan också enkelt definiera alternativ för panelbehållare för en smidig användarupplevelse.

### Fliken Grundläggande {#basic-tab}

![Fliken Grundläggande](/help/adaptive-forms/assets/basic-panel.png)

- **Namn** - Du kan enkelt identifiera en formulärkomponent med dess unika namn både i formuläret och i regelredigeraren, men namnet får inte innehålla blanksteg eller specialtecken.

- **Titel** - Med titeln kan du enkelt identifiera en komponent i ett formulär. Som standard visas titeln ovanpå komponenten. Om du inte lägger till en titel visas komponentens namn i stället för rubriktexten.
- **Tillåt RTF-text för rubrik** - Med den här funktionen kan användare formatera oformaterad text med funktioner som fet, kursiv, understruken text, olika teckensnitt, teckenstorlekar, färger och ytterligare alternativ för att förbättra visuell presentation och anpassning. Det ger större flexibilitet och kreativ kontroll när det gäller att få titlar att sticka ut i dokument, på webbplatser och i tillämpningar.\
  När du markerar kryssrutan för **Tillåt RTF-text för titel** visas formateringsalternativ som formaterar komponentens titel. Om du vill visa alla tillgängliga formateringsalternativ klickar du på fliken ![Helskärmsikon](/help/adaptive-forms/assets/fullscreen-icon.png) .

  ![RTF-stöd](/help/adaptive-forms/assets/richtext-support-title.png)

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

### Panelfliken Upprepa {#repeat-panel}

![upprepningsflik](/help/adaptive-forms/assets/repeat-panel.png)

Du kan använda alternativen för upprepning för att duplicera panelbehållaren och dess underordnade komponenter, definiera ett minsta och högsta antal upprepningar och underlätta replikering av liknande avsnitt i ett formulär. När du interagerar med panelbehållarkomponenten och använder dess inställningar visas följande alternativ:

- **Gör panelen repeterbar**: En växlingsfunktion som gör att användare kan aktivera eller inaktivera repeteringsfunktionen.
- **Minsta antal upprepningar**: Anger det minsta antal gånger som panelbehållaren kan upprepas. Värdet noll anger att guidepanelen inte upprepas. Standardvärdet är noll.
- **Maximalt antal upprepningar**: Anger maximalt antal gånger som panelbehållaren kan upprepas. Som standard är det här värdet obegränsat.

Om du effektivt vill hantera upprepningsbara avsnitt i panelbehållaren följer du stegen i artikeln [Skapa formulär med repeterbara avsnitt](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/create-forms-repeatable-sections.html?lang=sv-SE) .

### Fliken Hjälpinnehåll {#help-content}

![Fliken Hjälpinnehåll](/help/adaptive-forms/assets/helpcontent-panel.png)

- **Kort beskrivning** - En kort beskrivning är en kort textförklaring som ger ytterligare information eller förtydliganden om syftet med ett visst formulärfält. Det hjälper användaren att förstå vilken typ av data som ska anges i fältet och kan ge riktlinjer eller exempel som hjälper till att säkerställa att den angivna informationen är giltig och uppfyller de önskade kriterierna. Som standard är korta beskrivningar dolda. Aktivera alternativet **Visa alltid kort beskrivning** för att visa det under komponenten.

- **Visa alltid kort beskrivning** - Aktivera alternativet att visa den korta beskrivningen under komponenten.

- **Hjälptext** - Hjälptexten hänvisar till ytterligare information eller vägledning som användaren får för att hjälpa dem att fylla i ett formulärfält korrekt. Det visas när användaren klickar på hjälpikonen (i) som finns bredvid komponenten. Hjälptexten ger mer detaljerad information än etiketten eller platshållartexten för ett formulärfält och är utformad för att hjälpa användaren förstå fältets krav eller begränsningar. Den kan också ge förslag eller exempel som gör det enklare och exaktare att fylla i formuläret.

### Fliken Tillgänglighet {#accessibility}

![Fliken Tillgänglighet](/help/adaptive-forms/assets/accessibilty-panel.png)


- **Text för skärmläsare** - Text för skärmläsare hänvisar till ytterligare text som är särskilt avsedd att läsas av hjälpmedelstekniker, som skärmläsare, som används av personer med nedsatt syn. Den här texten innehåller en ljudbeskrivning av formulärfältets syfte och kan innehålla information om fältets titel, beskrivning, namn och relevanta meddelanden (anpassad text). Skärmläsartexten ser till att formuläret är tillgängligt för alla användare, även användare med nedsatt syn, och ger dem en fullständig förståelse för formulärfältet och dess krav.
   - **Egen text**: Välj det här alternativet om du vill använda den anpassade texten för ARIA-hjälpmedelsetiketter. Om du väljer det här alternativet visas dialogrutan Egen text. Du kan lägga till relevant information i dialogrutan Egen text.
   - **Beskrivning**: Välj det här alternativet om du vill använda beskrivningen för ARIA-hjälpmedelsetiketter.
   - **Titel**: Välj det här alternativet om du vill använda titeln för ARIA-hjälpmedelsetiketter.
   - **Namn**: Välj det här alternativet om du vill använda namnet på ARIA-hjälpmedelsetiketter.
   - **Inget**: Välj det här alternativet om du inte vill lägga till för hjälpmedelsetiketter för ARIA.

- **HTML-roll för skärmläsare som ska tillkännages** - HTML-rollen är ett attribut som används för att ange syftet med ett HTML-element för hjälpmedelstekniker som skärmläsare. Rollattributet används för att ge ytterligare kontext och semantisk innebörd till ett element, vilket gör det enklare för skärmläsare att tolka och meddela innehållet till användaren. I AEM Forms kan till exempel etiketten för ett formulärfält ha rollen&quot;label&quot;, och inmatningsfältet kan ha rollen&quot;texbox&quot;. Detta gör att skärmläsaren förstår förhållandet mellan etiketten och inmatningsfältet och kan meddela användaren dem på rätt sätt.

## Designdialogruta {#design-dialog}

Designdialogrutan används för att definiera och hantera CSS-format för panelkomponenten.

### Fliken Tillåtna komponenter {#allowed-components-tab}

![Komponentfliken tillåts i designdialogrutan](/help/adaptive-forms/assets/panel-container-allowed-component.png)

På fliken **Tillåtna komponenter** kan mallredigeraren ange vilka komponenter som kan läggas till som objekt på panelerna i komponenten i den adaptiva Forms-redigeraren.

### Fliken Standardkomponenter {#default-components-tab}

![Standardkomponentflik i designdialogrutan](/help/adaptive-forms/assets/panel-container-default-component.png)

På fliken **Standardkomponenter** kan mallredigeraren ange vilka komponenter som är synliga som standard som objekt i formulärbehållarkomponenten i den adaptiva Forms-redigeraren.

### Fliken Responsiva inställningar {#responsive-tab}

![Fliken Responsiva inställningar i designdialogrutan](/help/adaptive-forms/assets/panel-container-responsive-style-tab.png)

På fliken **Responsiva inställningar** kan mallredigeraren ange antalet kolumner i rutnätet i formulärbehållarkomponenten i den adaptiva Forms-redigeraren.

### Fliken Behållarinställningar

![Fliken Behållarinställningar](/help/adaptive-forms/assets/panel-container-container-settings.png)

- **Layout** - Du kan ha en fast layout (enkel) eller en flexibel layout (responsivt stödraster) för guiden. Med den enkla layouten är allt fast på plats, medan det responsiva rutnätet gör att du kan justera komponenternas placering efter dina behov. Använd till exempel responsivt stödraster för att justera&quot;Förnamn&quot;,&quot;Mittennamn&quot; och&quot;Efternamn&quot; i ett formulär på en enda rad.

- **Inaktivera layout**: Välj det här alternativet om du vill inaktivera layoutval i redigeringsdialogrutan för en komponent.

- **Aktivera bakgrundsbild**: Med det här alternativet kan användaren konfigurera panelens inställningar så att en visuell bakgrund inkluderas för att förbättra det visuella tilltalandet.

- **Aktivera bakgrundsfärg**: Med det här alternativet kan du ange eller ändra panelens bakgrundsfärg. Den här funktionen används ofta i gränssnittsdesign för att anpassa utseendet på paneler i ett större gränssnitt. När du väljer alternativet **Aktivera bakgrundsfärg** visas alternativet **Endast färgrutor** . Med alternativet **Färgrutor endast** kan du ange eller välja färger för bakgrunden, texten eller andra visuella element på panelen med knappen **Lägg till**

### Fliken Format {#styles-tab}

Kärnkomponenten för adaptiv bifogad Forms-fil stöder AEM [Style System](/help/get-started/authoring.md#component-styling).

![Designdialogrutan](/help/adaptive-forms/assets/panel-container-styles-tab.png)

- **Standardklasser för CSS**: Du kan ange en standardklass för CSS för kärnkomponenten för den adaptiva Forms-panelbehållaren.

- **Tillåtna format**: Du kan definiera format genom att ange ett namn och den CSS-klass som representerar formatet. Du kan till exempel skapa ett format med namnet&quot;bold text&quot; och ge CSS-klassen&quot;font-weight: bold&quot;. Du kan använda eller tillämpa dessa format på ett adaptivt formulär i en anpassad Forms-redigerare. Om du vill använda ett format väljer du den komponent du vill använda formatet på i Adaptiv Forms-redigerare, navigerar till egenskapsdialogrutan och väljer önskat format i listrutan **Format**. Om du behöver uppdatera eller ändra formaten går du tillbaka till designdialogrutan, uppdaterar formaten på formatfliken och sparar ändringarna.

### Fliken Anpassade egenskaper

![Dialogrutan Anpassade egenskaper](/help/adaptive-forms/assets/panel-container-custom-properties.png)

Med anpassade egenskaper kan du koppla anpassade attribut (nyckelvärdepar) till en anpassad formulärets kärnkomponent med hjälp av formulärmallen. De anpassade egenskaperna återspeglas i egenskapsavsnittet i den headless-renderingen av komponenten. Det gör att du kan skapa dynamiskt formulärbeteende som anpassas baserat på anpassade attributvärden. Utvecklare kan till exempel utforma olika renderingar av en Headless Forms-komponent för mobiler, datorer eller webbplattformar, vilket avsevärt förbättrar användarupplevelsen på en mängd olika enheter.

- **Gruppnamn**: Du kan ange ett namn som identifierar den anpassade egenskapsgruppen. Du kan lägga till, ta bort eller ordna om flera anpassade egenskapsgrupper. När du har lagt till den anpassade egenskapsgruppen kan du se följande alternativ:

   - **Nyckelvärdepar**: Du kan lägga till flera anpassade egenskapsnamn och anpassade egenskapsvärden genom att klicka på knappen **Lägg till** för varje anpassad egenskapsgrupp.

   - **Ta bort**: Tryck eller klicka för att ta bort det anpassade egenskapsnamnet och det anpassade egenskapsvärdet.

   - **Ordna om**: Tryck eller klicka och dra för att ändra ordningen på det anpassade egenskapsnamnet och det anpassade egenskapsvärdet.

<!--

## Related article {#related-article}

* [Create a standalone Adaptive Form](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html?lang=sv-SE)

-->

## Relaterade artiklar {#related-articles}

{{more-like-this}}

## Se även {#see-also}

{{see-also}}