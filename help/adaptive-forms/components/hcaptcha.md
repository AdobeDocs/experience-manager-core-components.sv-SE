---
title: Kaptcha i AEM Adaptiv Forms
description: Förbättra formulärsäkerheten med Captcha&reg; service utan problem. Stegvisa anvisningar inifrån!
feature-set: Experience Manager Sites, Experience Manager Forms
feature: Adaptive Forms, Core Components
role: Architect, Developer, Admin, User
source-git-commit: 9a691fc2aa656f5a96d8cd4b6285e6bd473cdaa4
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 0%

---

# hCaptcha-komponent{#hCaptcha-component-adaptive-forms-core-component}

<span class="preview"> Den här funktionen är under Tidiga Adobe-program. Du kan skriva till aem-forms-ea@adobe.com från ditt officiella e-post-id för att gå med i det tidiga adopterprogrammet och begära åtkomst till funktionen. </span>

Med tjänsten Captcha® kan du skydda dina formulär från stötar, skräppost och automatiskt missbruk. Det utgör en utmaning för kryssrutewidgeten och utvärderar användarens svar för att avgöra om det är en människa eller en robot som interagerar med formuläret. Det förhindrar användaren att fortsätta om testet misslyckas och gör onlinetransaktionerna säkra genom att förhindra att skräppost eller skadliga aktiviteter publiceras.

![hCaptcha®](/help/adaptive-forms/assets/hCaptcha-challenge.png)

## Användning {#usage}

Det finns många skäl till att det är bra att ta med en Captcha-utmaning i en formulärinlämningsprocess:

- **Punktförebyggande**: Den ser till att formuläret skickas av en människa, vilket minskar risken för skräppost och automatiserade överföringar.

- **Säkerhet**: Den lägger till ett extra säkerhetsskikt som verifierar legitimiteten hos varje formulärsändning och skyddar mot skadliga attacker.

- **Dataintegritet**: Genom att förhindra flera eller bedrägliga överföringar kan det bevara integriteten och exaktheten hos de data som samlas in via formuläret.

- **Användarverifiering**: Identiteten hos användaren som skickar formuläret verifieras, så att bara autentiserade användare kan slutföra känsliga transaktioner.

- **Belastningshantering**: Den hjälper till att hantera serverinläsningen genom att styra hastigheten för formuläröverföringar och förhindra systemöverbelastning under höga trafikperioder.

## Teknisk information {#technical-details}

Hämta den senaste informationen om hCaptcha-komponenten i den tekniska dokumentationen för [GitHub](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/hCaptcha/v1/hCaptcha/README.md). Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).

Ange egenskaperna för Capture-komponenten med hjälp av dialogrutan [Konfigurera](#configure-dialog). Dialogrutan Konfigurera är en del av de centrala komponenterna som gör det enkelt att skapa formulären och som är ett effektivt sätt att skapa komplexa formulär.

## Version och kompatibilitet {#version-and-compatibility}


Den adaptiva Forms Captcha-komponenten släpptes i maj 2024 som en del av [Core Components 3.0.20](https://github.com/adobe/aem-core-forms-components/commit/a4cb97131ffad47137a8f5f173401128a1cf3491). Här är en tabell med alla versioner som stöds, AEM kompatibilitet och länkar till motsvarande dokumentation:

|  |  |
|---|---|
| Komponentversion | AEM as a Cloud Service |
| — | — |
| v1 | Kompatibel med <br>[version 2.0.4](/help/adaptive-forms/version.md) och senare | Kompatibel | Kompatibel |

Information om versioner och versioner av kärnkomponenter finns i dokumentet [Core Components Versions](/help/adaptive-forms/version.md) .

## Konfigurera dialogruta {#configure-dialog}

Du kan enkelt anpassa egenskaperna för din hCaptcha-komponent med hjälp av dialogrutan Konfigurera som har fliken Grundläggande och fliken Validering för att anpassa olika egenskaper.

### Fliken Grundläggande {#basic-tab}

- **[!UICONTROL Name]:** Ange namnet på din hCaptcha-komponent. Du kan enkelt identifiera en formulärkomponent med dess unika namn både i formuläret och i regelredigeraren.
- **[!UICONTROL Title]:** Ange titeln för din hCaptcha-komponent.
- **[!UICONTROL Configuration Settings]:** Välj en molnkonfiguration som har konfigurerats för hCaptcha®.
- **Captcha-storlek:** Du kan välja visningsstorlek för utmaningsdialogrutan hCaptcha®. Använd alternativet **[!UICONTROL Compact]** om du vill visa en liten storlek och alternativet **[!UICONTROL Normal]** om du vill visa en relativt stor hCaptcha®-utmaningsdialogruta.<!-- or **[!UICONTROL Invisible]** to validate hCaptcha&reg; without explicitly rendering the checkbox widget on the user interface. -->

  ![hCaptcha Basic Tab](/help/adaptive-forms/assets/hcaptcha-basic.png)

### Fliken Validering {#validation-tab}

- **[!UICONTROL Validation Message]:** Ange ett valideringsmeddelande för din Captcha-validering när formuläret skickas.
- **[!UICONTROL Script Validation Message]** - Använd det här alternativet om du vill ange ett meddelande om skriptvalideringen misslyckas.

  ![hCaptcha-valideringsflik](/help/adaptive-forms/assets/hcaptcha-validation-tab.png)

**hCaptcha® är ett registrerat varumärke som tillhör Intuition Machines, Inc.**

**Lär dig mer** om andra **Captcha-komponenter** och deras tjänster, till exempel:

- [Använd hCaptcha i ett adaptivt formulär för kärnkomponenter](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/integrate-adaptive-forms-hcaptcha-core-components)

- [Använd hCaptcha i ett adaptivt formulär för Foundation-komponenter](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/add-components-to-an-adaptive-form/integrate-adaptive-forms-hcaptcha)

- [Använd Turnstile CAPTCHA i ett adaptivt formulär för Foundation-komponenter](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/add-components-to-an-adaptive-form/integrate-adaptive-forms-turnstile)

- [Använd Google reCAPTCHA i ett adaptivt formulär för Foundation-komponenter](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/captcha-adaptive-forms-core-components)

## Relaterade artiklar {#related-articles}

{{more-like-this}}

## Se även {#see-also}

{{see-also}}
