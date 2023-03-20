---
title: Dragspel med adaptiv form
description: Använd dragspelspanelen för att ordna och förenkla ett långt eller komplext formulär genom att dela upp det i mindre, mer hanterbara avsnitt.
role: Architect, Developer, Admin, User
exl-id: 0ed38eee-fc22-4708-82eb-3fb1839b1ff2
source-git-commit: 0cfdc56fe5508e156eee2ae818be311748af7247
workflow-type: tm+mt
source-wordcount: '1677'
ht-degree: 0%

---

# Dragspelskomponent {#accordion-component-adaptive-forms-core-component}

Med Accordion Core Component kan man skapa expanderbara och komprimerbara sektioner i en adaptiv form. Det används ofta för att organisera och förenkla långa eller komplexa formulär genom att dela upp dem i mindre, mer hanterbara avsnitt. Varje avsnitt i ett dragspel representeras vanligtvis av ett sidhuvud som användaren kan klicka på för att expandera eller komprimera motsvarande innehåll. Innehållet kan vara vilken kärnkomponent som helst.

## Användning {#usage}

Det finns många skäl till att det är bra att ta med ett dragspel i en adaptiv form, bland annat:

* **Spara utrymme**: Med ett dragspel kan användare expandera och komprimera avsnitt i ett formulär, vilket minskar det utrymme som krävs för att visa alla formulärfält samtidigt.

* **Navigering**: Ett dragspel kan användas för att skapa en hierarkisk navigeringsstruktur, vilket gör det enklare för användarna att hitta de formulärfält de behöver.

* **Användarupplevelse**: Accordion kan användas för att göra formuläret mer användarvänligt genom att ge användarna ett tydligt och intuitivt sätt att komma åt och fylla i formulärfält.

* **Long Forms**: Accordion är en idealisk komponent för att hantera långa formulär, eftersom det gör det möjligt för användarna att fokusera på ett avsnitt i taget, i stället för att försöka bearbeta mycket information samtidigt.

Du kan använda:

