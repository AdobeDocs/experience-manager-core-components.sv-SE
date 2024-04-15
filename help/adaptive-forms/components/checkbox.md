---
title: Adaptiv Forms Core-komponent - kryssruta
description: Använda eller anpassa den adaptiva Forms Checkbox Core-komponenten.
role: Architect, Developer, Admin, User
exl-id: c6ca4800-bd10-4aeb-957a-fb1780cf94f3
source-git-commit: e843ccf5c030cd4f1015e3290347b5799828537a
workflow-type: tm+mt
source-wordcount: '1780'
ht-degree: 0%

---

# Kryssrutekomponent{#checkbox-component}

<span class="preview"> Den här artikeln innehåller innehåll om **Tillåt RTF-text för rubrik** en förhandsversion. Förhandsversionen är bara tillgänglig via vår [kanal för förhandsversion](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/release-notes/prerelease.html#new-features).</span>

En kryssruta är ett grafiskt element i användargränssnittet som ofta används i program och formulär för att användaren ska kunna göra ett binärt val mellan två alternativ: markerad (markerad) eller avmarkerad (avmarkerad).

En kryssruta representeras vanligtvis som en liten fyrkant som du kan aktivera eller inaktivera genom att klicka eller trycka på den. När en kryssruta är markerad visas en bockmarkering som visar att det associerade alternativet eller den associerade funktionen är aktiv eller aktiverad.

>[!NOTE]
>
> För AEM 6.5 Forms introducerades denna komponent i AEM 6.5 Forms Service Pack 19 (6.5.19.0). Om du vill aktivera den här komponenten kontrollerar du att de nödvändiga versionerna av både Forms Core Components och WCM Core Components är installerade. Detaljerad information om releaserna av adaptiva Forms Core-komponenter finns i [Adaptiva versioner av Forms Core Components](/help/adaptive-forms/version.md)

**Exempel**

![kryssrutegrupp](/help/adaptive-forms/assets/checkbox-example.png)

## Användning {#reasons-to-use-checkbox}

De vanligaste skälen att använda kryssrutan i ett anpassat formulär är:

- **Lätt att använda**: Kryssrutor är visuellt tydliga och är ett enkelt sätt att göra binära val. De är intuitiva och lätta att förstå och gör dem användarvänliga.

- **Godkännande och avtal**: Kryssrutor används för att få användarens samtycke för olika syften, till exempel för att acceptera villkor, prenumerera på nyhetsbrev eller för att bekräfta ålder. De klargör att användaren aktivt samtycker till något.

- **Visuell bekräftelse**: Kryssrutor ger en visuell bekräftelse på att användaren har registrerat sitt val. Denna feedback hjälper till att förhindra användarfel och säkerställer att de vet att deras val har registrerats.

- **Felförebyggande**: Kryssrutor minskar risken för fel genom att användarna kan granska och bekräfta alternativen innan formuläret skickas.

## Version och kompatibilitet {#version-and-compatibility}

Kärnkomponenten i den adaptiva Forms-kryssrutan släpptes som en del av Core Components 2.0.52. Här är en tabell med alla versioner som stöds, AEM kompatibilitet och länkar till motsvarande dokumentation:

|  |  |
|---|---|
| Komponentversion | AEM as a Cloud Service |
| — | — |
| v1 | Kompatibel med<br>[version 2.0.52](/help/adaptive-forms/version.md) och senare | Kompatibel | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i [Huvudkomponentversioner](/help/adaptive-forms/version.md) -dokument.

## Teknisk information {#technical-details}

Hämta den senaste informationen om kärnkomponenten i den adaptiva Forms-kryssrutan i den tekniska dokumentationen om [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/checkbox/v1/checkbox). Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Du kan enkelt anpassa kryssruteupplevelsen för besökare med dialogrutan Konfigurera. Du kan också enkelt definiera kryssrutealternativ för en smidig användarupplevelse.

![fliken Grundläggande](/help/adaptive-forms/assets/checkbox-basic.png)

- **Namn** - Du kan enkelt identifiera en formulärkomponent med dess unika namn både i formuläret och i regelredigeraren, men namnet får inte innehålla blanksteg eller specialtecken.

- **Titel** - Med dess titel kan du enkelt identifiera en komponent i ett formulär. Som standard visas titeln bredvid komponenten. Om du inte lägger till en titel visas inte komponenten.

- **Tillåt RTF-text för rubrik** - Med den här funktionen kan användare formatera vanliga texttitlar med funktioner som fet, kursiv, understruken text, olika teckensnitt, teckenstorlekar, färger och ytterligare alternativ för att förbättra visuell presentation och anpassning. Det ger större flexibilitet och kreativ kontroll när det gäller att få titlar att sticka ut i dokument, på webbplatser och i tillämpningar.\
  När du markerar kryssrutan för **Tillåt RTF-text för rubrik** blir formateringsalternativen synliga för att formatera komponentens titel. Om du vill visa alla tillgängliga formateringsalternativ klickar du på ![Helskärmsikon](/help/adaptive-forms/assets/fullscreen-icon.png) -fliken.

  ![Stöd för RTF](/help/adaptive-forms/assets/richtext-support-title.png)

- **Dölj titel** - Välj alternativet om du vill dölja komponentens titel.

- **Bindningsreferens** - En bind referens är en referens till ett dataelement som lagras i en extern datakälla och används i ett formulär. Med den binda referensen kan du binda data dynamiskt till formulärfält så att formuläret kan visa de senaste data från datakällan. En bindningsreferens kan till exempel användas för att visa en kunds namn och adress i ett formulär baserat på kundens ID som anges i formuläret. Bindningsreferensen kan också användas för att uppdatera datakällan med data som anges i formuläret. På så sätt kan du med AEM Forms skapa formulär som interagerar med externa datakällor, vilket ger en smidig användarupplevelse för att samla in och hantera data.

- **Markera som obundet formulärelement**: Välj alternativet att konfigurera ett formulärfält som inte är länkat till något schema. Med det här alternativet kan du spara data utan att uppdatera datakällan. Det gör det också möjligt att hantera data på ett anpassat sätt, skilt från standarddatabasintegrering.

- **Datatyp för skickat värde**: Det här alternativet anger datatypen för det värde som skickas när något alternativ är markerat. Om **datatyp för skickat värde** är inställd på `Number` och du lägger till strängdata i **Datavärde** &#x200B; &#x200B; på **Alternativ** visas en `Value type mismatch` felmeddelande.

- **Dölj komponent** - Välj alternativet att dölja komponenten från formuläret. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren. Detta är användbart när du behöver lagra information som inte behöver visas eller ändras direkt av användaren.

- **Inaktivera komponent** - Välj alternativet att inaktivera eller låsa komponenten. Den inaktiverade komponenten är inte aktiv eller redigerbar av slutanvändaren. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.
  <!-- - **Read-only** - Select the option to make the component non-editable. The user can see the value of the field but cannot modify it. The component remains accessible for other purposes, such as using it for calculations in the Rule Editor.-->
- **Vid markering, returvärde** -Välj det här alternativet om du vill ange vilket värde som ska associeras med kryssrutan när den är markerad eller markerad. Det är den åtgärd som inträffar när du markerar eller kryssar i kryssrutan.
- **Bevara omarkerat lägesvärde**- Välj det här alternativet om du vill ange vilket värde som ska returneras när kryssrutekomponenten inte är markerad. If **Bevara omarkerat lägesvärde** är aktiverad eller inställd på true, **Vid avmarkering, returvärde** visas.
- **Vid avmarkering, returvärde** - Med det här alternativet kan du ange vilket värde som ska associeras med kryssrutan när den är omarkerad eller avmarkerad.

- **Standardvärde**: Med det här alternativet kan du lägga till ett standardvärde i ett formulärfält. If **Inaktiverad komponent** eller **Skrivskyddad komponent** är markerat visas standardvärdet på skärmen. Om användaren inte anger något värde i formulärfältet skickas det här värdet när formuläret skickas.

### Fliken Validering {#validation-tab}

![Fliken Validering](/help/adaptive-forms/assets/checkbox-validation.png)

- **Obligatoriskt** - Välj det här alternativet om du vill visa komponenten i ett adaptivt formulär. När du har valt alternativet måste du göra ett val innan du kan fortsätta med en formuläröverföring. Du kan inte välja **Dölj komponent** eller **Inaktivera komponent**  i **Grundläggande** när det här alternativet är markerat.

- **Felmeddelande** - Med det här alternativet kan du ange ett meddelande som visas om **Obligatoriskt** kryssrutan är markerad och formulärfältet är tomt.
- **Skriptverifieringsmeddelande** - Med det här alternativet kan du ange ett meddelande som ska visas om skriptvalideringen misslyckas.

### Fliken Hjälpinnehåll {#helpcontent-tab}

![Fliken Hjälpinnehåll](/help/adaptive-forms/assets/checkbox-help.png)

- **Kort beskrivning** - En kort beskrivning är en kort textförklaring som ger ytterligare information eller förtydliganden om syftet med ett visst formulärfält. Det hjälper användaren att förstå vilken typ av data som ska anges i fältet och kan ge riktlinjer eller exempel som hjälper till att säkerställa att den angivna informationen är giltig och uppfyller de önskade kriterierna. Som standard är korta beskrivningar dolda. Aktivera **Visa alltid kort beskrivning** för att visa den under komponenten.

- **Visa alltid kort beskrivning** - Aktivera alternativet att visa den korta beskrivningen under komponenten.

- **Hjälptext** - Hjälptexten hänvisar till ytterligare information eller vägledning som användaren får för att hjälpa sig fylla i ett formulärfält på rätt sätt. Det visas när användaren klickar på hjälpikonen (i) som finns bredvid komponenten. Hjälptexten ger mer detaljerad information än etiketten eller platshållartexten för ett formulärfält och är utformad för att hjälpa användaren förstå fältets krav eller begränsningar. Den kan också ge förslag eller exempel som gör det enklare och exaktare att fylla i formuläret.

### Fliken Tillgänglighet {#accessibility-tab}

![Fliken Tillgänglighet](/help/adaptive-forms/assets/checkbox-accessibility.png)

**Text för skärmläsare** - Text för skärmläsare avser text som är avsedd att läsas av hjälpmedelstekniker, t.ex. skärmläsare, som används av personer med nedsatt syn. Den här texten innehåller en ljudbeskrivning av formulärfältets syfte och kan innehålla information om fältets titel, beskrivning, namn och relevanta meddelanden (anpassad text). Skärmläsartexten ser till att formuläret är tillgängligt för alla användare, även användare med nedsatt syn, och ger dem en fullständig förståelse för formulärfältet och dess krav.

## Designdialogruta {#design-dialog}

Designdialogrutan används för att definiera och hantera CSS-format för Check-box-komponenten.

### Fliken Format {#styles-tab}

Kärnkomponenten i den adaptiva Forms-kryssrutan stöder AEM [Formatsystem](/help/get-started/authoring.md#component-styling).

![Designdialogruta](/help/adaptive-forms/assets/checkbox-style.png)

- **CSS-standardklasser**: Du kan ange en standard-CSS-klass för kärnkomponenten i den adaptiva Forms-kryssrutan.

- **Tillåtna format**: Du kan definiera format genom att ange ett namn och den CSS-klass som representerar formatet. Du kan till exempel skapa ett format med namnet&quot;bold text&quot; och ge CSS-klassen&quot;font-weight: bold&quot;. Du kan använda eller tillämpa dessa format på ett adaptivt formulär i en anpassad Forms-redigerare. Om du vill använda ett format väljer du den komponent du vill använda formatet på i Adaptiv Forms-redigerare, navigerar till egenskapsdialogrutan och väljer önskat format i dialogrutan **Stilar** listruta. Om du behöver uppdatera eller ändra formaten går du tillbaka till designdialogrutan, uppdaterar formaten på formatfliken och sparar ändringarna.

### Anpassade egenskaper

![Dialogrutan Anpassade egenskaper](/help/adaptive-forms/assets/checkbox-customproperties.png)

Med anpassade egenskaper kan du koppla anpassade attribut (nyckelvärdepar) till en anpassad formulärets kärnkomponent med hjälp av formulärmallen. De anpassade egenskaperna återspeglas i egenskapsavsnittet i den headless-renderingen av komponenten. Det gör att du kan skapa dynamiskt formulärbeteende som anpassas baserat på anpassade attributvärden. Utvecklare kan till exempel utforma olika renderingar av en Headless Forms-komponent för mobiler, datorer eller webbplattformar, vilket avsevärt förbättrar användarupplevelsen på en mängd olika enheter.

- **Gruppnamn**: Du kan ange ett namn som identifierar den anpassade egenskapsgruppen. Du kan lägga till, ta bort eller ordna om flera anpassade egenskapsgrupper. När du har lagt till den anpassade egenskapsgruppen kan du se följande alternativ:

   - **Nyckelvärdepar**: Du kan lägga till flera anpassade egenskapsnamn och anpassade egenskapsvärden genom att klicka på **Lägg till** för varje anpassad egenskapsgrupp.

   - **Ta bort**: Tryck eller klicka för att ta bort det anpassade egenskapsnamnet och det anpassade egenskapsvärdet.

   - **Ordna om**: Tryck eller klicka och dra för att ändra ordningen på det anpassade egenskapsnamnet och det anpassade egenskapsvärdet.

## Relaterade artiklar {#related-articles}

{{more-like-this}}

## Se även {#see-also}

{{see-also}}
