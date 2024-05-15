---
title: Adaptiv Forms Core-komponent - lodräta flikar
description: Använda eller anpassa de adaptiva Forms-flikarna Core Component (Core-komponent).
role: Architect, Developer, Admin, User
exl-id: d5cd1c18-6840-4f2f-a767-a69b803e6075
source-git-commit: 58a0f0f2ef6d9dec3ce2436dad954a8a7aca188c
workflow-type: tm+mt
source-wordcount: '2112'
ht-degree: 0%

---

# Lodräta flikar, komponent{#vertical-tabs-adaptive-forms-core-component}

<span class="preview"> Den här artikeln innehåller innehåll om   **Tillåt RTF-text för rubrik**    en förhandsversion. Förhandsversionen är bara tillgänglig via vår [kanal för förhandsversion](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/release-notes/prerelease.html#new-features).</span>

Lodräta flikar i ett adaptivt formulär avser ett designmönster där flera avsnitt i ett formulär grupperas tillsammans och visas som separata flikar, justerade lodrätt. Användaren kan växla mellan flikarna för att komma åt olika avsnitt i formuläret. Varje flik fungerar som en utlösare som visar och döljer det relaterade formulärinnehållet. Med hjälp av de lodräta flikarna kan du ordna långa formulär i hanterbara avsnitt och förbättra användarupplevelsen. Med flikar kan du göra ett formulär mer tillgängligt för användare med funktionshinder, eftersom de kan växla mellan sektioner med hjälp av tangentbordsnavigering.
När en användare klickar på en flik uppdateras formulärinnehållet dynamiskt för att visa motsvarande avsnitt.

>[!NOTE]
>
> För AEM 6.5 Forms introducerades denna komponent i AEM 6.5 Forms Service Pack 19 (6.5.19.0). Om du vill aktivera den här komponenten kontrollerar du att de nödvändiga versionerna av både Forms Core Components och WCM Core Components är installerade. Detaljerad information om releaserna av adaptiva Forms Core-komponenter finns i [Adaptiva versioner av Forms Core Components](/help/adaptive-forms/version.md)

![exempel](/help/adaptive-forms/assets/horizontal-example.png)

## Användning {#reasons-to-use-vertical-tabs}

De vanligaste skälen att använda lodräta flikar i en adaptiv form är:

- **Förbättrad användbarhet**: Lodräta flikar gör det enklare för användare att navigera i formuläret, särskilt om formuläret har flera avsnitt eller ett stort antal fält.

- **Rymdhantering**: Lodräta flikar hjälper till att spara skärmutrymme genom att gruppera relaterade formuläravsnitt i flikar och bara visa ett avsnitt i taget.

- **Bättre organisation**: På flikar finns en tydlig och ordnad struktur för ett formulär som gör det lättare för användarna att förstå och fylla i formuläret.

- **Ökat användarengagemang**: Lodräta flikar kan göra ett formulär mer visuellt tilltalande och engagerande för användarna, vilket kan förbättra formulärets slutförandefrekvens.

## Version och kompatibilitet {#version-and-compatibility}

Core Component (kärnkomponent) på de adaptiva, lodräta flikarna i Forms släpptes som en del av Core Components 2.0.18. Här är en tabell med alla versioner som stöds, AEM kompatibilitet och länkar till motsvarande dokumentation:

|  |  |
|---|---|
| Komponentversion | AEM as a Cloud Service |
| — | — |
| v1 | Kompatibel med<br>[version 2.0.18](/help/adaptive-forms/version.md) och senare | Kompatibel | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i [Huvudkomponentversioner](/help/adaptive-forms/version.md) -dokument.

## Teknisk information {#technical-details}

Den senaste informationen om de adaptiva Forms-flikarna Core Component finns i den tekniska dokumentationen om [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/verticaltabs/v1/verticaltabs). Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Med dialogrutan Konfigurera kan du enkelt anpassa den vertikala flikfunktionen för besökare. Du kan också enkelt definiera alternativ för lodräta flikar för en smidig användarupplevelse.

### Fliken Grundläggande {#basic-tab}

![fliken Grundläggande](/help/adaptive-forms/assets/vertical-tab-basic.png)

- **Namn** - Du kan enkelt identifiera en formulärkomponent med dess unika namn både i formuläret och i regelredigeraren, men namnet får inte innehålla blanksteg eller specialtecken.

- **Titel** - Med dess titel kan du enkelt identifiera en komponent i ett formulär. Som standard visas titeln ovanpå komponenten. Om du inte lägger till en titel visas komponentens namn i stället för rubriktexten.
- **Tillåt RTF-text för rubrik** - Med den här funktionen kan användare formatera vanliga texttitlar med funktioner som fet, kursiv, understruken text, olika teckensnitt, teckenstorlekar, färger och ytterligare alternativ för att förbättra visuell presentation och anpassning. Det ger större flexibilitet och kreativ kontroll när det gäller att få titlar att sticka ut i dokument, på webbplatser och i tillämpningar.\
  När du markerar kryssrutan för **Tillåt RTF-text för rubrik** blir formateringsalternativen synliga för att formatera komponentens titel. Om du vill visa alla tillgängliga formateringsalternativ klickar du på ![Helskärmsikon](/help/adaptive-forms/assets/fullscreen-icon.png) -fliken.

  ![Stöd för RTF](/help/adaptive-forms/assets/richtext-support-title.png)

- **Dölj titel** - Välj alternativet om du vill dölja komponentens titel.

- **Gruppera underordnade komponenters data när formulär skickas (kapsla in data i objekt)** - När alternativet är markerat kapslas data från dess underordnade komponenter in i den överordnade komponentens JSON-objekt. Om alternativet inte är markerat har inskickade JSON-data en platt struktur utan objekt för den överordnade komponenten. Till exempel:

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

- **Bindningsreferens** - En bind referens är en referens till ett dataelement som lagras i en extern datakälla och används i ett formulär. Med den binda referensen kan du binda data dynamiskt till formulärfält så att formuläret kan visa de senaste data från datakällan. En bindningsreferens kan till exempel användas för att visa en kunds namn och adress i ett formulär baserat på kundens ID som anges i formuläret. Bindningsreferensen kan också användas för att uppdatera datakällan med data som anges i formuläret. På så sätt kan du med AEM Forms skapa formulär som interagerar med externa datakällor, vilket ger en smidig användarupplevelse för att samla in och hantera data.
- **Dölj komponent** - Välj alternativet att dölja komponenten från formuläret. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren. Detta är användbart när du behöver lagra information som inte behöver visas eller ändras direkt av användaren.
- **Inaktivera komponent** - Välj alternativet att inaktivera komponenten. Den inaktiverade komponenten är inte aktiv eller redigerbar av slutanvändaren. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.

- **Skrivskyddad** - Välj alternativet att göra komponenten icke-redigerbar. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.

### Upprepa lodrät tabb {#repeat-tabs-on-top}

![Upprepa tabb](/help/adaptive-forms/assets/vertical-tab-repeat-vertical-tab.png)

Du kan använda alternativen för upprepning för att duplicera en komponent med lodräta flikar och dess underordnade komponenter, definiera ett minsta och högsta repetitionsantal och underlätta replikering av liknande avsnitt i ett formulär. När du interagerar med komponenten Vertical-tabs och öppnar dess inställningar visas följande alternativ:

- **Gör lodräta flikar repeterbara**: En växlingsfunktion som gör att användarna kan aktivera eller inaktivera repeteringsfunktionen.
- **Minsta antal upprepningar**: Fastställer det minsta antalet gånger som komponenten Vertical-tabs kan upprepas. Värdet noll anger att komponenten Vertical-tabs inte upprepas. Standardvärdet är noll.
- **Maximalt antal upprepningar**: Anger det maximala antalet gånger som komponenten Vertical-tabs kan upprepas. Som standard är det här värdet obegränsat.

Om du vill hantera upprepningsbara avsnitt på de lodräta flikarna på ett effektivt sätt följer du stegen i [Skapa formulär med repeterbara avsnitt](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/create-forms-repeatable-sections.html) artikel.

### Fliken Objekt {#items-tab}

![Fliken Objekt](/help/adaptive-forms/assets/vertical-tab-items.png)

The **Lägg till** Med knappen kan du markera en komponent som du vill lägga till som en panel i fönstret för komponentval. När du har lagt till komponenten kan du se följande alternativ:

- **Ikon** - Ikonen identifierar panelens komponent i listan. Du kan hålla muspekaren över ikonen för att visa det fullständiga komponentnamnet som ett verktygstips.
- **Beskrivning** - Den beskrivning som används som text på panelen. Som standard är namnet på komponenten som är markerad för panelen.
- **Ta bort** - Tryck eller klicka för att ta bort panelen från komponenten Lodräta flikar.
- **Ordna om** - Tryck eller klicka och dra för att ordna om panelerna.

### Fliken Hjälpinnehåll {#help-content}

![Fliken Hjälpinnehåll](/help/adaptive-forms/assets/vertical-tab-help.png)

- **Kort beskrivning** - En kort beskrivning är en kort textförklaring som ger ytterligare information eller förtydliganden om syftet med ett visst formulärfält. Det hjälper användaren att förstå vilken typ av data som ska anges i fältet och kan ge riktlinjer eller exempel som hjälper till att säkerställa att den angivna informationen är giltig och uppfyller de önskade kriterierna. Som standard är korta beskrivningar dolda. Aktivera **Visa alltid kort beskrivning** för att visa den under komponenten.

- **Visa alltid kort beskrivning** - Aktivera alternativet att visa den korta beskrivningen under komponenten.

- **Hjälptext** - Hjälptexten hänvisar till ytterligare information eller vägledning som användaren får för att hjälpa sig fylla i ett formulärfält på rätt sätt. Det visas när användaren klickar på hjälpikonen (i) som finns bredvid komponenten. Hjälptexten ger mer detaljerad information än etiketten eller platshållartexten för ett formulärfält och är utformad för att hjälpa användaren förstå fältets krav eller begränsningar. Den kan också ge förslag eller exempel som gör det enklare och exaktare att fylla i formuläret.

### Fliken Tillgänglighet {#accessibility}

![Fliken Tillgänglighet](/help/adaptive-forms/assets/vertical-tab-accessibility.png)

- **Text för skärmläsare** - Text för skärmläsare avser text som är avsedd att läsas av hjälpmedelstekniker, t.ex. skärmläsare, som används av personer med nedsatt syn. Den här texten innehåller en ljudbeskrivning av formulärfältets syfte och kan innehålla information om fältets titel, beskrivning, namn och relevanta meddelanden (anpassad text). Skärmläsartexten ser till att formuläret är tillgängligt för alla användare, även användare med nedsatt syn, och ger dem en fullständig förståelse för formulärfältet och dess krav.

- **HTML roll som skärmläsaren kan meddela** - Rollen HTML är ett attribut som används för att ange syftet med ett HTML-element för hjälpmedelstekniker som skärmläsare. Rollattributet används för att ge ytterligare kontext och semantisk innebörd till ett element, vilket gör det enklare för skärmläsare att tolka och meddela innehållet till användaren. I AEM Forms kan till exempel etiketten för ett formulärfält ha rollen&quot;label&quot;, och inmatningsfältet kan ha rollen&quot;texbox&quot;. Detta gör att skärmläsaren förstår förhållandet mellan etiketten och inmatningsfältet och kan meddela användaren dem på rätt sätt.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskapare styra hur saker visas som standard. För den adaptiva Forms-komponenten med lodräta flikar kan du ange följande:

- De kärnkomponenter som en formulärskapare kan lägga till på de lodräta flikarna i den adaptiva Forms-redigeraren
- Enkla namn på format (CSS-klasser) som kan användas i egenskapsdialogrutan för komponenten Vertical-tabs i den adaptiva Forms-redigeraren.

Detta gör det enklare och effektivare att skapa och anpassa formulär.

### Fliken Tillåtna komponenter {#allowed-components-tab}

![Fliken Tillåtna komponenter](/help/adaptive-forms/assets/tabs-allowed-component.png)

The **Tillåtna komponenter** kan mallredigeraren ange vilka komponenter som kan läggas till som objekt på panelerna i komponenten Lodrät tabb i den adaptiva Forms-redigeraren.

### Fliken Format {#styles-tab}

![Fliken Format](/help/adaptive-forms/assets/tabs-styles-tab.png)

Designdialogrutan används för att definiera och hantera CSS-format för en komponent. Core Component (Core-komponenten) för de adaptiva, lodräta Forms-flikarna har stöd för AEM [Formatsystem](/help/get-started/authoring.md#component-styling).

- **CSS-standardklasser**: Du kan ange en standard-CSS-klass för kärnkomponenten på de adaptiva Forms-lodräta flikarna.

- **Tillåtna format**: Du kan definiera format genom att ange ett namn och den CSS-klass som representerar formatet. Du kan till exempel skapa ett format med namnet&quot;bold text&quot; och ge CSS-klassen&quot;font-weight: bold&quot;. Du kan använda eller tillämpa dessa format på ett adaptivt formulär i en anpassad Forms-redigerare. Om du vill använda ett format väljer du den komponent du vill använda formatet på i Adaptiv Forms-redigerare, navigerar till egenskapsdialogrutan och väljer önskat format i dialogrutan **Stilar** listruta. Om du behöver uppdatera eller ändra formaten går du tillbaka till designdialogrutan, uppdaterar formaten på formatfliken och sparar ändringarna.

### Fliken Anpassade egenskaper

![Fliken Anpassade egenskaper](/help/adaptive-forms/assets/tabs-custom-properties.png)

Med anpassade egenskaper kan du koppla anpassade attribut (nyckelvärdepar) till en anpassad formulärets kärnkomponent med hjälp av formulärmallen. De anpassade egenskaperna återspeglas i egenskapsavsnittet i den headless-renderingen av komponenten. Det gör att du kan skapa dynamiskt formulärbeteende som anpassas baserat på anpassade attributvärden. Utvecklare kan till exempel utforma olika renderingar av en Headless Forms-komponent för mobiler, datorer eller webbplattformar, vilket avsevärt förbättrar användarupplevelsen på en mängd olika enheter.

- **Gruppnamn**: Du kan ange ett namn som identifierar den anpassade egenskapsgruppen. Du kan lägga till, ta bort eller ordna om flera anpassade egenskapsgrupper. När du har lagt till den anpassade egenskapsgruppen kan du se följande alternativ:

   - **Nyckelvärdepar**: Du kan lägga till flera anpassade egenskapsnamn och anpassade egenskapsvärden genom att klicka på **Lägg till** för varje anpassad egenskapsgrupp.

   - **Ta bort**: Tryck eller klicka för att ta bort det anpassade egenskapsnamnet och det anpassade egenskapsvärdet.

   - **Ordna om**: Tryck eller klicka och dra för att ändra ordningen på det anpassade egenskapsnamnet och det anpassade egenskapsvärdet.

## Relaterade artiklar {#related-articles}

{{more-like-this}}

## Se även {#see-also}

{{see-also}}
