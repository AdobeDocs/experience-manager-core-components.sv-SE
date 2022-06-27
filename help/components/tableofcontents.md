---
title: Innehållsförteckningskomponent
description: Innehållsförteckningskomponenten skapar en innehållsförteckning som baseras på rubrikerna i sidinnehållet, vilket gör att läsarna snabbt kan navigera på sidan.
role: Architect, Developer, Admin, User
exl-id: 006adde2-ebff-4e74-8e79-325cccd43e8f
source-git-commit: 394a8b968d7bcde7e766ed719c5914ec5cb60744
workflow-type: tm+mt
source-wordcount: '759'
ht-degree: 0%

---

# Innehållsförteckningskomponent {#table-of-contents-component}

Innehållsförteckningskomponenten skapar en innehållsförteckning som baseras på rubrikerna i sidinnehållet, vilket gör att läsarna snabbt kan navigera på sidan.

## Användning {#usage}

Innehållsförteckningskomponenten ger besökare möjlighet att snabbt navigera i sidans innehåll via en effektivt genererad innehållsförteckning baserat på rubrikerna för sidinnehållet.

* ToC genereras på serversidan.
* Den cachelagras fullständigt av dispatchern för snabb leverans.
* Det fungerar med alla komponenter på sidan, inte bara med kärnkomponenterna.

The [redigeringsdialogruta](#edit-dialog) gör att innehållsförfattaren kan definiera det intervall med titlar som ska användas i ToC. Använda [designdialogruta](#design-dialog)kan mallskaparen ange standardvärdet för titlarna när en innehållsförfattare lägger till en innehållsförteckningskomponent på en sida, samt begränsa titlar som ingår i innehållsförteckningen baserat på klassnamn.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av innehållsförteckningskomponenten är v1, som introducerades i version 2.20.0 av grundkomponenterna i maj 2022, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | Kompatibel | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Huvudkomponentversioner](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill visa komponenterna i innehållsförteckningen, samt se exempel på konfigurationsalternativen samt HTML och JSON-utdata, går du till [Komponentbibliotek](https://adobe.com/go/aem_cmp_library_tableofcontents).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om innehållsförteckningskomponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_tableofcontents_v1).

Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Dialogrutan Redigera {#edit-dialog}

I redigeringsdialogrutan kan innehållsförfattaren definiera intervall med titelnivåer som innehållsförteckningskomponenten ska återge som en ToC.

![Dialogrutan Redigera i innehållsförteckningskomponenten](/help/assets/tableofcontents-edit.png)

**Listtyp** - Det här alternativet anger om listan ska vara en punktlista eller en numrerad lista.
* **Startnivå för titel** - Det här alternativet definierar den högsta nivån med titlar som innehållsförteckningskomponenten ska återge.
* **Titelstoppnivå** - Det här alternativet definierar den lägsta nivån med titlar som innehållsförteckningskomponenten ska återge.
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [Datalager](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

## Designdialogruta {#design-dialog}

Med hjälp av designdialogrutan kan mallskaparen ange standardvärdet för namnområdet för innehållsförteckningskomponenten samt begränsa rubrikerna i innehållsförteckningen baserat på klassnamn.

### Fliken Egenskaper {#properties-tab}

![Snabbsökningskomponentens designdialogruta](/help/assets/tableofcontents-design.png)

* **Begränsa listtyp** - Det här alternativet definierar den typ av lista som komponenten ska generera. Om du väljer det här alternativet begränsas innehållsförfattarens möjlighet att välja en annan listtyp.
* **Begränsa startnivån** - Det här alternativet definierar den högsta titelnivå som innehållsförfattaren kan välja för att definiera ToC.
* **Begränsa stoppnivån** - Det här alternativet definierar den lägsta titelnivå som innehållsförfattaren kan välja för att definiera ToC.
* **Inkludera klassnamn** - Om det här alternativet är inställt beaktas endast titlar med de angivna klassnamnen eller som finns i element i de angivna klassnamnen av komponenten Innehållsförteckning.
   * Tryck eller klicka på **Lägg till** om du vill lägga till ett eller flera klassnamn.
   * Tryck eller klicka på **Ta bort** -ikonen bredvid ett klassnamn för att ta bort det.
* **Ignorera klassnamn** - Om det här alternativet anges kommer titlar med de angivna klassnamnen eller som finns i element i de angivna klassnamnen att ignoreras av innehållsförteckningskomponenten.
   * Tryck eller klicka på **Lägg till** om du vill lägga till ett eller flera klassnamn.
   * Tryck eller klicka på **Ta bort** -ikonen bredvid ett klassnamn för att ta bort det.

### Fliken Format {#styles-tab}

Innehållsförteckningskomponenten har stöd för AEM [Formatsystem](/help/get-started/authoring.md#component-styling).

## Adobe-klientdatalager {#data-layer}

Innehållsförteckningskomponenten har stöd för [Adobe Client Data Layer.](/help/developing/data-layer/overview.md)
