---
title: Adaptiv Forms Core-komponent - Google reCAPTCHA
description: Förbättra säkerheten med Google reCAPTCHA-tjänsten utan problem med AEM Forms. Förklara egenskaperna för den adaptiva formen reCaptcha
role: Architect, Developer, Admin, User
exl-id: 2d986b90-e596-4e8f-9a32-0ebced5461c8
source-git-commit: 6725784bd4c94d433c91d6bd65d14d03cbefd954
workflow-type: tm+mt
source-wordcount: '1325'
ht-degree: 0%

---


# Adaptiv form reCAPTCHA {#google-recaptcha}

CAPTCHA (Completely Automated Public Turing Test to tell Computers and Humans Apart) är ett program som ofta används vid onlinetransaktioner för att skilja mellan människor och automatiserade program eller organ. Det utgör en utmaning och utvärderar användarens svar för att avgöra om det är en människa eller en robot som interagerar med webbplatsen. Det förhindrar användaren att fortsätta om testet misslyckas och gör onlinetransaktionerna säkra genom att förhindra att skräppost eller skadliga syften publiceras.

AEM Forms as a Cloud Service stöder Google reCAPTCHA v2 i Adaptiv Forms. Du kan använda den för att presentera en CAPTCHA-utmaning när du skickar in formulär

{{traditional-aem}}

## Användning {#reasons-to-use-google-recaptcha}


- **Spam and Bot Prevention**: En av de främsta anledningarna till att använda reCAPTCHA är att förhindra att skräppost och skadliga bottar översvämmar ditt formulär. reCAPTCHA:s avancerade algoritmer kan upptäcka automatiska försök att skicka formuläret, vilket säkerställer att endast berättigade användare kan interagera med det.

- **Förbättrat skydd**: Genom att implementera reCAPTCHA lägger du till ett extra säkerhetslager i det anpassade formuläret. Detta bidrar till att skydda känslig information och förhindra att obehöriga använder säkerhetsluckor.

- **Användarupplevelse**: Även om CAPTCHA ibland kan ses som ett besvär innebär ReCAPTCHA:s adaptiva metod att de flesta användare får en smidig, användarvänlig upplevelse som kräver minimal interaktion. Detta kan bidra till att upprätthålla en positiv användarupplevelse samtidigt som man fortfarande avvärjer robotar.

- **Anpassningsbarhet**: reCAPTCHA:s adaptiva mekanism analyserar användarbeteende och interaktioner för att avgöra om de är mänskliga eller inte. Detta innebär att den grad av utmaning som användaren får kan variera beroende på sannolikheten att de är en robot. Denna anpassningsbarhet minskar friktionen för äkta användare samtidigt som säkerheten bibehålls.

- **Reducerad manuell moderering**: Genom att avsevärt minska antalet skräppost och robotgenererat innehåll kan reCAPTCHA spara tid och resurser som annars skulle ha använts för manuell moderering och rensning.

## Version och kompatibilitet {#version-and-compatibility}

Den adaptiva Forms Google reCAPTCHA Core-komponenten släpptes i augusti 2023 som en del av Core Components &#39;version&#39;. Här är en tabell som visar alla versioner som stöds, kompatibiliteten med AEM och länkar till motsvarande dokumentation:


| Komponentversion | AEM as a Cloud Service |
|--- |--- |
| v1 | Kompatibel med <br>[version 2.0.4](/help/versions.md) och senare | Kompatibel | Kompatibel |

Information om versioner och versioner av kärnkomponenter finns i dokumentet [Core Components Versions](/help/versions.md) .

## Teknisk information {#technical-details}

Hämta den senaste informationen om den adaptiva Forms Google reCAPTCHA Core-komponenten i den tekniska dokumentationen för [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/recaptcha/v1/recaptcha). Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Du kan enkelt anpassa Google reCAPTCHA-upplevelsen för besökare med dialogrutan Konfigurera. Du kan också enkelt definiera Google reCAPTCHA-alternativ för en smidig användarupplevelse.

### Fliken Grundläggande {#basic-tab}

![Grundläggande flik](/help/adaptive-forms/assets/recaptcha-basictab.png)

- **Namn** - Du kan enkelt identifiera en formulärkomponent med dess unika namn både i formuläret och i regelredigeraren, men namnet får inte innehålla blanksteg eller specialtecken.

- **Titel** - Med titeln kan du enkelt identifiera en komponent i ett formulär. Som standard visas titeln ovanpå komponenten. Om du inte lägger till en titel visas komponentens namn i stället för rubriktexten.

- **Tillåt RTF-text för rubrik** - Med den här funktionen kan användare formatera oformaterad text med funktioner som fet, kursiv, understruken text, olika teckensnitt, teckenstorlekar, färger och ytterligare alternativ för att förbättra visuell presentation och anpassning. Det ger större flexibilitet och kreativ kontroll när det gäller att få titlar att sticka ut i dokument, på webbplatser och i tillämpningar.\
  När du markerar kryssrutan för **Tillåt RTF för rubrik, visas formateringsalternativen för att formatera komponentens rubrik. Om du vill visa alla tillgängliga formateringsalternativ klickar du på fliken ![Helskärmsikon](/help/adaptive-forms/assets/fullscreen-icon.png) .

  ![RTF-stöd](/help/adaptive-forms/assets/richtext-support-title.png)

