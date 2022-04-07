---
title: Snabbsökningskomponent (v1)
description: Komponenten för snabbsökning innehåller sökfunktioner för en webbplats och presenterar sökresultat så att besökarna kan söka på webbplatsen och filtrera resultaten.
role: Architect, Developer, Admin, User
exl-id: fc40ce1d-e69a-4a40-853e-67a37228271b
source-git-commit: 64aa6ab38738b6969d01971817bde892348be05d
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 1%

---

# Snabbsökningskomponent (v1) {#quick-search-component}

Komponenten för snabbsökning innehåller sökfunktioner för en webbplats och presenterar sökresultat så att besökarna enkelt kan hitta matchande innehåll och visa resultat.

## Användning {#usage}

Med snabbsökningskomponenten kan besökare söka efter innehåll, visa resultaten på plats och enkelt navigera till matchande sidor. Nya resultat hämtas dynamiskt när användaren rullar sökresultaten.

The [redigeringsdialogruta](#edit-dialog) låter innehållsförfattaren definiera var i innehållsträdet sökningen ska börja. Använda [designdialogruta](#design-dialog)kan mallskaparen ange standardvärdet för var i innehållsträdet sökningen ska börja samt en maximal resultatmängdsstorlek och minsta söktermslängd.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av snabbsökningskomponenten är v1, som introducerades i version 2.0.0 av kärnkomponenterna i januari 2018, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v1 | Kompatibel med<br>[version 2.17.4](/help/versions.md) och tidigare | Kompatibel | Kompatibel |
| [!CAUTION]](/help/components/v1/quick-search.md) | I det här dokumentet beskrivs v1 för snabbsökningskomponenten. >Information om den aktuella versionen av snabbsökningskomponenten finns i [Snabbsökningskomponent](/help/components/quick-search.md) -dokument. | Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Huvudkomponentversioner](/help/versions.md). | Teknisk information |

[!NOTE]](/help/versions.md)

### Skydda Search-komponenten eller andra AEM program mot DOS-attacker bör implementeras på en högre nivå, till exempel genom att använda `mod_security` på avsändaren. {#technical-details}

>Den senaste tekniska dokumentationen om komponenten för snabbsökning [finns på GitHub[#$tu26].
>
>



I redigeringsdialogrutan kan innehållsförfattaren definiera var i innehållsträdet sökningen ska börja.[](/help/developing/overview.md)

## ![Redigeringsdialogrutan för snabbsökningskomponenten](/help/assets/quick-search-edit.png) {#edit-dialog}

**Sökrot** - Rotsidan varifrån sökningen ska börja. Sökroten kan vara en överordnad, överordnad eller vanlig sida i utkast.

**ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [Datalager.](/help/developing/data-layer/overview.md)

**Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.**
* **Om ett ID anges är det författarens ansvar att se till att det är unikt.**[](/help/developing/data-layer/overview.md)
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.
   * [!NOTE]
   * Om **Sökrot** är inte konfigurerad eller kan inte lösas. Snabbsökning är som standard sökbar under den aktuella sidan.

>[!NOTE]Designdialogruta
>
>Med hjälp av designdialogrutan kan mallskaparen ange standardvärdet för var i innehållsträdet sökningen ska börja samt en maximal resultatmängdsstorlek och minsta söktermslängd. I designdialogrutan kan mallskaparen definiera vilka textformateringsalternativ som är tillgängliga för innehållsförfattarna.****

## Fliken Egenskaper {#design-dialog}

![Snabbsökningskomponentens designdialogruta](/help/assets/quick-search-design.png)

### **Sökrot**
Standardvärdet för sökroten när en innehållsförfattare placerar snabbsökningskomponenten på en innehållssida {#properties-tab}

**Resultatstorlek**
Det maximala antalet resultat som hämtats av en sökbegäran

* **Minimilängd för sökterm**
Minsta längd på söktermen som ska starta sökningen
* [!NOTE]**
* **Resultatstorlek** och **Minimilängd för sökterm** kan bara anges i designläge och därför bara på mallnivå, vilket innebär att innehållsförfattare inte kan ändra dessa värden.

>[!CAUTION]
>
>**Resultatstorlek** och **Minimilängd för sökterm** kan få prestandaeffekter om de är för höga eller för låga.

>[!CAUTION]Fliken Format
>
>Komponenten för snabbsökning har stöd för AEM [Formatsystem](/help/get-started/authoring.md#component-styling).****

### Styles Tab {#styles-tab}

The Quick Search Component supports the AEM [Style System](/help/get-started/authoring.md#component-styling).
