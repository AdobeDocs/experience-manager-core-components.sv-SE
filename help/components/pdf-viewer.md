---
title: PDF Viewer-komponent
description: Med PDF Viewer Component kan du visa ett PDF-dokument.
role: Architect, Developer, Administrator, Business Practitioner
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 1%

---


# PDF Viewer Component {#pdf-viewer-component}

Komponenten Core Component PDF Viewer gör det möjligt att inkludera ett PDF-dokument på en sida.

## Användning {#usage}

Komponenten Core Component PDF Viewer bäddar in ett visningsprogram som visar PDF-filer som sparats som resurser på sidan.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av PDF Viewer Component är v1, som introducerades i version 2.10.0 av Core Components i juni 2020, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Kompatibel | Kompatibel | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempelkomponentutdata {#sample-component-output}

Om du vill visa PDF Viewer-komponenten och se exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_pdfviewer).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om PDF Viewer Component [finns på GitHub](https://adobe.com/go/aem_cmp_tech_pdfviewer_v1).

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen till Core Components developer](/help/developing/overview.md).

>[!NOTE]
>
>PDF Viewer-komponenten använder [Adobe Document Services API:er](https://www.adobe.io/apis/documentcloud/dcsdk.html) och kräver att administratören konfigurerar en [kontextmedveten konfiguration](/help/developing/context-aware-configs.md) för att kunna använda dessa tjänster. Läs den tekniska dokumentationen för komponenten [om du vill ha mer information om den här konfigurationen.](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/pdfviewer/v1/pdfviewer#context-aware-config)

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera visningsprogrammet och hur det ska fungera och visas för en besökare på sidan.

### Konfigurationsflik {#configuration-tab}

På fliken Konfiguration kan författaren definiera vilken PDF som ska visas. Sökvägen kan definieras som en resurs i AEM eller en absolut sökväg till en annan resurs.

![Fliken Konfiguration i redigeringsdialogrutan för PDF-visningskomponenten](/help/assets/pdf-viewer-edit-configuration.png)

### Anpassa flik {#customize-tab}

På fliken Anpassa kan författaren definiera vilka alternativ som är tillgängliga i visningsprogrammet för läsaren och hur visningsprogrammet ska visas.

![Anpassa fliken i redigeringsdialogrutan för PDF-visningskomponenten](/help/assets/pdf-viewer-edit-customize.png)

Hur många alternativ som är tillgängliga beror på vilken **typ** som är vald.

* [Fullständigt fönster](#full-window)  - Visningsområdet återges i hela webbläsaren. Detta passar bäst för lagrings- och produktivitetsprogram.
* [Storleksstyrd behållare](#sized-container)  - Visningsområdet återges i hela webbläsaren. Detta passar bäst för lagrings- och produktivitetsprogram.
* [In-Line](#in-line)  - Alla PDF-sidor som återges i linje på en webbsida. Detta passar bäst för läsning av program.

#### Fullständigt fönster {#full-window}

Visningsområdet återges i hela webbläsaren. Detta passar bäst för lagrings- och produktivitetsprogram.

![Anpassa flikens fullständiga fönsteralternativ i redigeringsdialogrutan för PDF-visningskomponenten](/help/assets/pdf-viewer-edit-customize-full.png)

* **Standardvisningsläge**  - Hur visningsprogrammet passar in på sidan där det visas
   * Anpassa till sidan
   * Anpassa bredd
* **Helskärm**  - När det här alternativet är aktiverat får visningsprogrammet full höjd/bredd för visningsrutan.
* **Anteckningsverktyg**  - När det här alternativet är aktiverat är anteckningsverktygen tillgängliga.
* **Vänster handpanel**  - När den är aktiverad visas den vänstra panelen.
* **Hämta PDF**  - När det här alternativet är aktiverat visas hämtningsknappen.
* **Skriv ut PDF**  - När det här alternativet är aktiverat visas knappen Skriv ut.
* **Sidkontroller**  - Växlar sidkontrollernas beteende.
   * Docka
   * Avbryt dockning

#### Sized Container {#sized-container}

Visningsområdet återges i hela webbläsaren. Detta passar bäst för lagrings- och produktivitetsprogram.

![Anpassa behållaralternativet för flikstorlek i redigeringsdialogrutan för PDF-visningskomponenten](/help/assets/pdf-viewer-edit-customize-sized-container.png)

* **Helskärm**  - När det här alternativet är aktiverat får visningsprogrammet full höjd/bredd för visningsrutan.
* **Hämta PDF**  - När det här alternativet är aktiverat visas hämtningsknappen.
* **Skriv ut PDF**  - När det här alternativet är aktiverat visas knappen Skriv ut.
* **Sidkontroller**  - Växlar sidkontrollernas beteende.
   * Docka
   * Avbryt dockning

#### Inline {#in-line}

Alla PDF-sidor som återges i linje på en webbsida. Detta passar bäst för läsning av program.

![Anpassa behållaralternativet för flikstorlek i redigeringsdialogrutan för PDF-visningskomponenten](/help/assets/pdf-viewer-edit-customize-inline.png)

* **Hämta PDF**  - När det här alternativet är aktiverat visas hämtningsknappen.
* **Skriv ut PDF**  - När det här alternativet är aktiverat visas knappen Skriv ut.

## Designdialog {#design-dialog}

Det finns ingen designdialogruta för PDF Viewer-komponenten.
