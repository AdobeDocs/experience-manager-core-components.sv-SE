---
title: E-postinnehållets fragmentkomponent
description: Med komponenten E-postinnehållsfragment kan du visa ett innehållsfragment i ditt innehåll.
role: Architect, Developer, Admin, User
exl-id: 9bc6b730-0d2a-4e5b-891c-d2f67f600bcc
index: false
source-git-commit: eb77567dc32cccb81a9fc131493d11fb55b7e93b
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 0%

---


# E-postinnehållets fragmentkomponent {#email-content-fragment-component}

Med komponenten E-postinnehållsfragment kan du visa ett [innehållsfragment](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html?lang=sv-SE) i ditt innehåll.

## Användning {#usage}

Med e-postinnehållets fragmentkomponent kan du inkludera ett [innehållsfragment](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html?lang=sv-SE) i ditt e-postinnehåll. Innehållsfragment är flerkanaligt strukturerat innehåll som kan redigeras centralt och enkelt återanvändas.

* Fragmentet och dess egenskaper kan väljas i dialogrutan [Konfigurera.](#configure-dialog)
* Resurstyper för att hantera vissa bilder och stödraster kan definieras i dialogrutan [Design.](#design-dialog)
* Redigeringsalternativet öppnar det valda fragmentet i [innehållsfragmentredigeraren &#x200B;](#edit-dialog), som är anpassad för användning med e-postkärnkomponenterna.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av E-postinnehållets fragmentkomponent är v1, som introducerades med version X av E-postkärnkomponenterna i oktober 2022, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponenterna är kompatibla med samt länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|---|---|---|---|
| v1 | Kompatibel | - | - |

Mer information om grundkomponentversioner och releaser för e-postmeddelanden finns i dokumentet [E-postversioner av grundkomponenter.](/help/email/versions.md)

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om e-postinnehållets fragmentkomponent [finns på GitHub.](https://adobe.com/go/aem_cmp_tech_email_cf_v1)

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen till utvecklaren av kärnkomponenter.](/help/developing/overview.md)

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera vilket innehållsfragment och vilka element i fragmentet som ska inkluderas.

### Fliken Egenskaper {#properties-tab}

![E-postinnehållets fragmentkomponent](/help/email/assets/email-content-fragment-edit-properties.png)

* **Innehållsfragment**

   * Sökväg till önskat innehållsfragment
   * Du kan använda dialogrutan **Markering** för att hitta fragmentet

* **Visningsläge**
   * **Enkelt textelement** - Aktiverar markering av ett flerradigt textelement och aktiverar styckekontrollalternativ
* **Variation** - Vilken variant av innehållsfragmentet som ska användas (standard är **Master**)

* **ID** - Med det här alternativet kan du kontrollera den unika identifieraren för komponenten i HTML.
   * Om du inte anger något värde genereras ett unikt ID automatiskt och du hittar det genom att kontrollera innehållet.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka CSS.

### Styckekontrollflik {#paragraph-control-tab}

![E-postinnehållets fragmentkomponent](/help/assets/content-fragment-edit-paragraph.png)

* **Stycken** - Tillåt markering av alla stycken eller ett intervall
   * **Alla** - Visa alla stycken
   * **Intervall**
      * Ange styckeintervall som ska visas, avgränsade med semikolon
      * `1;3-5;7;9-*` ska till exempel inkludera det första, tredje till femte, sjunde och nionde till det sista stycket
* **Hantera rubrik som egna stycken**

## Dialogrutan Redigera {#edit-dialog}

När du har konfigurerat ett innehållsfragment med komponenten för e-postinnehållsfragment visas ett **redigeringsalternativ** när du väljer komponenten i innehållsredigeraren.

![Verktygsfält för e-postinnehållets fragmentkomponent](/help/email/assets/email-content-fragment-edit-toolbar.png)

Om du trycker eller klickar på knappen **Redigera** öppnas redigeraren för innehållsfragment. Innehållsfragmentsredigeraren har utökats så att den innehåller knappar för **Välj Adobe Campaign-variabel** för att infoga Adobe Campaign-variabler i dina innehållsfragment.

![Innehållsfragmentredigerare för e-post](/help/email/assets/email-content-fragment-editor.png)

Mer information om redigering och redigering av innehållsfragment finns i dokumentet [Skapa fragmentinnehåll.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/content-fragments/content-fragments-variations.html?lang=sv-SE)

## Designdialogruta {#design-dialog}

När en komponent för e-postinnehållsfragment konfigureras med ett innehållsfragment visas en knapp i verktygsfältet när du markerar den i innehållsredigeraren.


### Huvudflik {#main-tab}

![Dialogrutan Design för komponenten E-postinnehållsfragment](/help/email/assets/email-content-fragment-design.png)

* **Intern responsiv stödraster**

   * Den Sling-resurstyp som används för det interna responsiva rutnätet

### Fliken Format {#styles-tab}

Komponenten för e-postupplevelsefragment stöder AEM [Style System.](/help/get-started/authoring.md#component-styling)
