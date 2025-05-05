---
title: Anpassa adaptiva Forms Core-komponenter
description: Lär dig att utöka eller skapa en adaptiv Forms Core-komponent för att implementera funktioner som är anpassade för din organisation.
role: Architect, Developer, Admin
exl-id: f3ab12aa-d48d-47e9-a965-15052cac6f18
source-git-commit: 79cedf7099e2dc267a4cb1c25c06d4f0460367b2
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 0%

---

# Anpassa adaptiva Forms Core-komponenter

Genom att anpassa adaptiva Forms Core-komponenter kan du skräddarsy de färdiga funktionerna efter just dina behov. Den här guiden hjälper dig att anpassa de här komponenterna för att skapa en mer personaliserad upplevelse.

## Förutsättning

Innan du börjar anpassa adaptiva Forms Core-komponenter

* Lär dig mer om [arkitekturen för en kärnkomponent](customizing.md#customizing-the-markup-customizing-the-markup) och gå igenom den [officiella dokumentationen för Adobe Experience Manager Core Components](customizing.md). Dessa omfattande resurser är en guide under hela anpassningsprocessen.
* Konfigurera utvecklingsmiljön Detta ger ett smidigt arbetsflöde för att göra ändringar i kärnkomponenterna. När du konfigurerar utvecklingsmiljön ska du använda ett AEM Archetype-projekt baserat på det senaste AEM Archetype-projektet. Beroende på din miljö kan du:

   * [Konfigurera en lokal utvecklingsmiljö för Forms as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/setup-configure-migrate/setup-local-development-environment.html?lang=sv-SE).
   * [Konfigurera en lokal utvecklingsmiljö för AEM 6.5 Forms](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html?lang=sv-SE)

## Anpassa en adaptiv Forms Core-komponent

Följ stegen nedan för att ändra utseendet, beteendet och funktionaliteten för en adaptiv Forms Core-komponent.

1. **Identifiera och duplicera kärnkomponenten**

   När du konfigurerade utvecklingsmiljön har du skapat ett Arketype-baserat projekt. I AEM Archetype Project identifierar du den specifika Core Component du vill anpassa. Skapa en kopia av komponenten i det AEM Archetype-baserade projektet när du har identifierat den. Håll det parallellt med andra adaptiva Forms Core-komponenter. Med det här steget kan du vara säker på att dina anpassningar inte påverkar den ursprungliga komponenten, vilket gör att du kan experimentera fritt.

1. **Anpassa den kopierade komponenten**

   Öppna den duplicerade komponenten och börja göra nödvändiga ändringar enligt dina krav:

   * **Anpassa HTML-strukturen**: Anpassa HTML-strukturen efter dina designbehov samtidigt som du följer [BEM (Blockelementsmodifierare)](https://github.com/adobe/aem-core-wcm-components/wiki/css-coding-conventions) -stilmetoder för underhålls- och skalbar kod.
   * **Uppdatera etikett**: Uppdatera komponentens etikett för att ange ett tydligt och beskrivande namn för den anpassade versionen. Se etikettmallen [OTB (utanför rutan)](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/af-commons/v1/fieldTemplates/label.html) som tillhandahålls för konsekvens.
   * **Anpassa widget**: Justera widgeten som används i komponenten (listrutor, kryssrutor) så att den passar ditt specifika användningssätt. Se [exempelwidgetimplementeringen](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/textinput/v1/textinput/textinput.html) för referens.
   * **Hjälptext och verktygstips**: Anpassa hjälptexten eller verktygstipsen som är kopplade till komponenten för att ge användarna kontext och vägledning. Använd hjälptextmallen [OTB](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/af-commons/v1/fieldTemplates/questionMark.html) som utgångspunkt.
   * **Dataattribut**: Inkludera alla nödvändiga dataattribut i komponentens HTML-element. Dessa attribut är avgörande för att komponenten ska fungera korrekt vid körning. Läs [dokumentationen](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/textinput/v1/textinput) om du vill veta vilken roll dataattribut har i adaptiva Forms Core-komponenter.

1. **Implementera serverdelslogik**

   Om din anpassning kräver backend-logik kan du utöka befintliga snedmodeller. Se det tillhandahållna [exemplet](https://github.com/adobe/aem-core-forms-components/blob/master/bundles/af-core/src/main/java/com/adobe/cq/forms/core/components/internal/models/v1/form/TextInputImpl.java) för att sömlöst integrera de önskade funktionerna i din anpassade komponent.

1. **Konfigurera komponentens dialogruta**

   Konfigurera den dialogruta som är kopplad till den anpassade komponenten. Använd exemplet [komponentdialogruta](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/textinput/v1/textinput/_cq_dialog/.content.xml) som finns i dokumentationen för att se till att användarinteraktioner och inställningar hanteras på rätt sätt.

1. **Distribuera och testa komponenten i den lokala utvecklingsmiljön**

   Använd [maven för att skapa och distribuera komponenten](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/developing/archetype/using.html?lang=sv-SE#building-and-installing) i din lokala utvecklingsmiljö. När komponenten har distribuerats skapar du ett adaptivt formulär för att testa den anpassade komponenten.

1. **Distribuera den anpassade komponenten i din produktionsmiljö**

   När du har testat komponenten i den lokala utvecklingsmiljön distribuerar du komponenten i produktionsmiljöerna.
