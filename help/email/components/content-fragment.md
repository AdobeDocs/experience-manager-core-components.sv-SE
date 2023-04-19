---
title: E-postinnehållets fragmentkomponent
description: Med komponenten E-postinnehållsfragment kan du visa ett innehållsfragment i ditt innehåll.
role: Architect, Developer, Admin, User
exl-id: 9bc6b730-0d2a-4e5b-891c-d2f67f600bcc
source-git-commit: 3abc29e0c186a84f079d5938b8b716f4c7378d65
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 1%

---


# E-postinnehållets fragmentkomponent {#email-content-fragment-component}

Med komponenten E-postinnehållsfragment kan du visa en [innehållsfragment](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html) i innehållet.

## Användning {#usage}

Med e-postinnehållets fragmentkomponent kan en [innehållsfragment](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html) i ditt e-postinnehåll. Innehållsfragment är flerkanaligt strukturerat innehåll som kan redigeras centralt och enkelt återanvändas.

* Fragmentet och dess egenskaper kan markeras i [dialogrutan konfigurera.](#configure-dialog)
* Resurstyper för att hantera vissa bilder och stödraster kan definieras i [designdialog.](#design-dialog)
* Redigeringsalternativet öppnar det markerade fragmentet i [innehållsfragmentredigerare,](#edit-dialog) anpassade för användning med e-postkärnkomponenter.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av E-postinnehållets fragmentkomponent är v1, som introducerades med version X av E-postkärnkomponenterna i oktober 2022, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | Kompatibel | - |

Mer information om e-postkärnkomponentversioner och -versioner finns i dokumentet [E-postkärnkomponentversioner.](/help/email/versions.md)

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om e-postinnehållets fragmentkomponent [finns på GitHub.](https://adobe.com/go/aem_cmp_tech_email_cf_v1)

Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentens utvecklare.](/help/developing/overview.md)

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera vilket innehållsfragment och vilka element i fragmentet som ska inkluderas.

### Fliken Egenskaper {#properties-tab}

![E-postinnehållets fragmentkomponent](/help/email/assets/email-content-fragment-edit-properties.png)

* **Innehållsfragment**

   * Sökväg till önskat innehållsfragment
   * The **Dialogrutan Markering** kan användas för att hitta fragmentet

* **Visningsläge**
   * **Enkelt textelement** - Aktiverar markering av ett flerradigt textelement och aktiverar alternativ för styckekontroll
* **Variation** - Vilken variant av innehållsfragmentet som ska användas (standard är **Överordnad**)

* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML.
   * Om du inte anger något värde genereras ett unikt ID automatiskt och du hittar det genom att kontrollera innehållet.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka CSS.

### Styckekontrollflik {#paragraph-control-tab}

![E-postinnehållets fragmentkomponent](/help/assets/content-fragment-edit-paragraph.png)

* **Stycken** - Tillåt markering av alla stycken eller ett intervall
   * **Alla** - Visa alla stycken
   * **Intervall**
      * Ange styckeintervall som ska visas, avgränsade med semikolon
      * Till exempel `1;3-5;7;9-*` som omfattar det första, tredje till femte, sjunde och nionde till de sista styckena
* **Hantera rubrik som egna stycken**

## Dialogrutan Redigera {#edit-dialog}

När du har konfigurerat ett innehållsfragment med hjälp av komponenten för att skicka e-postinnehållsfragment, visas en **Redigera** alternativ.

![Verktygsfält för komponent för e-postinnehållsfragment](/help/email/assets/email-content-fragment-edit-toolbar.png)

Tryck eller klicka på **Redigera** knappen öppnar innehållsfragmentredigeraren. Innehållsfragmentsredigeraren har utökats till att omfatta knappar för **Välj Adobe Campaign-variabel** om du vill infoga Adobe Campaign-variabler i dina innehållsfragment.

![Redigera innehållsfragment för e-post](/help/email/assets/email-content-fragment-editor.png)

Mer information om redigering och redigering av innehållsfragment finns i dokumentet [Skapa fragmentinnehåll.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/content-fragments/content-fragments-variations.html)

## Designdialogruta {#design-dialog}

När en komponent för e-postinnehållsfragment konfigureras med ett innehållsfragment visas en knapp i verktygsfältet när du markerar den i innehållsredigeraren.


### Huvudflik {#main-tab}

![Designdialogrutan för komponenten E-postinnehållsfragment](/help/email/assets/email-content-fragment-design.png)

* **Intern responsiv stödraster**

   * Den Sling-resurstyp som används för det interna responsiva rutnätet

### Fliken Format {#styles-tab}

E-postupplevelsefragmentkomponenten stöder AEM [Formatsystem.](/help/get-started/authoring.md#component-styling)
