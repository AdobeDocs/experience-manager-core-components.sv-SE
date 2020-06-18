---
title: PDF Viewer-komponent
description: Med PDF Viewer Component kan du visa ett PDF-dokument.
translation-type: tm+mt
source-git-commit: 0df759a020020c21d776eb8f45d40cb7aff45cea
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 1%

---


# PDF Viewer-komponent {#pdf-viewer-component}


Komponenten Core Component PDF Viewer gör det möjligt att inkludera ett PDF-dokument på en sida.

## Användning {#usage}

Komponenten Core Component PDF Viewer bäddar in ett visningsprogram som visar PDF-filer som sparats som resurser på sidan.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av PDF Viewer Component är v1, som introducerades i version 2.10.0 av Core Components i juni 2020, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponentversionerna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Kompatibel | Kompatibel | Kompatibel |

Mer information om Core Component-versioner och -versioner finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill visa komponenterna i PDF Viewer samt se exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_pdf_viewer).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om PDF Viewer Component [finns på GitHub](https://adobe.com/go/aem_cmp_tech_pdf-viewer_v1).

Mer information om hur du utvecklar kärnkomponenter finns i dokumentationen till [Core Components Developer](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera visningsprogrammet och hur det ska fungera och visas för en besökare på sidan.

### Fliken Konfiguration {#configuration-tab}

På fliken Konfiguration kan författaren definiera vilken PDF som ska visas. Sökvägen kan definieras som en resurs i AEM eller en absolut sökväg till en annan resurs.

![Fliken Konfiguration i redigeringsdialogrutan för PDF-visningskomponenten](/help/assets/pdf-viewer-edit-configuration.png)

### Anpassa flik {#customize-tab}

På fliken Anpassa kan författaren definiera vilka alternativ som är tillgängliga i visningsprogrammet för läsaren och hur visningsprogrammet ska visas.

![Anpassa fliken i redigeringsdialogrutan för PDF-visningskomponenten](/help/assets/pdf-viewer-edit-customize.png)

Hur många alternativ som är tillgängliga beror på vilken **typ** som är vald.

* [Fullständigt fönster](#full-window) - Visningsområdet återges i hela webbläsaren. Detta passar bäst för lagrings- och produktivitetsprogram.
* [Sized Container](#sized-container) - Visningsområdet återges i hela webbläsaren. Detta passar bäst för lagrings- och produktivitetsprogram.
* [Textbunden](#in-line) - Alla PDF-sidor som återges i linje på en webbsida. Detta passar bäst för läsning av program.

#### Fullständigt fönster {#full-window}

Visningsområdet återges i hela webbläsaren. Detta passar bäst för lagrings- och produktivitetsprogram.

![Anpassa flikens fullständiga fönsteralternativ i redigeringsdialogrutan för PDF-visningskomponenten](/help/assets/pdf-viewer-edit-customize-full.png)

* **Standardvisningsläge** - Hur visningsprogrammet passar in på sidan där det visas
   * Anpassa till sidan
   * Anpassa bredd
* **Helskärm** - När det här alternativet är aktiverat får visningsprogrammet hela höjd/bredd för visningsrutan.
* **Anteckningsverktyg** - När det här alternativet är aktiverat är anteckningsverktygen tillgängliga.
* **Vänster handpanel** - När den är aktiverad visas den vänstra panelen.
* **Hämta PDF** - När det här alternativet är aktiverat visas hämtningsknappen.
* **Skriv ut PDF** - När det här alternativet är aktiverat visas utskriftsknappen.
* **Sidkontroller** - Växlar sidkontrollernas beteende.
   * Docka
   * Avbryt dockning

#### Sized Container {#sized-container}

Visningsområdet återges i hela webbläsaren. Detta passar bäst för lagrings- och produktivitetsprogram.

![Anpassa behållaralternativet för flikstorlek i redigeringsdialogrutan för PDF-visningskomponenten](/help/assets/pdf-viewer-edit-customize-sized-container.png)

* **Helskärm** - När det här alternativet är aktiverat får visningsprogrammet hela höjd/bredd för visningsrutan.
* **Hämta PDF** - När det här alternativet är aktiverat visas hämtningsknappen.
* **Skriv ut PDF** - När det här alternativet är aktiverat visas utskriftsknappen.
* **Sidkontroller** - Växlar sidkontrollernas beteende.
   * Docka
   * Avbryt dockning

#### Textbunden {#in-line}

Alla PDF-sidor som återges i linje på en webbsida. Detta passar bäst för läsning av program.

![Anpassa behållaralternativet för flikstorlek i redigeringsdialogrutan för PDF-visningskomponenten](/help/assets/pdf-viewer-edit-customize-inline.png)

* **Hämta PDF** - När det här alternativet är aktiverat visas hämtningsknappen.
* **Skriv ut PDF** - När det här alternativet är aktiverat visas utskriftsknappen.

## Designdialogruta {#design-dialog}

Det finns ingen designdialogruta för PDF Viewer-komponenten.
