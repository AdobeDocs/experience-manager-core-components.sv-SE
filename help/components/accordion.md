---
title: Dragspelskomponent
description: Med komponenten Core Component Accordion kan du skapa en samling paneler som ordnas i ett dragspel på en sida.
role: Architect, Developer, Admin, User
exl-id: 1deb570a-3d8d-409e-805f-8460c49cf9bb
source-git-commit: d39fe0084522f67664203a026340b23d325c1883
workflow-type: tm+mt
source-wordcount: '1098'
ht-degree: 0%

---


# Dragspelskomponent{#accordion-component}

Med komponenten Core Component Accordion kan du skapa en samling paneler som ordnas i ett dragspel på en sida.

## Användning {#usage}

Med komponenten Core Component Accordion kan du skapa en samling komponenter, som består av paneler och som ordnas i ett dragspel på en sida, ungefär som med [Tabbar-komponent](tabs.md), men gör det möjligt att expandera och komprimera panelerna.

* Egenskaperna för dragspelet kan definieras i [konfigurera dialogruta](#configure-dialog).
* Ordningen på panelerna i dragspelet kan definieras i dialogrutan Konfigurera och i dialogrutan [välj panellikon](#select-panel-popover).
* Standardvärden för dragspelskomponenten när du lägger till den på en sida kan definieras i [designdialogruta](#design-dialog).

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av dragspelskomponenten är v1, som introducerades i version 2.5.0 av kärnkomponenterna i juni 2019, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Kompatibel med<br>[version 2.17.4](/help/versions.md) och tidigare | Kompatibel | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Huvudkomponentversioner](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill visa Accordion Component och se exempel på dess konfigurationsalternativ samt HTML och JSON-utdata går du till [Komponentbibliotek](https://adobe.com/go/aem_cmp_library_accordion).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Accordion-komponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_accordion_v1).

Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Djuplänkning till en panel {#deep-linking}

The Accordion, [Carousel,](carousel.md) och [Tabbar-komponenter](tabs.md) har stöd för att länka direkt till en panel i komponenten.

Så här gör du:

1. Visa sidan med komponenten med **[Visa som publicerad](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)** i sidredigeraren.
1. Inspect innehållet på sidan och identifierar panelens ID.
   * Till exempel `id="accordion-86196c94d3-item-ca319dbb0b"`
1. ID:t blir det ankare som du kan lägga till i URL:en med hjälp av ett hash-tecken (`#`).
   * Till exempel `https://wknd.site/content/wknd/language-masters/en/magazine/western-australia.html#accordion-86196c94d3-item-ca319dbb0b`

Om du navigerar till URL-adressen med panel-ID som ankarpunkt, rullar webbläsaren direkt till den aktuella komponenten och visar den angivna panelen. Om panelen inte är konfigurerad att expanderas som standard kommer den att expanderas automatiskt.

## Dragspel och responsiv design {#responsive-design}

Alla kärnkomponenter är utformade för att vara fullt responsiva och ger en sömlös upplevelse på alla enheter.

Vissa avancerade komponenter som dragspelskomponenten kan kräva särskild hänsyn i samband med implementeringsprojektet för att kunna behålla svarstiden under alla förhållanden. Se dokumentet [Responsiv design av kärnkomponenterna](/help/responsive.md) för mer information.

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera dragspelsobjektet, dess paneler och hur det fungerar och visas för en besökare på sidan.

### Fliken Objekt {#items-tab}

![Fliken Objekt i redigeringsdialogrutan för dragspelskomponenten](/help/assets/accordion-edit-items.png)

Använd **Lägg till** för att öppna komponentväljaren och välja vilken komponent som ska läggas till som en panel. När du har lagt till en post läggs den till i listan, som innehåller följande kolumner:

* **Ikon** - Ikonen för panelens komponenttyp, vilket gör det enkelt att identifiera i listan. För musen över för att se det fullständiga komponentnamnet som ett verktygstips.
* **Beskrivning** - Den beskrivning som används som text på panelen. Namnet på den komponent som valts för panelen används som standard.
* **Ta bort** - Tryck eller klicka för att ta bort panelen från dragspelskomponenten.
* **Ordna om** - Tryck eller klicka och dra för att ordna om panelerna.

>[!TIP]
>
>Om sidans visningsruta minskas så att redigeringsdialogrutan blir helskärm, **Lägg till** knappen döljs. Komponenter kan fortfarande läggas till i dragspelskomponenten med [dra från komponentwebbläsaren och släppa på dragspelskomponenten i sidredigeraren](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html#InsertingaComponent).

### Fliken Egenskaper {#properties-tab}

![Fliken Egenskaper i redigeringsdialogrutan för dragspelskomponenten](/help/assets/accordion-edit-properties.png)

* **Expandering av enstaka objekt** - När du väljer det här alternativet utökas ett enskilt dragspelsobjekt i taget. Om du expanderar ett objekt komprimeras alla andra.
* **Utökade objekt** - Det här alternativet definierar de objekt som expanderas som standard när sidan läses in.
   * När **Expandering av enstaka objekt** är markerat måste en panel vara markerad. Som standard är den första panelen markerad.
   * När **Expandering av enstaka objekt** är inte markerat, det här alternativet är ett flerval och är valfritt.
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [Datalager](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

## Välj panelpekare {#select-panel-popover}

Innehållsförfattaren kan använda **Välj panel** i komponentens verktygsfält för att ändra till en annan panel för redigering och för att enkelt ändra ordningen på panelerna i dragspelet.

![Ikonen Välj panel](/help/assets/select-panel-icon.png)

När du har valt **Välj panel** i komponentens verktygsfält visas de konfigurerade dragspelspanelerna som en listruta.

![Välj panelpekare](/help/assets/select-panel-popover.png)

* Listan ordnas efter panelernas tilldelade ordning och återspeglas i numreringen.
* Panelens komponenttyp visas först, följt av panelens beskrivning med ett ljusare teckensnitt.
* Om du trycker eller klickar på en post i listrutan växlar vyn i redigeraren till den panelen.
* Panelerna kan ordnas om på plats med hjälp av draghandtagen.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera de alternativ som är tillgängliga för den som använder dragspelskomponenten och de standardvärden som anges när dragspelskomponenten monteras.

### Fliken Egenskaper {#properties-tab-design}

![Egenskapflik i designdialogrutan](/help/assets/accordion-design-properties.png)

* **Tillåtna rubrikelement** - Den här flervalslistrutan definierar dragspelsobjektsrubrikens HTML-element som tillåts markeras av en författare.
* **Standardrubrikelement** - Den här listrutan definierar standardobjektsrubrikens HTML-element.

### Fliken Tillåtna komponenter {#allowed-components-tab}

The **Tillåtna komponenter** -fliken används för att definiera vilka komponenter som innehållsförfattaren kan lägga till som objekt på paneler i dragspelskomponenten.

Fliken Tillåtna komponenter fungerar på samma sätt som fliken med samma namn när [definiera policyn och egenskaperna för en layoutbehållare i mallredigeraren.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html#editing-a-template-layout-template-author)

### Fliken Format {#styles-tab}

Accordion-komponenten stöder AEM [Formatsystem](/help/get-started/authoring.md#component-styling).

## Adobe-klientdatalager {#data-layer}

Accordion-komponenten har stöd för [Adobe Client Data Layer.](/help/developing/data-layer/overview.md)
