---
title: Adaptiv Forms Core-komponent - bild
description: Använda eller anpassa den adaptiva Forms Image Core-komponenten.
role: Architect, Developer, Admin, User
exl-id: 9ee42d5d-16e3-4973-8364-5bc512ebe72e
source-git-commit: 0bebc248ee2b708f7677950d90356abd5bc70a98
workflow-type: tm+mt
source-wordcount: '1051'
ht-degree: 0%

---

# Bild {#image-adaptive-forms-core-component}

En bildkomponent i ett adaptivt formulär är ett sätt att inkludera bilder i ett formulär. Dessa bilder kan användas för att förbättra formulärets övergripande design, ge ytterligare information eller fungera som visuell hjälp för att hjälpa användarna förstå formulärets syfte. Bildkomponenten kan användas för att lägga till en logotyp, ett foto eller en bild i formuläret.

För tillgänglighet är det viktigt att du anger **Alternativ text** till bilden för att ge ett kort, beskrivande textalternativ för bilden som beskriver bilden för användare som inte kan se den.


**Exempel**

![](/help/adaptive-forms/assets/image.png)


## Användning {#reasons-to-use-image-in-a-form}

Det finns många skäl till att det är bra att ta med en bildkomponent i en adaptiv form, bland annat:

* **Varumärke**: En bild kan användas för att visa logotypen eller namnet på den organisation som skapade formuläret, vilket bidrar till att etablera varumärkesigenkänning och trovärdighet.

* **Visuella hjälpmedel**: En bild kan bidra till att ge användarna en extra nivå av information genom att den är ett visuellt hjälpmedel som hjälper dem att förstå formulärets syfte.

* **Dekoration**: En bild kan användas för att förbättra formulärdesignen och göra den mer visuellt tilltalande.

* **Användarupplevelse**: En bild kan användas för att göra formuläret mer användarvänligt genom ett tydligt och intuitivt sätt för användarna att komma åt och fylla i formulärfält.

## Version och kompatibilitet {#version-and-compatibility}

Den adaptiva Forms Accordion Core-komponenten släpptes i februari 2023 som en del av Core Components 2.0.4 för Cloud Service och Core Components 1.1.12 för AEM 6.5.16.0 Forms eller senare. Här är en tabell med alla versioner som stöds, AEM kompatibilitet och länkar till motsvarande dokumentation:

| Komponentversion | AEM as a Cloud Service | AEM 6.5.16.0 Forms eller senare |
|---|---|---|
| v1 | Kompatibel med<br>[version 2.0.4](/help/adaptive-forms/version.md) och senare | Kompatibel med<br>[version 1.1.12](/help/adaptive-forms/version.md) och senare men mindre än 2.0.0. |

Mer information om versioner och versioner av kärnkomponenter finns i [Huvudkomponentversioner](/help/adaptive-forms/version.md) -dokument.


<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Teknisk information {#technical-details}

Hämta den senaste informationen om den adaptiva Forms Image Core-komponenten i den tekniska dokumentationen om [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/image/v1/image). Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).


## Konfigurera dialogruta {#configure-dialog}

Du kan enkelt anpassa din bildupplevelse för besökare med dialogrutan Konfigurera. Du kan också enkelt definiera bildalternativ för en smidig användarupplevelse.

![Fliken Egenskaper](/help/adaptive-forms/assets/image_properties.png)

* **Namn** - Du kan enkelt identifiera en formulärkomponent med dess unika namn både i formuläret och i regelredigeraren, men namnet får inte innehålla blanksteg eller specialtecken.

* **Titel** - Med dess titel kan du enkelt identifiera en komponent i ett formulär. Som standard visas titeln ovanpå komponenten. Om du inte lägger till en titel visas komponentens namn i stället för rubriktexten.

* **Bindningsreferens för dokument** - Med det här alternativet kan du koppla ett adaptivt formulärfält till fältet Dokument för post. När användaren anger ett värde i ett länkat fält i ett adaptivt formulär visas det värdet också i det länkade fältet i motsvarande postdokument. En dokumentbindningsreferens kan t.ex. användas för att visa en kunds namn och adress i ett arkivdokument, baserat på kundens ID som anges i formuläret. På så sätt kan du med AEM Forms generera ett dokument för inspelning och det ger en smidig användarupplevelse när du samlar in och hanterar data.

