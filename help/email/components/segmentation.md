---
title: E-postsegmenteringskomponent
description: E-postsegmentkomponenten
role: Architect, Developer, Admin, User
exl-id: 6c88b8c5-189a-40c0-ab28-04d37dc5fbac
source-git-commit: 3abc29e0c186a84f079d5938b8b716f4c7378d65
workflow-type: tm+mt
source-wordcount: '1133'
ht-degree: 0%

---


# E-postsegmenteringskomponent {#email-segmentation-component}

E-postsegmentkomponenten använder variabler från Adobe Campaign för att visa och dölja innehåll baserat på innehållets mottagare.

## Användning {#usage}

Med e-postsegmentkomponenten kan innehållsförfattaren dölja och visa innehåll baserat på villkor som uppfylls av variabler om mottagaren som tillhandahålls av Adobe Campaign. På så sätt ser mottagarna av innehållet innehåll baserat på deras segmentering.

* Mallförfattaren kan använda [designdialogruta](#design-dialog) för att definiera vilka komponenter som kan läggas till som segment.
* Innehållsförfattaren kan använda [konfigurera dialogruta](#configure-dialog) om du vill lägga till komponenter som segment och konfigurera vilka segment som visas baserat på Adobe Campaign-variabler.

Som ett alternativ till att använda konfigurationsdialogrutan kan innehållsförfattaren, när innehållsförfattaren har lagt till e-postsegmentkomponenten på en innehållssida, dra och släppa ytterligare komponenter till e-postsegmentskomponenterna för att skapa nya segment.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av e-postsegmentkomponenten är v1, som introducerades med version x av e-postkärnkomponenterna i oktober 2022, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | Kompatibel | - |

### Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om e-postteamkomponenten [finns på GitHub.](https://adobe.com/go/aem_cmp_tech_email_segmentation_v1)

Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentens utvecklare.](/help/developing/overview.md)

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren skapa, byta namn på och ordna om segment samt definiera det aktiva segmentet. I e-postsegmentkomponenten är ett segment helt enkelt en annan komponent som döljs eller visas baserat på de villkor som uppfylls av mottagaren av innehållet. Du kan jämföra den med [Flikkomponenten Core Components,](/help/components/tabs.md) men i segmenteringskomponenten visas bara innehållet på fliken vars villkor uppfylls.

### Fliken Objekt {#items-tab}

![Komponenten för e-postsegmentering Konfigurera dialogruteobjekt](/help/email/assets/email-segmentation-configure-items.png)

Använd **Lägg till segment** för att öppna komponentväljaren och välja vilken komponent som ska läggas till som ett segment. När den har lagts till läggs en post till i listan, som innehåller följande element:

* **Ikon** - Ikonen för segmentets komponenttyp, vilket gör det enkelt att identifiera i listan. För musen över för att se det fullständiga komponentnamnet som ett verktygstips.
* **Villkor** - Det villkor som måste uppfyllas för att det här segmentet ska visas för mottagaren av innehållet.
   * De tillgängliga villkoren definieras i [designdialog.](#design-dialog)
   * **Standard** - Definierar standardsegmentet som ska visas om inga andra villkor uppfylls
   * **Egen** - Låter författaren definiera ett villkor
      * Villkoren baseras på Adobe Campaign personaliseringsvariabler
      * [Här finns information om Adobe Campaign Standard personaliseringsresurser.](https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/personalization.html?)
      * [Här finns information om Adobe Campaign Classic personaliseringsresurser.](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-fields.html)
* **Ta bort** - Tryck eller klicka för att ta bort segmentet från e-postsegmentkomponenten.
* **Ordna om** - Tryck eller klicka och dra för att ordna om segmenten.

>[!TIP]
>
>Om visningsrutan för innehållet minskas så att redigeringsdialogrutan blir helskärm, visas **Lägg till** knappen döljs. Komponenter kan fortfarande läggas till i e-postsegmentkomponenten av [dra från komponentwebbläsaren och släpp på E-postsegmentkomponenten i innehållsredigeraren.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#inserting-a-component)

### Fliken Egenskaper {#properties-tab}

![Fliken Egenskaper i dialogrutan Konfigurera för e-postsegmentkomponenten](/help/email/assets/email-segmentation-configure-properties.png)

* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML.
   * Om du inte anger något värde genereras ett unikt ID automatiskt och du hittar det genom att kontrollera innehållet.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka CSS.

### Fliken Tillgänglighet {#accessibility-tab}

![Komponenten för e-postsegmentering Konfigurera fliken för tillgänglighet i dialogrutan](/help/email/assets/email-segmentation-configure-accessibility.png)

På **Tillgänglighet** -tabb kan värden anges för [Tillgänglighet för ARIA](https://www.w3.org/WAI/standards-guidelines/aria/) -etiketter för komponenten.

* **Etikett** - Värdet på ett ARIA-etikettattribut för komponenten

### Fliken Format {#styles-tab-edit}

E-postsegmentkomponenten stöder AEM [Formatsystem.](/help/get-started/authoring.md#component-styling)

Använd listrutan för att välja de format som du vill använda på komponenten. Markeringar som görs i redigeringsdialogrutan har samma effekt som de som väljs i komponentverktygsfältet.

Format måste konfigureras för den här komponenten i [designdialogruta](#design-dialog) för att fliken ska vara tillgänglig.

## Välj panel {#select-panel}

Innehållsförfattaren kan använda **Välj panel** i komponentens verktygsfält för att ändra till ett annat segment för redigering samt för att enkelt ordna om segmenten.

![Ikonen Välj panel](/help/email/assets/select-panel-icon.png)

När du har valt **Välj panel** i komponentverktygsfältet visas de konfigurerade segmenten som en listruta.

* Listan ordnas efter segmentens tilldelade ordning och återspeglas i numreringen.
* Segmentets komponenttyp visas först, följt av segmentets beskrivning med ett ljusare teckensnitt.

![Välj panelpekare](/help/email/assets/select-panel-popover.png)

* Om du trycker eller klickar på en post i listrutan växlar vyn i redigeraren till det segmentet.
* Segmenten kan ordnas om på plats med hjälp av draghandtagen.

>[!NOTE]
>
>Segment återges som flikar i sidredigeraren för att visa att det finns flera alternativ för det slutliga innehållet. Dessa flikar kan inte markeras av författaren i sidredigeraren. Använd markeringspanelen för att växla mellan visade segment.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera vilka komponenter som kan läggas till som segment i e-postsegmentkomponenten samt definiera vilka anpassade format som är tillgängliga för innehållsförfattaren.

### Fliken Tillåtna komponenter {#allowed-components-tab}

The **Tillåtna komponenter** -fliken används för att definiera vilka komponenter som innehållsförfattaren kan lägga till som segment i e-postsegmentkomponenten.

The **Tillåtna komponenter** tabbfunktioner på samma sätt som tabben med samma namn när [definiera policyn och egenskaperna för en layoutbehållare i mallredigeraren.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)

### Fliken Format {#styles-tab}

E-postsegmentkomponenten stöder AEM [Formatsystem.](/help/get-started/authoring.md#component-styling)

### Fliken Definierade villkor {#defined-conditions}

Använda **Definierade villkor** kan mallredigeraren definiera vilka villkor som är tillgängliga för innehållsförfattaren att välja när segment skapas.

![Fliken Definierade villkor i dialogrutan Design](/help/email/assets/email-segmentation-design-defined-conditions.png)

Tryck eller klicka på **Lägg till** för att skapa nya villkor.

* **Namn på segmentvillkor** - En beskrivning av villkoret
* **Segmentvillkor** - Det faktiska villkor som måste uppfyllas, baserat på Adobe Campaign personaliseringsvariabler
   * [Här finns information om Adobe Campaign Standard personaliseringsresurser.](https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/personalization.html?)
   * [Här finns information om Adobe Campaign Classic personaliseringsresurser.](https://experienceleague.adobe.com/docs/
* **Ta bort** - Tryck för att klicka för att ta bort villkoret
* **Ordna om** - Tryck eller klicka och dra för att ändra ordningen på villkoren
