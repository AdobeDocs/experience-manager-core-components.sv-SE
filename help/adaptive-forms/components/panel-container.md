---
title: Adaptiv Forms Core-komponent - panelbehållare
description: Använda eller anpassa Core-komponenten för den adaptiva Forms-panelbehållaren.
role: Architect, Developer, Admin, User
source-git-commit: 77ff7425be1e591b8f5b973a344d7def8191c033
workflow-type: tm+mt
source-wordcount: '1218'
ht-degree: 0%

---


# Panelbehållare {#panel-container-adaptive-forms-core-component}

I ett adaptivt formulär är en panel ett behållarelement som kan användas för att gruppera relaterade formulärelement. Det gör att du kan gruppera och ordna olika formulärelement på ett logiskt och meningsfullt sätt. Detta kan förbättra formulärets övergripande struktur och läsbarhet, vilket gör det lättare för användarna att förstå och navigera.

Paneler kan också användas för att skapa komprimerbara avsnitt, vilket kan vara användbart för att dölja komplexa eller mindre ofta använda formulärfält, vilket gör formuläret enkelt och lätt att använda. Du kan även inkludera andra komponenter som text, kryssrutor, knappar och så vidare.

Den kan också användas för att ange olika regelbaserade åtgärder som att skicka formulär, öppna en webbplats, visa/dölja komponenter eller lägga till en instans av en panel.

**Exempel**

![](/help/adaptive-forms/assets/panel-container.png)

## Användning {#reasons-to-use-panel-container}

Det finns flera skäl att använda en panel i ett formulär, bland annat:

* **Ordna formulärelement**: En panel kan användas för att gruppera relaterade formulärelement, vilket gör det enklare för användarna att förstå och navigera i formuläret.

* **Förbättra formulärstrukturen**: Genom att gruppera formulärelement i paneler kan det förbättra formulärets övergripande struktur och läsbarhet, vilket gör det lättare att förstå.

* **Skapa komprimerbara avsnitt**: Paneler kan användas för att skapa komprimerbara avsnitt, vilket kan vara användbart för att dölja komplexa eller mindre ofta använda formulärfält, vilket gör formuläret enkelt och lätt att använda.

* **Förbättra användbarheten**: Genom att använda paneler för att ordna formulärelement kan det göra formuläret mer användarvänligt och lättare att använda, vilket kan leda till högre slutförandegrad.

## Version och kompatibilitet {#version-and-compatibility}

Core-komponenten för den adaptiva Forms-panelbehållaren släpptes i februari 2023 som en del av Core Components 2.0.4. Här är en tabell med alla versioner som stöds, AEM kompatibilitet och länkar till motsvarande dokumentation:

| Komponentversion | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Kompatibel med<br>[version 2.0.4](/help/versions.md) och senare | Kompatibel | Kompatibel |

