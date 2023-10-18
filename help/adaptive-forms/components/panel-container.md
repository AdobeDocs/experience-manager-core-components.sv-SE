---
title: Adaptiv Forms Core-komponent - panelbehållare
description: Använda eller anpassa Core-komponenten för den adaptiva Forms-panelbehållaren.
role: Architect, Developer, Admin, User
exl-id: 104836fe-8325-47de-978d-1ff2d6a9dd15
source-git-commit: 37ac7d3a9ae8c88d4c9be8129cfbd1eb4a7cccd1
workflow-type: tm+mt
source-wordcount: '1828'
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

- **Ordna formulärelement**: En panel kan användas för att gruppera relaterade formulärelement, vilket gör det enklare för användarna att förstå och navigera i formuläret.

- **Förbättra formulärstrukturen**: Genom att gruppera formulärelement i paneler kan det förbättra formulärets övergripande struktur och läsbarhet, vilket gör det lättare att förstå.

- **Skapa komprimerbara avsnitt**: Paneler kan användas för att skapa komprimerbara avsnitt, vilket kan vara användbart för att dölja komplexa eller mindre ofta använda formulärfält, vilket gör formuläret enkelt och lätt att använda.

- **Förbättra användbarheten**: Genom att använda paneler för att ordna formulärelement kan det göra formuläret mer användarvänligt och lättare att använda, vilket kan leda till högre slutförandegrad.

## Version och kompatibilitet {#version-and-compatibility}

Core-komponenten för den adaptiva Forms-panelbehållaren släpptes i februari 2023 som en del av Core Components 2.0.4. Här är en tabell med alla versioner som stöds, AEM kompatibilitet och länkar till motsvarande dokumentation:

