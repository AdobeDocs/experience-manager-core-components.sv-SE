---
title: Skapa med kärnkomponenter
description: I AEM är komponenterna de strukturella element som utgör innehållet på de sidor som skapas - Core Components erbjuder flexibla och funktionsrika redigeringsfunktioner.
role: Architect, Developer, Admin, User
exl-id: 56e58303-a178-45ab-b59d-e374c9cf90cf
source-git-commit: 945e1793ae4e959f83960db46d2de4257916fe32
workflow-type: tm+mt
source-wordcount: '742'
ht-degree: 0%

---

# Skapa med kärnkomponenter

I Adobe Experience Manager är komponenter de strukturella element som utgör innehållet på de sidor som skapas.

Core Components erbjuder flexibla och funktionsrika redigeringsfunktioner. The [WKND-referensplats](https://wknd.site) och visar hur de viktigaste komponenterna kan användas för att implementera en omfattande webbplatsupplevelse.

Om du vill se exempel på kärnkomponenterna och deras konfigurationsalternativ samt HTML och JSON-utdata går du till [Komponentbibliotek](https://adobe.com/go/aem_cmp_library).

För en mer djupgående, utvecklarorienterad introduktion till implementering av kärnkomponenterna i ett AEM projekt med [AEM Project Archetype](/help/developing/archetype/overview.md) checka ut [WKND-självstudiekursen.](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)

>[!NOTE]
>
>Kärnkomponenter är inte omedelbart tillgängliga för författare, [Utvecklingsteamet måste först integrera dem i din miljö](/help/get-started/using.md). När de är integrerade kan de göras tillgängliga och förkonfigurerade via [mallredigerare](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html).

>[!CAUTION]
>
>Kärnkomponenter [kräver AEM 6.4 eller senare](/help/versions.md) och kräver att [redigerbara mallar](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html). De fungerar inte med det klassiska användargränssnittet och inte heller med statiska mallar.

## Skapa med kärnkomponenter {#authoring-with-core-components}

Som författare kommer du att märka flera fördelar med Core Components, bland annat:

* Enkelt att använda och väl integrerat med [sidredigerare](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html)

* Funktioner för många användningsområden, som [WKND-referensplats](https://wknd.site) och i [Komponentbibliotek](https://adobe.com/go/aem_cmp_library)

* [Förkonfigurerbar](#pre-configuring-core-components) för att definiera vilka funktioner som är tillgängliga för sidförfattare via [mallredigerare](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)

* Byggd runt [riktlinjer för hjälpmedel](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html)

* Byggd för support [responsiv layout](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/responsive-layout.html)

* Byggd för support [enkel lokalisering](localization.md)

Komponenter är tillgängliga på **Komponenter** fliken på sidpanelen i sidredigeraren när [redigera en sida](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html).

Komponenterna grupperas enligt kategorier som kallas komponentgrupper för att enkelt ordna och filtrera komponenterna. Komponentgruppnamnet visas med komponenten i [komponentwebbläsare](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html) och det går också att filtrera efter grupp för att enkelt hitta rätt komponent.

>[!NOTE]
>
>Kärnkomponenterna är som standard en del av en dold grupp och visas inte i komponentwebbläsaren.
>
>Lägg till de nödvändiga komponenterna i en synlig grupp eller anpassa dem så att de blir tillgängliga för författare.

## Förkonfigurering av kärnkomponenter {#pre-configuring-core-components}

Att konfigurera Foundation Components var en uppgift för en utvecklare. Men med Core Components kan mallskapare nu konfigurera ett antal funktioner via mallredigeraren.

Om en bildkomponent t.ex. inte ska tillåta bildöverföring från filsystemet, eller om en textkomponent bara ska tillåta viss styckeformatering, kan dessa funktioner aktiveras eller inaktiveras med ett enkelt klick.

Se [Skapa sidmallar](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html) för mer information.

### Redigera och designa dialogrutor {#edit-and-design-dialogs}

Eftersom kärnkomponenterna kan förkonfigureras av mallförfattare för att definiera vilka alternativ som tillåts som en del av en mall, och sedan konfigureras ytterligare av sidförfattaren för att definiera det faktiska sidinnehållet, kan varje komponent ha alternativ i två olika dialogrutor.

|  | Beskrivning | Vad det styr | Exempel |
|--- |--- |--- |--- |
| **Dialogrutan Redigera** | Alternativ som **sidförfattare** kan ändras under normal sidredigering för monterade komponenter | Innehållet som visas av komponenten och hur det slutligen visas på sidan. | Formatering av innehållstext, rotera en bild på en sida |
| **Designdialogruta** | Alternativ som **mallskapare** kan ändras när du konfigurerar en sidmall. | Vilka alternativ sidförfattaren har tillgängliga när komponenten redigeras | Vilka textformateringsalternativ som är tillgängliga, vilka bildmonteringsalternativ som är tillgängliga |

### Komponentformat {#component-styling}

Stilarna för de flesta kärnkomponenter kan definieras med hjälp av det AEM.

* En mallskapare kan definiera vilka format som är tillgängliga för en viss komponent i designdialogrutan för den komponenten.
* Innehållsförfattaren kan sedan välja vilka format som ska användas när komponenten läggs till och innehållet skapas.

Mer information finns i [Formatsystem](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/style-system.html) dokumentation.

## Resurser för utvecklare {#developer-resources}

Se [Utveckla kärnkomponenter](/help/developing/overview.md) dokumentation för utvecklare av teknisk information om kärnkomponenter.
