---
title: Adaptiv Forms Core-komponent - horisontella flikar
description: Använda eller anpassa den adaptiva, vågräta Forms-flikkomponenten Core.
role: Architect, Developer, Admin, User
exl-id: fbdf330b-3b85-4f94-9dab-eea8465fba67
source-git-commit: d2a6108f17f6e0c6b91bec84893d64a8bd48effd
workflow-type: tm+mt
source-wordcount: '1609'
ht-degree: 0%

---

# Vågräta flikar {#horizontal-tabs-adaptive-forms-core-component}

Vågräta flikar i ett adaptivt formulär avser ett designmönster där flera avsnitt i ett formulär grupperas tillsammans och visas som separata flikar, justerade vågrätt. Användaren kan växla mellan flikarna för att komma åt olika avsnitt i formuläret. Varje flik fungerar som en utlösare som visar och döljer det relaterade formulärinnehållet. De vågräta flikarna hjälper dig att ordna långa formulär i hanterbara avsnitt och förbättra användarupplevelsen. Med flikar kan du göra ett formulär mer tillgängligt för användare med funktionshinder, eftersom de kan växla mellan sektioner med hjälp av tangentbordsnavigering.

Flikarna skapas vanligtvis som en serie länkar eller knappar, där varje länk eller knapp motsvarar ett avsnitt i formuläret. När en användare klickar på en flik uppdateras formulärinnehållet dynamiskt för att visa motsvarande avsnitt.

## Användning {#reasons-to-use-horizontal-tabs}

De vanligaste skälen att använda vågräta flikar i en adaptiv form är:

* **Förbättrad användbarhet**: Vågräta flikar gör det enklare för användarna att navigera i formuläret, särskilt om formuläret har flera avsnitt eller ett stort antal fält.

* **Rymdhantering**: Vågräta flikar hjälper till att spara skärmutrymme genom att gruppera relaterade formuläravsnitt i flikar och bara visa ett avsnitt i taget.

* **Bättre organisation**: Flikarna ger en tydlig och ordnad struktur för ett formulär, vilket gör det enklare för användarna att förstå och fylla i formuläret.

* **Ökat användarengagemang**: Vågräta flikar kan göra ett formulär mer visuellt tilltalande och engagerande för användarna, vilket kan förbättra formulärets ifyllnadsgrad.

## Version och kompatibilitet {#version-and-compatibility}

Den adaptiva Forms Accordion Core-komponenten släpptes i februari 2023 som en del av Core Components 2.0.4 för Cloud Service och Core Components 1.1.12 för AEM 6.5.16.0 Forms eller senare. Här är en tabell med alla versioner som stöds, AEM kompatibilitet och länkar till motsvarande dokumentation:

| Komponentversion | AEM as a Cloud Service | AEM 6.5.16.0 Forms eller senare |
|---|---|---|
| v1 | Kompatibel med<br>[version 2.0.4](/help/adaptive-forms/version.md) och senare | Kompatibel med<br>[version 1.1.12](/help/adaptive-forms/version.md) och senare men mindre än 2.0.0. |

Information om versioner och versioner av kärnkomponenter finns i [Huvudkomponentversioner](/help/adaptive-forms/version.md) -dokument.


<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->


## Teknisk information {#technical-details}

Den senaste informationen om de adaptiva Forms Horizontal tabs Core Component finns i den tekniska dokumentationen om [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/pageHorizontal tabbar/v1/pageVågräta tabbar). Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Du kan enkelt anpassa de horisontella flikarna för besökare med dialogrutan Konfigurera. Du kan också enkelt definiera alternativ för vågräta flikar för en smidig användarupplevelse.

### Fliken Grundläggande {#basic-tab}

![Fliken Grundläggande](/help/adaptive-forms/assets/tabsontop_basictab.png)

* **Namn** - Du kan enkelt identifiera en formulärkomponent med dess unika namn både i formuläret och i regelredigeraren, men namnet får inte innehålla blanksteg eller specialtecken.

* **Titel** - Med dess titel kan du enkelt identifiera en komponent i ett formulär. Som standard visas titeln ovanpå komponenten. Om du inte lägger till en titel visas komponentens namn i stället för titeltexten.

* **Dölj titel** - Välj alternativet om du vill dölja komponentens titel.

* **Radbryt data i objekt** - Välj &quot;Radbryt data i ett objekt&quot; om du vill placera fältdata från guiden i ett JSON-objekt. Om du inte väljer det här alternativet har JSON-objektet för att skicka data en platt struktur för guidens fält.

* **Layout** - Du kan ha en fast layout (enkel) eller en flexibel layout (responsivt stödraster) för guiden. Med den enkla layouten är allt fast på plats, medan det responsiva rutnätet gör att du kan justera komponenternas placering efter dina behov. Använd till exempel responsivt stödraster för att justera&quot;Förnamn&quot;,&quot;Mittennamn&quot; och&quot;Efternamn&quot; i ett formulär på en enda rad.

* **Bindningsreferens** - En bind referens är en referens till ett dataelement som lagras i en extern datakälla och används i ett formulär. Med den binda referensen kan du binda data dynamiskt till formulärfält så att formuläret kan visa de senaste data från datakällan. En bindningsreferens kan till exempel användas för att visa en kunds namn och adress i ett formulär baserat på kundens ID som anges i formuläret. Bindningsreferensen kan också användas för att uppdatera datakällan med data som anges i formuläret. På så sätt kan AEM Forms skapa formulär som interagerar med externa datakällor, vilket ger en smidig användarupplevelse för att samla in och hantera data.
* **Dölj komponent** - Välj alternativet att dölja komponenten från formuläret. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren. Detta är användbart när du behöver lagra information som inte behöver visas eller ändras direkt av användaren.
* **Inaktivera komponent** - Välj alternativet att inaktivera komponenten. Den inaktiverade komponenten är inte aktiv eller redigerbar av slutanvändaren. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.

