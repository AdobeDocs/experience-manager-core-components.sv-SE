---
title: Adaptiv Forms Core-komponent - guide
description: Använda eller anpassa den adaptiva Forms Wizard Core Component.
role: Architect, Developer, Admin, User
exl-id: fd785cd2-5ed6-4efb-997f-ce9056ed113d
source-git-commit: ad3e3bca5cb46f14e864e4704c90ac3b62779794
workflow-type: tm+mt
source-wordcount: '1902'
ht-degree: 0%

---

# guide {#wizard-adaptive-forms-core-component}

En guidelayout i ett adaptivt formulär refererar till ett formulär som är uppdelat i flera steg eller på flera sidor där användaren förflyttar sig i formuläret ett steg i taget. Layouten kallas för en guide eftersom den guidar användaren genom formuläret steg för steg.

Varje steg i guiden innehåller vanligtvis en grupp relaterade formulärfält och en navigeringsmekanism, som knapparna Nästa och Bakåt, som du kan använda för att gå mellan stegen. Användaren kan bara fortsätta till nästa steg när det aktuella steget har slutförts och alla obligatoriska fält har fyllts i.

Guidelayouten är användbar för formulär som innehåller många fält eller information som behöver samlas in, eftersom den delar upp formuläret i mindre, mer hanterbara segment. Det hjälper också användarna att fokusera på en uppsättning fält i taget, vilket kan göra ifyllningsprocessen mindre överväldigande.

Det kan dock även göra formuläret mer komplicerat, eftersom användaren måste gå igenom flera sidor för att fylla i formuläret. Därför är det nödvändigt att utvärdera formulärets krav och användarens behov innan man bestämmer sig för att använda en guidelayout.

Du kan använda huvudkomponenten för guidelayouten i ett adaptivt formulär för att skapa en guidelayout.


**Exempel**

![](/help/adaptive-forms/assets/wizard.png)

## Användning {#reasons-to-use-wizard-in-an-adaptive-form}

Det finns flera skäl till att det kan vara bra att använda en guidelayout i anpassad form:

* **Enkelt**: Att dela upp ett formulär i flera steg kan göra det lättare för användarna att förstå och slutföra, eftersom de kan fokusera på en uppsättning fält i taget.

* **Organisation**: En guidelayout kan hjälpa dig att ordna formulär efter ämne eller syfte, och den kan också gruppera relaterade fält tillsammans, vilket kan göra ifyllningsprocessen mer logisk och effektiv.

* **Validering**: En guidelayout möjliggör stegvis validering, som kan hjälpa användare att identifiera och korrigera fel medan de arbetar, i stället för att vänta tills formuläret är slut.

* **Förloppsindikator**: En guidelayout kan visa formulärets förlopp, vilket kan hjälpa användaren förstå hur mycket av formuläret som återstår att fylla i.

* **Långa formulär**: Om formuläret innehåller många fält kan det vara överväldigande för användaren att se alla samtidigt, så att det blir mindre skrämmande om de delas upp i mindre, mer hanterbara segment.

* **Undvika övergivna**: En guidelayout kan också bidra till att minska antalet avhopp från formulär, eftersom användarna lättare kan fylla i ett formulär om de kan se förloppet och förstå hur mycket som återstår att göra.

* **Mobil upplevelse**: En guidelayout kan också vara bra för formulär som öppnas på mobila enheter, eftersom det gör det möjligt att läsa in mindre sidor snabbare och enklare att navigera i.

Generellt sett kan en guidelayout göra det enklare och effektivare att fylla i formulär, men det är viktigt att tänka på hur komplext formuläret är och användarens behov innan du bestämmer dig för att använda den här typen av layout.

## Version och kompatibilitet {#version-and-compatibility}

Kärnkomponenten i den adaptiva Forms-guiden Layout släpptes i februari 2023 som en del av kärnkomponenterna 2.0.4. Här är en tabell med alla versioner som stöds, AEM kompatibilitet och länkar till motsvarande dokumentation:

