---
title: AEM Forms Core Components Versions
description: AEM kärnkomponenter publiceras som versioner som kan innehålla mer än en version av samma kärnkomponenter. I det här dokumentet förklaras vad som är releaser och versioner och hur man förstår kompatibiliteten med kärnkomponenter och AEM.
role: Architect, Developer, Admin, User
exl-id: 8146a5b1-acf6-4b54-ad6b-6e1747a137f6
source-git-commit: 5ba402a0f781f73fe7eb5afc9b4beb47ba28851e
workflow-type: tm+mt
source-wordcount: '879'
ht-degree: 0%

---

# Huvudkomponentversioner {#core-components-versions}

Den aktuella versionen av Core Components 2.0.10 är kompatibel med [AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html) och Core Components version 1.1.12 är kompatibel med [AEM 6.5 Form on Prestatione och AMS](https://experienceleague.adobe.com/docs/experience-manager-65/user-guide/home.html) installationer.

## AEM som versionshistorik för Cloud Service {#aem-as-cs-version-history}

I följande tabell visas en lista över de Core Components-versioner som är kompatibla med AEM as a Cloud Service och som är tillgängliga på [GitHub tillsammans med omfattande information om deras releaser](https://github.com/adobe/aem-core-forms-components/releases).

| Frigör | Beskrivning | AEM as a Cloud Service | Java™ | Releasedatum |
|---|---|---|---|---|
| [2.0.76](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.76) | I den här versionen är formatfliken och den anpassade egenskapsfliken fasta för villkorskomponenten. I den här versionen har även en komponent med alternativknappar korrigerats för att spara booleskt värde för första klicket. | Kontinuerlig | 8, 11 | 15 november 2023 |
| [2.0.74](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.74) | I den här versionen uppdateras ett inskickningsfel för åtgärden Skicka i AEM Forms. | Kontinuerlig | 8, 11 | 15 november 2023 |
| [2.0.70](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.70) | I den här versionen har stöd lagts till för att hantera webbplatssidspråket i formulärbehållaren. | Kontinuerlig | 8, 11 | 10 november 2023 |
| [2.0.64](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.64) | Stöd för formaterad text för etiketter för Radio- och kryssrutekomponenter. I den här versionen har även stöd för Switch-komponenten lagts till. Den här versionen innehåller även korrigeringar för villkorskomponenten och villkorskomponenten. | Kontinuerlig | 8, 11 | 6 november 2023 |
| [2.0.62](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.62) | I den här versionen har stöd för villkorskomponenten lagts till. Dessutom stöds kvalificerat namn i kärnkomponenterna. | Kontinuerlig | 8, 11 | 16 oktober 2023 |
| [2.0.60](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.60) | Den här versionen innehåller korrigeringar för anpassade egenskapsfunktioner, guiden och datumväljarkomponenten. | Kontinuerlig | 8, 11 | 12 september 2023 |
| [2.0.56](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.56) | I den här versionen har stöd för anpassade egenskaper för alla kärnkomponenter lagts till. | Kontinuerlig | 8, 11 | 12 september 2023 |
| [2.0.54](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.54) | Den här versionen åtgärdade problemet med lokalisering med datumväljarkomponenten. | Kontinuerlig | 8, 11 | 30 augusti 2023 |
| [2.0.52](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.52) | Stöd för att använda kryssrutekomponenter i ett adaptivt formulär. | Kontinuerlig | 8, 11 | 25 augusti 2023 |
| [2.0.50](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.50) | Stöd för formulärfragment i ett anpassat formulär har lagts till i den här versionen. | Kontinuerlig | 8, 11 | 4 augusti 2023 |
| [2.0.48](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.48) | De största förbättringarna i den här versionen har att göra med prestanda i Lightroom. | Kontinuerlig | 8, 11 | 25 juli 2023 |
| [2.0.42](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.42) | Versionen innehåller förbättringar i programslutet. | Kontinuerlig | 8, 11 | 18 juli 2023 |
| [2.0.38](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.38) | Tillgänglighetsfunktionen har förbättrats i den här versionen. | Kontinuerlig | 8, 11 | 17 juli 2023 |
| [2.0.36](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.36) | I den här versionen kan du använda den anpassade felhanteraren med regelredigerarens anropstjänst. | Kontinuerlig | 8, 11 | 3 juli 2023 |
| [2.0.34](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.34) | Lagt till stöd för lokalisering av standardfelmeddelanden tillsammans med knappen Lägg till/ta bort för komponenten Repetable. | Kontinuerlig | 8, 11 | 28 juni 2023 |
| [2.0.32](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.32) | I den här versionen finns stöd för Captcha för Adaptive Forms. | Kontinuerlig | 8, 11 | 15 juni 2023 |
| [2.0.26](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.26) | Stöd för att lägga till adaptiva formulär i AEM Sites. | Kontinuerlig | 8, 11 | 7 juni 2023 |
| [2.0.18](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.18) | I den här versionen finns stöd för repeterbarhet för dragspelskomponenten. En ny komponent har också lagts till som lodräta flikar. | Kontinuerlig | 8, 11 | 5 juni 2023 |
| [2.0.10](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.10) | I den här versionen finns det stöd för en komponent med adaptiv formulärbehållare i webbplatsredigeraren. | Kontinuerlig | 8, 11 | 17 mars 2023 |
| [2.0.8](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.8) | Repeteringsfunktionen för guidekomponenten introducerades i den här versionen. | Kontinuerlig | 8, 11 | 3 mars 2023 |
| [2.0.6](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.6) | Flera format för den numeriska indatastkärnkomponenten introducerades i den här versionen. | Kontinuerlig | 8, 11 | 8 februari 2023 |
| [2.0.4](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.6) | Komponentstöd för AEM as a Cloud Service introducerades i den här versionen. | Kontinuerlig | 8, 11 | 30 januari 2023 |

## AEM 6.5 Forms - versionshistorik {#aem-as-form-version-history}

I följande tabell visas en lista över de Core Components-versioner som är kompatibla med AEM 6.5 Form On Premise och AMS som finns på [GitHub tillsammans med omfattande information om deras releaser](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-1.1.12).

| Frigör | Beskrivning | AEM 6.4 | AEM 6.5 | Java™ | Releasedatum |
|---|---|---|---|---|---|
| [1.1.32](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-1.1.32) | Den här versionen uppdaterade informationen om paketet i AEM Service Pack 6.5.18.0. | - | 6.5.16.0+ | 8, 11 | 15 oktober 2023 |
| [1.1.28](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-1.1.28) | Stöd för formaterad text för etiketter för Radio- och kryssrutekomponenter. Den här versionen innehåller även stöd för komponenterna Terms and Condition och Switch. | - | 6.5.16.0+ | 8, 11 | 15 oktober 2023 |
| [1.1.26](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-1.1.26) | I den här versionen finns stöd för kryssrutekomponenter för adaptiva formulär och formulärfragment. Den innehåller även förbättringar av prestanda i Lightroom. Den anpassade felhanteraren med Regelredigerarens anropstjänst ingår också i den här versionen. | - | 6.5.16.0+ | 8, 11 | 15 oktober 2023 |
| [1.1.24](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-1.1.24) | Lagt till stöd för lokalisering av standardfelmeddelanden tillsammans med knappen Lägg till/ta bort för komponenten Repetable. Stöd för recaptcha har också lagts till i Adaptive Forms. | - | 6.5.16.0+ | 8, 11 | 29 juni 2023 |
| [1.1.22](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-1.1.22) | Stöd för att lägga till adaptiva formulär i AEM Sites. Fliken Objekt har lagts till i redigeringsdialogrutan för komponenten Wizard och Vertical Tabs. | - | 6.5.16.0+ | 8, 11 | 7 juni 2023 |
| [1.1.12](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-1.1.12) | Komponentstöd för AEM Forms lokalt och AMS introduceras i den här versionen. | - | 6.5.16.0+ | 8, 11 | 8 februari 2023 |

## Se även {#see-also}

{{see-also}}