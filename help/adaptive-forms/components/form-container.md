---
title: Adaptiv Forms Core-komponent - formulärbehållare
description: Lägg till ett anpassat formulär på en webbsida.
role: Architect, Developer, Admin, User
exl-id: 03c4cf7c-51d6-4850-a566-1c0514d52dab
source-git-commit: 7862206660909b396cb3d95b7ac81eee9221957b
workflow-type: tm+mt
source-wordcount: '1339'
ht-degree: 0%

---

# Formulärbehållare {#form-container-adaptive-forms-core-component}

Med Forms kan besökare interagera med webbplatsen genom att tillhandahålla värdefull information, vilket kan öka engagemanget och få nöjdare användare. Med en adaptiv formulärbehållare i Adobe Experience Manager (AEM) kan webbplatsägare enkelt lägga till formulär på sina sidor. Detta underlättar kommunikationen mellan webbplatsens besökare och webbplatsens ägare eller organisation genom att ge besökarna ett smidigt sätt att ge feedback, ställa frågor och slutföra andra åtgärder

## Användning {#reasons-to-use-forms-container}

Det finns flera orsaker till varför ett formulär kan läggas till på en webbplats:

- **Datainsamling**: Forms kan användas för att samla in data från webbplatsbesökare för olika syften, t.ex. marknadsundersökningar, användarbeteendeanalyser och annat.

- **Leadgenerering**: Ett formulär kan användas för att samla in information från potentiella kunder, som namn och e-postadress, för att generera leads för försäljning och marknadsföring.

- **E-handel**: Forms kan användas för webbutik där kunderna kan lägga order och göra betalningar via webbplatsen.

- **Kontakt**: Med ett kontaktformulär kan besökarna enkelt nå ut till webbplatsens ägare eller organisation.

- **Undersökningar och undersökningar**: Forms kan användas för att samla in feedback och åsikter från besökare via enkäter och undersökningar.

- **Händelseregistrering**: Forms kan användas för anmälan av evenemang, så att besökare kan anmäla sig till event eller webbinarier.

- **Prenumerationer**: Forms kan användas för webbplatsprenumerationer så att besökare kan registrera sig för ett nyhetsbrev eller annan vanlig kommunikation.

- **Användarautentisering**: Forms kan användas för användarautentisering, vilket gör att webbplatsbesökare kan skapa konton och logga in för att få tillgång till exklusivt innehåll eller funktioner.

- **Öka konverteringsgraden**: Ett väldesignat formulär kan öka konverteringsgraden genom att göra det enkelt för användarna att slutföra en önskad åtgärd, som att köpa en produkt eller registrera sig för en tjänst.


## Version och kompatibilitet {#version-and-compatibility}

Den adaptiva Forms Accordion Core-komponenten släpptes i februari 2023 som en del av Core Components 2.0.4 för Cloud Service och Core Components 1.1.12 för AEM 6.5.16.0 Forms eller senare. Här är en tabell med alla versioner som stöds, AEM kompatibilitet och länkar till motsvarande dokumentation:

| Komponentversion | AEM as a Cloud Service | AEM 6.5.16.0 Forms eller senare |
|---|---|---|
| v1 | Kompatibel med<br>[version 2.0.4](/help/adaptive-forms/version.md) och senare | Kompatibel med<br>[version 1.1.12](/help/adaptive-forms/version.md) och senare men mindre än 2.0.0. |

