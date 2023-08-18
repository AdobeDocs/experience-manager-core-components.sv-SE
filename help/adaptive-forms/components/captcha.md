---
title: Adaptiv Forms Core-komponent - formulärbehållare
description: Lägg till ett anpassat formulär på en webbsida.
role: Architect, Developer, Admin, User
hide: true
hidefromtoc: true
source-git-commit: 8db061f3d6f1041336c379b34f3b6b7f03083560
workflow-type: tm+mt
source-wordcount: '723'
ht-degree: 1%

---


# Google reCPATCHA {#google-recaptcha}

CAPTCHA (Completely Automated Public Turing test to tell Computers and Humans Apart) är ett program som ofta används vid onlinetransaktioner för att skilja mellan människor och automatiserade program eller organ. Det utgör en utmaning och utvärderar användarens svar för att avgöra om det är en människa eller en robot som interagerar med webbplatsen. Det förhindrar användaren att fortsätta om testet misslyckas och gör onlinetransaktionerna säkra genom att förhindra att skräppost eller skadliga syften publiceras.

AEM Forms as a Cloud Service stöder Google reCAPTCHA v2 i Adaptiv Forms. Du kan använda den för att presentera en CAPTCHA-utmaning när du skickar in formulär

## Användning {#reasons-to-use-google-recaptcha}


- **Spam and Bot Prevention**: Ett av de främsta skälen att använda reCAPTCHA är att förhindra att skräppost och skadliga bottar översvämmar ditt formulär. reCAPTCHA:s avancerade algoritmer kan upptäcka automatiska försök att skicka formuläret, vilket säkerställer att endast berättigade användare kan interagera med det.

- **Förbättrat skydd**: Genom att implementera reCAPTCHA lägger du till ett extra säkerhetslager i det anpassade formuläret. Detta bidrar till att skydda känslig information och förhindra att obehöriga använder säkerhetsluckor.

- **Användarupplevelse**: Även om CAPTCHA ibland kan ses som ett besvär innebär reCAPTCHA:s adaptiva metod att de flesta användare får en smidig, användarvänlig upplevelse som kräver minimal interaktion. Detta kan bidra till att upprätthålla en positiv användarupplevelse samtidigt som man fortfarande avvärjer robotar.

- **Anpassningsbar**: reCAPTCHA:s adaptiva mekanism analyserar användarbeteende och interaktioner för att avgöra om de är mänskliga eller inte. Detta innebär att den grad av utmaning som användaren får kan variera beroende på sannolikheten att de är en robot. Denna anpassningsbarhet minskar friktionen för äkta användare samtidigt som säkerheten bibehålls.

- **Minskad manuell moderering**: Genom att avsevärt minska antalet skräppost och robotgenererat innehåll kan reCAPTCHA spara tid och resurser som annars skulle spenderas på manuell moderering och rensning.

## Version och kompatibilitet {#version-and-compatibility}

Den adaptiva Forms Google reCAPTCHA Core-komponenten släpptes i augusti 2023 som en del av Core Components &#39;version&#39;. Här är en tabell med alla versioner som stöds, AEM kompatibilitet och länkar till motsvarande dokumentation:

|  |  |
|---|---|
| Komponentversion | AEM as a Cloud Service |
| — | --- |
| v1 | Kompatibel med<br>[version 2.0.4](/help/versions.md) och senare | Kompatibel | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i [Huvudkomponentversioner](/help/versions.md) -dokument.

## Teknisk information {#technical-details}

Den senaste informationen om den adaptiva Forms Google reCAPTCHA Core Component finns i den tekniska dokumentationen om [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/recaptcha/v1/recaptcha). Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Du kan enkelt anpassa Google reCAPTCHA-upplevelsen för besökare med dialogrutan Konfigurera. Du kan också enkelt definiera Google reCAPTCHA-alternativ för en smidig användarupplevelse.

### Fliken Grundläggande {#basic-tab}

- **Namn** - Du kan enkelt identifiera en formulärkomponent med dess unika namn både i formuläret och i regelredigeraren, men namnet får inte innehålla blanksteg eller specialtecken.

- **Titel** - Med dess titel kan du enkelt identifiera en komponent i ett formulär. Som standard visas titeln ovanpå komponenten. Om du inte lägger till en titel visas komponentens namn i stället för rubriktexten.

- **Dölj titel** - Välj alternativet om du vill dölja komponentens titel.

- **Konfiguration** -

- **Typ** -

- **Dölj komponent** - Välj alternativet att dölja komponenten från formuläret. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren. Detta är användbart när du behöver lagra information som inte behöver visas eller ändras direkt av användaren.

- **Inaktivera komponent** - Välj alternativet att inaktivera komponenten. Den inaktiverade komponenten är inte aktiv eller redigerbar av slutanvändaren. Data för den inaktiverade komponenten skickas inte. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.

- **Skrivskyddad** - Välj alternativet att göra komponenten icke-redigerbar. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.

### Fliken Validering {#validation-tab}

- **Felmeddelande** - Med det här alternativet kan du ange ett meddelande som visas om **Obligatoriskt** kryssrutan är markerad och formulärfältet är tomt.

