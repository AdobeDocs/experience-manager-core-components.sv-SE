---
title: Introduktion till kärnkomponenter
description: 'Core Components introducerades för att tillhandahålla stabila och utökningsbara baskomponenter som bygger på den senaste tekniken och bästa praxis. '
translation-type: tm+mt
source-git-commit: fe8a121520000ffd56ae3347469590e89121eaf0

---


# Introduktion till kärnkomponenter{#core-components-introduction}

I Adobe Experience Manager är komponenter de strukturella element som utgör innehållet på de sidor som skapas. Komponenter har alltid varit en grundläggande del av AEM-upplevelsen, vilket gjort det enkelt men kraftfullt att skapa sidor för författaren och utveckla komponenter flexibelt och utbyggbart för utvecklaren.

Core Components introducerades för att tillhandahålla robusta och utbyggbara baskomponenter som bygger på den senaste tekniken och bästa praxis, och som följer riktlinjer för hjälpmedel och är kompatibla med WCAG 2.0 AA-standarden. Med de centrala komponenterna blir det enklare att skapa sidor, och det är enkelt för utvecklaren att bygga ut dem för anpassade funktioner.

## Testa kärnkomponenterna

Om du vill komma igång direkt med att testa kärnkomponenterna går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library). Komponentbiblioteket är ett onlineexempel på den aktuella versionen av de flesta kärnkomponenterna, som gör att du kan interagera med variationer av komponenterna samt se exempel på HTML- och JSON-utdata.

Självstudiekursen [för](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html) WKND visar också hur kärnkomponenterna kan användas.

## Kärnkomponenter - kärnfunktioner {#core-components-core-features}

Kärnkomponenterna är:

|  |  |
|--- |--- |
| Förkonfigurerbar | Mallar kan definiera hur sidförfattare kan använda dem. |
| Mångsidig | Författare kan skapa de flesta typer av innehåll med sig. |
| Lättanvänt | Man kan effektivt skapa och hantera material med dem. |
| Produktionsklart | Körklar! De är robusta, vältestade och fungerar bra. |
| Tillgänglig | De uppfyller WCAG 2.0-standarden, har ARIA-etiketter och har stöd för tangentbordsnavigering. |
| Lätt att formatera | Komponenterna implementerar Style System och koden följer BEM CSS-namngivning. |
| Egen SEO | HTML-utdata är semantiska och innehåller schema.org-mikrodataanteckningar. |
| PWA/SPA/App Ready | Deras strömlinjeformade JSON-utdata kan även användas för återgivning på klientsidan. |
| Utbyggbart | För att täcka anpassade behov, men utan att börja om från början, kan allt utökas. |
| Öppna källa | Om något inte är som det ska vara bidrar du till förbättringar av GitHub (Apache License). |
| Versionerat | Kärnkomponenterna bryter inte mot din webbplats när du förbättrar något som kan påverka dig. |
| [Lokaliserad](get-started/localization.md) | Med smart referensupplösning kan vissa komponenter hitta och återge motsvarande lokaliserat innehåll automatiskt |

## Tillgängliga komponenter {#available-components}

Den aktuella versionen av Core Components innehåller följande komponenter.

* [Dragspel](components/accordion.md)
* [Breadcrumb](components/breadcrumb.md)
* [Knapp](components/button.md)
* [Behållare](components/container.md)
* [Carousel](components/carousel.md)
* [Innehållsfragment](components/content-fragment-component.md)
* [Innehållsfragmentlista](components/content-fragment-list.md)
* [Hämta](components/download.md)
* [Bädda in](components/embed.md)
* [Experience Fragment](components/experience-fragment.md)
* [Formulärknapp](components/forms/form-button.md)
* [Formulärbehållare](components/forms/form-container.md)
* [Dolt formulär](components/forms/form-hidden.md)
* [Formuläralternativ](components/forms/form-options.md)
* [Formulärtext](components/forms/form-text.md)
* [Bild](components/image.md)
* [Språknavigering](components/language-navigation.md)
* [Lista](components/list.md)
* [Navigering](components/navigation.md)
* [Sida](components/page.md)
* [Snabbsökning](components/quick-search.md)
* [Avgränsare](components/separator.md)
* [Delning av sociala medier](components/sharing.md)
* [Tabbar](components/tabs.md)
* [Text](components/text.md)
* [Titel](components/title.md)