### Fliken Objekt {#items-tab}

![Fliken Objekt](/help/adaptive-forms/assets/tabsontop_itemstab.png)

The **Lägg till** Med knappen kan du markera en komponent som du vill lägga till som en panel i fönstret för komponentval. När du har lagt till komponenten kan du se följande alternativ:

* **Ikon** - Ikonen identifierar panelens komponent i listan. Du kan hålla muspekaren över ikonen för att visa det fullständiga komponentnamnet som ett verktygstips.
* **Beskrivning** - Den beskrivning som används som text på panelen. Som standard är namnet på komponenten som är markerad för panelen.
* **Ta bort** - Tryck eller klicka för att ta bort panelen från den vågräta tabbkomponenten.
* **Ordna om** - Tryck eller klicka och dra för att ordna om panelerna.

### Fliken Hjälpinnehåll {#help-content}

![Fliken Hjälpinnehåll](/help/adaptive-forms/assets/tabsontop_helptab.png)

* **Kort beskrivning** - En kort beskrivning är en kort textförklaring som ger ytterligare information eller förtydliganden om syftet med ett visst formulärfält. Det hjälper användaren att förstå vilken typ av data som ska anges i fältet och kan ge riktlinjer eller exempel som hjälper till att säkerställa att den angivna informationen är giltig och uppfyller de önskade kriterierna. Som standard är korta beskrivningar dolda. Aktivera **Visa alltid kort beskrivning** för att visa den under komponenten.

* **Visa alltid kort beskrivning** - Aktivera alternativet att visa den korta beskrivningen under komponenten.

* **Hjälptext** - Hjälptexten hänvisar till ytterligare information eller vägledning som användaren får för att hjälpa sig fylla i ett formulärfält på rätt sätt. Det visas när användaren klickar på hjälpikonen (i) som finns bredvid komponenten. Hjälptexten ger mer detaljerad information än etiketten eller platshållartexten för ett formulärfält och är utformad för att hjälpa användaren förstå fältets krav eller begränsningar. Den kan också ge förslag eller exempel som gör det enklare och exaktare att fylla i formuläret.

### Fliken Tillgänglighet {#accessibility}

![Fliken Tillgänglighet](/help/adaptive-forms/assets/tabsontop_accessibilitytab.png)

* **Text för skärmläsare** - Text för skärmläsare avser text som är avsedd att läsas av hjälpmedelstekniker, t.ex. skärmläsare, som används av personer med nedsatt syn. Den här texten innehåller en ljudbeskrivning av formulärfältets syfte och kan innehålla information om fältets titel, beskrivning, namn och relevanta meddelanden (anpassad text). Skärmläsartexten ser till att formuläret är tillgängligt för alla användare, även användare med nedsatt syn, och ger dem en fullständig förståelse för formulärfältet och dess krav.

* **HTML roll som skärmläsaren kan meddela** - Rollen HTML är ett attribut som används för att ange syftet med ett HTML-element för hjälpmedelstekniker som skärmläsare. Rollattributet används för att ge ytterligare kontext och semantisk innebörd till ett element, vilket gör det enklare för skärmläsare att tolka och meddela innehållet till användaren. I AEM Forms kan till exempel etiketten för ett formulärfält ha rollen&quot;label&quot;, och inmatningsfältet kan ha rollen&quot;texbox&quot;. Detta gör att skärmläsaren förstår förhållandet mellan etiketten och inmatningsfältet och kan meddela användaren dem på rätt sätt.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskapare styra hur saker visas som standard. För den adaptiva Forms-komponenten kan du ange följande:

* De kärnkomponenter som en formulärskapare kan lägga till på de vågräta flikarna i den adaptiva Forms-redigeraren
* Enkla namn på format (CSS-klasser) som kan användas i egenskapsdialogrutan för vågräta flikkomponenter i den adaptiva Forms-redigeraren.

Detta gör det enklare och effektivare att skapa och anpassa formulär.

### Fliken Tillåtna komponenter {#allowed-components-tab}

The **Tillåtna komponenter** kan mallredigeraren ange vilka komponenter som kan läggas till som objekt på panelerna i komponenten Vågräta flikar i den adaptiva Forms-redigeraren.

![Vågräta flikar](/help/adaptive-forms/assets/horizontaltabs_designdilog.png)

### Fliken Format {#styles-tab}

Fliken används för att definiera och hantera CSS-format för en komponent. Core-komponenten för de adaptiva horisontella Forms-flikarna stöder AEM [Formatsystem](/help/get-started/authoring.md#component-styling).

![Fliken Format](/help/adaptive-forms/assets/horizontaltabs_designstyletab.png)

* **CSS-standardklasser**: Du kan ange en standard-CSS-klass för kärnkomponenten för de adaptiva vågräta Forms-flikarna.

* **Tillåtna format**: Du kan definiera format genom att ange ett namn och den CSS-klass som representerar formatet. Du kan till exempel skapa ett format med namnet&quot;bold text&quot; och ge CSS-klassen&quot;font-weight: fet&quot;. Du kan använda eller tillämpa dessa format på ett adaptivt formulär i den adaptiva Forms-redigeraren. Om du vill använda ett format väljer du den komponent du vill använda formatet på i Adaptiv Forms-redigerare, navigerar till egenskapsdialogrutan och väljer önskat format i dialogrutan **Stilar** nedrullningsbar lista. Om du behöver uppdatera eller ändra formaten går du tillbaka till designdialogrutan, uppdaterar formaten på formatfliken och sparar ändringarna.
