---
title: Adaptiv Forms Core-komponent - formulärbehållare
description: Lägg till ett anpassat formulär på en webbsida.
role: Architect, Developer, Admin, User
hide: true
hidefromtoc: true
exl-id: 1e413ef3-7a6f-41fc-825d-dbe09ebaffe9
source-git-commit: e843ccf5c030cd4f1015e3290347b5799828537a
workflow-type: tm+mt
source-wordcount: '869'
ht-degree: 0%

---

# Google reCPATCHA {#google-recaptcha}

CAPTCHA (Completely Automated Public Turing test to tell Computers and Humans Apart) är ett program som ofta används vid onlinetransaktioner för att skilja mellan människor och automatiserade program eller organ. Det utgör en utmaning och utvärderar användarens svar för att avgöra om det är en människa eller en robot som interagerar med webbplatsen. Det förhindrar användaren att fortsätta om testet misslyckas och gör onlinetransaktionerna säkra genom att förhindra att skräppost eller skadliga syften publiceras.

AEM Forms as a Cloud Service stöder Google reCAPTCHA v2 i Adaptiv Forms. Du kan använda den för att presentera en CAPTCHA-utmaning när du skickar in formulär

## Användning {#reasons-to-use-google-recaptcha}

- **Spam and Bot Prevention**: En av de främsta anledningarna till att använda reCAPTCHA är att förhindra att skräppost och skadliga bottar översvämmar ditt formulär. reCAPTCHA:s avancerade algoritmer kan upptäcka automatiska försök att skicka formuläret, vilket säkerställer att endast berättigade användare kan interagera med det.

- **Förbättrat skydd**: Genom att implementera reCAPTCHA lägger du till ett extra säkerhetslager i det anpassade formuläret. Detta bidrar till att skydda känslig information och förhindra att obehöriga använder säkerhetsluckor.

- **Användarupplevelse**: Även om CAPTCHA ibland kan ses som ett besvär innebär ReCAPTCHA:s adaptiva metod att de flesta användare får en smidig, användarvänlig upplevelse som kräver minimal interaktion. Detta kan bidra till att upprätthålla en positiv användarupplevelse samtidigt som man fortfarande avvärjer robotar.

- **Anpassningsbarhet**: reCAPTCHA:s adaptiva mekanism analyserar användarbeteende och interaktioner för att avgöra om de är mänskliga eller inte. Detta innebär att den grad av utmaning som användaren får kan variera beroende på sannolikheten att de är en robot. Denna anpassningsbarhet minskar friktionen för äkta användare samtidigt som säkerheten bibehålls.

- **Reducerad manuell moderering**: Genom att avsevärt minska antalet skräppost och robotgenererat innehåll kan reCAPTCHA spara tid och resurser som annars skulle ha använts för manuell moderering och rensning.

## Version och kompatibilitet {#version-and-compatibility}

Den adaptiva Forms Google reCAPTCHA Core-komponenten släpptes i augusti 2023 som en del av Core Components &#39;version&#39;. Här är en tabell med alla versioner som stöds, AEM kompatibilitet och länkar till motsvarande dokumentation:


|  |  |
|---|---|
| Komponentversion | AEM as a Cloud Service |
| — | — |
| v1 | Kompatibel med <br>[version 2.0.4](/help/versions.md) och senare | Kompatibel | Kompatibel |

Information om versioner och versioner av kärnkomponenter finns i dokumentet [Core Components Versions](/help/versions.md) .

## Teknisk information {#technical-details}

Hämta den senaste informationen om den adaptiva Forms Google reCAPTCHA Core-komponenten i den tekniska dokumentationen för [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/recaptcha/v1/recaptcha). Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Du kan enkelt anpassa Google reCAPTCHA-upplevelsen för besökare med dialogrutan Konfigurera. Du kan också enkelt definiera Google reCAPTCHA-alternativ för en smidig användarupplevelse.

### Fliken Grundläggande {#basic-tab}

- **Namn** - Du kan enkelt identifiera en formulärkomponent med dess unika namn både i formuläret och i regelredigeraren, men namnet får inte innehålla blanksteg eller specialtecken.

- **Titel** - Med titeln kan du enkelt identifiera en komponent i ett formulär. Som standard visas titeln ovanpå komponenten. Om du inte lägger till en titel visas komponentens namn i stället för rubriktexten.

- **Dölj titel** - Välj alternativet för att dölja komponentens titel.

- **Konfiguration** -

- **Typ** -

- **Dölj komponent** - Välj alternativet att dölja komponenten från formuläret. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren. Detta är användbart när du behöver lagra information som inte behöver visas eller ändras direkt av användaren.

- **Inaktivera komponent** - Välj alternativet att inaktivera komponenten. Den inaktiverade komponenten är inte aktiv eller redigerbar av slutanvändaren. Data för den inaktiverade komponenten skickas inte. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.

- **Skrivskyddad** - Välj alternativet för att göra komponenten icke-redigerbar. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.

### Fliken Validering {#validation-tab}

- **Felmeddelande** - Med det här alternativet kan du ange ett meddelande som visas om kryssrutan **Obligatorisk** är markerad och formulärfältet lämnas tomt.

## Se även {#see-also}

- [Skapa ett AEM anpassat formulär](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)
- [Lägg till ett AEM anpassat formulär på AEM Sites-sidan](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html)
- [Använd teman i ett AEM anpassat formulär](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-themes-in-core-components.html)
- [Lägga till komponenter i ett AEM adaptivt formulär](/help/adaptive-forms/introduction.md#adaptive-forms-core-components-components)
- [Använd reCAPTCHA i ett AEM anpassat formulär](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/add-components-to-an-adaptive-form/captcha-adaptive-forms.html)
- [Generera PDF-version (DoR) av ett AEM anpassat formulär](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/generate-document-of-record-core-components.html)
- [Översätt ett AEM anpassat formulär](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-aem-translation-workflow-to-localize-adaptive-forms-core-components.html)
- [Aktivera Adobe Analytics för ett adaptivt formulär för att spåra formuläranvändning](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/integrate/services/enable-adobe-analytics-adaptive-form-using-experience-cloud-setup-automation.html)
- [Ansluta anpassat formulär till Microsoft SharePoint](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html#create-sharepoint-configuration)
- [Ansluta anpassat formulär till Microsoft Power Automate](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html#microsoft-power-automate)
- [Ansluta anpassat formulär till Microsoft OneDrive](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html#submit-to-onedrive)
- [Ansluta anpassat formulär till Microsoft Azure Blob Storage](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html#submit-to-azure-blob-storage)
- [Ansluta anpassat formulär till Salesforce](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/integrate/use-form-data-model/oauth2-client-credentials-flow-for-server-to-server-integration.html)
- [Använd Adobe Sign i ett AEM anpassat formulär](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/use-adobe-sign/working-with-adobe-sign.html)
- [Lägg till en ny språkinställning för ett adaptivt formulär](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/supporting-new-language-localization-core-components.html)
- [Skicka adaptiva formulärdata till en databas](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/integrate/use-form-data-model/data-integration.html)
- [Skicka data för anpassat formulär till en REST-slutpunkt](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html#submit-to-rest-endpoint)
- [Skicka anpassade formulärdata AEM arbetsflödet](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html#invoke-an-aem-workflow)
- [Använd Forms Portal för att lista AEM Adaptiv Forms på en AEM webbplats](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/configure-forms-portal.html)

