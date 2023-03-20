---
title: Adaptiv Forms Core-komponent - formulärbehållare
description: Lägg till ett anpassat formulär på en webbsida.
role: Architect, Developer, Admin, User
source-git-commit: d2a6108f17f6e0c6b91bec84893d64a8bd48effd
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 0%

---


# Formulärbehållare {#form-container-adaptive-forms-core-component}

Med Forms kan besökare interagera med webbplatsen genom att tillhandahålla värdefull information, vilket kan öka engagemanget och få nöjdare användare. Med en adaptiv formulärbehållare i Adobe Experience Manager (AEM) kan webbplatsägare enkelt lägga till formulär på sina sidor. Detta underlättar kommunikationen mellan webbplatsens besökare och webbplatsens ägare eller organisation genom att ge besökarna ett smidigt sätt att ge feedback, ställa frågor och slutföra andra åtgärder

## Användning {#reasons-to-use-forms-container}

Det finns flera orsaker till varför ett formulär kan läggas till på en webbplats:

* **Datainsamling**: Forms kan användas för att samla in data från webbplatsbesökare för olika syften, t.ex. marknadsundersökningar, användarbeteendeanalyser och annat.

* **Leadgenerering**: Ett formulär kan användas för att samla in information från potentiella kunder, som namn och e-postadress, för att generera leads för försäljning och marknadsföring.

* **E-handel**: Forms kan användas för webbutik där kunderna kan lägga order och göra betalningar via webbplatsen.

* **Kontakt**: Med ett kontaktformulär kan besökarna enkelt nå ut till webbplatsens ägare eller organisation.

* **Undersökningar och undersökningar**: Forms kan användas för att samla in feedback och åsikter från besökare via enkäter och enkäter.

* **Händelseregistrering**: Forms kan användas för anmälan av event, vilket gör att besökare kan anmäla sig till event eller webbinarier.

* **Prenumerationer**: Forms kan användas för webbplatsprenumerationer så att besökare kan registrera sig för ett nyhetsbrev eller annan vanlig kommunikation.

* **Användarautentisering**: Forms kan användas för användarautentisering, vilket gör att webbplatsbesökare kan skapa konton och logga in för att få tillgång till exklusivt innehåll eller funktioner.

* **Öka konverteringsgraden**: Ett väldesignat formulär kan öka konverteringsgraden genom att göra det enkelt för användarna att slutföra en önskad åtgärd, som att köpa en produkt eller registrera sig för en tjänst.


## Version och kompatibilitet {#version-and-compatibility}

Den adaptiva Forms Accordion Core-komponenten släpptes i februari 2023 som en del av Core Components 2.0.4 för Cloud Service och Core Components 1.1.12 för AEM 6.5.16.0 Forms eller senare. Här är en tabell med alla versioner som stöds, AEM kompatibilitet och länkar till motsvarande dokumentation:

| Komponentversion | AEM as a Cloud Service | AEM 6.5.16.0 Forms eller senare |
|---|---|---|
| v1 | Kompatibel med<br>[version 2.0.4](/help/adaptive-forms/version.md) och senare | Kompatibel med<br>[version 1.1.12](/help/adaptive-forms/version.md) och senare men mindre än 2.0.0. |

Information om versioner och versioner av kärnkomponenter finns i [Huvudkomponentversioner](/help/adaptive-forms/version.md) -dokument.
<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Teknisk information {#technical-details}

Den senaste informationen om den adaptiva Forms Container Core Component finns i den tekniska dokumentationen om [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/container/v1/container). Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Du kan enkelt anpassa formulärbehållarupplevelsen för besökare med dialogrutan Konfigurera. Du kan också enkelt definiera alternativ för formulärbehållare för en smidig användarupplevelse.

### Fliken Grundläggande {#basic-tab}

![Fliken Grundläggande](/help/adaptive-forms/assets/formcontainer_basictab.png)

* **Förifyllning** - Med det här alternativet kan användaren välja en förifyllningstjänst för att hämta data när det adaptiva formuläret återges. Läs mer om [skapa och konfigurera en förifyllningstjänst](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/prepopulate-adaptive-form-fields.html?lang=en#aem-forms-custom-prefill-service).

* **Kategorin Klientbibliotek** - Användaren kan konfigurera ett anpassat JavaScript-bibliotek per adaptiv form. Vi rekommenderar att du bara behåller återanvändbara funktioner i biblioteket, som är beroende av jquery- och underscore.js-bibliotek från tredje part.

### Fliken Skicka {#submission-tab}

![Fliken Skicka](/help/adaptive-forms/assets/formcontainer_submissiontab.png)

Användare kan konfigurera olika åtgärder för att skicka adaptiva formulär.

* **Omdirigerings-URL/sökväg** - Med det här alternativet kan användaren konfigurera en sida för varje formulär som formuläranvändarna omdirigeras till efter att ha skickat in ett adaptivt formulär. Klicka här för mer information om [konfigurera omdirigeringssidor](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-redirect-page.html).

![Visa fliken Meddelande](/help/adaptive-forms/assets/formconatiner_showmessage.png)

* **Visa meddelande** - Med det här alternativet kan användare lägga till ett meddelande som visas när det adaptiva formuläret har skickats. Den fördefinierade texten tas med i dialogrutan och kan ändras av användaren. Dialogrutan Visa meddelande har stöd för formateringsverktyg med formaterad text som gör att användare kan formatera den tillagda texten.

* **Skicka åtgärd** - En Skicka-åtgärd aktiveras när en användare klickar på Skicka-knappen på ett anpassat formulär. Användarna kan välja Skicka åtgärder i listrutan som stöds direkt. Lär dig hur [konfigurera en Skicka-åtgärd på fliken Skicka](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#supporting-custom-functions-in-validation-expressions-br).
