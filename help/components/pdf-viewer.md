---
title: PDF Viewer Component
description: Med PDF-visningsprogramkomponenten kan du visa ett PDF-dokument.
role: Architect, Developer, Admin, User
exl-id: deb635f5-2b73-4e7a-9838-3a941e39e898
source-git-commit: 9767a3a10cb9a77f385edc0ac3fb00096c0087af
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 1%

---

# PDF Viewer Component {#pdf-viewer-component}

Med komponenten Core Component PDF Viewer kan du ta med ett PDF-dokument på en sida.

## Användning {#usage}

Core Component PDF Viewer-komponenten bäddar in ett visningsprogram som visar PDF-filer som sparats som resurser på.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av PDF Viewer Component är v1, som introducerades i version 2.10.0 av Core Components i juni 2020, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Kompatibel med<br>[version 2.17.4](/help/versions.md) och tidigare | Kompatibel | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Huvudkomponentversioner](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill visa PDF Viewer Component och se exempel på dess konfigurationsalternativ samt HTML och JSON-utdata går du till [Komponentbibliotek](https://adobe.com/go/aem_cmp_library_pdfviewer).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om PDF Viewer Component [finns på GitHub](https://adobe.com/go/aem_cmp_tech_pdfviewer_v1).

Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

>[!NOTE]
>
>PDF Viewer Components använder [Adobe Document Services API:er](https://www.adobe.io/apis/documentcloud/dcsdk.html) och kräver att administratören konfigurerar [kontextmedveten konfiguration](/help/developing/context-aware-configs.md) för att kunna använda dessa tjänster. Kontrollera komponentens tekniska dokumentation för [information om den här konfigurationen.](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/pdfviewer/v1/pdfviewer#context-aware-config)

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera visningsprogrammet och hur det ska fungera och visas för en besökare på sidan.

### Fliken Konfiguration {#configuration-tab}

På fliken Konfiguration kan författaren definiera vilken PDF som ska visas. Sökvägen kan definieras som en resurs i AEM eller en absolut sökväg till en annan resurs.

![Fliken Konfiguration i redigeringsdialogrutan för komponenten PDF Viewer](/help/assets/pdf-viewer-edit-configuration.png)

### Anpassa flik {#customize-tab}

På fliken Anpassa kan författaren definiera vilka alternativ som är tillgängliga i visningsprogrammet för läsaren och hur visningsprogrammet ska visas.

![Fliken Anpassa i redigeringsdialogrutan för komponenten PDF Viewer](/help/assets/pdf-viewer-edit-customize.png)

Antalet tillgängliga alternativ beror på **Typ** som är markerat.

* [Fullständigt fönster](#full-window) - Visningsområdet återges i hela webbläsaren. Detta passar bäst för lagrings- och produktivitetsprogram.
* [Sized Container](#sized-container) - Visningsområdet återges i hela webbläsaren. Detta passar bäst för lagrings- och produktivitetsprogram.
* [Textbunden](#in-line) - Alla PDF-sidor som återges i linje på en webbsida. Detta passar bäst för läsning av program.

#### Fullständigt fönster {#full-window}

Visningsområdet återges i hela webbläsaren. Detta passar bäst för lagrings- och produktivitetsprogram.

![Anpassa flikens alternativ för hela fönster i redigeringsdialogrutan för komponenten PDF Viewer](/help/assets/pdf-viewer-edit-customize-full.png)

* **Standardvisningsläge** - Hur visningsprogrammet passar in på sidan där det visas
   * Anpassa till sidan
   * Anpassa bredd
* **Helskärm** - När det här alternativet är aktiverat får visningsprogrammet hela höjden/bredden för visningsrutan.
* **Anteckningsverktyg** - När det här alternativet är aktiverat är anteckningsverktygen tillgängliga.
* **Vänster handpanel** - När det här alternativet är aktiverat visas den vänstra panelen.
* **Hämta PDF** - När det här alternativet är aktiverat visas hämtningsknappen.
* **Skriv ut PDF** - När det här alternativet är aktiverat visas utskriftsknappen.
* **Sidkontroller** - Växlar beteendet för sidkontrollerna.
   * Docka
   * Avbryt dockning

#### Sized Container {#sized-container}

Visningsområdet återges i hela webbläsaren. Detta passar bäst för lagrings- och produktivitetsprogram.

![Anpassa behållaralternativet för flikstorlek i redigeringsdialogrutan för komponenten PDF Viewer](/help/assets/pdf-viewer-edit-customize-sized-container.png)

* **Helskärm** - När det här alternativet är aktiverat får visningsprogrammet hela höjden/bredden för visningsrutan.
* **Hämta PDF** - När det här alternativet är aktiverat visas hämtningsknappen.
* **Skriv ut PDF** - När det här alternativet är aktiverat visas utskriftsknappen.
* **Sidkontroller** - Växlar beteendet för sidkontrollerna.
   * Docka
   * Avbryt dockning

#### Textbunden {#in-line}

Alla PDF-sidor som återges i linje på en webbsida. Detta passar bäst för läsning av program.

![Anpassa behållaralternativet för flikstorlek i redigeringsdialogrutan för komponenten PDF Viewer](/help/assets/pdf-viewer-edit-customize-inline.png)

* **Hämta PDF** - När det här alternativet är aktiverat visas hämtningsknappen.
* **Skriv ut PDF** - När det här alternativet är aktiverat visas utskriftsknappen.

## Designdialogruta {#design-dialog}

Det finns ingen designdialogruta för PDF-visningsprogramkomponenten.
