---
title: Innehållsfragmentkomponent
description: Komponenten Core Component Content Fragment gör det möjligt att visa ett innehållsfragment.
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# Innehållsfragmentkomponent{#content-fragment-component}

Komponenten Core Component Content Fragment gör det möjligt att visa ett [innehållsfragment](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/content-fragments/content-fragments.html).

>[!NOTE]
>
>Före version 2.4.0 av Core Components var Content Fragment-komponenten tillgänglig som ett tillägg till kärnkomponenterna och måste laddas ned separat och uttryckligen aktiveras.

## Användning {#usage}

Med komponenten Core Component Content Fragment Component kan du inkludera ett [innehållsfragment](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/content-fragments/content-fragments.html) på en sida.

* Fragmentet och dess egenskaper kan väljas i [konfigurationsdialogrutan](#configure-dialog).
* Resurstyper för att hantera vissa bilder och stödraster kan definieras i [designdialogrutan](#design-dialog).
* Redigeringsalternativet öppnar det markerade fragmentet i [innehållsfragmentredigeraren](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/content-fragments/content-fragments-variations.html).

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Content Fragment Component är v1, som introducerades i version 1.1.0 av Core Components i oktober 2017, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponentversionerna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|---|
| v1 | Kompatibel | Kompatibel | Kompatibel | Kompatibel |

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

Mer information om Core Component-versioner och -versioner finns i dokumentet [Core Components Versions](/help/versions.md).

## Exempel på komponentutdata {#sample-component-output}

Om du vill visa komponenterna för innehållsfragment samt se exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_cf).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Content Fragment Component [finns på GitHub](https://adobe.com/go/aem_cmp_tech_cf_v1).

Mer information om hur du utvecklar kärnkomponenter finns i dokumentationen till [Core Components Developer](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera vilket innehållsfragment och vilka element i fragmentet som ska inkluderas.

![](/help/assets/chlimage_1-87.png)

* **Innehållsfragment**

   * Sökväg till önskat innehållsfragment
   * Du kan använda dialogrutan **** Markering för att hitta fragmentet

* **Element** - det element i innehållsfragmentet som ska inkluderas
* **Variation** - Vilken variant av innehållsfragmentet som ska användas (standard är **mallsida**)

* **Stycken**

   * **Alla** - Visa alla stycken
   * **Intervall**

      * Ange styckeintervall som ska visas, avgränsade med semikolon
      * Om du `1;3-5;7;9-*` till exempel vill ta med det första, det tredje till femte, det sjunde och det nionde till det sista stycket

* **Hantera rubrik som egna stycken**

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera de resurstyper som används för att hantera bilder med olika medier och responsiva stödraster.

![](/help/assets/chlimage_1-88.png)

* **Bildtyp med blandade media**

   * En Sling-resurstyp som används för återgivning av blandade mediabilder

* **Intern responsiv stödraster**

   * Den Sling-resurstyp som används för det interna responsiva rutnätet
