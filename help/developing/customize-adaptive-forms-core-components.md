---
title: Anpassa adaptiva Forms Core-komponenter
description: Lär dig att utöka eller skapa en adaptiv Forms Core-komponent för att implementera funktioner som är anpassade för din organisation.
role: Architect, Developer, Admin
source-git-commit: 9a80b453d6a6cf7b347128654d3b5e673a063505
workflow-type: tm+mt
source-wordcount: '707'
ht-degree: 0%

---


# Anpassa adaptiva Forms Core-komponenter

Genom att anpassa adaptiva Forms Core-komponenter kan du skräddarsy de färdiga funktionerna efter just dina behov. Den här guiden hjälper dig att anpassa de här komponenterna för att skapa en mer personaliserad upplevelse.

## Förutsättning

Innan du börjar anpassa adaptiva Forms Core-komponenter

* Läs mer om [arkitektur för en kärnkomponent](customizing.md#customizing-the-markup-customizing-the-markup) och gå igenom [officiell Adobe Experience Manager Core Components-dokumentation](customizing.md). Dessa omfattande resurser är en guide under hela anpassningsprocessen.
* Konfigurera utvecklingsmiljön Detta ger ett smidigt arbetsflöde för att göra ändringar i kärnkomponenterna. När du konfigurerar utvecklingsmiljön ska du använda ett AEM Archetype-projekt baserat på det senaste AEM Archetype-projektet. Beroende på din miljö kan du:

   * [Konfigurera en lokal utvecklingsmiljö för Forms as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/setup-configure-migrate/setup-local-development-environment.html).
   * [Konfigurera en lokal utvecklingsmiljö för AEM 6.5 Forms](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html)

## Anpassa en adaptiv Forms Core-komponent

Följ stegen nedan för att ändra utseendet, beteendet och funktionaliteten för en adaptiv Forms Core-komponent.

1. **Identifiera och duplicera kärnkomponenten**

   När du konfigurerade utvecklingsmiljön har du skapat ett Arketype-baserat projekt. I AEM Archetype Project identifierar du den specifika Core Component du vill anpassa. Skapa en kopia av komponenten i det AEM Archetype-baserade projektet när du har identifierat den. Håll det parallellt med andra adaptiva Forms Core-komponenter. Med det här steget kan du vara säker på att dina anpassningar inte påverkar den ursprungliga komponenten, vilket gör att du kan experimentera fritt.

1. **Anpassa den kopierade komponenten**

   Öppna den duplicerade komponenten och börja göra nödvändiga ändringar enligt dina krav:

   * **Anpassa strukturen HTML**: Anpassa strukturen i HTML så att den passar dina designbehov samtidigt som du följer [BEM (Blockelementsmodifierare)](https://github.com/adobe/aem-core-wcm-components/wiki/css-coding-conventions) en stil för underhållbar och skalbar kod.
   * **Uppdatera etikett**: Uppdatera komponentens etikett för att ge den anpassade versionen ett tydligt och beskrivande namn. Se vad som anges [OTB-etikettmall (utanför rutan)](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/af-commons/v1/fieldTemplates/label.html) för enhetlighet.
   * **Anpassa widget**: Justera widgeten som används i komponenten (listrutor, kryssrutor) så att den passar ditt specifika användningssätt. Se [implementering av exempelwidget](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/textinput/v1/textinput/textinput.html) för referens.
   * **Hjälptext och verktygstips**: Anpassa hjälptexten eller verktygstipsen som är kopplade till komponenten för att ge användarna kontext och vägledning. Använd [OTB-hjälptextmall](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/af-commons/v1/fieldTemplates/questionMark.html) som startpunkt.
   * **Dataattribut**: Inkludera alla nödvändiga dataattribut i komponentens HTML-element. Dessa attribut är avgörande för att komponenten ska fungera korrekt vid körning. Läs [dokumentation](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/textinput/v1/textinput) för att förstå dataattributens roll i adaptiva Forms Core-komponenter.

1. **Implementera serverlogik**

   Om din anpassning kräver backend-logik kan du utöka befintliga snedmodeller. Se vad som anges [exempel](https://github.com/adobe/aem-core-forms-components/blob/master/bundles/af-core/src/main/java/com/adobe/cq/forms/core/components/internal/models/v1/form/TextInputImpl.java) för att smidigt integrera de önskade funktionerna i den anpassade komponenten.

1. **Konfigurera komponentdialogrutan**

   Konfigurera den dialogruta som är kopplad till den anpassade komponenten. Använd exemplet [komponentdialogruta](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/textinput/v1/textinput/_cq_dialog/.content.xml) i dokumentationen för att säkerställa att användarinteraktioner och -inställningar hanteras på rätt sätt.

1. **Distribuera och testa komponenten i den lokala utvecklingsmiljön**

   Använd [maven för att bygga och driftsätta komponenten](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/developing/archetype/using.html#building-and-installing) i den lokala utvecklingsmiljön. När komponenten har distribuerats skapar du ett adaptivt formulär för att testa den anpassade komponenten.

1. **Distribuera den anpassade komponenten i produktionsmiljön**

   När du har testat komponenten i den lokala utvecklingsmiljön distribuerar du komponenten i produktionsmiljöerna.

