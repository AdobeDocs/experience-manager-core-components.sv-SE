---
title: Dragspelskomponent
description: Med komponenten Core Component Accordion kan du skapa en samling paneler som ordnas i ett dragspel på en sida.
translation-type: tm+mt
source-git-commit: fe8a121520000ffd56ae3347469590e89121eaf0

---


# Dragspelskomponent{#accordion-component}

Med komponenten Core Component Accordion kan du skapa en samling paneler som ordnas i ett dragspel på en sida.

## Användning {#usage}

Med komponenten Core Component Accordion kan du skapa en samling komponenter, som består av paneler och som ordnas i ett dragspel på en sida, som liknar [Tabs-komponenten](tabs.md), men du kan expandera och komprimera panelerna.

* Egenskaperna för dragspelet kan definieras i [konfigurationsdialogrutan](#configure-dialog).
* Ordningen på panelerna i dragspelet kan definieras i dialogrutan Konfigurera och i [valpanelen](#select-panel-popover).
* Standardvärden för dragspelskomponenten när du lägger till den på en sida kan definieras i [designdialogrutan](#design-dialog).

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av dragspelskomponenten är v1, som introducerades i version 2.5.0 av kärnkomponenterna i juni 2019, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponentversionerna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|---|
| v1 | Kompatibel | Kompatibel | Kompatibel | Kompatibel |

Mer information om Core Component-versioner och -versioner finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill visa dragspelskomponenten och se exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_accordion).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om dragspelskomponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_accordion_v1).

Mer information om hur du utvecklar kärnkomponenter finns i dokumentationen till [Core Components Developer](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera dragspelsobjektet, dess paneler och hur det fungerar och visas för en besökare på sidan.

### Fliken Objekt {#items-tab}

![](/help/assets/screen-shot-2019-06-21-08.26.38.png)

Använd knappen **Lägg** till för att öppna komponentväljaren och välja vilken komponent som ska läggas till som en panel. När du har lagt till en post läggs den till i listan, som innehåller följande kolumner:

* **Ikon** - Ikonen för panelens komponenttyp, vilket gör den enkel att identifiera i listan. För musen över för att se det fullständiga komponentnamnet som ett verktygstips.
* **Beskrivning** - Den beskrivning som används som text på panelen. Namnet på den komponent som är markerad för panelen används som standard.
* **Ta bort** - Tryck eller klicka för att ta bort panelen från dragspelskomponenten.
* **Ordna** om - Tryck eller klicka och dra för att ordna om panelerna.

>[!TIP]
>
>Om sidans visningsruta minskas så att redigeringsdialogrutan blir helskärm, döljs knappen **Lägg till** . Komponenter kan fortfarande läggas till i dragspelskomponenten genom att [dra från komponentwebbläsaren och släppa på dragspelskomponenten i sidredigeraren](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html#InsertingaComponent).

### Fliken Egenskaper {#properties-tab}

![](/help/assets/screen-shot-2019-06-21-08.26.53.png)

* **Expandering** av enstaka objekt - När du väljer det här alternativet utökas ett enskilt dragspelsobjekt i taget. Om du expanderar ett objekt komprimeras alla andra.
* **Expanderade objekt** - Det här alternativet definierar de objekt som expanderas som standard när sidan läses in.
   * Om du väljer **Utökning** för ett objekt måste du markera en panel. Som standard är den första panelen markerad.
   * När du inte har valt **Utökning** för ett objekt är det här alternativet ett flerval och är valfritt.

## Välj panelpekare {#select-panel-popover}

Innehållsförfattaren kan använda alternativet **Välj panel** i komponentens verktygsfält för att ändra till en annan panel för redigering samt för att enkelt ordna om panelerna i dragspelet.

![](/help/assets/screen-shot-2019-06-21-08.49.36.png)

När du har valt alternativet **Välj panel** i komponentverktygsfältet visas de konfigurerade dragspelspanelerna som en listruta.

![](/help/assets/screen-shot-2019-06-21-08.52.14.png)

* Listan ordnas efter panelernas tilldelade ordning och återspeglas i numreringen.
* Panelens komponenttyp visas först, följt av panelens beskrivning med ett ljusare teckensnitt.
* Om du trycker eller klickar på en post i listrutan växlar vyn i redigeraren till den panelen.
* Panelerna kan ordnas om på plats med hjälp av draghandtagen.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera de alternativ som är tillgängliga för den som använder dragspelskomponenten och de standardvärden som anges när dragspelskomponenten monteras.

### Fliken Egenskaper {#properties-tab-design}

![](/help/assets/screen-shot-2019-06-21-08.58.11.png)

* **Tillåtna rubrikelement** - Den här flervalslistrutan definierar HTML-element för dragspelsobjektsrubriker som tillåts markeras av en författare.
* **Standardrubrikelement** - Den här listrutan definierar HTML-elementet för standarddragspelsobjektsrubriken.

### Fliken Tillåtna komponenter {#allowed-components-tab}

Fliken **Tillåtna komponenter** används för att definiera vilka komponenter som innehållsförfattaren kan lägga till som objekt i paneler i dragspelskomponenten.

Fliken Tillåtna komponenter fungerar på samma sätt som fliken med samma namn när du [definierar principen och egenskaperna för en layoutbehållare i mallredigeraren.](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/siteandpage/templates.html)

### Fliken Format {#styles-tab}

Dragspelskomponenten har stöd för AEM [Style System](/help/get-started/authoring.md#component-styling).