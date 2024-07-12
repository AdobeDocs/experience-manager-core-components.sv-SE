---
title: Dragspel med adaptiv form
description: Använd dragspelspanelen för att ordna och förenkla ett långt eller komplext formulär genom att dela upp det i mindre, mer hanterbara avsnitt.
role: Architect, Developer, Admin, User
exl-id: 0ed38eee-fc22-4708-82eb-3fb1839b1ff2
source-git-commit: 4c510b8fe59f4be6e1b329ee4257ab1b780fbf22
workflow-type: tm+mt
source-wordcount: '2237'
ht-degree: 0%

---

# Dragspelskomponent {#accordion-component-adaptive-forms-core-component}

Med Accordion Core Component kan man skapa expanderbara och komprimerbara sektioner i en adaptiv form. Det används ofta för att organisera och förenkla långa eller komplexa formulär genom att dela upp dem i mindre, mer hanterbara avsnitt. Varje avsnitt i ett dragspel representeras vanligtvis av ett sidhuvud som användaren kan klicka på för att expandera eller komprimera motsvarande innehåll. Innehållet kan vara vilken kärnkomponent som helst.

![exempel](/help/adaptive-forms/assets/example-accordion.png)

## Användning {#usage}

Det finns många skäl till att det är bra att ta med ett dragspel i en adaptiv form, bland annat:

- **Utrymmessparande**: Med ett dragspel kan användare expandera och komprimera avsnitt i ett formulär, vilket minskar det utrymme som krävs för att visa alla formulärfält samtidigt.

- **Navigering**: Ett dragspel kan användas för att skapa en hierarkisk navigeringsstruktur, vilket gör det enklare för användarna att hitta de formulärfält de behöver.

- **Användarupplevelse**: Dragspel kan användas för att göra formuläret mer användarvänligt genom att tillhandahålla ett tydligt och intuitivt sätt för användare att komma åt och fylla i formulärfält.

- **Lång Forms**: Accordion är en idealisk komponent för att hantera långa formulär, eftersom det gör att användare kan fokusera på ett avsnitt i taget, i stället för att försöka bearbeta mycket information samtidigt.

Du kan använda

