---
title: E-postbehållarkomponent
description: Med e-postbehållarkomponenten kan du skapa en behållare för flera ytterligare komponenter i e-postinnehållet.
role: Architect, Developer, Admin, User
exl-id: 3b271e95-0093-4cb1-bb83-8446ba12a821
index: false
source-git-commit: eb77567dc32cccb81a9fc131493d11fb55b7e93b
workflow-type: tm+mt
source-wordcount: '780'
ht-degree: 0%

---


# E-postbehållarkomponent {#email-container-component}

Med e-postbehållarkomponenten kan du skapa en behållare för flera ytterligare komponenter i e-postinnehållet.

## Användning {#usage}

Med e-postbehållarkomponenten kan du skapa en behållare för flera ytterligare komponenter i ditt e-postinnehåll, och den kan användas för att gruppera andra komponenter och tillämpa en gemensam stil eller layout.

* Behållarens egenskaper kan väljas i dialogrutan [Konfigurera.](#configure-dialog)
* Standardvärden för e-postbehållarkomponenten när du lägger till den på en sida kan definieras i [designdialogrutan.](#design-dialog)

När en e-postbehållarkomponent har lagts till på en sida kan en innehållsförfattare dra och släppa ytterligare komponenter i den.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av e-postbehållarkomponenten är v1, som introducerades med version X av E-postkärnkomponenterna i oktober 2022, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponenterna är kompatibla med samt länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|---|---|---|---|
| v1 | Kompatibel | - | - |

Mer information om grundkomponentversioner och releaser för e-postmeddelanden finns i dokumentet [E-postversioner av grundkomponenter.](/help/email/versions.md)

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om behållarkomponenten [finns på GitHub.](https://adobe.com/go/aem_cmp_tech_email_container_v1)

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen till utvecklaren av kärnkomponenter.](/help/developing/overview.md)

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera behållarobjektet och hur det fungerar och visas i innehållet.

![Dialogrutan Redigera för e-postbehållarkomponenten](/help/email/assets/email-container-configure.png)

* **Layout** - Det här alternativet definierar beteendet eller layoutbeteendet för e-postbehållarkomponenten.
   * **helbredd**
   * **hälften|hälften**
   * **en-tredjedel|två-tredjedel**
   * **två-tredje|en-tredjedel**
   * **tredje|tredje|tredje|tredje**
* **Bakgrundsfärg** - Definierbar antingen som RGB-värden med valfri form eller med färgväljaren, [beroende på konfiguration](#container-settings-tab)
* **Bakgrundsbild** - Definierar en bakgrundsbild för behållaren, [beroende på konfiguration](#container-settings-tab)
* **ID** - Med det här alternativet kan du kontrollera den unika identifieraren för komponenten i HTML.
   * Om du inte anger något värde genereras ett unikt ID automatiskt och du hittar det genom att kontrollera innehållet.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka CSS.

### Fliken Format {#styles-tab-edit}

E-postbehållarkomponenten stöder AEM [Style System.](/help/get-started/authoring.md#component-styling)

Använd listrutan för att välja de format som du vill använda på komponenten. Markeringar som görs i redigeringsdialogrutan har samma effekt som de som väljs i komponentverktygsfältet.

Format måste konfigureras för den här komponenten i [designdialogrutan](#design-dialog) för att fliken ska vara tillgänglig.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera de alternativ som är tillgängliga för den innehållsförfattare som använder e-postbehållarkomponenten.

### Fliken Tillåtna komponenter {#allowed-components-tab}

Fliken **Tillåtna komponenter** används för att definiera vilka komponenter som kan läggas till som objekt i e-postbehållarkomponenten av innehållsförfattaren.

Fliken **Tillåtna komponenter** fungerar på samma sätt som fliken med samma namn när [du definierar principen och egenskaperna för en layoutbehållare i mallredigeraren.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)

### Fliken Standardkomponenter {#default-components-tab}

Fliken **Standardkomponenter** används för att definiera vilken komponent som läggs till i komponenten när en viss resurstyp släpps i behållaren, ungefär som [hur standardkomponenter definieras i sidmallen.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)

### Fliken Inställningar för behållare {#container-settings-tab}

Fliken **Behållarinställningar** definierar om författaren kan definiera en bakgrundsbild eller -färg.

![Fliken Behållarinställningar i designdialogrutan för e-postbehållarkomponenten](/help/email/assets/email-container-design-container-settings.png)

* **Bakgrundsbild**
   * **Aktivera bakgrundsbild** - Välj det här alternativet om du vill att innehållsförfattaren ska kunna definiera en bakgrundsbild för behållaren.
* **Bakgrundsfärg**
   * **Aktivera bakgrundsfärg** - Välj det här alternativet om du vill att innehållsförfattaren ska kunna definiera en bakgrundsfärg för behållaren.
   * **Endast färgrutor** - Välj det här alternativet om du bara vill tillåta innehållsförfattaren att välja bland fördefinierade färgrutor för behållarens bakgrundsfärg.
      * Endast tillgängligt när **Aktivera bakgrundsfärg** har valts
* **Tillåtna färgrutor** - Definiera fördefinierade färger från vilka innehållsförfattaren kan välja behållarens bakgrundsfärg
   * Använd knappen **Lägg till** för att lägga till en fördefinierad färgruta. När du har lagt till en post läggs den till i listan, som innehåller följande kolumner:
   * **Värde** - Definiera färgen manuellt via RGB-värden
      * Tryck eller klicka på färgväljaren för att enklare välja en färg genom att justera enskilda RGB-värden eller definiera ett hexadecimalt värde.
   * **Ta bort** - Tryck eller klicka för att ta bort en färgruta.
   * **Ordna om** - Tryck eller klicka och dra för att ordna om färgrutorna.

### Fliken Format {#styles-tab}

E-postbehållarkomponenten stöder AEM [Style System.](/help/get-started/authoring.md#component-styling)
