---
title: Adaptiv Forms Core-komponent - sidfot
description: Använda eller anpassa den adaptiva kärnkomponenten i Forms Footer.
role: Architect, Developer, Admin, User
source-git-commit: 86fa434d884b24b8d4b231c6108f5e6151a89813
workflow-type: tm+mt
source-wordcount: '749'
ht-degree: 1%

---


# Sidfot {#footer-adaptive-forms-core-component}

En sidfotskomponent i ett adaptivt formulär är ett område som vanligtvis visas längst ned i formuläret och som innehåller information som ett copyrightmeddelande, länkar till relaterade resurser eller kontaktinformation. En sidfot kan innehålla ytterligare information, till exempel datumet för den senaste uppdateringen, vilket kan vara bra för användare med hjälpmedelsbehov.

**Exempel**

![](/help/adaptive-forms/assets/footer.png)

## Användning {#reasons-to-use-footer}

Det finns flera skäl till att det är bra att ta med en sidfotskomponent i ett formulär, bland annat:

* **Juridiska krav**: Vissa formulär kan behöva innehålla en ansvarsfriskrivning, ett copyrightmeddelande eller annan juridisk information. En sidfot är ett bra sätt att inkludera den här informationen.

* **Navigering**: En sidfot kan innehålla länkar till andra viktiga sidor på webbplatsen, till exempel en integritetspolicy, användarvillkor eller kontaktsida.

* **Varumärke**: En sidfot kan användas för att inkludera en logotyp eller andra varumärkeselement, vilket kan förstärka organisationens eller webbplatsens identitet.

* **Konsekvens**: En sidfot ger en konsekvent design och layout av formuläret, vilket gör det mer intuitivt och enkelt för användarna att navigera.

* **Ytterligare kontext**: En sidfot kan ge formuläret ytterligare kontext, t.ex. en text som beskriver formuläret eller en länk till relaterade resurser, vilket gör formuläret mer informativt och användarvänligt.

## Version och kompatibilitet {#version-and-compatibility}

Den adaptiva huvudkomponenten i Forms Footer kom i februari 2023 som en del av Core Components 2.0.4. Här är en tabell med alla versioner som stöds, AEM kompatibilitet och länkar till motsvarande dokumentation:

|  |  |
|---|---|
| Komponentversion | AEM as a Cloud Service |
| — | --- |
| v1 | Kompatibel med<br>[version 2.0.4](/help/versions.md) och senare | Kompatibel | Kompatibel |

Information om versioner och versioner av kärnkomponenter finns i [Huvudkomponentversioner](/help/versions.md) -dokument.

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## Teknisk information {#technical-details}

Den senaste informationen om den adaptiva Forms Footer Core Component finns i den tekniska dokumentationen om [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/footer/v1/footer). Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).


## Konfigurera dialogruta {#configure-dialog}

Du kan enkelt anpassa sidfotsupplevelsen för besökare med dialogrutan Konfigurera. Du kan också enkelt definiera sidfotsalternativ för en smidig användarupplevelse.

![Fliken Egenskaper](/help/adaptive-forms/assets/footer_propertiestab.png)

* **Dialogrutan Redigera**
I redigeringsdialogrutan finns standardverktyg för formatering av RTF-text som gör att användaren kan skapa text för sidfoten.

* **Fet** - Det här alternativet använder fet stil på markerad text eller fetstilt formatera text som skrivs efter markören. `Ctrl+B` är ett kortkommando.

* **Kursiv** - Med det här alternativet används kursiv formatering på markerad text eller kursiv stil som anges efter markören. `Ctrl+I` är ett kortkommando.

![Punktalternativ](/help/adaptive-forms/assets/footer_bullet.png)


* **Punkt**

   * **Punktlikon** - Den markerade texten formateras som en punktlista eller börjar infogningen av en punktlista efter markören. Om du vill avsluta en punktlista trycker eller klickar du på knappen Bullet en gång till eller anger två vagnreturer.

   * **Ikon för numrerad lista** - Den markerade texten formateras som en numrerad lista eller börjar infogningen av en numrerad lista efter markören. Om du vill avsluta en numrerad lista trycker eller klickar du på knappen Numrerad igen eller anger två radmatningstecken.

   * **Ikon för indrag** - Den minskar indragsnivån för den markerade texten eller texten som anges efter markören. Endast aktivt om markörens markerade text eller position redan är indragen.

   * **Ikon för indrag** - Ökar indraget för den markerade texten eller texten som anges efter markören.

![Hyperlänksalternativ](/help/adaptive-forms/assets/footer_link.png)

* **Hyperlänk**

   * **Bana** - Ange sökvägen
      1. Använd dialogrutan Öppna markering för att välja en bana i AEM.
      1. Om länken inte finns i AEM anger du den absoluta URL:en.
      1. Icke-absoluta sökvägar tolkas som relativa AEM.
   * **Alternativ text** - Ange alternativ beskrivande text för länken.

   * **Mål** - Välj länkbeteende
      * Mål
      * Samma flik
      * Ny flik
      * Överordnad ram
      * Övre bildruta
   * **Ikonen Bryt länk** - Det här alternativet tar bort en länk som redan används för den markerade texten. Det här alternativet är bara aktivt om länken redan är markerad.

   * **Ikon för styckeformat** - Med det här alternativet kan du använda styckeformatering på den markerade texten. Du kan också formatera texten som infogats efter markören. Den definierar rubriknivån för titeln.



* **ID**: Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i datalagret.

   * Om inget anges skapas ett unikt ID automatiskt* som du hittar genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.


