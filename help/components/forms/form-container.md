---
title: Formulärbehållarkomponent
description: Med komponenten Core Component Form Container Component kan man skapa enkla inskickningsformulär.
role: Architect, Developer, Admin, User
exl-id: 552f9dd5-6a3a-42d9-9969-e62a1f36e811
source-git-commit: 16930ccaa281f9d9c4ddbb890d4222e128557580
workflow-type: tm+mt
source-wordcount: '955'
ht-degree: 0%

---

# Formulärbehållarkomponent {#form-container-component}

Med komponenten Core Component Form Container Component kan man skapa enkla inskickningsformulär.

## Användning {#usage}

Med formulärbehållarkomponenten kan du skapa enkla formulär och funktioner för inlämning av information genom att stödja enkla WCM-formulär och använda en kapslad struktur för att tillåta ytterligare formulärkomponenter.

Genom att använda [konfigurera dialogruta](#configure-dialog) innehållsredigeraren kan definiera den åtgärd som ska utföras när formulär skickas, vilken URl som ska hantera överföringen och om ett arbetsflöde ska aktiveras. Mallförfattaren kan använda [designdialogruta](#design-dialog) för att definiera de tillåtna komponenterna och deras mappningar som liknar designdialogrutan för [standardlayoutbehållare i mallredigeraren](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html).

>[!NOTE]
>
>Huvudkomponenterna Form Container Component har endast stöd för användning av kärnkomponenter i form av komponenter (knapp, text, dold etc.). Använda [grundkomponenter](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/siteandpage/default-components-foundation.html) formulärkomponenter i kärnkomponentens formulärbehållare (och vice versa) stöds inte.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Form Container Component är v2, som introducerades i version 2.0.0 av Core Components i januari 2018, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | Kompatibel med<br>[version 2.17.4](/help/versions.md) och tidigare | Kompatibel | Kompatibel |
| [v1](/help/components/v1/form-container-v1.md) | Kompatibel | Kompatibel | Kompatibel |

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Huvudkomponentversioner](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill visa Form Container-komponenten samt se exempel på dess konfigurationsalternativ samt HTML och JSON-utdata går du till [Komponentbibliotek](https://adobe.com/go/aem_cmp_library_form_container).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om komponenten Formulärbehållare [finns på GitHub](https://adobe.com/go/aem_cmp_tech_form_container_v2).

Mer information om hur du utvecklar kärnkomponenter finns i [Dokumentation för grundkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera vilka åtgärder som ska vidtas när komponenten skickas.

Beroende på det markerade **Åtgärdstyp**&#x200B;ändras de tillgängliga alternativen i behållaren. De tillgängliga åtgärdstyperna är:

* [Bokför formulärdata](#post-data)
* [E-post](#mail)
* [Lagra innehåll](#store-content)

Oavsett typ finns det [allmänna inställningar](#general-settings) som gäller för varje åtgärd.

### Bokför formulärdata {#post-data}

När formuläret skickas skickar dataåtgärden post form till en tredje part som JSON för bearbetning.

![Alternativ för att skicka formulärdata i formulärbehållarkomponentens redigeringsdialogruta](/help/assets/form-container-edit-post.png)

* **Slutpunkt** - Den fullständiga HTTPS-tjänsten som kommer att bearbeta data
* **Felmeddelande** - Meddelande som visas om överföringen inte lyckas

>[!TIP]
>Det finns ytterligare timeout-alternativ som en systemadministratör kan justera för att hantera bearbetningen av vidarebefordrade formulärdata. [Mer information finns i den tekniska dokumentationen om GitHub.](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/actions/rpc)

### E-post {#mail}

När formuläret skickas skickar poståtgärdstypen ett e-postmeddelande till angivna mottagare.

![E-postalternativ i dialogrutan Redigera i komponenten Formulärbehållare](/help/assets/form-container-edit-mail.png)

* **Ämne** - Ämnet i det e-postmeddelande som skickas när formulär skickas
* **Från** - Från-e-postadressen till det e-postmeddelande som ska skickas när formulär skickas
* **Till** - Adresserna till mottagarna som får ett e-postmeddelande när formuläret skickas in
   * Tryck eller klicka på **Lägg till** knapp för att lägga till ytterligare adresser
   * Tryck eller klicka på **Ta bort** knapp för att ta bort en e-postadress
* **CC** - Adresserna till mottagare som ska få en kopia av e-postmeddelandet som skickas när formuläret skickas in
   * Tryck eller klicka på **Lägg till** knapp för att lägga till ytterligare adresser
   * Tryck eller klicka på **Ta bort** knapp för att ta bort en e-postadress

### Lagra innehåll {#store-content}

När formuläret skickas kommer innehållet i formuläret att lagras på en angiven plats i databasen.

![Alternativ för att lagra innehåll i redigeringsdialogrutan för formulärbehållaren](/help/assets/form-container-edit-store.png)

* **Innehållsbana** - Sökväg till innehållsdatabas där skickat innehåll lagras
* **Visa data** - Tryck eller klicka för att visa lagrade skickade data som JSON
* **Starta arbetsflöde** - Konfigurera för att starta ett arbetsflöde med lagrat innehåll som nyttolast när formuläret skickas

>[!NOTE]
>
>För att förenkla hanteringen av användardata och för att framtvinga olika problemområden rekommenderar vi i allmänhet inte att användargenererat innehåll lagras i databasen.
>
>Använd i stället [Bokför formulärdata](#post-data) åtgärdstyp för att skicka användarinnehåll vidare till en dedikerad tjänsteleverantör.

### Allmänna inställningar {#general-settings}

Oavsett vilken åtgärdstyp du väljer kan du alltid definiera en tacksida.

![Allmänna alternativ i redigeringsdialogrutan för komponenten Formulärbehållare](/help/assets/form-container-edit-general.png)

* **Tack** - Användaren omdirigeras till den angivna sidan när formuläret har skickats.
   * Använd dialogrutan Markering för att välja en resurs i AEM.
   * Om tacksidan inte finns i AEM anger du den absoluta URL:en. Icke-absoluta URL:er tolkas i förhållande till AEM.
   * Lämna tomt om du vill visa formuläret igen när det har skickats.
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [Datalager](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera de tillåtna komponenterna och deras mappningar för behållaren som liknar designdialogrutan för [standardlayoutbehållare i mallredigeraren](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html).

### Fliken Format {#styles-tab}

Komponenten Form Container stöder AEM [Formatsystem](/help/get-started/authoring.md#component-styling).
