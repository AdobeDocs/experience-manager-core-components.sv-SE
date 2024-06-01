---
title: Kaptcha i AEM Adaptiv Forms
description: Förbättra formulärsäkerheten med Captcha&reg; utan problem. Stegvisa anvisningar inifrån!
feature-set: Experience Manager Sites, Experience Manager Forms
feature: Adaptive Forms, Core Components
role: Architect, Developer, Admin, User
source-git-commit: 08d44e4db42594fb5aaf33d7d42df6fe19c70f59
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 0%

---

# hCaptcha-komponent{#hCaptcha-component-adaptive-forms-core-component}

<span class="preview"> Den här funktionen ingår i Tidig Adobe-program. Du kan skriva till aem-forms-ea@adobe.com från ditt officiella e-post-id för att gå med i det tidiga adopterprogrammet och begära åtkomst till funktionen. </span>

Med tjänsten Captcha® kan du skydda dina formulär från stötar, skräppost och automatiskt missbruk. Det utgör en utmaning för kryssrutewidgeten och utvärderar användarens svar för att avgöra om det är en människa eller en robot som interagerar med formuläret. Det förhindrar användaren att fortsätta om testet misslyckas och gör onlinetransaktionerna säkra genom att förhindra att skräppost eller skadliga aktiviteter publiceras.

![hCaptcha®](/help/adaptive-forms/assets/hCaptcha-challenge.png)

## Användning {#usage}

Det finns många skäl till att det är bra att ta med en Captcha-utmaning i en formulärinlämningsprocess:

- **Punktförebyggande**: Det säkerställer att blanketten skickas in av en människa, vilket minskar risken för skräppost och automatiserade inlämningar.

- **Säkerhet**: Den lägger till ett extra säkerhetsskikt som verifierar legitimiteten hos varje inskickad blankett och skyddar mot skadliga attacker.

- **Dataintegritet**: Genom att förhindra att data skickas in flera gånger eller bedrägligt hjälper det till att bibehålla integriteten och exaktheten hos de data som samlas in via formuläret.

- **Användarverifiering**: Den verifierar identiteten på den användare som skickar formuläret och ser till att endast autentiserade användare kan slutföra känsliga transaktioner.

- **Läs in hantering**: Det hjälper till att hantera serverbelastningen genom att styra hastigheten för formulärinskickning, vilket förhindrar att systemet överbelastas under trafikperioder.

## Teknisk information {#technical-details}

Hämta den senaste informationen om hCaptcha-komponenten i den tekniska dokumentationen om [GitHub](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/hCaptcha/v1/hCaptcha/README.md). Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

Ange egenskaperna för hCaptcha-komponenten med hjälp av [konfigurera dialogruta](#configure-dialog). Dialogrutan Konfigurera är en del av de centrala komponenterna som gör det enkelt att skapa formulären och som är ett effektivt sätt att skapa komplexa formulär.

## Version och kompatibilitet {#version-and-compatibility}


Den adaptiva Forms Captcha-komponenten släpptes i maj 2024 som en del av [Kärnkomponenter 3.0.20](https://github.com/adobe/aem-core-forms-components/commit/a4cb97131ffad47137a8f5f173401128a1cf3491). Här är en tabell med alla versioner som stöds, AEM kompatibilitet och länkar till motsvarande dokumentation:

|  |  |
|---|---|
| Komponentversion | AEM as a Cloud Service |
| — | — |
| v1 | Kompatibel med<br>[version 2.0.4](/help/adaptive-forms/version.md) och senare | Kompatibel | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i [Huvudkomponentversioner](/help/adaptive-forms/version.md) -dokument.

## Konfigurera dialogruta {#configure-dialog}

Du kan enkelt anpassa egenskaperna för din hCaptcha-komponent med hjälp av dialogrutan Konfigurera som har fliken Grundläggande och fliken Validering för att anpassa olika egenskaper.

### Fliken Grundläggande {#basic-tab}

- **[!UICONTROL Name]:** Ange namnet på din hCaptcha-komponent. Du kan enkelt identifiera en formulärkomponent med dess unika namn både i formuläret och i regelredigeraren.
- **[!UICONTROL Title]:** Ange namnet på din hCaptcha-komponent.
- **[!UICONTROL Configuration Settings]:** Välj en molnkonfiguration som har konfigurerats för Captcha®.
- **Storlek:** Du kan välja visningsstorlek för dialogrutan för Captcha®-utmaning. Använd **[!UICONTROL Compact]** för att visa en liten storlek och **[!UICONTROL Normal]** för att visa en relativt stor hCaptcha®-utmaningsdialogruta.<!-- or **[!UICONTROL Invisible]** to validate hCaptcha&reg; without explicitly rendering the checkbox widget on the user interface. -->

  ![hCaptcha Basic Tab](/help/adaptive-forms/assets/hcaptcha-basic.png)

### Fliken Validering {#validation-tab}

- **[!UICONTROL Validation Message]:** Ange ett valideringsmeddelande för din Captcha-validering när formuläret skickas.
- **[!UICONTROL Script Validation Message]** - Använd det här alternativet för att ange ett meddelande om skriptvalideringen misslyckas.

  ![hCaptcha-valideringsflik](/help/adaptive-forms/assets/hcaptcha-validation-tab.png)

**Captcha® är ett registrerat varumärke som tillhör Intuition Machines, Inc.**

**Mer information** om andra **Captcha-komponenter** och deras tjänster, som

- [Använd hCaptcha i anpassad form för kärnkomponenter](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/integrate-adaptive-forms-hCaptcha-core-components)

- [Använd Captcha i ett adaptivt formulär för Foundation-komponenter](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/add-components-to-an-adaptive-form/integrate-adaptive-forms-hcaptcha)

- [Använd Turnstle CAPTCHA i ett adaptivt format för grundkomponenter](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/add-components-to-an-adaptive-form/integrate-adaptive-forms-turnstile)

- [Använd Google reCAPTCHA i ett adaptivt formulär för grundkomponenter](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/captcha-adaptive-forms-core-components)

## Relaterade artiklar {#related-articles}

{{more-like-this}}

## Se även {#see-also}

{{see-also}}