Information om versioner och versioner av kärnkomponenter finns i [Huvudkomponentversioner](/help/versions.md) -dokument.

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Teknisk information {#technical-details}

Hämta den senaste informationen om den adaptiva kärnkomponenten i Forms-panelbehållaren i den tekniska dokumentationen om [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/panelcontainer/v1/panelcontainer). Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Du kan enkelt anpassa panelbehållarupplevelsen för besökare med dialogrutan Konfigurera. Du kan också enkelt definiera alternativ för panelbehållare för en smidig användarupplevelse.

### Fliken Grundläggande {#basic-tab}

![Fliken Grundläggande](/help/adaptive-forms/assets/panelcontainer_basictab.png)

* **Namn** - Du kan enkelt identifiera en formulärkomponent med dess unika namn både i formuläret och i regelredigeraren, men namnet får inte innehålla blanksteg eller specialtecken.

* **Titel** - Med dess titel kan du enkelt identifiera en komponent i ett formulär. Som standard visas titeln ovanpå komponenten. Om du inte lägger till en titel visas komponentens namn i stället för titeltexten.

* **Dölj titel** - Välj alternativet om du vill dölja komponentens titel.

* **Radbryt data i objekt** - Välj &quot;Radbryt data i ett objekt&quot; om du vill placera fältdata från guiden i ett JSON-objekt. Om du inte väljer det här alternativet har JSON-objektet för att skicka data en platt struktur för guidens fält.

* **Layout** - Du kan ha en fast layout (enkel) eller en flexibel layout (responsivt stödraster) för guiden. Med den enkla layouten är allt fast på plats, medan det responsiva rutnätet gör att du kan justera komponenternas placering efter dina behov. Använd till exempel responsivt stödraster för att justera&quot;Förnamn&quot;,&quot;Mittennamn&quot; och&quot;Efternamn&quot; i ett formulär på en enda rad.

* **Bindningsreferens** - En bind referens är en referens till ett dataelement som lagras i en extern datakälla och används i ett formulär. Med den binda referensen kan du binda data dynamiskt till formulärfält så att formuläret kan visa de senaste data från datakällan. En bindningsreferens kan till exempel användas för att visa en kunds namn och adress i ett formulär baserat på kundens ID som anges i formuläret. Bindningsreferensen kan också användas för att uppdatera datakällan med data som anges i formuläret. På så sätt kan AEM Forms skapa formulär som interagerar med externa datakällor, vilket ger en smidig användarupplevelse för att samla in och hantera data.
* **Dölj komponent** - Välj alternativet att dölja komponenten från formuläret. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren. Detta är användbart när du behöver lagra information som inte behöver visas eller ändras direkt av användaren.
* **Inaktivera komponent** - Välj alternativet att inaktivera komponenten. Den inaktiverade komponenten är inte aktiv eller redigerbar av slutanvändaren. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.

### Fliken Hjälpinnehåll {#help-content}

![Fliken Hjälpinnehåll](/help/adaptive-forms/assets/panelcontainer_helptab.png)

* **Kort beskrivning** - En kort beskrivning är en kort textförklaring som ger ytterligare information eller förtydliganden om syftet med ett visst formulärfält. Det hjälper användaren att förstå vilken typ av data som ska anges i fältet och kan ge riktlinjer eller exempel som hjälper till att säkerställa att den angivna informationen är giltig och uppfyller de önskade kriterierna. Som standard är korta beskrivningar dolda. Aktivera **Visa alltid kort beskrivning** för att visa den under komponenten.

* **Visa alltid kort beskrivning** - Aktivera alternativet att visa den korta beskrivningen under komponenten.

* **Hjälptext** - Hjälptexten hänvisar till ytterligare information eller vägledning som användaren får för att hjälpa sig fylla i ett formulärfält på rätt sätt. Det visas när användaren klickar på hjälpikonen (i) som finns bredvid komponenten. Hjälptexten ger mer detaljerad information än etiketten eller platshållartexten för ett formulärfält och är utformad för att hjälpa användaren förstå fältets krav eller begränsningar. Den kan också ge förslag eller exempel som gör det enklare och exaktare att fylla i formuläret.

### Fliken Tillgänglighet {#accessibility}

![Fliken Tillgänglighet](/help/adaptive-forms/assets/panelcontainer_accessibilitytab.png)

* **Text för skärmläsare** - Text för skärmläsare avser text som är avsedd att läsas av hjälpmedelstekniker, t.ex. skärmläsare, som används av personer med nedsatt syn. Den här texten innehåller en ljudbeskrivning av formulärfältets syfte och kan innehålla information om fältets titel, beskrivning, namn och relevanta meddelanden (anpassad text). Skärmläsartexten ser till att formuläret är tillgängligt för alla användare, även användare med nedsatt syn, och ger dem en fullständig förståelse för formulärfältet och dess krav.

* **HTML roll som skärmläsaren kan meddela** - Rollen HTML är ett attribut som används för att ange syftet med ett HTML-element för hjälpmedelstekniker som skärmläsare. Rollattributet används för att ge ytterligare kontext och semantisk innebörd till ett element, vilket gör det enklare för skärmläsare att tolka och meddela innehållet till användaren. I AEM Forms kan till exempel etiketten för ett formulärfält ha rollen&quot;label&quot;, och inmatningsfältet kan ha rollen&quot;texbox&quot;. Detta gör att skärmläsaren förstår förhållandet mellan etiketten och inmatningsfältet och kan meddela användaren dem på rätt sätt.

## Designdialogruta {#design-dialog}