- Dialogrutan [Konfigurera](#configure-dialog) för att ange egenskaper för dragspelskomponenten.

- [Välj panelpekaren](#select-panel-popover) för att definiera ordningen på panelerna i dragspelet. Detta gör att författaren kan ordna panelerna i den ordning som panelerna ska visas.

- Alternativ för formulärförfattare att aktivera eller inaktivera vissa funktioner i [designdialogrutan](#design-dialog). En författare kan till exempel välja att inaktivera vissa fält eller avsnitt i ett formulär. Med dessa alternativ får författaren bättre kontroll över formulärens utformning och funktion, vilket gör det enklare att skapa formulär som är anpassade efter organisationens specifika behov.

Dialogrutan för att konfigurera och välja panel-pover och designdialogrutan är alla en del av de centrala komponenter som gör det enkelt att skapa formulären och som är ett effektivt sätt att skapa komplexa formulär.

## Version och kompatibilitet {#version-and-compatibility}


Den adaptiva kärnkomponenten i Forms Accordion lanserades i februari 2023 som en del av Core Components 2.0.4. Här är en tabell med alla versioner som stöds, AEM kompatibilitet och länkar till motsvarande dokumentation:

|  |  |
|---|---|
| Komponentversion | AEM as a Cloud Service |
| — | — |
| v1 | Kompatibel med <br>[version 2.0.4](/help/adaptive-forms/version.md) och senare | Kompatibel | Kompatibel |

Information om versioner och versioner av kärnkomponenter finns i dokumentet [Core Components Versions](/help/adaptive-forms/version.md) .


<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Teknisk information {#technical-details}

Hämta den senaste informationen om dragspelskomponenten i den tekniska dokumentationen för [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/accordion/v1/accordion). Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Du kan enkelt anpassa dragspelsupplevelsen för besökare med dialogrutan Konfigurera. Du kan också enkelt definiera dragspelsobjekt, paneler, beteenden och utseende för en smidig användarupplevelse.

### Fliken Grundläggande {#basic-tab}

![Fliken Grundläggande](/help/adaptive-forms/assets/acc-basic.png)

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

<!--  **Layout** - You can have either a fixed layout (Simple) or a flexible layout (Responsive Grid) for your wizard. The Simple layout keeps everything fixed in the place, while the Responsive Grid allows you to adjust the position of components to suit your needs. For example, use Responsive Grid to align "First Name", "Middle Name" and "Last Name" in a form in a single row. -->

- **Bindningsreferens** - En bindningsreferens är en referens till ett dataelement som lagras i en extern datakälla och används i ett formulär. Med den binda referensen kan du binda data dynamiskt till formulärfält så att formuläret kan visa de senaste data från datakällan. En bindningsreferens kan till exempel användas för att visa en kunds namn och adress i ett formulär baserat på kundens ID som anges i formuläret. Bindningsreferensen kan också användas för att uppdatera datakällan med data som anges i formuläret. På så sätt kan AEM Forms skapa formulär som interagerar med externa datakällor, vilket ger en smidig användarupplevelse för att samla in och hantera data.

- **Dölj komponent** - Välj alternativet att dölja komponenten från formuläret. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren. Detta är användbart när du behöver lagra information som inte behöver visas eller ändras direkt av användaren.

- **Inaktivera komponent** - Välj alternativet att inaktivera komponenten. Den inaktiverade komponenten är inte aktiv eller redigerbar av slutanvändaren. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.

- **Skrivskyddad** - Välj alternativet för att göra komponenten icke-redigerbar. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.

### Upprepa dragspel {#repeat-accordion}

![repeat-accordion](/help/adaptive-forms/assets/repeat-accordion.png)

Du kan använda alternativen för upprepning för att duplicera dragspelspaneler och dess underordnade komponenter, definiera ett minsta och högsta antal upprepningar och underlätta replikering av liknande avsnitt i ett formulär. När du interagerar med dragspelskomponenten och använder dess inställningar visas följande alternativ:

- **Gör dragspelspanelen upprepningsbar**: En växlingsfunktion som gör att användare kan aktivera eller inaktivera upprepningsfunktionen.
- **Minsta antal upprepningar**: Anger det minsta antal gånger dragspelspanelen kan upprepas. Värdet noll anger att dragspelspanelen inte upprepas. Standardvärdet är noll.
- **Maximalt antal upprepningar**: Anger maximalt antal gånger dragspelspanelen kan upprepas. Som standard är det här värdet obegränsat.

Om du effektivt vill hantera upprepningsbara avsnitt i dragspelet följer du stegen i artikeln [Skapa formulär med repeterbara avsnitt](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/create-forms-repeatable-sections.html) .

### Fliken Objekt {#items-tab}

![Fliken Objekt](/help/adaptive-forms/assets/acc-items.png)

Med knappen Lägg till kan du markera en komponent som ska läggas till som en panel i fönstret för komponentval. När du har lagt till komponenten kan du se följande alternativ:

- **Ikon** - Ikonen identifierar panelens komponent i listan. Du kan hålla muspekaren över ikonen för att visa det fullständiga komponentnamnet som ett verktygstips.
- **Beskrivning** - Den beskrivning som används som text på panelen. Som standard är komponentens namn markerat för panelen.
- **Ta bort** - Tryck eller klicka för att ta bort panelen från dragspelskomponenten.
- **Ordna om** - Tryck eller klicka och dra för att ordna om panelerna.

### Fliken Hjälpinnehåll {#help-content}

![Fliken Hjälpinnehåll](/help/adaptive-forms/assets/acc-helpcontent.png)

- **Kort beskrivning** - En kort beskrivning är en kort textförklaring som ger ytterligare information eller förtydliganden om syftet med ett visst formulärfält. Det hjälper användaren att förstå vilken typ av data som ska anges i fältet och kan ge riktlinjer eller exempel som hjälper till att säkerställa att den angivna informationen är giltig och uppfyller de önskade kriterierna. Som standard är korta beskrivningar dolda. Aktivera alternativet **Visa alltid kort beskrivning** för att visa det under komponenten.

- **Visa alltid kort beskrivning** - Aktivera alternativet att visa den korta beskrivningen under komponenten.

- **Hjälptext** - Hjälptexten hänvisar till ytterligare information eller vägledning som användaren får för att hjälpa dem att fylla i ett formulärfält korrekt. Det visas när användaren klickar på hjälpikonen (i) som finns bredvid komponenten. Hjälptexten ger mer detaljerad information än etiketten eller platshållartexten för ett formulärfält och är utformad för att hjälpa användaren förstå fältets krav eller begränsningar. Den kan också ge förslag eller exempel som gör det enklare och exaktare att fylla i formuläret.

### Fliken Tillgänglighet {#accessibility}

![Fliken Tillgänglighet](/help/adaptive-forms/assets/acc-accessisbilty.png)

På fliken **Hjälpmedel** anges värden för [ARIA-hjälpmedelsetiketter](https://www.w3.org/WAI/standards-guidelines/aria/) för komponenten. Det finns olika alternativ för att använda texten för skärmläsare:

- **Text för skärmläsare** - Text för skärmläsare hänvisar till ytterligare text som är särskilt avsedd att läsas av hjälpmedelstekniker, som skärmläsare, som används av personer med nedsatt syn. Den här texten innehåller en ljudbeskrivning av formulärfältets syfte och kan innehålla information om fältets titel, beskrivning, namn och relevanta meddelanden (anpassad text). Skärmläsartexten ser till att formuläret är tillgängligt för alla användare, även användare med nedsatt syn, och ger dem en fullständig förståelse för formulärfältet och dess krav.

   - **Egen text**: Välj det här alternativet om du vill använda den anpassade texten för ARIA-hjälpmedelsetiketter. Om du väljer det här alternativet visas dialogrutan Egen text. Du kan lägga till relevant information i dialogrutan Egen text.
   - **Beskrivning**: Välj det här alternativet om du vill använda beskrivningen för ARIA-hjälpmedelsetiketter.
   - **Titel**: Välj det här alternativet om du vill använda titeln för ARIA-hjälpmedelsetiketter.
   - **Namn**: Välj det här alternativet om du vill använda namnet på ARIA-hjälpmedelsetiketter.
   - **Inget**: Välj det här alternativet om du inte vill lägga till för hjälpmedelsetiketter för ARIA.

<!--

### Properties Tab {#properties-tab}

![Properties tab of the edit dialog of the Accordion Component](/help/assets/accordion-edit-properties.png)

*   **Single item expansion** - When selected, this option forces a single accordion item to be expanded at a time. Expanding one item will then collapse all others.
*   **Expanded items** - This option defines the items that are expanded by default when the page is loaded.
    * When **Single item expansion** is selected, one panel must be selected. By default the first panel is selected.
    * When **Single item expansion** is not selected, this option is a multi-select and is optional.
*   **ID** - This option allows to control the unique identifier of the component in the HTML and in the [Data Layer](/help/developing/data-layer/overview.md).
    * If left blank, a unique ID is automatically generated for you and can be found by inspecting the resulting page.
    * If an ID is specified, it is the responsibility of the author to make sure that it is unique.
    * Changing the ID can have an impact on CSS, JS and Data Layer tracking.

## Select Panel Popover {#select-panel-popover}

The **Select Panel** option (![Select panel icon](/help/assets/select-panel-icon.png)) on the component toolbar enables content authors to modify the panels in an accordion with ease. By selecting this option, the author can switch to a different panel for editing and rearrange the order of the panels in the accordion. The configured panels will be displayed in a drop-down menu for the author to choose from. This feature optimizes the editing process and makes it user-friendly for content authors.

![Select panel popover](/help/assets/select-panel-popover.png)


* The panels are displayed in a numbered list, reflecting the assigned arrangement.
* Each panel is listed with its component type in bold, followed by a brief description in lighter font.
* By clicking or tapping on a panel in the drop-down, you can easily switch the view in the editor to that specific panel.
* To rearrange the panels, simply use the drag handles to move them into the desired order. -->

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskapare styra hur saker visas som standard. För den adaptiva Forms-dragspelskomponenten kan du ange följande:

- Den typ av rubrikelement som är tillåtna och inställda som standard i HTML (t.ex. H1, H2, H3)
- De kärnkomponenter som en formulärskapare kan lägga till i dragspelet i den adaptiva Forms-redigeraren
- Enkla namn på format (CSS-klasser) som kan användas i egenskapsdialogrutan för dragspelskomponenten i den adaptiva Forms-redigeraren.

Detta gör det enklare och effektivare att skapa och anpassa formulär.

### Fliken Egenskaper {#properties-tab-design}

På fliken Egenskaper kan mallskapare ange standardrubrikelement och tillåtna rubrikelement för HTML för formulärförfattare:

![Egenskaper för designdialogruta, flik](/help//adaptive-forms/assets/accordion-design-properties.png)

- **Tillåtna rubrikelement**: En nedrullningsbar lista med flera alternativ där mallens författare kan välja vilka rubrikelement som formulärförfattaren kan använda för dragspelspanelen.

- **Standardrubrikelement**: En nedrullningsbar lista anger standardrubrikelementet för dragspelskomponenten.

### Fliken Tillåtna komponenter {#allowed-components-tab}

![Komponentfliken tillåts i designdialogrutan](/help//adaptive-forms/assets/accordion-allowed-components.png)

På fliken **Tillåtna komponenter** kan mallredigeraren ange vilka komponenter som kan läggas till som objekt på panelerna i dragspelskomponenten i den adaptiva Forms-redigeraren.

### Fliken Format {#styles-tab}

![Formatflik i designdialogrutan](/help/adaptive-forms/assets/accordion-styles-tab.png)

Designdialogrutan används för att definiera och hantera CSS-format för en komponent. Den adaptiva kärnkomponenten i Forms Accordion stöder AEM [Style System](/help/get-started/authoring.md#component-styling).

- **Standard-CSS-klasser**: Du kan ange en standard-CSS-klass för dragspelskomponenten.

- **Tillåtna format**: Du kan definiera format genom att ange ett namn och den CSS-klass som representerar formatet. Du kan till exempel skapa ett format med namnet&quot;bold text&quot; och ge CSS-klassen&quot;font-weight: bold&quot;. Du kan använda eller tillämpa dessa format på ett adaptivt formulär i en anpassad Forms-redigerare. Om du vill använda ett format väljer du den komponent du vill använda formatet på i Adaptiv Forms-redigerare, navigerar till egenskapsdialogrutan och väljer önskat format i listrutan **Format**. Om du behöver uppdatera eller ändra formaten går du tillbaka till designdialogrutan, uppdaterar formaten på formatfliken och sparar ändringarna.

### Anpassade egenskaper

![accordion-custom-properties-tab](/help/adaptive-forms/assets/accordion-custom-properties-tab.png)
Med anpassade egenskaper kan du koppla anpassade attribut (nyckelvärdepar) till en anpassad formulärets kärnkomponent med hjälp av formulärmallen. De anpassade egenskaperna återspeglas i egenskapsavsnittet i den headless-renderingen av komponenten. Det gör att du kan skapa dynamiskt formulärbeteende som anpassas baserat på anpassade attributvärden. Utvecklare kan till exempel utforma olika renderingar av en Headless Forms-komponent för mobiler, datorer eller webbplattformar, vilket avsevärt förbättrar användarupplevelsen på en mängd olika enheter.

- **Gruppnamn**: Du kan ange ett namn som identifierar den anpassade egenskapsgruppen. Du kan lägga till, ta bort eller ordna om flera anpassade egenskapsgrupper. När du har lagt till den anpassade egenskapsgruppen kan du se följande alternativ:

   - **Nyckelvärdepar**: Du kan lägga till flera anpassade egenskapsnamn och anpassade egenskapsvärden genom att klicka på knappen **Lägg till** för varje anpassad egenskapsgrupp.

   - **Ta bort**: Tryck eller klicka för att ta bort det anpassade egenskapsnamnet och det anpassade egenskapsvärdet.

   - **Ordna om**: Tryck eller klicka och dra för att ändra ordningen på det anpassade egenskapsnamnet och det anpassade egenskapsvärdet.

## Relaterade artiklar {#related-articles}

{{more-like-this}}

## Se även {#see-also}

{{see-also}}