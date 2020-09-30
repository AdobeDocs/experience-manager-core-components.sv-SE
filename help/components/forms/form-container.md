---
title: Formulärbehållarkomponent
description: Med komponenten Core Component Form Container Component kan man skapa enkla inskickningsformulär.
translation-type: tm+mt
source-git-commit: 4813748bcfa83ce7c73e81d4e4d445ecc8215d26
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Formulärbehållarkomponent {#form-container-component}

Med komponenten Core Component Form Container Component kan man skapa enkla inskickningsformulär.

## Användning {#usage}

Med formulärbehållarkomponenten kan du skapa enkla formulär och funktioner för inlämning av information genom att stödja enkla WCM-formulär och använda en kapslad struktur för att tillåta ytterligare formulärkomponenter.

Genom att använda dialogrutan [](#configure-dialog) Konfigurera kan innehållsredigeraren definiera åtgärden som ska aktiveras när formulär skickas, var det skickade innehållet ska lagras och om ett arbetsflöde ska aktiveras. Mallförfattaren kan använda [designdialogrutan](#design-dialog) för att definiera de tillåtna komponenterna och deras mappningar som liknar designdialogrutan för [standardlayoutbehållaren i mallredigeraren](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html).

>[!NOTE]
>
>Huvudkomponenterna Form Container Component har endast stöd för användning av kärnkomponenter i form av komponenter (knapp, text, dold etc.). Det går inte att använda [baskomponenter](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/siteandpage/default-components-foundation.html) i kärnkomponentens formulärbehållare (och vice versa).

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Form Container Component är v2, som introducerades i version 2.0.0 av Core Components i januari 2018, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | Kompatibel | Kompatibel | Kompatibel |
| [v1](/help/components/v1/form-container-v1.md) | Kompatibel | Kompatibel | - |

Mer information om Core Component-versioner och -versioner finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill visa komponenterna i Form Container samt se exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_form_container).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Form Container Component [finns på GitHub](https://adobe.com/go/aem_cmp_tech_form_container_v2).

Mer information om hur du utvecklar kärnkomponenter finns i dokumentationen till [Core Components Developer](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera vilka åtgärder som ska vidtas när komponenten skickas.

Beroende på den valda **åtgärdstypen**&#x200B;ändras de tillgängliga alternativen i behållaren. De tillgängliga åtgärdstyperna är:

* [E-post](#mail)
* [Lagra innehåll](#store-content)

Oavsett typ finns det [allmänna inställningar](#general-settings) för varje åtgärd.

### E-post {#mail}

När formuläret skickas skickar poståtgärdstypen ett e-postmeddelande till angivna mottagare.

![E-postalternativ i dialogrutan Redigera i komponenten Formulärbehållare](/help/assets/form-container-edit-mail.png)

* **Ämne** - Ämnet för det e-postmeddelande som ska skickas när formulär skickas
* **Från** - Från-e-postadressen till e-postmeddelandet som ska skickas när formulär skickas
* **Till** - Adresserna till mottagarna som ska få ett e-postmeddelande när formuläret skickas in
   * Tryck eller klicka på knappen **Lägg till** för att lägga till ytterligare adresser
   * Tryck eller klicka på knappen **Ta bort** för att ta bort en e-postadress
* **CC** - Adresserna till mottagarna som ska få en kopia av e-postmeddelandet som skickas när formuläret skickas in
   * Tryck eller klicka på knappen **Lägg till** för att lägga till ytterligare adresser
   * Tryck eller klicka på knappen **Ta bort** för att ta bort en e-postadress

### Lagra innehåll {#store-content}

När formuläret skickas kommer innehållet i formuläret att lagras på en angiven plats i databasen.

![Alternativ för att lagra innehåll i redigeringsdialogrutan för formulärbehållaren](/help/assets/form-container-edit-store.png)

* **Innehållssökväg** - Sökväg till innehållsdatabas där skickat innehåll lagras
* **Visa data** - tryck eller klicka för att visa lagrade skickade data som JSON
* **Starta arbetsflöde** - Konfigurera för att starta ett arbetsflöde med det lagrade innehållet som nyttolast när formuläret skickas

### Allmänna inställningar {#general-settings}

Oavsett vilken åtgärdstyp du väljer kan du alltid definiera en tacksida.

![Allmänna alternativ i redigeringsdialogrutan för komponenten Formulärbehållare](/help/assets/form-container-edit-general.png)

* **Tack** ! Användaren omdirigeras till den angivna sidan när formuläret har skickats.
   * Använd dialogrutan Markering för att välja en resurs i AEM.
   * Om tacksidan inte finns i AEM anger du den absoluta URL:en. Icke-absoluta URL:er tolkas i förhållande till AEM.
   * Lämna tomt om du vill visa formuläret igen när det har skickats.
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [datalagret](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera de tillåtna komponenterna och deras mappningar för behållaren som liknar designdialogrutan för [standardlayoutbehållaren i mallredigeraren](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html).

### Fliken Format {#styles-tab}

Komponenten Form Container stöder AEM [Style System](/help/get-started/authoring.md#component-styling).
