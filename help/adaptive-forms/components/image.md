---
title: Adaptiv Forms Core-komponent - bild
description: Använda eller anpassa den adaptiva Forms Image Core-komponenten.
role: Architect, Developer, Admin, User
exl-id: 9ee42d5d-16e3-4973-8364-5bc512ebe72e
source-git-commit: 6725784bd4c94d433c91d6bd65d14d03cbefd954
workflow-type: tm+mt
source-wordcount: '1056'
ht-degree: 0%

---


# Bildkomponent{#image-adaptive-forms-core-component}

En bildkomponent i ett adaptivt formulär är ett sätt att inkludera bilder i ett formulär. Dessa bilder kan användas för att förbättra formulärets övergripande design, ge ytterligare information eller fungera som visuell hjälp för att hjälpa användarna förstå formulärets syfte. Bildkomponenten kan användas för att lägga till en logotyp, ett foto eller en bild i formuläret.

För hjälpmedel är det viktigt att ange **Alternativ text** till bilden för att ge bilden ett kort, beskrivande textalternativ som beskriver bilden för användare som inte kan se den.

{{traditional-aem}}

**Exempel**

![exempel](/help/adaptive-forms/assets/image.png)


## Användning {#reasons-to-use-image-in-a-form}

Det finns många skäl till att det är bra att ta med en bildkomponent i en adaptiv form, bland annat:

- **Varumärkning**: En bild kan användas för att visa logotypen eller namnet på den organisation som skapade formuläret, vilket bidrar till att etablera varumärkesigenkänning och trovärdighet.

- **Visuella hjälpmedel**: En bild kan bidra till att ge en extra nivå av information till användarna genom att den används som visuell hjälp för att hjälpa användarna förstå formulärets syfte.

- **Dekoration**: En bild kan användas för att förbättra formulärets allmänna design och göra den mer visuellt tilltalande.

- **Användarupplevelse**: En bild kan användas för att göra formuläret mer användarvänligt genom att ge användarna ett tydligt och intuitivt sätt att komma åt och fylla i formulärfält.

## Version och kompatibilitet {#version-and-compatibility}

Den adaptiva Forms Image Core-komponenten släpptes i februari 2023 som en del av Core Components 2.0.4 för Cloud Service och Core Components 1.1.12 för AEM 6.5.16.0 Forms eller senare. Här är en tabell som visar alla versioner som stöds, kompatibiliteten med AEM och länkar till motsvarande dokumentation:

| Komponentversion | AEM as a Cloud Service | AEM 6.5.16.0 Forms eller senare |
|---|---|---|
| v1 | Kompatibel med <br>[version 2.0.4](/help/adaptive-forms/version.md) och senare | Kompatibel med <br>[version 1.1.12](/help/adaptive-forms/version.md) och senare, men mindre än 2.0.0. |

Information om versioner och versioner av kärnkomponenter finns i dokumentet [Core Components Versions](/help/adaptive-forms/version.md) .


<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Teknisk information {#technical-details}

Hämta den senaste informationen om den adaptiva Forms Image Core-komponenten i den tekniska dokumentationen för [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/image/v1/image). Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).


## Konfigurera dialogruta {#configure-dialog}

Du kan enkelt anpassa din bildupplevelse för besökare med dialogrutan Konfigurera. Du kan också enkelt definiera bildalternativ för en smidig användarupplevelse.

![Fliken Egenskaper](/help/adaptive-forms/assets/image_properties.png)

- **Namn** - Du kan enkelt identifiera en formulärkomponent med dess unika namn både i formuläret och i regelredigeraren, men namnet får inte innehålla blanksteg eller specialtecken.

- **Titel** - Med titeln kan du enkelt identifiera en komponent i ett formulär. Som standard visas titeln ovanpå komponenten. Om du inte lägger till en titel visas komponentens namn i stället för rubriktexten.

- **Markera som obundet formulärelement**: Välj alternativet att konfigurera ett formulärfält som inte är länkat till något schema. Med det här alternativet kan du spara data utan att uppdatera datakällan. Det gör det också möjligt att hantera data på ett anpassat sätt, skilt från standarddatabasintegrering.

<!--   **Document of Record bind reference** - This option allows you to associate an Adaptive Form field with Document of Record field. When user enters any value in a linked field of an Adaptive Form that value also appears in the linked field of the corresponding Document of Record. For example, a Document of Record bind reference can be used to display a customer's name and address in a Document of Record, based on the customer's ID entered into the form. In this way, AEM Forms enable you to generate Document of Record and offers a seamless user experience for collecting and managing data.-->

