---
title: Adaptiv Forms Core-komponent - text
description: Använda eller anpassa den adaptiva Forms Text Core-komponenten.
role: Architect, Developer, Admin, User
exl-id: b8de68e4-ca0d-4ae5-9a04-104cc617f1be
source-git-commit: be630c4d0a10ebaa679b77419b901fac818addb1
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 0%

---

# Text {#text-adaptive-forms-core-component}

I ett adaptivt formulär avser text det innehåll som visas i formuläret och som användaren kan läsa. Detta kan inkludera den text som används för att etikettera en grupp formulärelement, t.ex. textfält, samt eventuella ytterligare instruktioner eller information som tillhandahålls användaren.

Detta kan också bidra till att dela upp ett formulärs struktur i logiska avsnitt, vilket gör det lättare för användarna att förstå och fylla i formuläret. Dessutom kan den användas för hjälpmedelssyften för att ge en kort beskrivning av det element den är kopplad till. Sådana textfält visas vanligtvis i närheten av formulärkomponenterna, till exempel före eller efter det.

**Exempel**

![](/help/adaptive-forms/assets/text.png)

## Användning {#reasons-to-use-text-label}

Det finns flera skäl till att använda text i ett formulär:

* **Ange instruktioner**: Text kan användas för att ge instruktioner om hur formuläret ska fyllas i eller vilken information som krävs.

* **Ange sammanhang**: Text kan användas för att skapa sammanhang för formuläret, t.ex. förklara syftet med formuläret eller den organisation som samlar in informationen.

* **Dela upp formuläret i logiska avsnitt**: Text kan användas för att dela upp ett formulär i logiska avsnitt, vilket gör det lättare för användarna att förstå och fylla i formuläret.

* **Varumärke och identitet**: Text kan användas för varumärken och identitetssyften, t.ex. att inkludera organisationens namn i formuläret.

## Version och kompatibilitet {#version-and-compatibility}

Den adaptiva Forms Accordion Core-komponenten släpptes i februari 2023 som en del av Core Components 2.0.4 för Cloud Service och Core Components 1.1.12 för AEM 6.5.16.0 Forms eller senare. Här är en tabell med alla versioner som stöds, AEM kompatibilitet och länkar till motsvarande dokumentation:

| Komponentversion | AEM as a Cloud Service | AEM 6.5.16.0 Forms eller senare |
|---|---|---|
| v1 | Kompatibel med<br>[version 2.0.4](/help/adaptive-forms/version.md) och senare | Kompatibel med<br>[version 1.1.12](/help/adaptive-forms/version.md) och senare men mindre än 2.0.0. |

Mer information om versioner och versioner av kärnkomponenter finns i [Huvudkomponentversioner](/help/adaptive-forms/version.md) -dokument.

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Teknisk information {#technical-details}

Den senaste informationen om den adaptiva Forms Text Core-komponenten finns i den tekniska dokumentationen om [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/text/v1/text). Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Du kan enkelt anpassa din textupplevelse för besökare med dialogrutan Konfigurera. Du kan också enkelt definiera textalternativ för en smidig användarupplevelse.

![fliken Grundläggande](/help/adaptive-forms/assets/text_properties.png)

* **Namn** - Du kan enkelt identifiera en formulärkomponent med dess unika namn både i formuläret och i regelredigeraren, men namnet får inte innehålla blanksteg eller specialtecken.

* **Bindningsreferens** - En bind referens är en referens till ett dataelement som lagras i en extern datakälla och används i ett formulär. Med den binda referensen kan du binda data dynamiskt till formulärfält så att formuläret kan visa de senaste data från datakällan. En bindningsreferens kan till exempel användas för att visa en kunds namn och adress i ett formulär baserat på kundens ID som anges i formuläret. Bindningsreferensen kan också användas för att uppdatera datakällan med data som anges i formuläret. På så sätt kan AEM Forms skapa formulär som interagerar med externa datakällor, vilket ger en smidig användarupplevelse för att samla in och hantera data.
* **Dölj komponent** - Välj alternativet att dölja komponenten från formuläret. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren. Detta är användbart när du behöver lagra information som inte behöver visas eller ändras direkt av användaren.
* **Skrivskyddad** - Välj alternativet att göra komponenten icke-redigerbar. Användaren kan se fältets värde, men kan inte ändra det. Komponenten är fortfarande tillgänglig för andra syften, som att använda den för beräkningar i regelredigeraren.


## Designdialogruta {#design-dialog}

Designdialogrutan används för att definiera och hantera CSS-format för komponenten Text.

### Fliken Format {#styles-tab}

Fliken används för att definiera och hantera CSS-format för en komponent. Den adaptiva Forms Text Core-komponenten stöder AEM [Formatsystem](/help/get-started/authoring.md#component-styling).

![Designdialogruta](/help/adaptive-forms/assets/reset_designdialog.png)

* **CSS-standardklasser**: Du kan ange en standard-CSS-klass för den adaptiva Forms Text Core-komponenten.

* **Tillåtna format**: Du kan definiera format genom att ange ett namn och den CSS-klass som representerar formatet. Du kan till exempel skapa ett format med namnet&quot;bold text&quot; och ge CSS-klassen&quot;font-weight: bold&quot;. Du kan använda eller tillämpa dessa format på ett adaptivt formulär i en anpassad Forms-redigerare. Om du vill använda ett format väljer du den komponent du vill använda formatet på i Adaptiv Forms-redigerare, navigerar till egenskapsdialogrutan och väljer önskat format i dialogrutan **Stilar** listruta. Om du behöver uppdatera eller ändra formaten går du tillbaka till designdialogrutan, uppdaterar formaten på formatfliken och sparar ändringarna.

<!--

## Related article {#related-article}

* [Create a standalone Adaptive Form](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)

-->


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
>* [Bild](/help/adaptive-forms/components/image.md)
>* [Nummerindata](/help/adaptive-forms/components/number-input.md)
>* [Panelbehållare](/help/adaptive-forms/components/panel-container.md)
>* [Alternativknapp](/help/adaptive-forms/components/radio-button.md)
>* [Återställ knapp](/help/adaptive-forms/components/reset-button.md)
>* [Skicka-knapp](/help/adaptive-forms/components/submit-button.md)
>* [Telefonindata](/help/adaptive-forms/components/telephone-input.md)
>* [Textindata](/help/adaptive-forms/components/text-input.md)
>* [Titel](/help/adaptive-forms/components/title.md)
>* [guide](/help/adaptive-forms/components/wizard.md)

## Se även {#see-also}

{{see-also}}