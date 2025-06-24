---
title: PDF Viewer-komponent
description: Med PDF Viewer Component kan du visa ett PDF-dokument.
role: Architect, Developer, Admin, User
exl-id: deb635f5-2b73-4e7a-9838-3a941e39e898
source-git-commit: dd30def59a8f037864da875ef4c831b11f766e57
workflow-type: tm+mt
source-wordcount: '685'
ht-degree: 0%

---


# PDF Viewer-komponent {#pdf-viewer-component}

Med komponenten Core Component PDF Viewer kan du inkludera ett PDF-dokument på en sida.

{{traditional-aem}}

## Användning {#usage}

Komponenten Core Component PDF Viewer bäddar in ett visningsprogram som visar PDF-filer som lagras som resurser på sidan.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av PDF Viewer Component är v1, som introducerades i version 2.10.0 av Core Components i juni 2020, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponenterna är kompatibla med samt länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|--- |--- |---|---|---|
| v1 | Kompatibel med <br>[version 2.17.4](/help/versions.md) och tidigare | Kompatibel | Kompatibel | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill visa komponenterna i PDF Viewer samt se exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_pdfviewer).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om PDF Viewer Component [finns på GitHub](https://adobe.com/go/aem_cmp_tech_pdfviewer_v1).

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).

>[!NOTE]
>
>PDF Viewer-komponenten använder [Adobe Document Services API:er](https://www.adobe.io/apis/documentcloud/dcsdk.html) och kräver att administratören konfigurerar en [kontextmedveten konfiguration](/help/developing/context-aware-configs.md) för att kunna använda dessa tjänster. Mer [information om den här konfigurationen finns i komponentens tekniska dokumentation.](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/pdfviewer/v1/pdfviewer#context-aware-config)

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera visningsprogrammet och hur det ska fungera och visas för en besökare på sidan.

### Fliken Konfiguration {#configuration-tab}

På fliken Konfiguration kan författaren definiera vilken PDF som ska visas. Sökvägen kan definieras som en resurs i AEM eller som en absolut sökväg till en annan resurs.

![Fliken Konfiguration i redigeringsdialogrutan för PDF Viewer-komponenten](/help/assets/pdf-viewer-edit-configuration.png)

### Anpassa flik {#customize-tab}

På fliken Anpassa kan författaren definiera vilka alternativ som är tillgängliga i visningsprogrammet för läsaren och hur visningsprogrammet ska visas.

![Fliken Anpassa i redigeringsdialogrutan för PDF Viewer-komponenten](/help/assets/pdf-viewer-edit-customize.png)

Antalet tillgängliga alternativ beror på vilken **typ** som är vald.

* [Fullständigt fönster](#full-window) - Visningsområdet återges i hela webbläsaren. Detta passar bäst för lagrings- och produktivitetsprogram.
* [Storlek på behållare](#sized-container) - Visningsområdet återges i hela webbläsaren. Detta passar bäst för lagrings- och produktivitetsprogram.
* [In-Line](#in-line) - Alla PDF-sidor som återges i linje på en webbsida. Detta passar bäst för läsning av program.

#### Fullständigt fönster {#full-window}

Visningsområdet återges i hela webbläsaren. Detta passar bäst för lagrings- och produktivitetsprogram.

![Anpassa flikens alternativ för hela fönster i redigeringsdialogrutan för PDF Viewer Component](/help/assets/pdf-viewer-edit-customize-full.png)

* **Standardvisningsläge** - Hur visningsprogrammet passar in på sidan där det visas
   * Anpassa till sida
   * Anpassa bredd
* **Helskärm** - När det här alternativet är aktiverat får visningsprogrammet hela visningsrutans höjd/bredd.
* **Anteckningsverktyg** - När det här alternativet är aktiverat är anteckningsverktygen tillgängliga.
* **Vänster handpanel** - När den är aktiverad visas den vänstra panelen.
* **Hämta PDF** - När det här alternativet är aktiverat visas hämtningsknappen.
* **Skriv ut PDF** - När det här alternativet är aktiverat visas utskriftsknappen.
* **Sidkontroller** - Växlar sidkontrollernas beteende.
   * Docka
   * Avbryt dockning

#### Sized Container {#sized-container}

Visningsområdet återges i hela webbläsaren. Detta passar bäst för lagrings- och produktivitetsprogram.

![Anpassa behållaralternativet för tabbstorlek i redigeringsdialogrutan för PDF Viewer Component](/help/assets/pdf-viewer-edit-customize-sized-container.png)

* **Helskärm** - När det här alternativet är aktiverat får visningsprogrammet hela visningsrutans höjd/bredd.
* **Hämta PDF** - När det här alternativet är aktiverat visas hämtningsknappen.
* **Skriv ut PDF** - När det här alternativet är aktiverat visas utskriftsknappen.
* **Sidkontroller** - Växlar sidkontrollernas beteende.
   * Docka
   * Avbryt dockning

#### Textbunden {#in-line}

Alla PDF-sidor som återges i linje på en webbsida. Detta passar bäst för läsning av program.

![Anpassa behållaralternativet för tabbstorlek i redigeringsdialogrutan för PDF Viewer Component](/help/assets/pdf-viewer-edit-customize-inline.png)

* **Hämta PDF** - När det här alternativet är aktiverat visas hämtningsknappen.
* **Skriv ut PDF** - När det här alternativet är aktiverat visas utskriftsknappen.

## Designdialogruta {#design-dialog}

Det finns ingen designdialogruta för PDF Viewer-komponenten.
