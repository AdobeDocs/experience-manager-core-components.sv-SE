---
title: Anpassa kärnkomponenter
description: Core Components implementerar flera mönster som gör det enkelt att anpassa, från enkel formatering till avancerad återanvändning av funktioner.
translation-type: tm+mt
source-git-commit: fe8a121520000ffd56ae3347469590e89121eaf0

---


# Anpassa kärnkomponenter{#customizing-core-components}

Med [kärnkomponenterna](overview.md) implementeras flera mönster som gör det enkelt att anpassa, från enkel formatering till avancerad återanvändning av funktioner.

## Flexibel arkitektur {#flexible-architecture}

Kärnkomponenterna var från början utformade för att vara flexibla och utökningsbara. En översikt över deras arkitektur visar var anpassningar kan göras.

![Kärnkomponentarkitektur](/help/assets/screen_shot_2018-12-07at093742.png)

* [Designdialogrutan](/help/get-started/authoring.md#edit-and-design-dialogs) definierar vad författare kan eller inte kan göra i redigeringsdialogrutan.
* [I redigeringsdialogrutan](/help/get-started/authoring.md#edit-and-design-dialogs) visas endast de alternativ som författare kan använda.
* [Sling-modellen](#customizing-the-logic-of-a-core-component) verifierar och förbereder innehållet för vyn (mallen).
* [Resultatet av Sling-modellen](#customizing-the-logic-of-a-core-component) kan serialiseras till JSON för SPA-användningsfall.
* [HTML-koden återger HTML](#customizing-the-markup) -servern för traditionell återgivning på serversidan.
* [HTML-utdata](#customizing-the-markup) är semantiska, tillgängliga, sökmotoroptimerade och enkla att formatera.

Och alla huvudkomponenter implementerar [Style System](#styling-the-components).

## AEM Project Archetype {#aem-project-archetype}

[AEM Project Archetype](/help/developing/archetype/overview.md) skapar ett minimalt Adobe Experience Manager-projekt som startpunkt för dina egna projekt, inklusive ett exempel på en anpassad HTML-komponent med SlingModels för en logisk och korrekt implementering av Core Components med det rekommenderade proxymönstret.

## Anpassningsmönster {#customization-patterns}

### Anpassa dialogrutor {#customizing-dialogs}

Du kan behöva anpassa de konfigurationsalternativ som är tillgängliga i en huvudkomponentdialogruta, oavsett om det är [designdialogrutan eller redigeringsdialogrutan](/help/get-started/authoring.md).

Varje dialogruta har en konsekvent nodstruktur. Vi rekommenderar att den här strukturen replikeras i en ärvande komponent så att [Dela resurssammanfogning](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/sling-resource-merger.html) och [Dölj villkor](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/hide-conditions.html) kan användas för att dölja, ersätta eller ändra ordning på avsnitt i den ursprungliga dialogrutan. Strukturen som ska replikeras definieras som allt upp till tabbobjektets nodnivå.

För att vara helt kompatibelt med ändringar som gjorts i en dialogruta i den aktuella versionen är det mycket viktigt att strukturer under flikobjektsnivån inte rörs (dold, läggs till, ersätts, sorteras om osv.). I stället ska ett flikobjekt från det överordnade objektet döljas via `sling:hideResource` egenskapen (se [Egenskaper](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/sling-resource-merger.html)för sammanslagning av delningresurser) och nya flikobjekt som innehåller anpassade konfigurationsfält läggas till. `sling:orderBefore` kan vid behov användas för att ändra ordningen på flikobjekt.

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

I huvudkomponenten för titeln används egenskapen `jcr:title` för den begärda resursen för att ge titeltexten. Om ingen `jcr:title` egenskap är definierad, kommer en reserv att implementeras för den aktuella sidrubriken. Vi vill ändra beteendet så att den aktuella sidans rubrik alltid visas.

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

Detta kan du enkelt göra genom att kopiera HTML-filerna som behöver ändras från Core-komponenten till proxykomponenten.

Om du än en gång tar exemplet med kärnkomponenten Breadcrumb Component och anpassar kodresultatet, måste filen kopieras till den platsspecifika komponenten som har en `breadcrumb.html` `sling:resourceSuperTypes` som pekar på kärnkomponenten Breadcrumb.

### Formatera komponenterna {#styling-the-components}

Den första formen av anpassning är att tillämpa CSS-format.

För att göra detta enklare återges semantisk kod med Core Components och en standardiserad namnkonvention som inspirerats av [Bootstrap](https://getbootstrap.com/). För att det ska vara enkelt att rikta in och namnge formaten för de enskilda komponenterna kapslas varje Core Component in i ett DIV-element med klasserna &quot; `cmp`&quot; och &quot; `cmp-<name>`&quot;.

Titta till exempel på HTML-filen för Breadcrumb-komponenten v1: [breadcrumb.html](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v2/breadcrumb/breadcrumb.html)ser vi att hierarkin för elementutdata är `ol.breadcrumb > li.breadcrumb-item > a`. För att vara säker på att en CSS-regel bara påverkar den komponentens klass breadcrumb ska alla regler ha ett namn enligt nedan:

```shell
.cmp-breadcrumb .breadcrumb {}  
.cmp-breadcrumb .breadcrumb-item {}  
.cmp-breadcrumb a {}
```

Dessutom utnyttjar var och en av kärnkomponenterna funktionen [i AEM](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/style-system.html) Style System, som gör att mallskapare kan definiera ytterligare CSS-klassnamn som kan tillämpas på komponenten av sidförfattarna. På så sätt kan du definiera en lista med tillåtna komponentformat för varje mall och om ett av dem ska användas som standard för alla komponenter av den typen.

## Uppgraderingskompatibilitet för anpassningar {#upgrade-compatibility-of-customizations}

Det finns tre olika typer av uppgraderingar:

* uppgradera AEM-versionen
* uppgradera kärnkomponenterna till en ny mindre version
* uppgradera kärnkomponenterna till en större version

I allmänhet påverkar inte en uppgradering av AEM till en ny version Core Components eller de anpassningar som görs, förutsatt att komponenternas versioner även stöder den nya AEM-versionen som migreras och att anpassningarna inte använder API:er som har [tagits bort](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/release-notes/deprecated-removed-features.html)eller tagits bort.

Om du uppgraderar kärnkomponenterna utan att växla till en senare huvudversion bör det inte påverka anpassningar, så länge som de anpassningsmönster som beskrivs på den här sidan används.

Att byta till en senare större version av Core Components är bara kompatibelt för innehållsstrukturen, men anpassningarna kan behöva omarbetas. Tydliga ändringsloggar kommer att publiceras för varje komponentversion för att markera de ändringar som skulle påverka den typ av anpassningar som beskrivs på den här sidan.

## Stöd för anpassningar {#support-of-customizations}

Precis som för alla AEM-komponenter finns det ett antal saker att tänka på när det gäller anpassningar:

1. **Ändra aldrig koden för kärnkomponenter direkt.**

   Detta gör att de inte stöds helt och hållet och gör framtida uppdateringar av komponenterna till en mödosam process. Använd i stället de anpassningsmetoder som beskrivs på den här sidan.

1. **Anpassad kod är ditt eget ansvar.**

   Vårt supportprogram täcker inte anpassad kod, och rapporterade problem som inte kan reproduceras med vanliga kärnkomponenter som [används som dokumenterade](/help/get-started/using.md) dokument kvalificerar inte.

1. **Se borttagna funktioner som tagits bort.**

   Kontrollera att alla API:er som används fortfarande är aktuella när du uppgraderar till varje ny AEM-version genom att hålla ett öga på sidan [Borttagna och borttagna funktioner](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/release-notes/deprecated-removed-features.html) .

Se även [Core Component Support](overview.md#core-component-support) .

**Läs nästa:**

* [Använda kärnkomponenter](/help/get-started/using.md) - Kom igång med Core Components i ditt eget projekt.
* [Komponentriktlinjer](guidelines.md) - för att lära dig implementeringsmönstren för kärnkomponenterna.