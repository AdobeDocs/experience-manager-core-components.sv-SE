---
title: Snabbsökningskomponent
description: Komponenten för snabbsökning innehåller sökfunktioner för en webbplats och presenterar sökresultat så att besökarna kan söka på webbplatsen och filtrera resultaten.
role: Architect, Developer, Admin, User
exl-id: fc40ce1d-e69a-4a40-853e-67a37228271b
source-git-commit: 327c239b02e0aecee878784c918bfa98d960530e
workflow-type: tm+mt
source-wordcount: '621'
ht-degree: 0%

---

# Snabbsökningskomponent {#quick-search-component}

Komponenten för snabbsökning innehåller sökfunktioner för en webbplats och presenterar sökresultat så att besökarna enkelt kan hitta matchande innehåll och visa resultat.

## Användning {#usage}

Med snabbsökningskomponenten kan besökare söka efter innehåll, visa resultaten på plats och enkelt navigera till matchande sidor. Nya resultat hämtas dynamiskt när användaren rullar sökresultaten.

I [redigeringsdialogrutan](#edit-dialog) kan innehållsförfattaren definiera var i innehållsträdet sökningen ska börja. Med hjälp av [designdialogrutan](#design-dialog) kan mallskaparen ange standardvärdet för var i innehållsträdet sökningen ska börja samt en maximal resultatuppsättningsstorlek och minsta söktermslängd.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Quick Search Component är v2, som introducerades i version 2.18.0 av Core Components i januari 2018, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | - | Kompatibel | Kompatibel |
| [v1](/help/components/v1/quick-search.md) | Kompatibel med <br>[version 2.17.4](/help/versions.md) och tidigare | Kompatibel | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Core Components Versions](/help/versions.md).

### Teknisk information {#technical-details}

>[!NOTE]
>
>Skydda Search-komponenten eller andra AEM program mot DOS-attacker ska implementeras på en högre nivå, till exempel genom att använda `mod_security` på dispatchern.

Den senaste tekniska dokumentationen om snabbsökningskomponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_search_v2).

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).

## Dialogrutan Redigera {#edit-dialog}

I redigeringsdialogrutan kan innehållsförfattaren definiera var i innehållsträdet sökningen ska börja.

![Redigeringsdialogrutan för snabbsökningskomponenten](/help/assets/quick-search-edit.png)

**Sökrot** - Rotsidan som sökningen ska startas från. Sökroten kan vara en överordnad rityta, en mallsida för språk eller en vanlig sida.
* **ID** - Det här alternativet tillåter kontroll av den unika identifieraren för komponenten i HTML och i [datalagret.](/help/developing/data-layer/overview.md)
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

>[!NOTE]
>
>Om **sökroten** inte är konfigurerad eller inte kan matchas är snabbsökningen som standard sökbar under den aktuella sidan.

## Designdialogruta {#design-dialog}

Med hjälp av designdialogrutan kan mallskaparen ange standardvärdet för var i innehållsträdet sökningen ska börja samt en maximal resultatmängdsstorlek och minsta söktermslängd. I designdialogrutan kan mallskaparen definiera vilka textformateringsalternativ som är tillgängliga för innehållsförfattarna.

### Fliken Egenskaper {#properties-tab}

![Snabbsökningskomponentens designdialogruta](/help/assets/quick-search-design.png)

* **Sökrot**
Standardvärdet för sökroten när en innehållsförfattare placerar snabbsökningskomponenten på en innehållssida
* **Resultatstorlek**
Det maximala antalet resultat som hämtats av en sökbegäran
* **Minimilängd för sökord**
Minsta längd på söktermen som ska starta sökningen

>[!NOTE]
>
>**Resultatstorlek** och **Minimilängd för sökord** kan bara anges i designläge och därför bara på mallnivå, vilket innebär att innehållsförfattare inte kan ändra dessa värden.

>[!CAUTION]
>
>**Resultatstorlek** och **Minimilängd för sökord** kan ha prestandaeffekter om de är för höga respektive för låga.

### Fliken Format {#styles-tab}

Quick Search-komponenten stöder AEM [Style System](/help/get-started/authoring.md#component-styling).
