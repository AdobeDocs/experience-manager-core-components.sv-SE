---
title: Bädda in komponent
description: Med inbäddningskomponenten kan du bädda in externt innehåll på en AEM innehållssida.
role: Architect, Developer, Admin, User
exl-id: 985fa304-70a3-4329-957e-76d1832a06f1
source-git-commit: d435e82d5950336c66997399829e3baf23f170c0
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

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

## Exempel på komponentutdata {#sample-component-output}

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

* Resurser som följer [Embed-standarden](https://oembed.com/) inklusive Facebook Post, Instagram, SoundCloud, Twitter och YouTube
* Pinterest

Utvecklare kan lägga till ytterligare URL-processorer av [efter utvecklardokumentationen för den inbäddade komponenten.](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)

![Bädda in komponentens redigeringsdialogruta för URL](/help/assets/embed-url.png)

### Inbäddad {#embeddable}

Inbäddade tabeller gör det möjligt att anpassa den inbäddade resursen mer, som kan parametriseras och innehålla ytterligare information. En författare kan välja bland förkonfigurerade tillförlitliga inbäddade filer och komponenten levereras med en YouTube-inbäddad som är färdig att användas.

Fältet **Embed** anger vilken typ av processor du vill använda. När det gäller den inbäddade YouTube-funktionen kan du definiera:

* **Video-ID**  - Det unika video-ID:t från YouTube för resursen som du vill bädda in
* **Bredd**  - Bredden på den inbäddade videon
* **Höjd**  - Höjden på den inbäddade videon
* **Aktivera ljud**  av - Den här parametern anger om videon spelas upp som standard. Om du aktiverar det här alternativet ökar risken för att Autoplay fungerar i moderna webbläsare.
* **Aktivera automatisk uppspelning**  - Den här parametern anger om den inledande videon automatiskt ska börja spelas upp när spelaren läses in. Detta gäller endast för publiceringsinstansen eller när du använder alternativet **Visa som publicerad** i redigeringsinstansen.
* **Aktivera slinga**  - I en enda video anger den här parametern om spelaren ska spela upp den inledande videon upprepade gånger. När det gäller en spellista spelar spelaren upp hela spellistan och startar sedan igen vid den första videon.
* **Aktivera textbunden uppspelning (iOS)**  - Den här parametern kontrollerar om videoklipp spelas upp textbundet (på) eller helskärm (av) i en HTML5-spelare på iOS.
* **Obegränsade relaterade videoklipp**  - Om det här alternativet är inaktiverat kommer relaterade videoklipp från samma kanal som videon som just spelades upp, annars kommer de från vilken kanal som helst.

Observera att&quot;aktivera&quot;-alternativen måste aktiveras via [designdialogrutan](#design-dialog) och kan anges som standardvärden.

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

Reglerna är dock mer komplicerade eftersom inbäddningskomponenten följer AEM globala filterregeluppsättningen för HTML AntiSamy-sanitets, som finns på `/libs/cq/xssprotection/config.xml`. Detta kan vid behov överlappas av en utvecklare för projektspecifik konfiguration.

Ytterligare säkerhetsinformation finns i [AEM för lokala installationer](https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/security.html) och [AEM som en Cloud Service installationer.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/security/home.html)

>[!NOTE]
>Trots att reglerna för antiSamys sanitets ramverk kan konfigureras genom att åsidosätta `/libs/cq/xssprotection/config.xml`, påverkar dessa ändringar alla HTML- och JSP-beteenden och inte bara Bädda in kärnkomponent.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera de alternativ som är tillgängliga för den som använder den inbäddade komponenten och de standardvärden som anges när den monterar den inbäddade komponenten.

### Fliken Inbäddade typer {#embeddable-types-tab}

![Bädda in komponentens designdialogruta](/help/assets/embed-design.png)

* **Inaktivera URL** - Inaktiverar  **** alternativet URLoption för innehållsförfattaren när det är markerat
* **Inaktivera inbäddade**  filer - Inaktiverar alternativet  **** Inbäddning för innehållsförfattaren när det är markerat, oavsett vilka inbäddade processorer som är tillåtna.
* **Inaktivera HTML** - Inaktiverar  **** HTML-alternativet för innehållsförfattaren när det är markerat.
* **Tillåtna inbäddade**  tabeller - Multimarkering som definierar vilka inbäddade processorer som är tillgängliga för innehållsförfattaren, förutsatt att alternativet  **** EmbedTable är aktivt.

### YouTube Tab {#youtube-tab}

![YouTube-flik i dialogrutan Bädda in komponent](/help/assets/embed-design-youtube.png)

* **Tillåt konfiguration av avstängningsbeteende**  - Innehållsförfattaren kan konfigurera alternativet  **Aktivera** aktivering i komponenten när YouTube-inbäddningstypen är vald
   * **Standardvärde för ljud**  av/på - Anger automatiskt  **Aktivera** alternativ när YouTube inbäddningstyp är markerad
* **Tillåt konfiguration av automatiskt uppspelningsbeteende**  - Innehållsförfattaren kan konfigurera alternativet  **Aktivera** automatisk uppspelning i komponenten när YouTube-inbäddningstypen har valts
   * **Standardvärde för automatisk uppspelning**  - Anger automatiskt  **Aktivera** automatisk uppspelning när YouTube inbäddningstyp är markerad
* **Tillåt konfiguration av loopbeteende**  - Innehållsförfattaren kan konfigurera  **Aktivera** loop i komponenten när YouTube-inbäddningstypen har valts
   * **Standardvärde för slinga**  - Anger automatiskt  **Aktivera** loop när inbäddningstypen för YouTube är markerad
* **Tillåt konfiguration av intern uppspelning (iOS)**  - Innehållsförfattaren kan konfigurera  **alternativet** Aktivera intern uppspelning (iOS) i komponenten när YouTube-inbäddningstypen är vald
   * **Standardvärde för direktuppspelning (iOS)**  - Anger automatiskt  **alternativet** Aktivera textbunden uppspelning (iOS) när inbäddningstypen för YouTube är vald
* **Tillåt konfiguration av textbundna videoklipp**  - Innehållsförfattaren kan konfigurera alternativet  **Obegränsade relaterade** videoklipp i komponenten när YouTube-inbäddningstypen är vald
   * **Standardvärde för obegränsade relaterade videoklipp**  - Anger automatiskt alternativet  **Obegränsade relaterade** videoklipp när YouTube-inbäddningstypen har valts
