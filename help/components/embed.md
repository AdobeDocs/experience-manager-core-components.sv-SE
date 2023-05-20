---
title: Bädda in komponent
description: Med inbäddningskomponenten kan du bädda in externt innehåll på en AEM innehållssida.
role: Architect, Developer, Admin, User
exl-id: 985fa304-70a3-4329-957e-76d1832a06f1
source-git-commit: 327c239b02e0aecee878784c918bfa98d960530e
workflow-type: tm+mt
source-wordcount: '1395'
ht-degree: 0%

---

# Bädda in komponent {#embed-component}

Med Core Components Embed Component (Bädda in kärnkomponenter) kan du bädda in externt innehåll på en AEM.

## Användning {#usage}

Med Core Component Embed Component (Bädda in kärnkomponent) kan innehållsförfattaren definiera markerat externt innehåll som ska bäddas in på en AEM innehållssida. Dessutom finns det ett alternativ för att definiera frihandsritad HTML som även ska bäddas in.

* Komponentens egenskaper kan definieras i [konfigurera dialogruta](#configure-dialog).
* Standardvärden för komponenten när du lägger till den på en sida kan definieras i [designdialogruta](#design-dialog).

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Embed Component är v2, som introducerades i version 2.18.0 av Core Components i februari 2022, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v2 | - | Kompatibel | Kompatibel |
| [v1](v1/embed.md) | Kompatibel | Kompatibel | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Huvudkomponentversioner](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill se exempel på den inbäddade komponenten och dess konfigurationsalternativ samt HTML och JSON-utdata går du till [Komponentbibliotek](https://adobe.com/go/aem_cmp_library_embed).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om komponenten Embed [finns på GitHub](https://adobe.com/go/aem_cmp_tech_embed_v2).

Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera den externa resurs som ska bäddas in på sidan.

### Fliken Egenskaper {#properties-tab}

Välj först vilken typ av resurs som ska bäddas in:

* [URL](#url)
* [Inbäddad](#embeddable)
* [HTML](#html)

Du kan definiera en **ID**. Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [Datalager](/help/developing/data-layer/overview.md).

* Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
* Om ett ID anges är det författarens ansvar att se till att det är unikt.
* Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

#### URL {#url}

Den enklaste inbäddningen är URL-adressen. Klistra bara in URL:en för resursen som du vill bädda in i **URL** fält. Komponenten försöker komma åt resursen och om den kan återges av någon av processorerna visas ett bekräftelsemeddelande under **URL** fält. Annars markeras fältet med fel.

Den inbäddade komponenten levereras med processorer för följande typer av resurser:

* Resurser som uppfyller [Bädda in standard](https://oembed.com/) inklusive Facebook Post, Instagram, SoundCloud, Twitter och YouTube
* Pinterest

Utvecklare kan lägga till ytterligare URL-processorer av [följer utvecklardokumentationen för Embed Component.](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)

![Bädda in komponentens redigeringsdialogruta för URL](/help/assets/embed-url.png)

#### Inbäddad {#embeddable}

Inbäddade tabeller gör det möjligt att anpassa den inbäddade resursen mer, som kan parametriseras och innehålla ytterligare information. En författare kan välja bland förkonfigurerade tillförlitliga inbäddade filer och komponenten levereras med en YouTube-inbäddad som är färdig att användas.

The **Inbäddad** -fältet anger vilken typ av processor som du vill använda. När det gäller den inbäddade YouTube-funktionen kan du definiera:

* **Video-ID** - Det unika video-ID:t från YouTube för resursen som du vill bädda in
* **Bredd** - Bredden på den inbäddade videon
* **Höjd** - Höjden på den inbäddade videon
* **Aktivera ljud av** - Den här parametern anger om videon spelas upp som standard. Om du aktiverar det här alternativet ökar risken för att Autoplay fungerar i moderna webbläsare.
* **Aktivera automatisk uppspelning** - Den här parametern anger om den inledande videon automatiskt ska börja spelas upp när spelaren läses in. Detta gäller endast för publiceringsinstansen eller när du använder **Visa som publicerad** i utvecklingsinstansen.
* **Aktivera loop** - Om det gäller en enda video anger den här parametern om spelaren ska spela upp den inledande videon upprepade gånger. När det gäller en spellista spelar spelaren upp hela spellistan och startar sedan igen vid den första videon.
* **Aktivera direktuppspelning (iOS)** - Den här parametern styr om videoklipp spelas upp textbundet (på) eller i helskärmsläge (av) i en HTML5-spelare på iOS.
* **Obegränsade relaterade videoklipp** - Om det här alternativet är inaktiverat kommer relaterade videofilmer från samma kanal som den video som just spelades upp, annars kommer de från vilken kanal som helst.

Andra inbäddade tabeller kan erbjuda liknande fält och kan definieras av en utvecklare av [följer utvecklardokumentationen för Embed Component.](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)

![Bädda in komponentens redigeringsdialogruta för inbäddade tabeller](/help/assets/embed-embeddable.png)

>[!NOTE]
>
>Inbäddade tabeller måste aktiveras på mallnivå via [Designdialogruta](#design-dialog) som ska vara tillgänglig för sidans författare.

#### HTML {#html}

Du kan lägga till frihandskomponenten HTML på sidan med hjälp av komponenten Bädda in.

![Bädda in komponentens redigeringsdialogruta för HTML](/help/assets/embed-html.png)

>[!NOTE]
>Alla osäkra taggar, till exempel skript, filtreras från det angivna HTML och återges inte på den resulterande sidan.

##### Dokumentskydd {#security}

Den HTML-kod som författaren kan ange filtreras av säkerhetsskäl för att undvika serveröverskridande skriptattacker (cross-site scripting) som till exempel skulle kunna ge författare administratörsbehörighet.

I allmänhet gäller alla skript och `style` element och alla `on*` och `style` attribut tas bort från utdata.

Reglerna är dock mer komplicerade eftersom inbäddningskomponenten följer AEM globala filterregeluppsättningen för HTML AntiSamy-sanitets, som finns på `/libs/cq/xssprotection/config.xml`. Detta kan vid behov överlappas av en utvecklare för projektspecifik konfiguration.

Ytterligare säkerhetsinformation finns i [AEM för lokala installationer](https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/security.html) och [AEM as a Cloud Service installationer.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/security/home.html)

>[!NOTE]
>
>Trots att reglerna för antiSamys sanitets-ramverk kan konfigureras genom överlagring `/libs/cq/xssprotection/config.xml`påverkar dessa ändringar alla HTML- och JSP-beteenden och inte bara Bädda in kärnkomponent.

### Fliken Format {#styles-tab-edit}

![Fliken Stilar i redigeringsdialogrutan för Bädda in komponent](/help/assets/embed-styles.png)

Komponenten Embed stöder AEM [Formatsystem.](/help/get-started/authoring.md#component-styling).

Använd listrutan för att välja de format som du vill använda på komponenten. Markeringar som görs i redigeringsdialogrutan har samma effekt som de som väljs i komponentverktygsfältet.

Format måste konfigureras för den här komponenten i [designdialogruta](#design-dialog) för att den nedrullningsbara menyn ska vara tillgänglig.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera de alternativ som är tillgängliga för den som använder den inbäddade komponenten och de standardvärden som anges när den monterar den inbäddade komponenten.

### Fliken Inbäddade typer {#embeddable-types-tab}

![Bädda in komponentens designdialogruta](/help/assets/embed-design.png)

* **Inaktivera URL** - Inaktiverar **URL** alternativ för innehållsförfattaren när den är vald
* **Inaktivera inbäddade tabeller** - Inaktiverar **Inbäddad** när det här alternativet är markerat för innehållsförfattaren, oavsett vilka inbäddade processorer som är tillåtna.
* **Inaktivera HTML** - Inaktiverar **HTML** för innehållsförfattaren när detta är markerat.
* **Tillåtna inbäddade tabeller** - Multiselect som definierar vilka inbäddade processorer som är tillgängliga för innehållsförfattaren, förutsatt att **Inbäddad** alternativet är aktivt.

### YouTube Tab {#youtube-tab}

![YouTube-flik i dialogrutan Bädda in komponent](/help/assets/embed-design-youtube.png)

* **Tillåt konfiguration av ljudavstängningsbeteende** - Innehållsförfattaren kan konfigurera **Aktivera ljud av** i komponenten när YouTube-inbäddningstypen är markerad
   * **Standardvärde för ljud av** - Anger automatiskt **Aktivera ljud av** när YouTube-inbäddningstypen är markerad
* **Tillåt konfiguration av automatiskt uppspelningsbeteende** - Innehållsförfattaren kan konfigurera **Aktivera automatisk uppspelning** i komponenten när YouTube-inbäddningstypen är markerad
   * **Standardvärde för automatisk uppspelning** - Anger automatiskt **Aktivera automatisk uppspelning** när YouTube-inbäddningstypen är markerad
* **Tillåt konfiguration av loopbeteende** - Innehållsförfattaren kan konfigurera **Aktivera loop** i komponenten när YouTube-inbäddningstypen är markerad
   * **Standardvärde för slinga** - Anger automatiskt **Aktivera loop** när YouTube-inbäddningstypen är markerad
* **Tillåt konfiguration av intern uppspelning (iOS)** - Innehållsförfattaren kan konfigurera **Aktivera direktuppspelning (iOS)** i komponenten när YouTube-inbäddningstypen är markerad
   * **Standardvärde för direktuppspelning (iOS)** - Anger automatiskt **Aktivera direktuppspelning (iOS)** när YouTube-inbäddningstypen är markerad
* **Tillåt konfiguration av textbundna videoklipp** - Innehållsförfattaren kan konfigurera **Obegränsade relaterade videoklipp** i komponenten när YouTube-inbäddningstypen är markerad
   * **Standardvärde för obegränsade relaterade videoklipp** - Anger automatiskt **Obegränsade relaterade videoklipp** när YouTube-inbäddningstypen är markerad
