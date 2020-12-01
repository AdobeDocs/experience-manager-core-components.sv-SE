---
title: Bädda in komponent
description: Med inbäddningskomponenten kan du bädda in externt innehåll på en AEM innehållssida.
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '944'
ht-degree: 2%

---


# Bädda in komponent{#embed-component}

Med Core Components Embed Component (Bädda in kärnkomponenter) kan du bädda in externt innehåll på en AEM.

## Användning {#usage}

Med Core Component Embed Component (Bädda in kärnkomponent) kan innehållsförfattaren definiera markerat externt innehåll som ska bäddas in på en AEM innehållssida. Dessutom finns det ett alternativ för att definiera frihandsbaserad HTML som också ska bäddas in.

* Komponentens egenskaper kan definieras i [konfigurationsdialogrutan](#configure-dialog).
* Standardvärden för komponenten när du lägger till den på en sida kan definieras i [designdialogrutan](#design-dialog).

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Embed Component är v1, som introducerades i version 2.7.0 av Core Components i september 2019, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Kompatibel | Kompatibel | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempelkomponentutdata {#sample-component-output}

Om du vill visa den inbäddade komponenten och se exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_embed).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om den inbäddade komponenten [finns på GitHub](https://adobe.com/go/aem_cmp_tech_embed_v1).

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen till Core Components developer](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera den externa resurs som ska bäddas in på sidan. Välj först vilken typ av resurs som ska bäddas in:

* [Webbadress](#url)
* [Inbäddad](#embeddable)
* [HTML](#html)

För varje typ av inbäddad kan du definiera och **ID**. Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [datalagret](/help/developing/data-layer/overview.md).

* Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
* Om ett ID anges är det författarens ansvar att se till att det är unikt.
* Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

### Webbadress {#url}

Den enklaste inbäddningen är URL-adressen. Klistra bara in URL:en för resursen som du vill bädda in i fältet **URL**. Komponenten försöker komma åt resursen och om den kan återges av någon av processorerna visas ett bekräftelsemeddelande under fältet **URL**. Annars markeras fältet med fel.

Den inbäddade komponenten levereras med processorer för följande typer av resurser:

* Resurser som följer [inbäddningsstandarden](https://oembed.com/) inklusive Facebook Post, Instagram, SoundCloud, Twitter och YouTube
* Pinterest

Utvecklare kan lägga till ytterligare URL-processorer av [efter utvecklardokumentationen för den inbäddade komponenten.](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)

![Bädda in komponentens redigeringsdialogruta för URL](/help/assets/embed-url.png)

### Inbäddad {#embeddable}

Inbäddade tabeller gör det möjligt att anpassa den inbäddade resursen mer, som kan parametriseras och innehålla ytterligare information. En författare kan välja bland förkonfigurerade tillförlitliga inbäddade tabeller och komponenten levereras med ett inbäddat YouTube-program.

Fältet **Embed** anger vilken typ av processor du vill använda. När det gäller den inbäddade YouTube-funktionen kan du definiera:

* **Video-ID**  - Det unika video-ID:t från YouTube för resursen som du vill bädda in
* **Bredd**  - Bredden på den inbäddade videon
* **Höjd**  - Höjden på den inbäddade videon

Andra inbäddade tabeller kan innehålla liknande fält och kan definieras av en utvecklare av [efter utvecklardokumentationen för den inbäddade komponenten.](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)

![Bädda in komponentens redigeringsdialogruta för inbäddade tabeller](/help/assets/embed-embeddable.png)

>[!NOTE]
>Inbäddade tabeller måste aktiveras på mallnivå via [designdialogrutan](#design-dialog) för att vara tillgängliga för sidans författare.

### HTML {#html}

Du kan lägga till HTML med valfri form på sidan med hjälp av komponenten Embed.

![Bädda in komponentens redigeringsdialogruta för HTML](/help/assets/embed-html.png)

>[!NOTE]
>Alla osäkra taggar, till exempel skript, filtreras från den angivna HTML-koden och återges inte på den resulterande sidan.

#### Dokumentskydd {#security}

Den HTML-kod som författaren kan ange filtreras av säkerhetsskäl för att undvika serveröverskridande skriptattacker (cross-site scripting) som till exempel skulle kunna ge författare administratörsbehörighet.

*I allmänhet tas* alla skript och  `style` element samt alla  `on*` och  `style` attribut bort från utdata.

Reglerna är dock mer komplicerade eftersom inbäddningskomponenten följer AEM globala filterregeluppsättning för HTML AntiSamy-rendering, som finns på `/libs/cq/xssprotection/config.xml`. Detta kan vid behov överlappas av en utvecklare för projektspecifik konfiguration.

Ytterligare säkerhetsinformation finns i [AEM för lokala installationer](https://docs.adobe.com/content/help/en/experience-manager-65/developing/introduction/security.html) och [AEM som en Cloud Service installationer.](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/security/home.html)

>[!NOTE]
>Trots att reglerna för antiSamys sanitets ramverk kan konfigureras genom att åsidosätta `/libs/cq/xssprotection/config.xml`, påverkar dessa ändringar alla HTML- och JSP-beteenden och inte bara Bädda in kärnkomponent.

## Designdialog {#design-dialog}

I designdialogrutan kan mallskaparen definiera de alternativ som är tillgängliga för den som använder den inbäddade komponenten och de standardvärden som anges när den monterar den inbäddade komponenten.

![Bädda in komponentens designdialogruta](/help/assets/embed-design.png)

* **Inaktivera URL** - Inaktiverar  **** alternativet URLoption för innehållsförfattaren när det är markerat
* **Inaktivera inbäddade**  filer - Inaktiverar alternativet  **** Inbäddning för innehållsförfattaren när det är markerat, oavsett vilka inbäddade processorer som är tillåtna.
* **Inaktivera HTML** - Inaktiverar  **** HTML-alternativet för innehållsförfattaren när det är markerat.
* **Tillåtna inbäddade**  tabeller - Multimarkering som definierar vilka inbäddade processorer som är tillgängliga för innehållsförfattaren, förutsatt att alternativet  **** Inbäddad kan användas.