* The [konfigurera dialogruta](#configure-dialog) för att ange egenskaper för dragspelskomponenten.

* The [Välj panelpekare](#select-panel-popover)  för att definiera ordningen på panelerna i dragspelet. Detta gör att författaren kan ordna panelerna i den ordning som panelerna ska visas.

* Alternativ för formulärförfattare att aktivera eller inaktivera vissa funktioner i [designdialogruta](#design-dialog). En författare kan till exempel välja att inaktivera vissa fält eller avsnitt i ett formulär. Med dessa alternativ får författaren bättre kontroll över formulärens utformning och funktion, vilket gör det enklare att skapa formulär som är anpassade efter organisationens specifika behov.

Dialogrutan för att konfigurera och välja panel-pover och designdialogrutan är alla en del av de centrala komponenter som gör det enkelt att skapa formulären och som är ett effektivt sätt att skapa komplexa formulär.

## Version och kompatibilitet {#version-and-compatibility}

Den adaptiva Forms Accordion Core-komponenten släpptes i februari 2023 som en del av Core Components 2.0.4 för Cloud Service och Core Components 1.1.12 för AEM 6.5.16.0 Forms eller senare. Här är en tabell med alla versioner som stöds, AEM kompatibilitet och länkar till motsvarande dokumentation:

| Komponentversion | AEM as a Cloud Service | AEM 6.5.16.0 Forms eller senare |
|---|---|---|
| v1 | Kompatibel med<br>[version 2.0.4](/help/adaptive-forms/version.md) och senare | Kompatibel med<br>[version 1.1.12](/help/adaptive-forms/version.md) och senare men mindre än 2.0.0. |

Information om versioner och versioner av kärnkomponenter finns i [Huvudkomponentversioner](/help/adaptive-forms/version.md) -dokument.

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Teknisk information {#technical-details}

Hämta den senaste informationen om Accordion-komponenten i den tekniska dokumentationen om [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/accordion/v1/accordion). Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Du kan enkelt anpassa dragspelsupplevelsen för besökare med dialogrutan Konfigurera. Du kan också enkelt definiera dragspelsobjekt, paneler, beteenden och utseende för en smidig användarupplevelse.

### Fliken Grundläggande {#basic-tab}

![Fliken Grundläggande](/help/adaptive-forms/assets/accordion_basictab.png)

* **Namn** - Du kan enkelt identifiera en formulärkomponent med dess unika namn både i formuläret och i regelredigeraren, men namnet får inte innehålla blanksteg eller specialtecken.

* **Titel** - Med dess titel kan du enkelt identifiera en komponent i ett formulär. Som standard visas titeln ovanpå komponenten. Om du inte lägger till en titel visas komponentens namn i stället för titeltexten.

* **Dölj titel** - Välj alternativet om du vill dölja komponentens titel.

* **Radbryt data i objekt** - Välj &quot;Radbryt data i ett objekt&quot; om du vill placera fältdata från guiden i ett JSON-objekt. Om du inte väljer det här alternativet har JSON-objektet för att skicka data en platt struktur för guidens fält.

* **Layout** - Du kan ha en fast layout (enkel) eller en flexibel layout (responsivt stödraster) för guiden. Med den enkla layouten är allt fast på plats, medan det responsiva rutnätet gör att du kan justera komponenternas placering efter dina behov. Använd till exempel responsivt stödraster för att justera&quot;Förnamn&quot;,&quot;Mittennamn&quot; och&quot;Efternamn&quot; i ett formulär på en enda rad.

* **Bindningsreferens** - En bind referens är en referens till ett dataelement som lagras i en extern datakälla och används i ett formulär. Med den binda referensen kan du binda data dynamiskt till formulärfält så att formuläret kan visa de senaste data från datakällan. En bindningsreferens kan till exempel användas för att visa en kunds namn och adress i ett formulär baserat på kundens ID som anges i formuläret. Bindningsreferensen kan också användas för att uppdatera datakällan med data som anges i formuläret. På så sätt kan AEM Forms skapa formulär som interagerar med externa datakällor, vilket ger en smidig användarupplevelse för att samla in och hantera data.
* **Dölj komponent** - Välj alternativet att dölja komponenten från formuläret. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren. Detta är användbart när du behöver lagra information som inte behöver visas eller ändras direkt av användaren.
* **Inaktivera komponent** - Välj alternativet att inaktivera komponenten. Den inaktiverade komponenten är inte aktiv eller redigerbar av slutanvändaren. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.

### Fliken Objekt {#items-tab}

![Fliken Objekt](/help/adaptive-forms/assets/accordion_itemstab.png)

Med knappen Lägg till kan du markera en komponent som ska läggas till som en panel i fönstret för komponentval. När du har lagt till komponenten kan du se följande alternativ:

* **Ikon** - Ikonen identifierar panelens komponent i listan. Du kan hålla muspekaren över ikonen för att visa det fullständiga komponentnamnet som ett verktygstips.
* **Beskrivning** - Den beskrivning som används som text på panelen. Som standard är komponentens namn markerat för panelen.
* **Ta bort** - Tryck eller klicka för att ta bort panelen från dragspelskomponenten.
* **Ordna om** - Tryck eller klicka och dra för att ordna om panelerna.

### Fliken Hjälpinnehåll {#help-content}

![Fliken Hjälpinnehåll](/help/adaptive-forms/assets/accordion_helpcontent.png)

* **Kort beskrivning** - En kort beskrivning är en kort textförklaring som ger ytterligare information eller förtydliganden om syftet med ett visst formulärfält. Det hjälper användaren att förstå vilken typ av data som ska anges i fältet och kan ge riktlinjer eller exempel som hjälper till att säkerställa att den angivna informationen är giltig och uppfyller de önskade kriterierna. Som standard är korta beskrivningar dolda. Aktivera **Visa alltid kort beskrivning** för att visa den under komponenten.

* **Visa alltid kort beskrivning** - Aktivera alternativet att visa den korta beskrivningen under komponenten.

* **Hjälptext** - Hjälptexten hänvisar till ytterligare information eller vägledning som användaren får för att hjälpa sig fylla i ett formulärfält på rätt sätt. Det visas när användaren klickar på hjälpikonen (i) som finns bredvid komponenten. Hjälptexten ger mer detaljerad information än etiketten eller platshållartexten för ett formulärfält och är utformad för att hjälpa användaren förstå fältets krav eller begränsningar. Den kan också ge förslag eller exempel som gör det enklare och exaktare att fylla i formuläret.

### Fliken Tillgänglighet {#accessibility}

![Fliken Tillgänglighet](/help/adaptive-forms/assets/accordion_accessibility.png)

**Text för skärmläsare** - Text för skärmläsare avser text som är avsedd att läsas av hjälpmedelstekniker, t.ex. skärmläsare, som används av personer med nedsatt syn. Den här texten innehåller en ljudbeskrivning av formulärfältets syfte och kan innehålla information om fältets titel, beskrivning, namn och relevanta meddelanden (anpassad text). Skärmläsartexten ser till att formuläret är tillgängligt för alla användare, även användare med nedsatt syn, och ger dem en fullständig förståelse för formulärfältet och dess krav.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskapare styra hur saker visas som standard. För den adaptiva Forms-dragspelskomponenten kan du ange följande:

* Den typ av rubrikelement som är tillåtna och inställda som standard i HTML (t.ex. H1, H2, H3)
* De kärnkomponenter som en formulärskapare kan lägga till i dragspelet i den adaptiva Forms-redigeraren
* Enkla namn på format (CSS-klasser) som kan användas i egenskapsdialogrutan för dragspelskomponenten i den adaptiva Forms-redigeraren.

Detta gör det enklare och effektivare att skapa och anpassa formulär.

### Fliken Egenskaper {#properties-tab-design}

På fliken Egenskaper kan mallskapare ange standardrubrikelement och tillåtna rubrikelement för HTML för formulärförfattare:

![Egenskapflik i designdialogrutan](/help/assets/accordion-design-properties.png)

* **Tillåtna rubrikelement**: En nedrullningsbar lista med flera alternativ som gör att mallskaparen kan välja vilka rubrikelement som kan användas av formulärförfattaren för dragspelspanelen.

* **Standardrubrikelement**: En nedrullningsbar lista anger standardrubrikelementet för dragspelskomponenten.

### Fliken Tillåtna komponenter {#allowed-components-tab}

The **Tillåtna komponenter** kan mallredigeraren ange vilka komponenter som kan läggas till som objekt på panelerna i dragspelskomponenten i den adaptiva Forms-redigeraren.

![Fliken Tillåtna komponenter](/help/adaptive-forms/assets/accordion_allowedcomponents.png)

### Fliken Format {#styles-tab}

Fliken används för att definiera och hantera CSS-format för en komponent. Den adaptiva kärnkomponenten i Forms Accordion har stöd för AEM [Formatsystem](/help/get-started/authoring.md#component-styling).

![Fliken Format](/help/adaptive-forms/assets/accordion_style.png)

* **CSS-standardklasser**: Du kan ange en standard-CSS-klass för dragspelskomponenten.

* **Tillåtna format**: Du kan definiera format genom att ange ett namn och den CSS-klass som representerar formatet. Du kan till exempel skapa ett format med namnet&quot;bold text&quot; och ge CSS-klassen&quot;font-weight: fet&quot;. Du kan använda eller tillämpa dessa format på ett adaptivt formulär i den adaptiva Forms-redigeraren. Om du vill använda ett format väljer du den komponent du vill använda formatet på i Adaptiv Forms-redigerare, navigerar till egenskapsdialogrutan och väljer önskat format i dialogrutan **Stilar** nedrullningsbar lista. Om du behöver uppdatera eller ändra formaten går du tillbaka till designdialogrutan, uppdaterar formaten på formatfliken och sparar ändringarna.

