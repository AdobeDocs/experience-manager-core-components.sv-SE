---
title: Adaptiv Forms Core-komponent - rubrik
description: Använda eller anpassa den adaptiva huvudkomponenten i Forms Header.
role: Architect, Developer, Admin, User
exl-id: aa18def9-0bec-4475-8dde-213860621ef5
source-git-commit: 59cd9d65bf4c1be6ab2eaf15bbb747b532863fdd
workflow-type: tm+mt
source-wordcount: '712'
ht-degree: 1%

---

# Sidhuvud {#header-adaptive-forms-core-component}

En rubrikkomponent i ett adaptivt formulär är ett avsnitt högst upp i formuläret som vanligtvis innehåller formulärets rubrik, logotyp eller namn. Rubriken kan även innehålla annan information, t.ex. en kort beskrivning av formulärets syfte, namnet på den organisation som skapade formuläret eller kontaktinformation för att få hjälp med formuläret. Rubriken används för att ge användarna en översikt över formuläret och ge kontext för den information de ska fylla i. Den används för att hjälpa användarna att förstå syftet med formuläret och hur det ska fyllas i på rätt sätt.

**Exempel**

![](/help/adaptive-forms/assets/header.png)

## Användning {#reasons-to-use-header}

* **Varumärke**: En rubrik kan användas för att visa logotypen eller namnet på den organisation som skapade formuläret, vilket bidrar till att etablera varumärkesigenkänning och trovärdighet.

* **Kontext**: En rubrik kan ge en kort beskrivning av syftet med formuläret, vilket hjälper användarna att förstå i vilket sammanhang formuläret används.

* **Navigering**: Ett sidhuvud kan innehålla länkar eller knappar som gör att användare kan navigera till andra delar av webbplatsen eller programmet.

* **Information**: Ett sidhuvud kan innehålla kontaktinformation eller länkar till hjälpresurser, vilket gör det enklare för användarna att få hjälp om de behöver det.

* **Användarupplevelse**: En rubrik kan användas för att göra formuläret mer användarvänligt genom att ge användarna ett tydligt och intuitivt sätt att komma åt och fylla i formulärfält.

## Version och kompatibilitet {#version-and-compatibility}

Den adaptiva Forms Accordion Core-komponenten släpptes i februari 2023 som en del av Core Components 2.0.4 för Cloud Service och Core Components 1.1.12 för AEM 6.5.16.0 Forms eller senare. Här är en tabell med alla versioner som stöds, AEM kompatibilitet och länkar till motsvarande dokumentation:

| Komponentversion | AEM as a Cloud Service | AEM 6.5.16.0 Forms eller senare |
|---|---|---|
| v1 | Kompatibel med<br>[version 2.0.4](/help/adaptive-forms/version.md) och senare | Kompatibel med<br>[version 1.1.12](/help/adaptive-forms/version.md) och senare men mindre än 2.0.0. |

Mer information om versioner och versioner av kärnkomponenter finns i [Huvudkomponentversioner](/help/adaptive-forms/version.md) -dokument.


<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->


## Teknisk information {#technical-details}

Få den senaste informationen om den adaptiva huvudkomponenten i Forms Header i den tekniska dokumentationen om [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/pageheader/v1/pageheader). Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Du kan enkelt anpassa sidhuvudsupplevelsen för besökare med dialogrutan Konfigurera. Du kan också enkelt definiera rubrikalternativ för en smidig användarupplevelse.

### Fliken Bild {#image-tab}

Den här delen av sidhuvudet innehåller rubriktiteln och bilden.

![Imagetab](/help/adaptive-forms/assets/header_image.png)

* **Bildresurs** - Med det här alternativet kan du släppa en resurs som en bild genom att dra och släppa med musen. Du kan också överföra en fil från ett lokalt filsystem med **Bläddra** -knappen. När du har lagt till en bild visas tre knappar längst ned i bilden. När du har lagt till en bild visas tre knappar längst ned i bilden:
   * **Redigera** - Tryck eller klicka **Redigera** om du vill hantera återgivningarna av resursen i Resursredigeraren.
   * **Rensa** - Tryck eller klicka **Rensa** för att avmarkera den markerade bilden.
   * **Välj** - Tryck eller klicka **Välj**  om du vill välja en annan bild från resursmappen.

* **Titel** - Det här alternativet används för att lägga till rubriken i sidhuvudet. Den fördefinierade texten tas med i dialogrutan och kan ändras av användaren.
* **Länka till** - Du kan länka rubriken till mappen med **Bläddra** -ikon.
* **Beskrivning** - En beskrivning är en kort textförklaring som ger ytterligare information eller förtydliganden om syftet med en viss bild.
* **Storlek (px)** - Det hjälper till att justera längden och bredden på bilden genom att öka eller minska pixlarna.

![hjälpmedelsflik](/help/adaptive-forms/assets/header_accessibility.png)

* **Alternativ text** - Det här alternativet används för att ange texten som ger ett kort och beskrivande textalternativ för bilden, som beskriver bilden för synskadade.

* **Bilden är dekorativ** - Kontrollera om bilden ska ignoreras av hjälpmedel och därför inte kräver någon alternativ text. Detta gäller endast dekorativa bilder.

### Fliken Text {#text-tab}

I det här avsnittet kan du ange den text som ska inkluderas i sidhuvudet.

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
>* [Vågräta flikar](/help/adaptive-forms/components/horizontal-tabs.md)
>* [Bild](/help/adaptive-forms/components/image.md)
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