- **Dölj titel** - Välj alternativet för att dölja komponentens titel.
- **Markera som obundet formulärelement**: Välj alternativet att konfigurera ett formulärfält som inte är länkat till något schema. Med det här alternativet kan du spara data utan att uppdatera datakällan. Det gör det också möjligt att hantera data på ett anpassat sätt, skilt från standarddatabasintegrering.
- **Konfigurationsinställningar**: Välj den konfigurationsbehållare som innehåller molnkonfigurationen som ansluter AEM Forms med reCAPTCHA-tjänsten från Google.

  >[!NOTE]
  >
  > Läs artikeln [Use Google reCAPTCHA in an AEM Adaptive Form based on Core Components](https://experienceleague.adobe.com/sv/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/captcha-adaptive-forms-core-components) om du vill veta mer om hur du skapar och konfigurerar Google reCAPTCHA för din miljö.

- **Typ**: Välj det här alternativet om du vill välja storlek för reCAPTCHA.
   - **Normal**: Avser den större standardversionen av reCAPTCHA-widgeten, som kan vara mer synlig och lättare att interagera med, särskilt på enheter med större skärmar.
   - **Kompakt**: Avser en mindre version av reCAPTCHA-widgeten. Det här alternativet är lämpligt i situationer där utrymmet är begränsat, t.ex. på mobila enheter eller i nära layouter på webbsidor.

- **Dölj komponent** - Välj alternativet att dölja komponenten från formuläret. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren. Detta är användbart när du behöver lagra information som inte behöver visas eller ändras direkt av användaren.

- **Inaktivera komponent** - Välj alternativet att inaktivera komponenten. Den inaktiverade komponenten är inte aktiv eller redigerbar av slutanvändaren. Data för den inaktiverade komponenten skickas inte. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.

- **Skrivskyddad** - Välj alternativet för att göra komponenten icke-redigerbar. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.

### Fliken Validering {#validation-tab}

![Fliken Validering](/help/adaptive-forms/assets/recaptcha-validationtab.png)

- **Felmeddelande** - Med det här alternativet kan du ange ett meddelande som visas om kryssrutan **Obligatorisk** är markerad och formulärfältet lämnas tomt.

- **Skriptvalideringsmeddelande** - Med det här alternativet kan du ange ett meddelande som ska visas om skriptvalideringen misslyckas.

## Designdialogruta {#design-dialog}

Designdialogrutan används för att definiera och hantera CSS-format för komponenten reCAPTCHA.

### Fliken Format {#styles-design-tab}

Den adaptiva Forms reCAPTCHA Core-komponenten stöder AEM [Style System](/help/get-started/authoring.md#component-styling).

![Designdialogrutan](/help/adaptive-forms/assets/checkbox-style.png)

- **Standard-CSS-klasser**: Du kan ange en standard-CSS-klass för den adaptiva Forms reCAPTCHA-kärnkomponenten.

- **Tillåtna format**: Du kan definiera format genom att ange ett namn och den CSS-klass som representerar formatet. Du kan till exempel skapa ett format med namnet&quot;bold text&quot; och ge CSS-klassen&quot;font-weight: bold&quot;. Du kan använda eller tillämpa dessa format på ett adaptivt formulär i en anpassad Forms-redigerare. Om du vill använda ett format väljer du den komponent du vill använda formatet på i Adaptiv Forms-redigerare, navigerar till egenskapsdialogrutan och väljer önskat format i listrutan **Format**. Om du behöver uppdatera eller ändra formaten går du tillbaka till designdialogrutan, uppdaterar formaten på formatfliken och sparar ändringarna.

### Anpassade egenskaper

![Dialogrutan Anpassade egenskaper](/help/adaptive-forms/assets/checkbox-customproperties.png)

Med anpassade egenskaper kan du associera anpassade attribut (nyckelvärdepar) till en huvudkomponent för adaptiva formulär med hjälp av formulärmallen. De anpassade egenskaperna återspeglas i egenskapsavsnittet i den headless-renderingen av komponenten. Det gör att du kan skapa dynamiskt formulärbeteende som anpassas baserat på anpassade attributvärden. Utvecklare kan till exempel utforma olika renderingar av en Headless Forms-komponent för mobiler, datorer eller webbplattformar, vilket avsevärt förbättrar användarupplevelsen på en mängd olika enheter.
- **Gruppnamn**: Du kan ange ett namn som identifierar den anpassade egenskapsgruppen. Du kan lägga till, ta bort eller ordna om flera anpassade egenskapsgrupper. När du har lagt till den anpassade egenskapsgruppen kan du se följande alternativ:

   - **Nyckelvärdepar**: Du kan lägga till flera anpassade egenskapsnamn och anpassade egenskapsvärden genom att klicka på knappen **Lägg till** för varje anpassad egenskapsgrupp.

   - **Ta bort**: Tryck eller klicka för att ta bort det anpassade egenskapsnamnet och det anpassade egenskapsvärdet.

   - **Ordna om**: Tryck eller klicka och dra för att ordna om det anpassade egenskapsnamnet och det anpassade egenskapsvärdet.


## Relaterade artiklar {#related-articles}

{{more-like-this}}

## Se även {#see-also}

{{see-also}}
