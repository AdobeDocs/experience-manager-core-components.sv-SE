---
title: Innehållsfragmentkomponent
description: Komponenten Core Component Content Fragment gör det möjligt att visa ett innehållsfragment.
role: Architect, Developer, Admin, User
exl-id: 551ff2a1-f8db-490c-84a3-4255b364fc83
source-git-commit: 6fbc781db555bc6abaed1d122a9a8756e3d53222
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 0%

---

# Innehållsfragmentkomponent{#content-fragment-component}

Komponenten Core Component Content Fragment gör det möjligt att visa ett [innehållsfragment](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html?lang=sv-SE).

>[!NOTE]
>
>Före version 2.4.0 av Core Components var Content Fragment-komponenten tillgänglig som ett tillägg till kärnkomponenterna och måste laddas ned separat och uttryckligen aktiveras.

## Användning {#usage}

Komponenten Core Component Content Fragment tillåter att ett [innehållsfragment](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html?lang=sv-SE) inkluderas på en sida.

* Fragmentet och dess egenskaper kan väljas i dialogrutan [Konfigurera](#configure-dialog).
* Resurstyper för att hantera vissa bilder och stödraster kan definieras i [designdialogrutan](#design-dialog).
* Redigeringsalternativet öppnar det markerade fragmentet i [redigeraren för innehållsfragment](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments-variations.html?lang=sv-SE).

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av Content Fragment Component är v1, som introducerades i version 1.1.0 av Core Components i oktober 2017, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM-versioner som komponenterna är kompatibla med samt länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|--- |--- |---|---|---|
| v1 | Kompatibel med <br>[version 2.17.4](/help/versions.md) och tidigare | Kompatibel | Kompatibel | Kompatibel |

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

## Exempel på komponentutdata {#sample-component-output}

Om du vill se både Content Fragment Component och exempel på dess konfigurationsalternativ samt HTML- och JSON-utdata går du till [komponentbiblioteket](https://adobe.com/go/aem_cmp_library_cf).

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Content Fragment-komponenten [ finns på GitHub](https://adobe.com/go/aem_cmp_tech_cf_v1).

Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren definiera vilket innehållsfragment och vilka element i fragmentet som ska inkluderas.

### Fliken Egenskaper {#properties-tab}

![Innehållsfragmentkomponent](/help/assets/content-fragment-edit-properties.png)

* **Innehållsfragment**

   * Sökväg till önskat innehållsfragment
   * Du kan använda dialogrutan **Markering** för att hitta fragmentet

* **Visningsläge**
   * **Enkelt textelement** - Aktiverar markering av ett flerradigt textelement och aktiverar styckekontrollalternativ
   * **Flera element** - Tillåter markering av ett eller flera element i det valda innehållsfragmentet
* **Element** - Elementet eller elementen i innehållsfragmentet som ska inkluderas
* **Variation** - Vilken variant av innehållsfragmentet som ska användas (standard är **Master**)

* **Stycken**

   * **Alla** - Visa alla stycken
   * **Intervall**

      * Ange styckeintervall som ska visas, avgränsade med semikolon
      * Till exempel `1;3-5;7;9-*` för att inkludera det första, det tredje till femte, det sjunde och det nionde till det sista stycket
* **ID** - Med det här alternativet kan du styra den unika identifieraren för komponenten i HTML och i [datalagret](/help/developing/data-layer/overview.md).
   * Om inget anges genereras ett unikt ID automatiskt åt dig och du hittar det genom att granska den resulterande sidan.
   * Om ett ID anges är det författarens ansvar att se till att det är unikt.
   * Om du ändrar ID:t kan det påverka spårningen av CSS, JS och datalager.

### Styckekontrollflik {#paragraph-control-tab}

Den här fliken är inte tillgänglig när läget **Flera element** har valts.

![Innehållsfragmentkomponent](/help/assets/content-fragment-edit-paragraph.png)

* **Stycken** - Tillåt markering av alla stycken eller ett intervall
* **Hantera rubrik som egna stycken**

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera de resurstyper som används för att hantera bilder med olika medier och responsiva stödraster.

![Dialogrutan Design för komponenten Content Fragment](/help/assets/content-fragment-design.png)

* **Intern responsiv stödraster**

   * Den Sling-resurstyp som används för det interna responsiva rutnätet

## Adobe Client Data Layer {#data-layer}

Komponenten för innehållsfragment har stöd för [Adobe-klientdatalagret.](/help/developing/data-layer/overview.md)