>[!NOTE]
>
>De centrala komponenterna är inte direkt tillgängliga för författare, [utvecklingsteamet måste först integrera dem i din miljö](get-started/using.md). När de är integrerade kan de göras tillgängliga och förkonfigurerade via [mallredigeraren](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html).

>[!CAUTION]
>
>Vissa versioner av enskilda kärnkomponenter kanske bara är kompatibla med vissa versioner av AEM.
>
>Mer information finns på den enskilda hjälpsidan (som länkats till i föregående lista) för den specifika komponenten. Du kan även läsa mer i dokumentet [Core Components Versions](versions.md) .

## När kärnkomponenter ska användas {#when-to-use-core-components}

Eftersom kärnkomponenterna är helt nya och ger flera fördelar rekommenderar vi att nya AEM-projekt använder dem. För befintliga projekt bör en migrering ingå i en större projektinsats, till exempel en omprofilering eller en övergripande omfaktorisering.

Specifika användningsrekommendationer finns i [När ska du använda kärnkomponenterna?](developing/overview.md#when-to-use-the-core-components) i dokumentet [Developing Core Components](developing/overview.md) .

## Översikt över Gems-session {#gems-session-overview}

En introduktion till kärnkomponenterna, de funktioner de erbjuder och hur de används i AEM finns i AEM Gems Session [AEM Core Components.](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)

[Gems on Adobe Experience Manager](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/aem-index.html) är en serie tekniska djupdykningar som levereras av Adobes experter. Den här serien kompletterar produktdokumentationen och alla andra tekniska kanaler, så att utvecklarna kan komma i kontakt med varandra och gå djupare på ett visst ämne.

## Utveckla med kärnkomponenterna {#developing-core-components}

Core-komponenterna har robusta och utbyggbara baskomponenter som implementerar flera mönster som gör det enkelt att anpassa, från enkel formatering till avancerad återanvändning av funktioner. Mer information finns i dokumentationen om utveckling av [kärnkomponenter](developing/overview.md) .

Kom igång med att utveckla AEM Sites med Core Components genom [att följa WKND-självstudiekursen.](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)

Glöm inte att starta ett eget AEM-projekt med hjälp av [AEM Project Archetype](developing/archetype/overview.md) med de senaste Core Components inbyggda!

## Stöd för kärnkomponenter {#core-components-support}

Core Components är en integrerad del av AEM och stöds i befintligt skick, på samma villkor som om de levererades som en del av QuickStart.

I likhet med andra produktfunktioner är den allmänna regeln om produktlivslängd:

* Komponenterna meddelas först att bli borttagna innan de tas bort
* Som tidigast tas de bort från AEM-versionen efter meddelandet.

Detta ger kunderna minst en releasecykel att gå över till den nya versionen av komponenten innan supporten upphör.

Versionen för varje komponent anger tydligt vilka AEM-versioner som stöds. När supporten upphör för en version av AEM gör även stödet för Core Components för den versionen av AEM det.

Mer information om stöd för komponentanpassningar finns på sidan [Anpassa kärnkomponenter](developing/customizing.md) i den relevanta Core Components-versionen.

## Stöd för Foundation Component {#foundation-component-support}

Eftersom Foundation Components har legat till grund för så mycket projektutveckling över många versioner kommer de att fortsätta att stödjas inom överskådlig framtid.

Men Adobes utvecklingstänkande har flyttats till kärnkomponenterna och nya funktioner kommer att läggas till i dem, medan [nästan alla grundkomponenterna har ersatts med AEM 6.5](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/siteandpage/default-components-foundation.html) och endast felkorrigeringar kommer att göras för grundkomponenterna i framtiden.