* **Beskrivning** - En beskrivning är en kort textförklaring som ger ytterligare information eller förtydliganden om syftet med en viss bild.

* **Släpp en resurs här eller bläddra efter en fil att överföra** - Med det här alternativet kan du släppa en resurs som en bild genom att dra och släppa med musen. Du kan också överföra en fil från ett lokalt filsystem med **Bläddra** -knappen. När du har lagt till en bild visas tre knappar längst ned i bilden:
   * **Redigera** - Tryck eller klicka **Redigera** om du vill hantera återgivningarna av resursen i Resursredigeraren.
   * **Rensa** - Tryck eller klicka **Rensa** för att avmarkera den markerade bilden.
   * **Välj** - Tryck eller klicka **Välj**  om du vill välja en annan bild från resursmappen.

* **Alternativ text** - Det här alternativet används för att ange texten som ger ett kort och beskrivande textalternativ för bilden, som beskriver bilden för synskadade.

* **Dölj komponent** - Välj alternativet att dölja komponenten från formuläret. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren. Detta är användbart när du behöver lagra information som inte behöver visas eller ändras direkt av användaren.

* **Skrivskyddad** - Välj alternativet att göra komponenten icke-redigerbar. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.

## Designdialogruta {#design-dialog}

Designdialogrutan används för att definiera och hantera CSS-format för bildkomponenten.

### Fliken Format {#styles-tab}

Fliken används för att definiera och hantera CSS-format för en komponent. Den adaptiva Forms Image Core-komponenten stöder AEM [Formatsystem](/help/get-started/authoring.md#component-styling).

![Designdialogruta](/help/adaptive-forms/assets/image_designdialog.png)

**CSS-standardklasser**: Du kan ange en standard-CSS-klass för den adaptiva Forms Image Core-komponenten.

**Tillåtna format**: Du kan definiera format genom att ange ett namn och den CSS-klass som representerar formatet. Du kan till exempel skapa ett format med namnet&quot;bold text&quot; och ge CSS-klassen&quot;font-weight: bold&quot;. Du kan använda eller tillämpa dessa format på ett adaptivt formulär i en anpassad Forms-redigerare. Om du vill använda ett format väljer du den komponent du vill använda formatet på i Adaptiv Forms-redigerare, navigerar till egenskapsdialogrutan och väljer önskat format i dialogrutan **Stilar** listruta. Om du behöver uppdatera eller ändra formaten går du tillbaka till designdialogrutan, uppdaterar formaten på formatfliken och sparar ändringarna.

## Relaterad artikel {#related-article}

* [Skapa ett anpassat formulär i AEM Sites Page eller Experience Fragment](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html)

* [Skapa ett fristående anpassat formulär](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)


>[!MORELIKETHIS]
>
>* [Dragspel](/help/adaptive-forms/components/accordion.md)
>* [Knapp](/help/adaptive-forms/components/button.md)
>* [Kryssrutegrupp](/help/adaptive-forms/components/checkbox-group.md)
>* [Datumväljaren](/help/adaptive-forms/components/date-picker.md)
>* [Nedrullningsbar lista](/help/adaptive-forms/components/drop-down.md)
>* [E-postinmatning](/help/adaptive-forms/components/email-input.md)
>* [Formulärbehållare](/help/adaptive-forms/components/form-container.md)
>* [Bifogad fil](/help/adaptive-forms/components/file-attachment.md)
>* [Sidfot](/help/adaptive-forms/components/footer.md)
>* [Sidhuvud](/help/adaptive-forms/components/header.md)
>* [Vågräta flikar](/help/adaptive-forms/components/horizontal-tabs.md)
>* [Nummerindata](/help/adaptive-forms/components/number-input.md)
>* [Panelbehållare](/help/adaptive-forms/components/panel-container.md)
>* [Alternativknapp](/help/adaptive-forms/components/radio-button.md)
>* [Återställ knapp](/help/adaptive-forms/components/reset-button.md)
>* [Skicka-knapp](/help/adaptive-forms/components/submit-button.md)
>* [Telefonindata](/help/adaptive-forms/components/telephone-input.md)
>* [Textindata](/help/adaptive-forms/components/text-input.md)
>* [Text](/help/adaptive-forms/components/text.md)
>* [Titel](/help/adaptive-forms/components/title.md)
>* [guide](/help/adaptive-forms/components/wizard.md)

## Se även {#see-also}

{{see-also}}