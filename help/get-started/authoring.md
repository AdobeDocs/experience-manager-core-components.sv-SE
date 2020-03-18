---
title: Skapa med kärnkomponenter
description: I AEM är komponenterna de strukturella element som utgör innehållet på de sidor som skapas - Core Components erbjuder flexibla och funktionsrika redigeringsfunktioner.
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# Skapa med kärnkomponenter

I Adobe Experience Manager är komponenter de strukturella element som utgör innehållet på de sidor som skapas.

Core Components erbjuder flexibla och funktionsrika redigeringsfunktioner. WKND:s [referenswebbplats](https://wknd.site) och dess illustrationer visar hur de viktigaste komponenterna kan användas för att implementera en omfattande webbplatsupplevelse.

Om du vill se exempel på kärnkomponenterna och deras konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library).

En mer detaljerad, utvecklarorienterad introduktion till implementering av kärnkomponenterna i ett AEM-projekt med hjälp av [AEM Project Archetype](/help/developing/archetype/overview.md) , se [självstudiekursen WKND.](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)

>[!NOTE]
>
>De centrala komponenterna är inte direkt tillgängliga för författare, [utvecklingsteamet måste först integrera dem i din miljö](/help/get-started/using.md). När de är integrerade kan de göras tillgängliga och förkonfigurerade via [mallredigeraren](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html).

>[!CAUTION]
>
>Core Components [kräver AEM 6.3 eller högre](/help/versions.md) och kräver [redigerbara mallar](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html). De fungerar inte med det klassiska användargränssnittet och inte heller med statiska mallar.

## Skapa med kärnkomponenter {#authoring-with-core-components}

Som författare kommer du att märka flera fördelar med Core Components, bland annat:

* Enkelt att använda och väl integrerat med [sidredigeraren](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html)

* Funktioner för många användningsområden, som illustreras av [WKND-referenswebbplatsen](https://wknd.site) och i [komponentbiblioteket](https://adobe.com/go/aem_cmp_library)

* [Kan konfigureras](#pre-configuring-core-components) i förväg för att definiera vilka funktioner som är tillgängliga för sidförfattare via [mallredigeraren](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)

* Byggt på riktlinjer för [tillgänglighet](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html)

* Utformad för [responsiv layout](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/responsive-layout.html)

* Byggd för [enkel lokalisering](localization.md)

Komponenter är tillgängliga på fliken **Komponenter** i sidpanelen i sidredigeraren när du [redigerar en sida](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html).

Komponenterna grupperas enligt kategorier som kallas komponentgrupper för att enkelt ordna och filtrera komponenterna. Komponentgruppnamnet visas med komponenten i [komponentwebbläsaren](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html) och det går även att filtrera efter grupp för att enkelt hitta rätt komponent.

>[!NOTE]
>
>Kärnkomponenterna är som standard en del av en dold grupp och visas inte i komponentwebbläsaren.
>
>Lägg till de nödvändiga komponenterna i en synlig grupp eller anpassa dem så att de blir tillgängliga för författare.

## Förkonfigurering av kärnkomponenter {#pre-configuring-core-components}

Att konfigurera Foundation Components var en uppgift för en utvecklare. Men med Core Components kan mallskapare nu konfigurera ett antal funktioner via mallredigeraren.

Om en bildkomponent t.ex. inte ska tillåta bildöverföring från filsystemet, eller om en textkomponent bara ska tillåta viss styckeformatering, kan dessa funktioner aktiveras eller inaktiveras med ett enkelt klick.

Mer information finns i [Skapa sidmallar](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html) .

### Redigera och designa dialogrutor {#edit-and-design-dialogs}

Eftersom kärnkomponenterna kan förkonfigureras av mallförfattare för att definiera vilka alternativ som tillåts som en del av en mall, och sedan konfigureras ytterligare av sidförfattaren för att definiera det faktiska sidinnehållet, kan varje komponent ha alternativ i två olika dialogrutor.

|  | Beskrivning | Vad det styr | Exempel |
|--- |--- |--- |--- |
| **Dialogrutan Redigera** | Alternativ som en **sidförfattare** kan ändra vid normal sidredigering för de monterade komponenterna | Innehållet som visas av komponenten och hur det slutligen visas på sidan. | Formatering av innehållstext, rotera en bild på en sida |
| **Designdialogruta** | Alternativ som en **mallskapare** kan ändra när en sidmall konfigureras. | Vilka alternativ sidförfattaren har tillgängliga när komponenten redigeras | Vilka textformateringsalternativ som är tillgängliga, vilka bildmonteringsalternativ som är tillgängliga |

### Komponentformat {#component-styling}

Stilarna för de flesta kärnkomponenter kan definieras med hjälp av AEM-formatsystemet.

* En mallskapare kan definiera vilka format som är tillgängliga för en viss komponent i designdialogrutan för den komponenten.
* Innehållsförfattaren kan sedan välja vilka format som ska användas när komponenten läggs till och innehållet skapas.

Mer information finns i dokumentationen för [Style System](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/style-system.html) .

>[!NOTE]
>
>I AEM 6.3 krävs Service Pack 2 (6.3.2.0) eller senare för att aktivera formatsystemfunktionen.

## Lista över tillgängliga kärnkomponenter {#list-of-core-components-available}

Nedan följer en lista över tillgängliga kärnkomponenter som är länkade till sidor som beskriver deras redigerings- och designdialogfunktioner i detalj.

Den aktuella versionen av Core Components innehåller följande komponenter.

* [Dragspel](/help/components/accordion.md)
* [Breadcrumb](/help/components/breadcrumb.md)
* [Knapp](/help/components/button.md)
* [Behållare](/help/components/container.md)
* [Carousel](/help/components/carousel.md)
* [Innehållsfragment](/help/components/content-fragment-component.md)
* [Innehållsfragmentlista](/help/components/content-fragment-list.md)
* [Hämta](/help/components/download.md)
* [Bädda in](/help/components/embed.md)
* [Experience Fragment](/help/components/experience-fragment.md)
* [Formulärknapp](/help/components/forms/form-button.md)
* [Formulärbehållare](/help/components/forms/form-container.md)
* [Dolt formulär](/help/components/forms/form-hidden.md)
* [Formuläralternativ](/help/components/forms/form-options.md)
* [Formulärtext](/help/components/forms/form-text.md)
* [Bild](/help/components/image.md)
* [Språknavigering](/help/components/language-navigation.md)
* [Lista](/help/components/list.md)
* [Navigering](/help/components/navigation.md)
* [Sida](/help/components/page.md)
* [Snabbsökning](/help/components/quick-search.md)
* [Avgränsare](/help/components/separator.md)
* [Delning av sociala medier](/help/components/sharing.md)
* [Tabbar](/help/components/tabs.md)
* [Text](/help/components/text.md)
* [Titel](/help/components/title.md)

>[!CAUTION]
>
>Vissa versioner av enskilda kärnkomponenter kanske bara är kompatibla med vissa versioner av AEM.
>
>Mer information finns på den enskilda hjälpsidan (som länkats till i föregående lista) för den specifika komponenten. Du kan även läsa mer i dokumentet [Core Components Versions](/help/versions.md) .

>[!NOTE]
>
>Beroende på vilken instans du har kan du ha utvecklat anpassade komponenter explicit för dina behov. De kan till och med ha samma namn som vissa av de komponenter som beskrivs här.
>Formulärets kärnkomponenter är inte relaterade till AEM Forms.

## Resurser för utvecklare {#developer-resources}

I [Developing Core Components](/help/developing/overview.md) developer documentation finns teknisk information om kärnkomponenterna.
