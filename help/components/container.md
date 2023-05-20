---
title: Behållarkomponent
description: Med komponenten Core Component Container kan du skapa en behållare för flera ytterligare komponenter på en sida.
role: Architect, Developer, Admin, User
exl-id: 53c7190d-44cb-42ff-bc1a-483c7875bcf8
source-git-commit: 9767a3a10cb9a77f385edc0ac3fb00096c0087af
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 0%

---

# Behållarkomponent{#container-component}

Med komponenten Core Component Container kan du skapa en behållare för flera ytterligare komponenter på en sida.

## Användning {#usage}

Med komponenten Core Component Container kan du skapa en behållare för flera ytterligare komponenter på en sida. Den kan användas för att gruppera andra komponenter och använda en gemensam stil eller layout.

* Behållarens egenskaper kan markeras i [konfigurera dialogruta](#configure-dialog).
* Standardvärden för behållarkomponenten när du lägger till den på en sida kan definieras i [designdialogruta](#design-dialog).

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Container Component är v1, som introducerades i version 2.5.0 av Core Components i juni 2019, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Kompatibel med<br>[version 2.17.4](/help/versions.md) och tidigare | Kompatibel | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Huvudkomponentversioner](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill visa Container Component (Behållarkomponent) och se exempel på dess konfigurationsalternativ samt HTML och JSON-utdata går du till [Komponentbibliotek](https://adobe.com/go/aem_cmp_library_container).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om behållarkomponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_container_v1).

Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera behållarobjektet och hur det fungerar och visas för en besökare på sidan.

![Dialogrutan Redigera för behållarkomponenten](/help/assets/container-edit.png)

* **Layout** - Det här alternativet definierar beteendet eller layoutbeteendet för Container-komponenten.
   * **Enkel** - Definierar en behållare som en enkel samling komponenter
   * **Responsivt rutnät** - Definierar en behållare som en [AEM responsiv layout](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/responsive-layout.html)
* **Bakgrundsfärg** - Definieras antingen som RGB i fri form eller med färgväljaren. [beroende på konfiguration](#background-tab)
* **Bakgrundsbild** - Definierar en bakgrundsfärg för behållaren,  [beroende på konfiguration](#background-tab)
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [Datalager](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera de alternativ som är tillgängliga för den innehållsförfattare som använder behållarkomponenten.

### Fliken Tillåtna komponenter {#allowed-components-tab}

The **Tillåtna komponenter** -fliken används för att definiera vilka komponenter som innehållsförfattaren kan lägga till som objekt i behållarkomponenten.

Fliken Tillåtna komponenter fungerar på samma sätt som fliken med samma namn när [definiera policyn och egenskaperna för en layoutbehållare i mallredigeraren.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)

### Fliken Standardkomponenter {#default-components-tab}

Fliken Standardkomponenter används för att definiera vilken komponent som läggs till i komponenten när en viss resurstyp släpps i behållaren, på liknande sätt som [hur standardkomponenter definieras i sidmallen](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html).

### Fliken Responsiva inställningar {#responsive-settings-tab}

![Fliken Responsiva inställningar i designdialogrutan för behållarkomponenten](/help/assets/container-design-responsive.png)

* **Kolumner** - Definierar antalet kolumner i rutnätet för den resulterande behållaren.

### Fliken Bakgrund {#background-tab}

![Fliken Bakgrund i designdialogrutan för behållarkomponenten](/help/assets/container-design-background.png)

* **Bakgrundsbild**
   * **Aktivera bakgrundsbild** - Välj det här alternativet om du vill att innehållsförfattaren ska kunna definiera en bakgrundsbild för behållaren.
* **Bakgrundsfärg**
   * **Aktivera bakgrundsfärg** - Välj det här alternativet om du vill att innehållsförfattaren ska kunna definiera en bakgrundsfärg för behållaren.
   * **Endast färgrutor** - Välj det här alternativet om du bara vill tillåta innehållsförfattaren att välja bland fördefinierade färgrutor för behållarens bakgrundsfärg.
      * Endast tillgängligt när **Aktivera bakgrundsfärg** är markerat
* **Tillåtna färgrutor** - Definiera fördefinierade färger från vilka innehållsförfattaren kan välja behållarens bakgrundsfärg
   * Använd **Lägg till** om du vill lägga till en fördefinierad färgruta. När du har lagt till en post läggs den till i listan, som innehåller följande kolumner:
   * **Värde** - Definiera färgen manuellt via RGB
      * Tryck eller klicka på färgväljaren för att enklare välja en färg genom att justera enskilda RGB-värden eller definiera ett hexadecimalt värde.
   * **Ta bort** - Tryck eller klicka för att ta bort en färgruta.
   * **Ordna om** - Tryck eller klicka och dra för att ändra ordningen på färgrutorna.

### Fliken Format {#styles-tab}

Container-komponenten stöder AEM [Formatsystem](/help/get-started/authoring.md#component-styling).
