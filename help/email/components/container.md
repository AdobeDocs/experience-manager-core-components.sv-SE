---
title: E-postbehållarkomponent
description: Med e-postbehållarkomponenten kan du skapa en behållare för flera ytterligare komponenter i e-postinnehållet.
role: Architect, Developer, Admin, User
hidefromtoc: true
index: false
source-git-commit: 8bebe3ca036557f3f7c6b8ec0e65d6d104d5ffae
workflow-type: tm+mt
source-wordcount: '835'
ht-degree: 1%

---


# E-postbehållarkomponent {#email-container-component}

Med e-postbehållarkomponenten kan du skapa en behållare för flera ytterligare komponenter i e-postinnehållet.

## Användning {#usage}

Med e-postbehållarkomponenten kan du skapa en behållare för flera ytterligare komponenter i ditt e-postinnehåll, och den kan användas för att gruppera andra komponenter och tillämpa en gemensam stil eller layout.

* Behållarens egenskaper kan markeras i [dialogrutan konfigurera.](#configure-dialog)
* Standardvärden för e-postbehållarkomponenten när du lägger till den på en sida kan definieras i [designdialog.](#design-dialog)

När en e-postbehållarkomponent har lagts till på en sida kan en innehållsförfattare dra och släppa ytterligare komponenter i den.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av e-postbehållarkomponenten är v1, som introducerades med version X av E-postkärnkomponenterna i oktober 2022, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | Kompatibel | Kompatibel |

Mer information om e-postkärnkomponentversioner och -versioner finns i dokumentet [E-postkärnkomponentversioner.](/help/email/versions.md)

## Exempel på komponentutdata {#sample-component-output}

Om du vill se exempel på e-postbehållarkomponenten och dess konfigurationsalternativ samt HTML och JSON-utdata går du till [Komponentbibliotek.](https://adobe.com/go/aem_cmp_library_email_container)

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om behållarkomponenten [finns på GitHub.](https://adobe.com/go/aem_cmp_tech_email_container_v1)

Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentens utvecklare.](/help/developing/overview.md)

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera behållarobjektet och hur det fungerar och visas i innehållet.

![Dialogrutan Redigera för e-postbehållarkomponenten](/help/email/assets/email-container-configure.png)

* **Layout** - Det här alternativet definierar beteendet eller layoutbeteendet för e-postbehållarkomponenten.
   * **helbredd**
   * **halv|halv**
   * **en tredjedel|två tredjedelar**
   * **två tredjedelar|en tredjedel**
   * **tredje|tredje|tredje**
* **Bakgrundsfärg** - Definieras antingen som RGB i fri form eller med färgväljaren. [beroende på konfiguration](#container-settings-tab)
* **Bakgrundsbild** - Definierar en bakgrundsbild för behållaren, [beroende på konfiguration](#container-settings-tab)
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML.
   * Om du inte anger något värde genereras ett unikt ID automatiskt och du hittar det genom att kontrollera innehållet.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka CSS.

### Fliken Format {#styles-tab-edit}

E-postbehållarkomponenten stöder AEM [Formatsystem.](/help/get-started/authoring.md#component-styling)

Använd listrutan för att välja de format som du vill använda på komponenten. Markeringar som görs i redigeringsdialogrutan har samma effekt som de som väljs i komponentverktygsfältet.

Format måste konfigureras för den här komponenten i [designdialogruta](#design-dialog) för att fliken ska vara tillgänglig.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera de alternativ som är tillgängliga för den innehållsförfattare som använder e-postbehållarkomponenten.

### Fliken Tillåtna komponenter {#allowed-components-tab}

The **Tillåtna komponenter** -fliken används för att definiera vilka komponenter som innehållsförfattaren kan lägga till som objekt i e-postbehållarkomponenten.

The **Tillåtna komponenter** tabbfunktioner på samma sätt som tabben med samma namn när [definiera policyn och egenskaperna för en layoutbehållare i mallredigeraren.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)

### Fliken Standardkomponenter {#default-components-tab}

The **Standardkomponenter** -fliken används för att definiera vilken komponent som läggs till i komponenten när en viss resurstyp släpps i behållaren, ungefär som [hur standardkomponenter definieras på sidmallen.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)

### Fliken Inställningar för behållare {#container-settings-tab}

The **Behållarinställningar** -fliken definierar om författaren kan definiera en bakgrundsbild eller -färg.

![Fliken Behållarinställningar i designdialogrutan för e-postbehållarkomponenten](/help/email/assets/email-container-design-container-settings.png)

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

E-postbehållarkomponenten stöder AEM [Formatsystem.](/help/get-started/authoring.md#component-styling)