|  |  |
|---|---|
| Komponentversion | AEM as a Cloud Service |
| — | --- |
| v1 | Kompatibel med<br>[version 2.0.4](/help/versions.md) och senare | Kompatibel | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i [Huvudkomponentversioner](/help/versions.md) -dokument.

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Teknisk information {#technical-details}

Hämta den senaste informationen om den adaptiva kärnkomponenten i Forms-panelbehållaren i den tekniska dokumentationen om [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/panelcontainer/v1/panelcontainer). Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Du kan enkelt anpassa panelbehållarupplevelsen för besökare med dialogrutan Konfigurera. Du kan också enkelt definiera alternativ för panelbehållare för en smidig användarupplevelse.

### Fliken Grundläggande {#basic-tab}

![fliken Grundläggande](/help/adaptive-forms/assets/basic-panel.png)

- **Namn** - Du kan enkelt identifiera en formulärkomponent med dess unika namn både i formuläret och i regelredigeraren, men namnet får inte innehålla blanksteg eller specialtecken.

- **Titel** - Med dess titel kan du enkelt identifiera en komponent i ett formulär. Som standard visas titeln ovanpå komponenten. Om du inte lägger till en titel visas komponentens namn i stället för rubriktexten.

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

- **Layout** - Du kan ha en fast layout (enkel) eller en flexibel layout (responsivt stödraster) för guiden. Med den enkla layouten är allt fast på plats, medan det responsiva rutnätet gör att du kan justera komponenternas placering efter dina behov. Använd till exempel responsivt stödraster för att justera&quot;Förnamn&quot;,&quot;Mittennamn&quot; och&quot;Efternamn&quot; i ett formulär på en enda rad.

- **Bindningsreferens** - En bind referens är en referens till ett dataelement som lagras i en extern datakälla och används i ett formulär. Med den binda referensen kan du binda data dynamiskt till formulärfält så att formuläret kan visa de senaste data från datakällan. En bindningsreferens kan till exempel användas för att visa en kunds namn och adress i ett formulär baserat på kundens ID som anges i formuläret. Bindningsreferensen kan också användas för att uppdatera datakällan med data som anges i formuläret. På så sätt kan AEM Forms skapa formulär som interagerar med externa datakällor, vilket ger en smidig användarupplevelse för att samla in och hantera data.
- **Dölj komponent** - Välj alternativet att dölja komponenten från formuläret. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren. Detta är användbart när du behöver lagra information som inte behöver visas eller ändras direkt av användaren.
- **Inaktivera komponent** - Välj alternativet att inaktivera komponenten. Den inaktiverade komponenten är inte aktiv eller redigerbar av slutanvändaren. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.

### Panelfliken Upprepa {#repeat-panel}

![upprepningsflik](/help/adaptive-forms/assets/repeat-panel.png)

Du kan använda alternativen för upprepning för att duplicera panelbehållaren och dess underordnade komponenter, definiera ett minsta och högsta antal upprepningar och underlätta replikering av liknande avsnitt i ett formulär. När du interagerar med panelbehållarkomponenten och använder dess inställningar visas följande alternativ:

- **Gör guiden repeterbar**: En växlingsfunktion som gör att användarna kan aktivera eller inaktivera repeteringsfunktionen.
- **Minsta antal upprepningar**: Anger det minsta antal gånger som panelbehållaren kan upprepas. Värdet noll anger att guidepanelen inte upprepas. Standardvärdet är noll.
- **Maximalt antal upprepningar**: Anger maximalt antal gånger som panelbehållaren kan upprepas. Som standard är det här värdet obegränsat.

Om du vill hantera upprepningsbara avsnitt i panelbehållaren på ett effektivt sätt följer du stegen i [Skapa formulär med repeterbara avsnitt](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/create-forms-repeatable-sections.html) artikel.

### Fliken Hjälpinnehåll {#help-content}

![Fliken Hjälpinnehåll](/help/adaptive-forms/assets/helpcontent-panel.png)


- **Kort beskrivning** - En kort beskrivning är en kort textförklaring som ger ytterligare information eller förtydliganden om syftet med ett visst formulärfält. Det hjälper användaren att förstå vilken typ av data som ska anges i fältet och kan ge riktlinjer eller exempel som hjälper till att säkerställa att den angivna informationen är giltig och uppfyller de önskade kriterierna. Som standard är korta beskrivningar dolda. Aktivera **Visa alltid kort beskrivning** för att visa den under komponenten.

- **Visa alltid kort beskrivning** - Aktivera alternativet att visa den korta beskrivningen under komponenten.

- **Hjälptext** - Hjälptexten hänvisar till ytterligare information eller vägledning som användaren får för att hjälpa sig fylla i ett formulärfält på rätt sätt. Det visas när användaren klickar på hjälpikonen (i) som finns bredvid komponenten. Hjälptexten ger mer detaljerad information än etiketten eller platshållartexten för ett formulärfält och är utformad för att hjälpa användaren förstå fältets krav eller begränsningar. Den kan också ge förslag eller exempel som gör det enklare och exaktare att fylla i formuläret.

### Fliken Tillgänglighet {#accessibility}

![Fliken Tillgänglighet](/help/adaptive-forms/assets/accessibilty-panel.png)


- **Text för skärmläsare** - Text för skärmläsare avser text som är avsedd att läsas av hjälpmedelstekniker, t.ex. skärmläsare, som används av personer med nedsatt syn. Den här texten innehåller en ljudbeskrivning av formulärfältets syfte och kan innehålla information om fältets titel, beskrivning, namn och relevanta meddelanden (anpassad text). Skärmläsartexten ser till att formuläret är tillgängligt för alla användare, även användare med nedsatt syn, och ger dem en fullständig förståelse för formulärfältet och dess krav.

- **HTML roll som skärmläsaren kan meddela** - Rollen HTML är ett attribut som används för att ange syftet med ett HTML-element för hjälpmedelstekniker som skärmläsare. Rollattributet används för att ge ytterligare kontext och semantisk innebörd till ett element, vilket gör det enklare för skärmläsare att tolka och meddela innehållet till användaren. I AEM Forms kan till exempel etiketten för ett formulärfält ha rollen&quot;label&quot;, och inmatningsfältet kan ha rollen&quot;texbox&quot;. Detta gör att skärmläsaren förstår förhållandet mellan etiketten och inmatningsfältet och kan meddela användaren dem på rätt sätt.

## Relaterade artiklar {#related-articles}

- [Dragspel](/help/adaptive-forms/components/accordion.md)
- [Knapp](/help/adaptive-forms/components/button.md)
- [Kryssrutegrupp](/help/adaptive-forms/components/checkbox-group.md)
- [Datumväljaren](/help/adaptive-forms/components/date-picker.md)
- [Nedrullningsbar lista](/help/adaptive-forms/components/drop-down.md)
- [E-postinmatning](/help/adaptive-forms/components/email-input.md)
- [Formulärbehållare](/help/adaptive-forms/components/form-container.md)
- [Bifogad fil](/help/adaptive-forms/components/file-attachment.md)
- [Sidfot](/help/adaptive-forms/components/footer.md)
- [Sidhuvud](/help/adaptive-forms/components/header.md)
- [Vågräta flikar](/help/adaptive-forms/components/horizontal-tabs.md)
- [Bild](/help/adaptive-forms/components/image.md)
- [Nummerindata](/help/adaptive-forms/components/number-input.md)
- [Alternativknapp](/help/adaptive-forms/components/radio-button.md)
- [Återställ knapp](/help/adaptive-forms/components/reset-button.md)
- [Skicka-knapp](/help/adaptive-forms/components/submit-button.md)
- [Telefonindata](/help/adaptive-forms/components/telephone-input.md)
- [Textindata](/help/adaptive-forms/components/text-input.md)
- [Text](/help/adaptive-forms/components/text.md)
- [Titel](/help/adaptive-forms/components/title.md)
- [guide](/help/adaptive-forms/components/wizard.md)


## Se även {#see-also}

- [Skapa ett AEM anpassat formulär](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)
- [Lägg till ett AEM anpassat formulär på AEM Sites-sidan](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html)
- [Använda teman i ett AEM anpassat formulär](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-themes-in-core-components.html)
- [Lägga till komponenter i ett AEM adaptivt formulär](/help/adaptive-forms/introduction.md#adaptive-forms-core-components-components)
- [Använd reCAPTCHA i en AEM adaptiv form](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/add-components-to-an-adaptive-form/captcha-adaptive-forms.html)
- [Generera PDF-version (DoR) av ett AEM adaptivt formulär](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/generate-document-of-record-core-components.html)
- [Översätt en AEM adaptiv form](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-aem-translation-workflow-to-localize-adaptive-forms-core-components.html)
- [Aktivera Adobe Analytics för ett adaptivt formulär för att spåra formuläranvändning](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/integrate/services/enable-adobe-analytics-adaptive-form-using-experience-cloud-setup-automation.html)
- [Ansluta anpassat formulär till Microsoft SharePoint](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html#create-sharepoint-configuration)
- [Ansluta anpassat formulär till Microsoft Power Automate](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html#microsoft-power-automate)
- [Ansluta anpassat formulär till Microsoft OneDrive](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html#submit-to-onedrive)
- [Ansluta anpassat formulär till Microsoft Azure Blob Storage](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html#submit-to-azure-blob-storage)
- [Ansluta anpassat formulär till Salesforce](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/integrate/use-form-data-model/oauth2-client-credentials-flow-for-server-to-server-integration.html)
- [Använda Adobe Sign i en AEM anpassad form](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/use-adobe-sign/working-with-adobe-sign.html)
- [Lägga till en ny språkinställning för ett adaptivt formulär](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/supporting-new-language-localization-core-components.html)
- [Skicka adaptiva formulärdata till en databas](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/integrate/use-form-data-model/data-integration.html)
- [Skicka data för anpassat formulär till en REST-slutpunkt](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html#submit-to-rest-endpoint)
- [Skicka anpassade formulärdata till AEM arbetsflöde](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html#invoke-an-aem-workflow)
- [Använd Forms Portal för att lista AEM Adaptive Forms på en AEM webbplats](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/configure-forms-portal.html)