|  |  |
|---|---|
| Komponentversion | AEM as a Cloud Service |
| — | --- |
| v1 | Kompatibel med<br>[version 2.0.4](/help/versions.md) och senare | Kompatibel | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i [Huvudkomponentversioner](/help/versions.md) -dokument.

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Teknisk information {#technical-details}

Den senaste informationen om den adaptiva huvudkomponenten i Forms Title finns i den tekniska dokumentationen om [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/wizard/v1/wizard). Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Du kan enkelt anpassa guideupplevelsen för besökare med dialogrutan Konfigurera. Du kan också enkelt definiera guidealternativ för en smidig användarupplevelse.

### Fliken Grundläggande {#basic-tab}

![fliken Grundläggande](/help/adaptive-forms/assets/wizard-basic.png)

* **Namn** - Du kan enkelt identifiera en formulärkomponent med dess unika namn både i formuläret och i regelredigeraren, men namnet får inte innehålla blanksteg eller specialtecken.

* **Titel** - Med dess titel kan du enkelt identifiera en komponent i ett formulär. Som standard visas titeln ovanpå komponenten.

* **Dölj titel** - Välj alternativet om du vill dölja komponentens titel.

* **Figursätta data i ett objekt** - Välj &quot;Radbryt data i ett objekt&quot; om du vill placera fältdata från guiden i ett JSON-objekt. Om du inte väljer det här alternativet har JSON-objektet för att skicka data en platt struktur för guidens fält.

* **Layout** - Du kan ha en fast layout (enkel) eller en flexibel layout (responsivt stödraster) för guiden. Med den enkla layouten är allt fast på plats, medan det responsiva rutnätet gör att du kan justera komponenternas placering efter dina behov. Använd till exempel responsivt stödraster för att justera&quot;Förnamn&quot;,&quot;Mittennamn&quot; och&quot;Efternamn&quot; i ett formulär på en enda rad.

* **Bindningsreferens** - En bind referens är en referens till ett dataelement som lagras i en extern datakälla och används i ett formulär. Med den binda referensen kan du binda data dynamiskt till formulärfält så att formuläret kan visa de senaste data från datakällan. En bindningsreferens kan till exempel användas för att visa en kunds namn och adress i ett formulär baserat på kundens ID som anges i formuläret. Bindningsreferensen kan också användas för att uppdatera datakällan med data som anges i formuläret. På så sätt kan du med AEM Forms skapa formulär som interagerar med externa datakällor, vilket ger en smidig användarupplevelse för att samla in och hantera data.

* **Dölj komponent** - Välj alternativet att dölja komponenten från formuläret. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren. Detta är användbart när du behöver lagra information som inte behöver visas eller ändras direkt av användaren.

* **Inaktivera komponent** - Välj alternativet att inaktivera komponenten. Den inaktiverade komponenten är inte aktiv eller redigerbar av slutanvändaren. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.

### Fliken Repeat Wizard {#repeat-wizard-tab}

![Repeat wizard](/help/adaptive-forms/assets/wizard-repeat.png)

Du kan använda alternativen för upprepning för att duplicera guiden och dess underordnade komponenter, definiera ett minsta och högsta antal upprepningar och underlätta replikering av liknande avsnitt i ett formulär. När du interagerar med Wizard-komponenten och använder dess inställningar visas följande alternativ:

* **Gör guiden repeterbar**: En växlingsfunktion som gör att användarna kan aktivera eller inaktivera repeteringsfunktionen.
* **Minsta antal upprepningar**: Anger det minsta antal gånger som guidepanelen kan upprepas. Värdet noll anger att guidepanelen inte upprepas. Standardvärdet är noll.
* **Maximalt antal upprepningar**: Anger maximalt antal gånger som guidepanelen kan upprepas. Som standard är det här värdet obegränsat.

Om du vill hantera repeterbara avsnitt i guiden på ett effektivt sätt följer du stegen i [Skapa formulär med repeterbara avsnitt](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/create-forms-repeatable-sections.html) artikel.

### Fliken Hjälp {#help-tab}

![Fliken Hjälp](/help/adaptive-forms/assets/wizard-helpcontent.png)

* **Kort beskrivning** - En kort beskrivning är en kort textförklaring som ger ytterligare information eller förtydliganden om syftet med ett visst formulärfält. Det hjälper användaren att förstå vilken typ av data som ska anges i fältet och kan ge riktlinjer eller exempel som hjälper till att säkerställa att den angivna informationen är giltig och uppfyller de önskade kriterierna. Som standard är korta beskrivningar dolda. Aktivera **Visa alltid kort beskrivning** för att visa den under komponenten.

* **Visa alltid kort beskrivning** - Aktivera alternativet att visa den korta beskrivningen under komponenten.

* **Hjälptext** - Hjälptexten hänvisar till ytterligare information eller vägledning som användaren får för att hjälpa sig fylla i ett formulärfält på rätt sätt. Det visas när användaren klickar på hjälpikonen (i) som finns bredvid komponenten. Hjälptexten ger mer detaljerad information än etiketten eller platshållartexten för ett formulärfält och är utformad för att hjälpa användaren förstå fältets krav eller begränsningar. Den kan också ge förslag eller exempel som gör det enklare och exaktare att fylla i formuläret.


### Fliken Tillgänglighet {#accessibility}

![Fliken Hjälpmedel](/help/adaptive-forms/assets/wizard-accessibility.png)

* **Text för skärmläsare** - Text för skärmläsare avser text som är avsedd att läsas av hjälpmedelstekniker, t.ex. skärmläsare, som används av personer med nedsatt syn. Den här texten innehåller en ljudbeskrivning av formulärfältets syfte och kan innehålla information om fältets titel, beskrivning, namn och relevanta meddelanden (anpassad text). Skärmläsartexten ser till att formuläret är tillgängligt för alla användare, även användare med nedsatt syn, och ger dem en fullständig förståelse för formulärfältet och dess krav.

* **HTML roll som skärmläsaren kan meddela** - Rollen HTML är ett attribut som används för att ange syftet med ett HTML-element för hjälpmedelstekniker som skärmläsare. Rollattributet används för att ge ytterligare kontext och semantisk innebörd till ett element, vilket gör det enklare för skärmläsare att tolka och meddela innehållet till användaren. I AEM Forms kan till exempel etiketten för ett formulärfält ha rollen&quot;label&quot;, och inmatningsfältet kan ha rollen&quot;texbox&quot;. Detta gör att skärmläsaren förstår förhållandet mellan etiketten och inmatningsfältet och kan meddela användaren dem på rätt sätt.


## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskapare styra hur saker visas som standard. För den adaptiva Forms-guidekomponenten kan du ange följande:

* Huvudkomponenterna som en formulärskapare kan lägga till i guiden i Adaptive Forms Editor
* Enkla namn på format (CSS-klasser) som kan användas i egenskapsdialogrutan för komponenten Wizard i den adaptiva Forms-redigeraren.

Detta gör det enklare och effektivare att skapa och anpassa formulär.

### Fliken Tillåtna komponenter {#allowed-components-tab}

The **Tillåtna komponenter** kan mallredigeraren ange vilka komponenter som kan läggas till som objekt i panelerna i guidekomponenten i den adaptiva Forms-redigeraren.

### Fliken Format {#styles-tab}

Designdialogrutan används för att definiera och hantera CSS-format för en komponent. Kärnkomponenten i den adaptiva Forms-guiden stöder AEM [Formatsystem](/help/get-started/authoring.md#component-styling).

**CSS-standardklasser**: Du kan ange en standard-CSS-klass för Wizard-komponenten.

**Tillåtna format**: Du kan definiera format genom att ange ett namn och den CSS-klass som representerar formatet. Du kan till exempel skapa ett format med namnet&quot;bold text&quot; och ge CSS-klassen&quot;font-weight: bold&quot;. Du kan använda eller tillämpa dessa format på ett adaptivt formulär i en anpassad Forms-redigerare. Om du vill använda ett format väljer du den komponent du vill använda formatet på i Adaptiv Forms-redigerare, navigerar till egenskapsdialogrutan och väljer önskat format i dialogrutan **Stilar** listruta. Om du behöver uppdatera eller ändra formaten går du tillbaka till designdialogrutan, uppdaterar formaten på formatfliken och sparar ändringarna.

## Relaterad artikel {#related-article}

* [Skapa ett anpassat formulär i AEM Sites Page eller Experience Fragment](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html)

* [Skapa ett fristående anpassat formulär](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)

## Se även {#see-also}

* [Dragspel](/help/adaptive-forms/components/accordion.md)
* [Knapp](/help/adaptive-forms/components/button.md)
* [Kryssrutegrupp](/help/adaptive-forms/components/checkbox-group.md)
* [Datumväljaren](/help/adaptive-forms/components/date-picker.md)
* [Nedrullningsbar lista](/help/adaptive-forms/components/drop-down.md)
* [E-postinmatning](/help/adaptive-forms/components/email-input.md)
* [Formulärbehållare](/help/adaptive-forms/components/form-container.md)
* [Bifogad fil](/help/adaptive-forms/components/file-attachment.md)
* [Sidfot](/help/adaptive-forms/components/footer.md)
* [Sidhuvud](/help/adaptive-forms/components/header.md)
* [Vågräta flikar](/help/adaptive-forms/components/horizontal-tabs.md)
* [Bild](/help/adaptive-forms/components/image.md)
* [Nummerindata](/help/adaptive-forms/components/number-input.md)
* [Panelbehållare](/help/adaptive-forms/components/panel-container.md)
* [Alternativknapp](/help/adaptive-forms/components/radio-button.md)
* [Återställ knapp](/help/adaptive-forms/components/reset-button.md)
* [Skicka-knapp](/help/adaptive-forms/components/submit-button.md)
* [Telefonindata](/help/adaptive-forms/components/telephone-input.md)
* [Textindata](/help/adaptive-forms/components/text-input.md)
* [Text](/help/adaptive-forms/components/text.md)
* [Titel](/help/adaptive-forms/components/title.md)
