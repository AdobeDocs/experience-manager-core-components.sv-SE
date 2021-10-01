---
title: Skapa med kärnkomponenter
description: I AEM är komponenterna de strukturella element som utgör innehållet på de sidor som skapas - Core Components erbjuder flexibla och funktionsrika redigeringsfunktioner.
role: Architect, Developer, Admin, User
exl-id: 56e58303-a178-45ab-b59d-e374c9cf90cf
source-git-commit: 888719359f9a1d1c9dccff97fb639b332f2be54c
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Skapa med kärnkomponenter

I Adobe Experience Manager är komponenter de strukturella element som utgör innehållet på de sidor som skapas.

Core Components erbjuder flexibla och funktionsrika redigeringsfunktioner. [WKND-referenswebbplatsen](https://wknd.site) och dess illustrerar hur de centrala komponenterna kan användas för att implementera en omfattande webbplatsupplevelse.

Om du vill visa Core Components och se exempel på deras konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library).

Om du vill få en mer djupgående, utvecklarorienterad introduktion till implementering av kärnkomponenterna i ett AEM projekt med [AEM Project Archetype](/help/developing/archetype/overview.md) ska du titta på [WKND-självstudiekursen.](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)

>[!NOTE]
>
>Core Components är inte omedelbart tillgängliga för författare, [utvecklingsteamet måste först integrera dem i din miljö](/help/get-started/using.md). När de är integrerade kan de göras tillgängliga och förkonfigurerade via [mallredigeraren](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html).

>[!CAUTION]
>
>Huvudkomponenter [kräver AEM 6.4 eller senare](/help/versions.md) och kräver [redigerbara mallar](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html). De fungerar inte med det klassiska användargränssnittet och inte heller med statiska mallar.

## Skapa med kärnkomponenter {#authoring-with-core-components}

Som författare kommer du att märka flera fördelar med Core Components, bland annat:

* Enkelt att använda och väl integrerat med [sidredigeraren](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html)

* Funktioner för att hantera många användningsfall, som framgår av [WKND-referensplatsen](https://wknd.site) samt i [komponentbiblioteket](https://adobe.com/go/aem_cmp_library)

* [I förväg ](#pre-configuring-core-components) konfigurerbara för att definiera vilka funktioner som är tillgängliga för sidförfattare via  [mallredigeraren](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)

* Byggt kring [riktlinjer för hjälpmedel](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html)

* Byggd för att stödja [responsiv layout](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/responsive-layout.html)

* Byggd för att stödja [enkel lokalisering](localization.md)

Komponenter är tillgängliga på fliken **Komponenter** i sidpanelen i sidredigeraren när [du redigerar en sida](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html).

Komponenterna grupperas enligt kategorier som kallas komponentgrupper för att enkelt ordna och filtrera komponenterna. Komponentgruppnamnet visas med komponenten i [komponentwebbläsaren](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html) och det går också att filtrera efter grupp för att enkelt hitta rätt komponent.

>[!NOTE]
>
>Kärnkomponenterna är som standard en del av en dold grupp och visas inte i komponentwebbläsaren.
>
>Lägg till de nödvändiga komponenterna i en synlig grupp eller anpassa dem så att de blir tillgängliga för författare.

## Förkonfigurering av kärnkomponenter {#pre-configuring-core-components}

Att konfigurera Foundation Components var en uppgift för en utvecklare. Men med Core Components kan mallskapare nu konfigurera ett antal funktioner via mallredigeraren.

Om en bildkomponent t.ex. inte ska tillåta bildöverföring från filsystemet, eller om en textkomponent bara ska tillåta viss styckeformatering, kan dessa funktioner aktiveras eller inaktiveras med ett enkelt klick.

Mer information finns i [Skapa sidmallar](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html).

### Redigera och designa dialogrutor {#edit-and-design-dialogs}

Eftersom kärnkomponenterna kan förkonfigureras av mallförfattare för att definiera vilka alternativ som tillåts som en del av en mall, och sedan konfigureras ytterligare av sidförfattaren för att definiera det faktiska sidinnehållet, kan varje komponent ha alternativ i två olika dialogrutor.

|  | Beskrivning | Vad det styr | Exempel |
|--- |--- |--- |--- |
| **Dialogrutan Redigera** | Alternativ som en **sidförfattare** kan ändra under normal sidredigering för de monterade komponenterna | Innehållet som visas av komponenten och hur det slutligen visas på sidan. | Formatering av innehållstext, rotera en bild på en sida |
| **Designdialogruta** | Alternativ som en **mallskapare** kan ändra när en sidmall konfigureras. | Vilka alternativ sidförfattaren har tillgängliga när komponenten redigeras | Vilka textformateringsalternativ som är tillgängliga, vilka bildmonteringsalternativ som är tillgängliga |

### Komponentformat {#component-styling}

Stilarna för de flesta kärnkomponenter kan definieras med hjälp av det AEM.

* En mallskapare kan definiera vilka format som är tillgängliga för en viss komponent i designdialogrutan för den komponenten.
* Innehållsförfattaren kan sedan välja vilka format som ska användas när komponenten läggs till och innehållet skapas.

Mer information finns i [Style System](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/style-system.html)-dokumentationen.

## Resurser för utvecklare {#developer-resources}

I [Developing Core Components](/help/developing/overview.md) utvecklardokumentationen finns teknisk information om kärnkomponenter.