Mer information om versioner och versioner av kärnkomponenter finns i [Huvudkomponentversioner](/help/adaptive-forms/version.md) -dokument.
<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Teknisk information {#technical-details}

Den senaste informationen om den adaptiva Forms Container Core Component finns i den tekniska dokumentationen om [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/container/v1/container). Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Du kan enkelt anpassa formulärbehållarupplevelsen för besökare med dialogrutan Konfigurera. Du kan också enkelt definiera alternativ för formulärbehållare för en smidig användarupplevelse.

### Fliken Grundläggande {#basic-tab}

![fliken Grundläggande](/help/adaptive-forms/assets/formcontainer_basictab.png)

- **Titel** - Med dess titel kan du enkelt identifiera en komponent i ett formulär. Som standard visas titeln ovanpå komponenten. Om du inte lägger till en titel visas komponentens namn i stället för rubriktexten.

- **Förifyllning** - Med det här alternativet kan användaren välja en förifyllningstjänst för att hämta data när det adaptiva formuläret återges. Läs mer om [skapa och konfigurera en förifyllningstjänst](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/prepopulate-adaptive-form-fields.html?lang=en#aem-forms-custom-prefill-service).

- **Kategorin Klientbibliotek** - Användaren kan konfigurera ett anpassat JavaScript-bibliotek per adaptiv form. Vi rekommenderar att du bara behåller återanvändbara funktioner i biblioteket, som är beroende av jquery- och underscore.js-bibliotek från tredje part.
Ibland, om det finns **komplexa valideringsregler**, det exakta valideringsskriptet finns i anpassade funktioner och användarna anropar dessa anpassade funktioner från fältvalideringsuttryck. Om du vill att det här anpassade funktionsbiblioteket ska vara känt och tillgängligt vid validering på serversidan kan formuläranvändaren konfigurera namnet på AEM klientbibliotek under **[!UICONTROL Basic]** fliken med egenskaper för adaptiv formulärbehållare så som visas nedan.

Användaren kan konfigurera customJavaScript-bibliotek per adaptiv form. I biblioteket behåller du bara återanvändbara funktioner som är beroende av jquery- och underscore.js-bibliotek från tredje part.

### Fliken Datamodell {#data-model-tab}

![Fliken Skicka](/help/adaptive-forms/assets/formcontainer_fdmtab.png)

Du kan använda formulärdatamodellen för att ansluta ett formulär till en datakälla för att skicka och ta emot data baserat på användaråtgärder. Du kan också ansluta ett formulär till ett JSON-schema för att ta emot skickade data i ett fördefinierat format. Beroende på vad som krävs kan du ansluta formuläret till ett JSON-schema eller en formulärdatamodell:
- Skapa ett JSON-schema och överför det till din miljö
- Skapa en formulärdatamodell

### Fliken Skicka {#submission-tab}

Användare kan konfigurera olika åtgärder för att skicka adaptiva formulär.

- **Omdirigerings-URL/sökväg** - Med det här alternativet kan användaren konfigurera en sida för varje formulär som formuläranvändarna omdirigeras till efter att ha skickat in ett adaptivt formulär. Klicka här för mer information om [konfigurera omdirigeringssidor](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-redirect-page.html).

![Fliken Skicka](/help/adaptive-forms/assets/formcontainer_submissiontab.png)

- **Visa meddelande** - Med det här alternativet kan användare lägga till ett meddelande som visas när det adaptiva formuläret har skickats. Den fördefinierade texten tas med i dialogrutan och kan ändras av användaren. Dialogrutan Visa meddelande har stöd för formateringsverktyg med formaterad text som gör att användare kan formatera den tillagda texten.

![Visa fliken Meddelande](/help/adaptive-forms/assets/formconatiner_showmessage.png)

- **Skicka åtgärd** - En Skicka-åtgärd aktiveras när en användare klickar på Skicka-knappen på ett anpassat formulär. Användarna kan välja Skicka åtgärder i listrutan som stöds direkt. Lär dig hur [konfigurera en Skicka-åtgärd på fliken Skicka](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#supporting-custom-functions-in-validation-expressions-br).

## Designdialogruta {#design-dialog}

Designdialogrutan används för att definiera och hantera CSS-format för komponenten Formulärbehållare.

### Fliken Tillåtna komponenter {#allowed-components-tab}

![Tillåten komponentflik i designdialogrutan](/help/adaptive-forms/assets/formcontainer-allowedcomponents.png)

The **Tillåtna komponenter** kan mallredigeraren ange vilka komponenter som kan läggas till som objekt på panelerna i komponenten i den adaptiva Forms-redigeraren.

### Fliken Standardkomponenter {#default-components-tab}

![Standardkomponentflik i designdialogrutan](/help/adaptive-forms/assets/formcontainer-defaultcomponents.png)

The **Standardkomponenter** kan mallredigeraren ange vilka komponenter som är synliga som standard som objekt i formulärbehållarkomponenten i den adaptiva Forms-redigeraren.

### Fliken Responsiva inställningar {#responsive-tab}

![Fliken Responsiva inställningar i designdialogrutan](/help/adaptive-forms/assets/formcontainer-responsivestyle.png)

The **Responsiva inställningar** kan mallredigeraren ange antalet kolumner i rutnätet i formulärbehållarkomponenten i den adaptiva Forms-redigeraren.

### Fliken Format {#styles-tab}

Kärnkomponenten för adaptiv bifogad Forms-fil stöder AEM [Formatsystem](/help/get-started/authoring.md#component-styling).

![Designdialogruta](/help/adaptive-forms/assets/formcontainer-styletab.png)

- **CSS-standardklasser**: Du kan ange en standard-CSS-klass för den adaptiva Forms Form Container Core Component.

- **Tillåtna format**: Du kan definiera format genom att ange ett namn och den CSS-klass som representerar formatet. Du kan till exempel skapa ett format med namnet&quot;bold text&quot; och ge CSS-klassen&quot;font-weight: bold&quot;. Du kan använda eller tillämpa dessa format på ett adaptivt formulär i en anpassad Forms-redigerare. Om du vill använda ett format väljer du den komponent du vill använda formatet på i Adaptiv Forms-redigerare, navigerar till egenskapsdialogrutan och väljer önskat format i dialogrutan **Stilar** listruta. Om du behöver uppdatera eller ändra formaten går du tillbaka till designdialogrutan, uppdaterar formaten på formatfliken och sparar ändringarna.

### Fliken Anpassade egenskaper

![Dialogrutan Anpassade egenskaper](/help/adaptive-forms/assets/formcontainer-custompropertiestab.png)

Med anpassade egenskaper kan du koppla anpassade attribut (nyckelvärdepar) till en anpassad formulärets kärnkomponent med hjälp av formulärmallen. De anpassade egenskaperna återspeglas i egenskapsavsnittet i den headless-renderingen av komponenten. Det gör att du kan skapa dynamiskt formulärbeteende som anpassas baserat på anpassade attributvärden. Utvecklare kan till exempel utforma olika renderingar av en Headless Forms-komponent för mobiler, datorer eller webbplattformar, vilket avsevärt förbättrar användarupplevelsen på en mängd olika enheter.

- **Gruppnamn**: Du kan ange ett namn som identifierar den anpassade egenskapsgruppen. Du kan lägga till, ta bort eller ordna om flera anpassade egenskapsgrupper. När du har lagt till den anpassade egenskapsgruppen kan du se följande alternativ:

   - **Nyckelvärdepar**: Du kan lägga till flera anpassade egenskapsnamn och anpassade egenskapsvärden genom att klicka på **Lägg till** för varje anpassad egenskapsgrupp.

   - **Ta bort**: Tryck eller klicka för att ta bort det anpassade egenskapsnamnet och det anpassade egenskapsvärdet.

   - **Ordna om**: Tryck eller klicka och dra för att ändra ordningen på det anpassade egenskapsnamnet och det anpassade egenskapsvärdet.

<!--

## Related article {#related-article}

* [Create a standalone Adaptive Form](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)

-->

## Relaterade artiklar {#related-articles}

{{more-like-this}}

## Se även {#see-also}

{{see-also}}