---
title: Innehållsförteckning, komponent
description: Innehållsförteckningskomponenten skapar en innehållsförteckning som baseras på rubrikerna i sidinnehållet, vilket gör att läsarna snabbt kan navigera på sidan.
role: Architect, Developer, Admin, User
exl-id: 006adde2-ebff-4e74-8e79-325cccd43e8f
source-git-commit: 1987431c99a1e4b834c86ea731c52a19909b297b
workflow-type: tm+mt
source-wordcount: '753'
ht-degree: 0%

---


# Innehållsförteckning, komponent {#table-of-contents-component}

Innehållsförteckningskomponenten skapar en innehållsförteckning som baseras på rubrikerna i sidinnehållet, vilket gör att läsarna snabbt kan navigera på sidan.

{{traditional-aem}}

## Användning {#usage}

Innehållsförteckningskomponenten ger besökare möjlighet att snabbt navigera i sidans innehåll via en effektivt genererad innehållsförteckning baserat på rubrikerna för sidinnehållet.

* ToC genereras på serversidan.
* Den cachelagras fullständigt av dispatchern för snabb leverans.
* Det fungerar med alla komponenter på sidan, inte bara med kärnkomponenterna.

I [redigeringsdialogrutan](#edit-dialog) kan innehållsförfattaren definiera intervallet med titlar som ska användas i ToC. Med hjälp av [designdialogrutan](#design-dialog) kan mallskaparen ange standardvärdet för rubrikerna när en innehållsförfattare lägger till en innehållsförteckningskomponent på en sida, samt begränsa titlar som ingår i innehållsförteckningen baserat på klassnamn.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av innehållsförteckningskomponenten är v1, som introducerades i version 2.20.0 av grundkomponenterna i maj 2022, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponenterna är kompatibla med samt länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|---|---|---|---|
| v1 | Kompatibel | Kompatibel | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Core Components Versions](/help/versions.md).

>[!NOTE]
>
>I AEM as a Cloud Service måste administratören aktivera ett filter för komponenten för att den ska kunna återge komponentens innehåll.
>
>[Mer information finns i GitHub-dokumentationen för komponenten](https://adobe.com/go/aem_cmp_tech_tableofcontents_v1).

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om innehållsförteckningskomponenten [ finns på GitHub](https://adobe.com/go/aem_cmp_tech_tableofcontents_v1).

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).

## Dialogrutan Redigera {#edit-dialog}

I redigeringsdialogrutan kan innehållsförfattaren definiera intervall med titelnivåer som innehållsförteckningskomponenten ska återge som en ToC.

![Dialogrutan Redigera i innehållsförteckningskomponenten](/help/assets/tableofcontents-edit.png)

**Listtyp** - Det här alternativet anger om listan ska vara en punktlista eller en numrerad lista.
* **Rubrikstartnivå** - Det här alternativet definierar den högsta nivån med titlar som innehållsförteckningskomponenten ska återge.
* **Titelstoppnivå** - Det här alternativet definierar den lägsta nivån med titlar som innehållsförteckningskomponenten ska återge.
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [datalagret](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

## Designdialogruta {#design-dialog}

Med hjälp av designdialogrutan kan mallskaparen ange standardvärdet för namnområdet för innehållsförteckningskomponenten samt begränsa rubrikerna i innehållsförteckningen baserat på klassnamn.

### Fliken Egenskaper {#properties-tab}

![Snabbsökningskomponentens designdialogruta](/help/assets/tableofcontents-design.png)

* **Begränsa listtyp** - Det här alternativet definierar den typ av lista som komponenten ska generera. Om du väljer det här alternativet begränsas innehållsförfattarens möjlighet att välja en annan listtyp.
* **Begränsa startnivån** - Det här alternativet definierar den högsta titelnivå som innehållsförfattaren kan välja för att definiera ToC.
* **Begränsa stoppnivån** - Det här alternativet definierar den lägsta titelnivån som innehållsförfattaren kan välja för att definiera ToC.
* **Inkludera klassnamn** - Om det här alternativet anges beaktas endast titlar med de angivna klassnamnen eller som finns i element i de angivna klassnamnen av komponenten Innehållsförteckning.
   * Tryck eller klicka på ikonen **Lägg till** för att lägga till ett eller flera klassnamn.
   * Tryck eller klicka på ikonen **Ta bort** bredvid ett klassnamn för att ta bort den.
* **Ignorera klassnamn** - Om det här alternativet anges ignoreras rubriker med de angivna klassnamnen eller som finns i element i de angivna klassnamnen av innehållsförteckningskomponenten.
   * Tryck eller klicka på ikonen **Lägg till** för att lägga till ett eller flera klassnamn.
   * Tryck eller klicka på ikonen **Ta bort** bredvid ett klassnamn för att ta bort den.

### Fliken Format {#styles-tab}

Innehållsförteckningskomponenten stöder AEM [Style System.](/help/get-started/authoring.md#component-styling).
