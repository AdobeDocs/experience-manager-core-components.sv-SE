---
title: Behållarkomponent
description: Med komponenten Core Component Container kan du skapa en behållare för flera ytterligare komponenter på en sida.
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# Behållarkomponent{#container-component}

Med komponenten Core Component Container kan du skapa en behållare för flera ytterligare komponenter på en sida.

## Användning {#usage}

Med komponenten Core Component Container kan du skapa en behållare för flera ytterligare komponenter på en sida. Den kan användas för att gruppera andra komponenter och använda en gemensam stil eller layout.

* Behållarens egenskaper kan väljas i [konfigurationsdialogrutan](#configure-dialog).
* Standardvärden för behållarkomponenten när du lägger till den på en sida kan definieras i [designdialogrutan](#design-dialog).

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Container Component är v1, som introducerades i version 2.5.0 av Core Components i juni 2019, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponentversionerna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|---|
| v1 | Kompatibel | Kompatibel | Kompatibel | Kompatibel |

Mer information om Core Component-versioner och -versioner finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill visa Container-komponenten och se exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_container).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om behållarkomponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_container_v1).

Mer information om hur du utvecklar kärnkomponenter finns i dokumentationen till [Core Components Developer](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera behållarobjektet och hur det fungerar och visas för en besökare på sidan.

![](/help/assets/screen-shot-2019-06-21-13.59.26.png)

* **Layout** - Det här alternativet definierar beteendet eller layoutbeteendet för Container-komponenten.
   * **Enkel** - definierar en behållare som en enkel samling komponenter
   * **Responsivt rutnät** - Definierar en behållare som en [AEM-responsiv layout](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/responsive-layout.html)
* **ID** - Använd det här alternativet för att definiera det HTML ID-attribut som ska användas för komponenten.
* **Bakgrundsfärg** - Definierbar antingen som RGB-värden i fri form eller med färgväljaren, [beroende på konfiguration](#background-tab)
* **Bakgrundsbild** - Definierar en bakgrundsfärg för behållaren, [beroende på konfigurationen](#background-tab)

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera de alternativ som är tillgängliga för den innehållsförfattare som använder behållarkomponenten.

### Fliken Tillåtna komponenter {#allowed-components-tab}

Fliken **Tillåtna komponenter** används för att definiera vilka komponenter som kan läggas till som objekt i behållarkomponenten av innehållsförfattaren.

Fliken Tillåtna komponenter fungerar på samma sätt som fliken med samma namn när du [definierar principen och egenskaperna för en layoutbehållare i mallredigeraren.](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)

### Fliken Standardkomponenter {#default-components-tab}

Fliken Standardkomponenter används för att definiera vilken komponent som läggs till i komponenten när en viss resurstyp släpps i behållaren, på samma sätt som [standardkomponenter definieras i sidmallen](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html).

### Fliken Responsiva inställningar {#responsive-settings-tab}

![](/help/assets/screen-shot-2019-06-21-09.33.03.png)

* **Kolumner** - Definierar antalet kolumner i rutnätet för den resulterande behållaren.

### Fliken Bakgrund {#background-tab}

![](/help/assets/screen-shot-2019-06-21-09.42.42.png)

* **Bakgrundsbild**
   * **Aktivera bakgrundsbild** - Välj det här alternativet om du vill att innehållsförfattaren ska kunna definiera en bakgrundsbild för behållaren.
* **Bakgrundsfärg**
   * **Aktivera bakgrundsfärg** - Välj det här alternativet om du vill att innehållsförfattaren ska kunna definiera en bakgrundsfärg för behållaren.
   * **Endast** färgrutor - Välj det här alternativet om du bara vill tillåta innehållsförfattaren att välja bland fördefinierade färgrutor för behållarens bakgrundsfärg.
      * Endast tillgängligt när **Aktivera bakgrundsfärg** har valts
* **Tillåtna färgrutor** - Definiera fördefinierade färger från vilka innehållsförfattaren kan välja behållarens bakgrundsfärg
   * Använd knappen **Lägg** till för att lägga till en fördefinierad färgruta. När du har lagt till en post läggs den till i listan, som innehåller följande kolumner:
   * **Värde** - Definiera färgen manuellt via RGB-värden
      * Tryck eller klicka på färgväljaren för att enklare välja en färg genom att justera enskilda RGB-värden eller definiera ett hexadecimalt värde.
   * **Ta bort** - Tryck eller klicka för att ta bort en färgruta.
   * **Ordna om** - Tryck eller klicka och dra för att ändra ordningen på färgrutorna.

### Fliken Format {#styles-tab}

Container-komponenten stöder AEM [Style System](/help/get-started/authoring.md#component-styling).
