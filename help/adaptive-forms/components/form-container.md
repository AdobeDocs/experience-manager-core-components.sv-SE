---
title: Adaptiv Forms Core-komponent - formulärbehållare
description: Lägg till ett anpassat formulär på en webbsida.
role: Architect, Developer, Admin, User
exl-id: 03c4cf7c-51d6-4850-a566-1c0514d52dab
source-git-commit: 6725784bd4c94d433c91d6bd65d14d03cbefd954
workflow-type: tm+mt
source-wordcount: '1523'
ht-degree: 0%

---


# Formulärbehållare {#form-container-adaptive-forms-core-component}

<span class="preview"> I den här artikeln beskrivs funktionen **Utkast** <!--and **Hamburger Menu Support** --> , som är en förhandsversion. Förhandsversionen är bara tillgänglig via vår [förhandsutgåva](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/release-notes/prerelease.html?lang=sv-SE#new-features).</span>

Med Forms kan besökare interagera med webbplatsen genom att tillhandahålla värdefull information, vilket kan öka engagemanget och få nöjdare användare. Med en adaptiv formulärbehållare i Adobe Experience Manager (AEM) kan webbplatsägare enkelt lägga till formulär på sina sidor. Detta underlättar kommunikationen mellan webbplatsens besökare och webbplatsens ägare eller organisation genom att ge besökarna ett smidigt sätt att ge feedback, ställa frågor och slutföra andra åtgärder

{{traditional-aem}}

## Användning {#reasons-to-use-forms-container}

Det finns flera orsaker till varför ett formulär kan läggas till på en webbplats:
- **Datainsamling**: Forms kan användas för att samla in data från webbplatsbesökare för olika syften, till exempel marknadsundersökning, användarbeteendeanalys och mycket annat.

- **Leadgenerering**: Ett formulär kan användas för att samla in information från potentiella kunder, som namn och e-postadress, för att generera leads för försäljning och marknadsföring.

- **E-handel**: Forms kan användas för onlineförsäljning, vilket gör att kunderna kan göra beställningar och göra betalningar via webbplatsen.

- **Kontakt**: Med ett kontaktformulär kan webbplatsbesökare enkelt kontakta webbplatsens ägare eller organisation.

- **Undersökningar och undersökningar**: Forms kan användas för att samla in feedback och åsikter från webbplatsbesökare via undersökningar och undersökningar.

- **Händelseregistrering**: Forms kan användas för händelseregistrering så att webbplatsbesökare kan registrera sig för event eller webbinarier.

- **Prenumerationer**: Forms kan användas för webbplatsprenumerationer så att besökare kan registrera sig för ett nyhetsbrev eller annan vanlig kommunikation.

- **Användarautentisering**: Forms kan användas för användarautentisering, vilket gör att webbplatsbesökare kan skapa konton och logga in för att få tillgång till exklusivt innehåll eller exklusiva funktioner.

- **Öka konverteringsgraden**: Ett väldesignat formulär kan öka konverteringsgraden genom att göra det enkelt för användarna att utföra en önskad åtgärd, som att köpa en produkt eller registrera sig för en tjänst.

## Version och kompatibilitet {#version-and-compatibility}

Den adaptiva Forms Accordion Core-komponenten släpptes i februari 2023 som en del av Core Components 2.0.4 för Cloud Service och Core Components 1.1.12 för AEM 6.5.16.0 Forms eller senare. Här är en tabell som visar alla versioner som stöds, kompatibiliteten med AEM och länkar till motsvarande dokumentation:

| Komponentversion | AEM as a Cloud Service | AEM 6.5.16.0 Forms eller senare |
|---|---|---|
| v1 | Kompatibel med <br>[version 2.0.4](/help/adaptive-forms/version.md) och senare | Kompatibel med <br>[version 1.1.12](/help/adaptive-forms/version.md) och senare, men mindre än 2.0.0. |

Information om versioner och versioner av kärnkomponenter finns i dokumentet [Core Components Versions](/help/adaptive-forms/version.md) .
<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Teknisk information {#technical-details}

Hämta den senaste informationen om den adaptiva Forms Container Core-komponenten i den tekniska dokumentationen för [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/container/v1/container). Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Du kan enkelt anpassa formulärbehållarupplevelsen för besökare med dialogrutan Konfigurera. Du kan också enkelt definiera alternativ för formulärbehållare för en smidig användarupplevelse.

### Fliken Grundläggande {#basic-tab}

![Fliken Grundläggande](/help/adaptive-forms/assets/formcontainer_basictab1.png)

- **Titel** - Med titeln kan du enkelt identifiera en komponent i ett formulär. Som standard visas titeln ovanpå komponenten. Om du inte lägger till en titel visas komponentens namn i stället för rubriktexten.

- **Förifyll tjänster** - Med det här alternativet kan användaren välja en förifyllningstjänst för att hämta data när det adaptiva formuläret återges. Läs mer om [hur du skapar och konfigurerar en förifyllningstjänst](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/prepopulate-adaptive-form-fields.html?lang=sv-SE#aem-forms-custom-prefill-service).

- **Roll**: Rollen är ett HTML-attribut som används för att ange syftet med ett HTML-element för hjälpmedelstekniker som skärmläsare. Rollattributet används för att ge ytterligare kontext och semantisk innebörd till ett element, vilket gör det enklare för skärmläsare att tolka och meddela innehållet till användaren. I AEM Forms kan till exempel etiketten för ett formulärfält ha rollen&quot;label&quot;, och inmatningsfältet kan ha rollen&quot;texbox&quot;. Detta gör att skärmläsaren förstår förhållandet mellan etiketten och inmatningsfältet och kan meddela användaren dem på rätt sätt.

- **Klientbibliotekskategori** - Användaren kan konfigurera ett anpassat JavaScript-bibliotek per anpassat formulär. Vi rekommenderar att du bara behåller återanvändbara funktioner i biblioteket, som är beroende av jquery- och underscore.js-bibliotek från tredje part.
Ibland, om det finns **komplexa valideringsregler**, finns det exakta valideringsskriptet i anpassade funktioner och användarna anropar dessa anpassade funktioner från fältvalideringsuttryck. Om du vill att det här anpassade funktionsbiblioteket ska vara känt och tillgängligt vid validering på serversidan kan formuläranvändaren konfigurera namnet på AEM klientbibliotek på fliken **[!UICONTROL Basic]** i egenskaper för adaptiv formulärbehållare.
Användaren kan konfigurera customJavaScript-bibliotek per adaptiv form. I biblioteket behåller du bara återanvändbara funktioner som är beroende av jquery- och underscore.js-bibliotek från tredje part.

<!--
- **Enable the hamburger menu for mobile view** - Select the checkbox to integrate a hamburger menu into your form for mobile view. Represented by three horizontal lines stacked vertically, this menu provides a clear and uncluttered display for panels on smaller devices, especially on mobile devices. For more information about the hamburger menu, refer to the [Learn more about the hamburger menu](#learn-more-about-the-hamburger-menu) section. -->


### Fliken Datamodell {#data-model-tab}

![fliken Skicka](/help/adaptive-forms/assets/formcontainer_fdmtab.png)

Du kan använda formulärdatamodellen för att ansluta ett formulär till en Data Source för att skicka och ta emot data baserat på användaråtgärder. Du kan också ansluta ett formulär till ett JSON-schema för att ta emot skickade data i ett fördefinierat format. Beroende på vad som krävs kan du ansluta formuläret till ett JSON-schema eller en formulärdatamodell:
- Skapa ett JSON-schema och överför det till din miljö
- Skapa en formulärdatamodell

### Utkast

![fliken Skicka](/help/adaptive-forms/assets/formcontainer_autosavetab.png)

- **Spara utkast automatiskt**: Markera kryssrutan **Spara utkast automatiskt** om du vill kunna spara formulär som utkast.
- **Spara inställningar**: Konfigurera **Spara inställningar** som **Spara utkast med regelbundna intervall** om du vill spara formuläret automatiskt efter ett visst tidsintervall.
  **Spara intervallfrekvens (sekunder)**: Ange tidsintervallet (i sekunder) för att ange den längd som utlöser det automatiska sparandet av formuläret vid det definierade intervallet.

### Fliken Skicka {#submission-tab}

Användare kan konfigurera olika åtgärder för att skicka adaptiva formulär.

- **Omdirigerings-URL/sökväg** - Med det här alternativet kan användaren konfigurera en sida för varje formulär som formuläranvändarna omdirigeras till efter att ha skickat ett anpassat formulär. Klicka här för mer information om [hur du konfigurerar omdirigeringssidor](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-redirect-page.html?lang=sv-SE).

![fliken Skicka](/help/adaptive-forms/assets/formcontainer_submissiontab.png)

- **Visa meddelande** - Med det här alternativet kan användare lägga till ett meddelande som visas när det adaptiva formuläret har skickats. Den fördefinierade texten tas med i dialogrutan och kan ändras av användaren. Dialogrutan Visa meddelande har stöd för formateringsverktyg med formaterad text som gör att användare kan formatera den tillagda texten.

![Visa fliken Meddelande](/help/adaptive-forms/assets/formconatiner_showmessage.png)

- **Skicka åtgärd** - En Skicka-åtgärd utlöses när en användare klickar på Skicka-knappen i ett anpassat formulär. Användarna kan välja Skicka åtgärder i listrutan som stöds direkt. Lär dig hur du [konfigurerar en Skicka-åtgärd på fliken ](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html?lang=sv-SE#supporting-custom-functions-in-validation-expressions-br).

## Designdialogruta {#design-dialog}

Designdialogrutan används för att definiera och hantera CSS-format för komponenten Formulärbehållare.

### Fliken Tillåtna komponenter {#allowed-components-tab}

![Komponentfliken tillåts i designdialogrutan](/help/adaptive-forms/assets/formcontainer-allowedcomponents.png)

På fliken **Tillåtna komponenter** kan mallredigeraren ange vilka komponenter som kan läggas till som objekt på panelerna i komponenten i den adaptiva Forms-redigeraren.

### Fliken Standardkomponenter {#default-components-tab}

![Standardkomponentflik i designdialogrutan](/help/adaptive-forms/assets/formcontainer-defaultcomponents.png)

På fliken **Standardkomponenter** kan mallredigeraren ange vilka komponenter som är synliga som standard som objekt i formulärbehållarkomponenten i den adaptiva Forms-redigeraren.

### Fliken Responsiva inställningar {#responsive-tab}

![Fliken Responsiva inställningar i designdialogrutan](/help/adaptive-forms/assets/formcontainer-responsivestyle.png)

På fliken **Responsiva inställningar** kan mallredigeraren ange antalet kolumner i rutnätet i formulärbehållarkomponenten i den adaptiva Forms-redigeraren.

### Fliken Format {#styles-tab}

Kärnkomponenten för adaptiv bifogad Forms-fil stöder AEM [Style System](/help/get-started/authoring.md#component-styling).

![Designdialogrutan](/help/adaptive-forms/assets/formcontainer-styletab.png)

- **Standardklasser för CSS**: Du kan ange en standardklass för CSS för kärnkomponenten för den adaptiva Forms-formulärbehållaren.

- **Tillåtna format**: Du kan definiera format genom att ange ett namn och den CSS-klass som representerar formatet. Du kan till exempel skapa ett format med namnet&quot;bold text&quot; och ge CSS-klassen&quot;font-weight: bold&quot;. Du kan använda eller tillämpa dessa format på ett adaptivt formulär i en anpassad Forms-redigerare. Om du vill använda ett format väljer du den komponent du vill använda formatet på i Adaptiv Forms-redigerare, navigerar till egenskapsdialogrutan och väljer önskat format i listrutan **Format**. Om du behöver uppdatera eller ändra formaten går du tillbaka till designdialogrutan, uppdaterar formaten på formatfliken och sparar ändringarna.

### Fliken Anpassade egenskaper

![Dialogrutan Anpassade egenskaper](/help/adaptive-forms/assets/formcontainer-custompropertiestab.png)

Med anpassade egenskaper kan du koppla anpassade attribut (nyckelvärdepar) till en anpassad formulärets kärnkomponent med hjälp av formulärmallen. De anpassade egenskaperna återspeglas i egenskapsavsnittet i den headless-renderingen av komponenten. Det gör att du kan skapa dynamiskt formulärbeteende som anpassas baserat på anpassade attributvärden. Utvecklare kan till exempel utforma olika renderingar av en Headless Forms-komponent för mobiler, datorer eller webbplattformar, vilket avsevärt förbättrar användarupplevelsen på en mängd olika enheter.

- **Gruppnamn**: Du kan ange ett namn som identifierar den anpassade egenskapsgruppen. Du kan lägga till, ta bort eller ordna om flera anpassade egenskapsgrupper. När du har lagt till den anpassade egenskapsgruppen kan du se följande alternativ:

   - **Nyckelvärdepar**: Du kan lägga till flera anpassade egenskapsnamn och anpassade egenskapsvärden genom att klicka på knappen **Lägg till** för varje anpassad egenskapsgrupp.

   - **Ta bort**: Tryck eller klicka för att ta bort det anpassade egenskapsnamnet och det anpassade egenskapsvärdet.

   - **Ordna om**: Tryck eller klicka och dra för att ändra ordningen på det anpassade egenskapsnamnet och det anpassade egenskapsvärdet.

<!--
## Learn more about the hamburger menu

A hamburger menu, often referred to as a mobile menu or navigation drawer, is a popular design element in mobile user interfaces. It features three horizontal lines stacked vertically, resembling a hamburger. The design efficiently conserves screen space by hiding secondary navigation options until they are needed, especially on smaller devices such as mobile. AEM forms can be efficiently organized within the hamburger menu, enabling users to access various panels within a form without overwhelming the main interface.

Consider a scenario, where a financial institution offers an online loan application form that requires users to provide detailed information across several panels, such as personal details, financial information, loan preferences, and supporting documents. The form includes multiple panels and options that can clutter the interface, especially on mobile devices. Users need an organized way to navigate through these panels without feeling overwhelmed. The hamburger menu is implemented to enhance the user experience on mobile devices.

### Components of hamburger menu

![Hamburger Menu](/help/adaptive-forms/assets/hamburger-menu.png){width=50%, align=center}

**A. Hamburger menu**: The hamburger menu features a navigation panel that slides out or drops down when the hamburger icon is clicked or tapped. The menu displays the panel headings, and selecting a panel shifts the focus to that panel. It allows users to easily navigate between different panels.

![Hamburger Menu](/help/adaptive-forms/assets/hamburger-menu-icon.png){width=50%}

**B. Breadcrumb**: Breadcrumbs indicate the user’s current location within the form. They offer a hierarchical trail that shows the user’s navigation path and helps them understand their position in the form.

**C. Active panel**: The active panel refers to the section or part of the form that is currently being displayed. When a user selects an option from the hamburger menu, the corresponding panel becomes the active panel, showing the relevant fields and information for that section.

### Points to consider while working with the hamburger menu

- The hamburger menu displays only the names of the panels. Here are different scenarios illustrating how the panel name appears in the navigation pane of the hamburger menu based on the configuration properties of the panel:  
  
  - If you set the properties of the panel to hidden, the panel's name does not appear in the navigation pane of the hamburger menu. For example, if you configure the properties of the `Financial Information` panel as `hidden`, the panel name does not appear in the navigation pane of the hamburger menu.
    
    ![Hidden panel](/help/adaptive-forms/assets/hidden-panel.png){width=50%}

  - If you set the properties of the panel to `disabled`, its name appears in the navigation pane of the hamburger menu, but you cannot select or edit it. For example, if you configure the properties of the `Financial Information` panel as `disabled`, the panel name appears in the navigation pane, but it cannot be selected or edited. 
     
    ![Disabled panel](/help/adaptive-forms/assets/disabled-panel.png){width=50%}

  - If you hide the  title of the panel, it does not appear in the navigation pane of the hamburger menu. A blank space shows up instead, but you can navigate to the fields of the panel by clicking on that space. For example, if you hide the title of the `Financial Information` panel, the blank space appears in its place in the navigation pane of the hamburger menu. You can navigate to the fields of the panel by clicking on the blank space.
    
    ![Hidden title panel](/help/adaptive-forms/assets/hidden-title-panel.png){width=50%}

- By default, the navigation pane in the breadcrumb component supports up to three levels of navigation. However, with the custom component, you can configure the navigation hierarchy to accommodate as many levels as needed.
- When using the hamburger menu, the user can navigate between panels using arrows. However, once a panel is selected, the menu automatically closes, and focus shifts to the fields within the chosen panel.

### Advantages to use hamburger menu

- **Space efficiency**: By hiding form navigation options until needed, the hamburger menu maximizes screen space, which is especially beneficial on smaller devices.

- **Clutter reduction**: It minimizes visual clutter by consolidating various form navigation links into a single, collapsible menu.

- **Improved focus**: With fewer visible navigation elements, users can concentrate on the main content of the form without being distracted by secondary options.

- **Simplified design**: It creates a more streamlined user interface, resulting in a cleaner and more organized form layout.

- **Enhanced mobile experience**: On mobile devices, where screen space is limited, the hamburger menu offers an efficient way to access all form navigation options without overwhelming the user.

### How to enable hamburger menu for your form?

To enable hamburger menu for form, perform the following steps:

1. Open form in an edit mode.
1. Open the Content browser, and select the **[!UICONTROL Guide Container]** component of your Adaptive Form. 
1. Click the Guide Container properties ![Guide properties](/help/adaptive-forms/assets/configure_icon.png) icon. The Adaptive Form Container dialog box opens. 
1. Click the  **[!UICONTROL Basic]** tab. 
1. Select the **[!UICONTROL Add hamburger menu support]** checkbox.
1. Click **[!UICONTROL Done]**.

![Basic tab](/help/adaptive-forms/assets/formcontainer_basictab.png)
-->

## Relaterade artiklar {#related-articles}

{{more-like-this}}

## Se även {#see-also}

{{see-also}}