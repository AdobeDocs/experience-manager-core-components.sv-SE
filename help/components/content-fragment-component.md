---
title: Innehållsfragmentkomponent
description: Komponenten Core Component Content Fragment gör det möjligt att visa ett innehållsfragment.
role: Arkitekt, utvecklare, administratör, affärsansvarig
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 1%

---


# Innehållsfragmentkomponent{#content-fragment-component}

Med komponenten Core Component Content Fragment kan du visa ett [innehållsfragment](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/content-fragments/content-fragments.html).

>[!NOTE]
>
>Före version 2.4.0 av Core Components var Content Fragment-komponenten tillgänglig som ett tillägg till kärnkomponenterna och måste laddas ned separat och uttryckligen aktiveras.

## Användning {#usage}

Med komponenten Core Component Content Fragment Component kan du inkludera ett [innehållsfragment](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/content-fragments/content-fragments.html) på en sida.

* Fragmentet och dess egenskaper kan väljas i [konfigurationsdialogrutan](#configure-dialog).
* Resurstyper för att hantera vissa bilder och stödraster kan definieras i [designdialogrutan](#design-dialog).
* Redigeringsalternativet öppnar det markerade fragmentet i [redigeraren för innehållsfragment](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/content-fragments/content-fragments-variations.html).

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Content Fragment Component är v1, som introducerades i version 1.1.0 av Core Components i oktober 2017, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | Kompatibel | Kompatibel | Kompatibel |

>[!NOTE]
>
>Före version 2.4.0 fanns komponenten Content Fragment i mappen extensions.
>
> `apps/core/wcm/extension/components/contentfragment/v1/contentfragment`
> 
>Från 2.4.0 har den flyttats till följande plats.
>
>`apps/core/wcm/components/contentfragment/v1/contentfragment`
>
>Även om båda är v1 måste alla Content Fragment-komponenter som användes från mappen extensions migreras för att de relaterade proxykomponenterna ska kunna använda den nya resurstypen när de uppgraderas till version 2.4.0 eller senare av kärnkomponenterna.

Mer information om versioner och versioner av kärnkomponenter finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempelkomponentutdata {#sample-component-output}

Om du vill visa komponenterna för innehållsfragment samt se exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_cf).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Content Fragment Component [finns på GitHub](https://adobe.com/go/aem_cmp_tech_cf_v1).

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen till Core Components developer](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera vilket innehållsfragment och vilka element i fragmentet som ska inkluderas.

### Fliken Egenskaper {#properties-tab}

![Innehållsfragmentkomponent](/help/assets/content-fragment-edit-properties.png)

* **Innehållsfragment**

   * Sökväg till önskat innehållsfragment
   * Dialogrutan **Markering** kan användas för att hitta fragmentet

* **Visningsläge**
   * **Enkelt textelement**  - Aktiverar markering av ett flerradigt textelement och aktiverar alternativ för styckekontroll
   * **Flera element**  - Tillåter markering av ett eller flera element i det markerade innehållsfragmentet
* **Element**  - det eller de element i innehållsfragmentet som ska inkluderas
* **Variation**  - Vilken variant av innehållsfragmentet som ska användas (standardvärdet är  **Överordnad**)

* **Stycken**

   * **Alla**  - Visa alla stycken
   * **Intervall**

      * Ange styckeintervall som ska visas, avgränsade med semikolon
      * Till exempel `1;3-5;7;9-*` för att inkludera det första, det tredje till femte, det sjunde och det nionde till det sista stycket
* **ID**  - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i  [datalagret](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

### Styckekontrollflik {#paragraph-control-tab}

Den här fliken är inte tillgänglig när du har valt läget **Flera element**.

![Innehållsfragmentkomponent](/help/assets/content-fragment-edit-paragraph.png)

* **Stycken**  - Tillåt markering av alla stycken eller ett intervall
* **Hantera rubrik som egna stycken**

## Designdialog {#design-dialog}

I designdialogrutan kan mallskaparen definiera de resurstyper som används för att hantera bilder med olika medier och responsiva stödraster.

![Designdialogrutan för komponenten Innehållsfragment](/help/assets/content-fragment-design.png)

* **Intern responsiv stödraster**

   * Den Sling-resurstyp som används för det interna responsiva rutnätet

## Adobe-klientdatalagret {#data-layer}

Komponenten för innehållsfragment stöder [Adobe-klientdatalagret.](/help/developing/data-layer/overview.md)
