---
title: Använda kärnkomponenter
description: '"För att komma igång med Core Components i ditt eget projekt finns det tre steg: ladda ned och installera, skapa proxykomponenter, ladda ned huvudformaten och tillåt komponenterna i mallarna."'
role: Arkitekt, utvecklare, administratör, affärsansvarig
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '762'
ht-degree: 0%

---


# Använda kärnkomponenter{#using-core-components}

För att komma igång med Core Components i ditt eget projekt finns det fyra steg, som beskrivs individuellt i avsnitten nedan:

1. [Hämta och installera](#download-and-install)
1. [Skapa proxykomponenter](#create-proxy-components)
1. [Läs in kärnformat](#load-the-core-styles)
1. [Aktivera komponenterna](#allow-the-components)

>[!NOTE]
>
>Om du vill ha mer omfattande anvisningar om hur du kommer igång från grunden med projektkonfigurationen, kärnkomponenter, redigerbara mallar, klientbibliotek och komponentutveckling kan följande självstudiekurs i flera delar vara av intresse:\
>[Komma igång med AEM Sites - WKND självstudiekurs](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)

## Hämta och installera {#download-and-install}

En av de drivande idéerna bakom kärnkomponenterna är flexibilitet. Genom att lansera nya versioner av de centrala komponenterna oftare kan Adobe bli mer flexibelt när det gäller att leverera nya funktioner. Utvecklarna kan i sin tur vara flexibla när det gäller vilka komponenter de väljer att integrera i sina projekt och hur ofta de vill uppdatera dem.

Därför ingår inte kärnkomponenterna i snabbstarten när du startar i produktionsläge (utan exempelinnehåll). Därför är det första steget att [hämta det senaste släppta innehållspaketet från GitHub](https://github.com/adobe/aem-core-wcm-components/releases/latest) och installera det i dina AEM miljöer.

Det finns flera sätt att automatisera detta, men det enklaste sättet att snabbt installera ett innehållspaket på en instans är att använda pakethanteraren. se [Installera paket](https://docs.adobe.com/content/help/en/experience-manager-65/administering/contentmanagement/package-manager.html#installing-packages). När du också har en publiceringsinstans som körs måste du replikera paketet till utgivaren. se [Replikera paket](https://docs.adobe.com/content/help/en/experience-manager-65/administering/contentmanagement/package-manager.html#replicating-packages).

## Skapa proxykomponenter {#create-proxy-components}

Av anledningar som förklaras i avsnittet [Proxykomponentmönster](/help/developing/guidelines.md#proxy-component-pattern) får inte kärnkomponenter refereras direkt från innehållet. För att undvika det tillhör de alla en dold komponentgrupp ( `.core-wcm` eller `.core-wcm-form`), vilket förhindrar att de visas direkt i redigeraren.

Istället måste webbplatsspecifika komponenter skapas, som definierar det komponentnamn och den grupp som ska visas för sidförfattare, och referera var och en till en Core Component som supertyp. Dessa platsspecifika komponenter kallas ibland för&quot;proxykomponenter&quot; eftersom de inte behöver innehålla något och i huvudsak används för att definiera vilken version av en komponent som ska användas för webbplatsen. När du anpassar [kärnkomponenterna](/help/developing/customizing.md) spelar dessa proxykomponenter en viktig roll för markering och logikanpassning.

För varje Core Component som ska användas för en plats måste du:

1. Skapa en motsvarande proxykomponent i platsens komponentmapp.

   ****
ExampleUnder  `/apps/my-site/components` skapar du en namnnod av typen  `cq:Component`

1. Peka på motsvarande Core Component-version med supertypen.

   ****
ExampleAdd following property:\
   `sling:resourceSuperType="core/wcm/components/title/v1/title"`

1. Definiera komponentens grupp, titel och eventuellt beskrivning. Dessa värden är projektspecifika och styr hur komponenten exponeras för författare.

   ****
ExampleLägg till följande egenskaper:

   ```shell
   componentGroup="My Site"
   jcr:title="Title"  
   jcr:description="Section Heading"
   ```

Titta till exempel på titelkomponenten [för WKND-platsen](https://github.com/adobe/aem-guides-wknd/blob/master/ui.apps/src/main/content/jcr_root/apps/wknd/components/title/.content.xml), som är ett bra exempel på en proxykomponent som är byggd på det sättet.

## Läs in kärnformat {#load-the-core-styles}

1. Om det inte är klart än skapar du ett [klientbibliotek](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html) som innehåller alla CSS- och JS-filer som behövs för platsen.
1. Lägg till beroenden till de kärnkomponenter som kan behövas i webbplatsens klientbibliotek. Detta görs genom att en `embed`-egenskap läggs till.

   Om du till exempel vill inkludera klientbiblioteken för alla v1 Core-komponenter blir den egenskap som ska läggas till:

   ```shell
   embed="[  
   core.wcm.components.image.v1,  
   core.wcm.components.list.v1,  
   core.wcm.components.breadcrumb.v1,  
   core.wcm.components.form.container.v1,  
   core.wcm.components.form.text.v1  
   ]"
   ```

Kontrollera att dina proxykomponenter och klientbibliotek har distribuerats till din AEM innan du går vidare till nästa avsnitt.

## Tillåt komponenterna {#allow-the-components}

Följande steg utförs i [mallredigeraren](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html).

1. Markera layoutbehållaren i mallredigeraren och öppna dess profil.
1. I listan över tillåtna komponenter väljer du de proxykomponenter som skapats tidigare, som ska visas under komponentgruppen som de tilldelats. När du är klar tillämpar du ändringarna.
1. Om du vill kan du förkonfigurera komponenter som har en designdialogruta.

Så ja! På de sidor som skapas från den redigerade mallen bör du nu kunna använda de nya komponenterna.

**Läs nästa:**

* [Anpassa kärnkomponenter](/help/developing/customizing.md)  för att lära dig hur du formaterar och anpassar kärnkomponenterna.
* [Komponentriktlinjer](/help/developing/guidelines.md)  - för att lära dig implementeringsmönstren för kärnkomponenterna.
