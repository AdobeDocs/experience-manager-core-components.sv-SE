---
title: Anpassa kärnkomponenter
description: Core Components implementerar flera mönster som gör det enkelt att anpassa, från enkel formatering till avancerad återanvändning av funktioner.
role: Architect, Developer, Admin
exl-id: ec4b918b-bc70-4d72-ba84-a24556aedb41
source-git-commit: 2ac16b15718128feefbe903e92f276b16fe96f69
workflow-type: tm+mt
source-wordcount: '1100'
ht-degree: 0%

---

# Anpassa kärnkomponenter{#customizing-core-components}

The [Kärnkomponenter](overview.md) implementera flera mönster som gör det enkelt att anpassa, från enkel formatering till avancerad återanvändning av funktioner.

## Flexibel arkitektur {#flexible-architecture}

Kärnkomponenterna var från början utformade för att vara flexibla och utökningsbara. En översikt över deras arkitektur visar var anpassningar kan göras.

![Kärnkomponentarkitektur](/help/assets/screen_shot_2018-12-07at093742.png)

* [Designdialogrutan](/help/get-started/authoring.md#edit-and-design-dialogs) definierar vad författare kan eller inte kan göra i redigeringsdialogrutan.
* [Redigeringsdialogrutan](/help/get-started/authoring.md#edit-and-design-dialogs) visar bara de alternativ som författare kan använda.
* [Sling-modellen](#customizing-the-logic-of-a-core-component) verifierar och förbereder innehållet för vyn (mallen).
* [Resultatet av Sling-modellen](#customizing-the-logic-of-a-core-component) kan serialiseras till JSON för SPA fall.
* [HTML återger HTML](#customizing-the-markup) serversidan för traditionell återgivning på serversidan.
* [Utdata från HTML](#customizing-the-markup) är semantiskt, tillgängligt, sökmotoroptimerat och enkelt att formatera.

Och alla kärnkomponenter implementerar [Formatsystem](#styling-the-components).

## AEM Project Archetype {#aem-project-archetype}

[AEM Project Archetype](/help/developing/archetype/overview.md) skapar ett minimalt Adobe Experience Manager-projekt som startpunkt för dina egna projekt, inklusive ett exempel på en anpassad HTML-komponent med SlingModels för att logika och implementera Core Components korrekt med det rekommenderade proxymönstret.

## Anpassningsmönster {#customization-patterns}

### Anpassa dialogrutor {#customizing-dialogs}

Du kan behöva anpassa de konfigurationsalternativ som finns i en kärnkomponentdialogruta, oavsett om det är [Designdialogrutan eller dialogrutan Redigera](/help/get-started/authoring.md).

Varje dialogruta har en konsekvent nodstruktur. Vi rekommenderar att den här strukturen replikeras i en ärvande komponent så att [Samla resurser](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/sling-resource-merger.html) och [Dölj villkor](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/hide-conditions.html) kan användas för att dölja, ersätta och ändra ordning på avsnitt i den ursprungliga dialogrutan. Strukturen som ska replikeras definieras som allt upp till tabbobjektets nodnivå.

För att vara helt kompatibelt med ändringar som gjorts i en dialogruta i den aktuella versionen är det mycket viktigt att strukturer under flikobjektsnivån inte rörs (dold, läggs till, ersätts, sorteras om osv.). I stället ska ett flikobjekt från det överordnade objektet döljas via `sling:hideResource` egenskap (se [Sammanfogningsegenskaper för segmenteringsresurs](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/sling-resource-merger.html)) och nya flikar som innehåller skräddarsydda konfigurationsfält läggs till. `sling:orderBefore` kan vid behov användas för att ändra ordningen på flikobjekt.

I dialogrutan nedan visas den rekommenderade dialogstrukturen samt hur du döljer och ersätter en ärvd flik enligt beskrivningen ovan:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<jcr:root xmlns:sling="https://sling.apache.org/jcr/sling/1.0"
          xmlns:jcr="https://www.jcp.org/jcr/1.0"
          xmlns:nt="https://www.jcp.org/jcr/nt/1.0"
          xmlns:granite="https://www.adobe.com/jcr/granite/1.0"
          jcr:primaryType="nt:unstructured">
    <content jcr:primaryType="nt:unstructured">
        <items jcr:primaryType="nt:unstructured">
            <tabs jcr:primaryType="nt:unstructured">
                <items jcr:primaryType="nt:unstructured">
                        <originalTab
                                jcr:primaryType="nt:unstructured"
                                sling:hideResource="true"/>
                        </originalTab>
                        <myTab
                               jcr:primaryType="nt:unstructured"
                               jcr:title="My Tab"
                               sling:resourceType="granite/ui/components/coral/foundation/container"/>
                               <!-- myTab content -->
                        </myTab>
                </items>
            </basic>
        </items>
    </content>
</jcr:root>
```

### Anpassa logiken i en kärnkomponent {#customizing-the-logic-of-a-core-component}

Affärslogiken för kärnkomponenterna implementeras i Sling Models. Den här logiken kan utökas med hjälp av ett delegeringsmönster för Sling.

I huvudkomponenten för title används till exempel `jcr:title` egenskapen för den begärda resursen som tillhandahåller titeltexten. Om nej `jcr:title` -egenskapen är definierad, en återgång till den aktuella sidrubriken implementeras. Vi vill ändra beteendet så att den aktuella sidans rubrik alltid visas.

Eftersom implementeringen av Core Components modeller är privata måste de utökas med ett delegeringsmönster.

```java
@Model(adaptables = SlingHttpServletRequest.class,
       adapters = Title.class,
       resourceType = "myproject/components/pageHeadline")
public class PageHeadline implements Title {
    @ScriptVariable private Page currentPage;
    @Self @Via(type = ResourceSuperType.class)
    private Title title;
    @Override public String getText() {
        return currentPage.getTitle();
    }
    @Override public String getType() {
        return title.getType();
    }
}
```

Mer information om delegeringsmönstret finns i Wiki-artikeln Core Components GitHub [Delegeringsmönster för segmenteringsmodeller](https://github.com/adobe/aem-core-wcm-components/wiki/Delegation-Pattern-for-Sling-Models).

### Anpassa markeringen {#customizing-the-markup}

Ibland kräver avancerad formatering en annan kodstruktur för komponenten.

Detta kan du enkelt göra genom att kopiera HTML-filerna som behöver ändras från Core Component (kärnkomponenten) till [proxykomponent.](guidelines.md#proxy-component-pattern)

Med hjälp av Core Breadcrumb Component kan du nu anpassa kodresultatet i `breadcrumb.html` filen måste kopieras till den platsspecifika komponent som har en `sling:resourceSuperTypes` som pekar på kärnkomponenten Breadcrumb.

### Formatera komponenterna {#styling-the-components}

Den första formen av anpassning är att tillämpa CSS-format.

För att förenkla detta återges semantiska markeringar med Core Components och en standardiserad namnkonvention som inspireras av [Bootstrap](https://getbootstrap.com/). För att enkelt ange format för de enskilda komponenterna som mål och namnrymd, kapslas varje Core Component in i ett DIV-element med &quot; `cmp`&quot; och &quot; `cmp-<name>`&quot;.

Titta till exempel på HTML-filen för Breadcrumb-komponenten v1: [breadcrumb.html](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v2/breadcrumb/breadcrumb.html)ser vi att hierarkin för elementutdata är `ol.breadcrumb > li.breadcrumb-item > a`. För att vara säker på att en CSS-regel bara påverkar den komponentens klass breadcrumb ska alla regler ha ett namn enligt nedan:

```shell
.cmp-breadcrumb .breadcrumb {}  
.cmp-breadcrumb .breadcrumb-item {}  
.cmp-breadcrumb a {}
```

Dessutom utnyttjar var och en av kärnkomponenterna AEM [Formatsystemfunktion](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/style-system.html) som gör att mallskapare kan definiera ytterligare CSS-klassnamn som kan användas på komponenten av sidförfattarna. På så sätt kan du definiera en lista med tillåtna komponentformat för varje mall och om ett av dem ska användas som standard för alla komponenter av den typen.

## Uppgraderingskompatibilitet för anpassningar {#upgrade-compatibility-of-customizations}

Det finns tre olika typer av uppgraderingar:

* uppgradera AEM
* uppgradera kärnkomponenterna till en ny mindre version
* uppgradera kärnkomponenterna till en större version

Om du uppgraderar AEM till en ny version påverkas inte huvudkomponenterna eller de anpassningar som görs, förutsatt att komponenternas versioner också har stöd för den nya AEM-versionen som migreras och att anpassningarna inte använder API:er som har [borttagen eller ersatt](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/deprecated-removed-features.html).

Om du uppgraderar kärnkomponenterna utan att växla till en senare huvudversion bör det inte påverka anpassningar, så länge som de anpassningsmönster som beskrivs på den här sidan används.

Att byta till en senare större version av Core Components är bara kompatibelt för innehållsstrukturen, men anpassningarna kan behöva omarbetas. Tydliga ändringsloggar kommer att publiceras för varje komponentversion för att markera de ändringar som skulle påverka den typ av anpassningar som beskrivs på den här sidan.

## Stöd för anpassningar {#support-of-customizations}

Precis som för alla AEM finns det ett antal saker att tänka på när det gäller anpassningar:

1. **Ändra aldrig koden för kärnkomponenter direkt.**

   Detta gör att de inte stöds helt och hållet och gör framtida uppdateringar av komponenterna till en mödosam process. Använd i stället de anpassningsmetoder som beskrivs på den här sidan.

1. **Anpassad kod är ditt eget ansvar.**

   Vårt supportprogram täcker inte anpassad kod och rapporterade problem som inte kan reproduceras med vanliga kärnkomponenter som är [används som dokumenterat](/help/get-started/using.md) Jag är inte berättigad.

1. **Se borttagna funktioner som tagits bort.**

   Se till att alla API:er som används fortfarande är aktuella när varje ny AEM uppgraderas till genom att hålla ett öga på [Föråldrade och borttagna funktioner](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/deprecated-removed-features.html) sida.

Se även [Stöd för kärnkomponenter](overview.md#core-component-support) -avsnitt.

**Läs nästa:**

* [Använda kärnkomponenter](/help/get-started/using.md) - Kom igång med Core Components i ditt eget projekt.
* [Riktlinjer för komponenter](guidelines.md) - för att lära sig implementeringsmönstren för kärnkomponenterna.