- **Beskrivning** - En beskrivning är en kort textförklaring som ger ytterligare information eller förtydliganden om syftet med en viss bild.

- **Släpp en resurs här eller bläddra efter en fil som ska överföras** - Med det här alternativet kan du släppa en resurs som en bild genom att dra och släppa med musen. Du kan också överföra en fil från ett lokalt filsystem med knappen **Bläddra** . När du har lagt till en bild visas tre knappar längst ned i bilden:
   - **Redigera** - Tryck eller klicka på **Redigera** för att hantera återgivningarna av resursen i Assets Editor.
   - **Radera** - Tryck eller klicka på **Radera** för att avmarkera den markerade bilden.
   - **Välj** - Tryck eller klicka på alternativet **Välj** om du vill välja en annan bild från Assets-mappen.

- **Alternativ text** - Det här alternativet används för att ange texten som ger ett kort och beskrivande textalternativ för bilden, som beskriver bilden för användare med nedsatt syn.

- **Dölj komponent** - Välj alternativet att dölja komponenten från formuläret. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren. Detta är användbart när du behöver lagra information som inte behöver visas eller ändras direkt av användaren.

<!--   **Read-only** - Select the option to make the component non-editable. The user can see the value of the field but cannot modify it. The component remains accessible for other purposes, such as using it for calculations in the Rule Editor.
-->

## Designdialogruta {#design-dialog}

Designdialogrutan används för att definiera och hantera CSS-format för bildkomponenten.

### Fliken Format {#styles-tab}

Fliken används för att definiera och hantera CSS-format för en komponent. Den adaptiva Forms Image Core-komponenten stöder AEM [Style System](/help/get-started/authoring.md#component-styling).

![Designdialogrutan](/help/adaptive-forms/assets/checkbox-style.png)

- **Standard-CSS-klasser**: Du kan ange en standard-CSS-klass för den adaptiva Forms Image Core-komponenten.

- **Tillåtna format**: Du kan definiera format genom att ange ett namn och den CSS-klass som representerar formatet. Du kan till exempel skapa ett format med namnet&quot;bold text&quot; och ge CSS-klassen&quot;font-weight: bold&quot;. Du kan använda eller tillämpa dessa format på ett adaptivt formulär i en anpassad Forms-redigerare. Om du vill använda ett format väljer du den komponent du vill använda formatet på i Adaptiv Forms-redigerare, navigerar till egenskapsdialogrutan och väljer önskat format i listrutan **Format**. Om du behöver uppdatera eller ändra formaten går du tillbaka till designdialogrutan, uppdaterar formaten på formatfliken och sparar ändringarna.

### Anpassade egenskaper

![Dialogrutan Anpassade egenskaper](/help/adaptive-forms/assets/checkbox-customproperties.png)

Med anpassade egenskaper kan du koppla anpassade attribut (nyckelvärdepar) till en anpassad formulärets kärnkomponent med hjälp av formulärmallen. De anpassade egenskaperna återspeglas i egenskapsavsnittet i den headless-renderingen av komponenten. Det gör att du kan skapa dynamiskt formulärbeteende som anpassas baserat på anpassade attributvärden. Utvecklare kan till exempel utforma olika renderingar av en Headless Forms-komponent för mobiler, datorer eller webbplattformar, vilket avsevärt förbättrar användarupplevelsen på en mängd olika enheter.

- **Gruppnamn**: Du kan ange ett namn som identifierar den anpassade egenskapsgruppen. Du kan lägga till, ta bort eller ordna om flera anpassade egenskapsgrupper. När du har lagt till den anpassade egenskapsgruppen kan du se följande alternativ:

   - **Nyckelvärdepar**: Du kan lägga till flera anpassade egenskapsnamn och anpassade egenskapsvärden genom att klicka på knappen **Lägg till** för varje anpassad egenskapsgrupp.

   - **Ta bort**: Tryck eller klicka för att ta bort det anpassade egenskapsnamnet och det anpassade egenskapsvärdet.

   - **Ordna om**: Tryck eller klicka och dra för att ändra ordningen på det anpassade egenskapsnamnet och det anpassade egenskapsvärdet.

## Relaterade artiklar {#related-articles}

{{more-like-this}}

## Se även {#see-also}

{{see-also}}