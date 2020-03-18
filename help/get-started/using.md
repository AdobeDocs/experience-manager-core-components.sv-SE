---
title: Använda kärnkomponenter
description: '"För att komma igång med Core Components i ditt eget projekt finns det tre steg: ladda ned och installera, skapa proxykomponenter, ladda ned huvudformaten och tillåt komponenterna i mallarna."'
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

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
>[Komma igång med AEM Sites - självstudiekurs om WKND](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)

## Hämta och installera {#download-and-install}

En av de drivande idéerna bakom kärnkomponenterna är flexibilitet. Genom att släppa nya versioner av de centrala komponenterna oftare kan Adobe bli mer flexibelt när det gäller att leverera nya funktioner. Utvecklarna kan i sin tur vara flexibla när det gäller vilka komponenter de väljer att integrera i sina projekt och hur ofta de vill uppdatera dem.

Därför ingår inte kärnkomponenterna i snabbstarten när du startar i produktionsläge (utan exempelinnehåll). Därför är det första steget att [hämta det senaste innehållspaketet från GitHub](https://github.com/adobe/aem-core-wcm-components/releases/latest) och installera det i dina AEM-miljöer.

Det finns flera sätt att automatisera detta, men det enklaste sättet att snabbt installera ett innehållspaket på en instans är att använda pakethanteraren. se [Installera paket](https://docs.adobe.com/content/help/en/experience-manager-65/administering/contentmanagement/package-manager.html#installing-packages). När du också har en publiceringsinstans som körs måste du replikera paketet till utgivaren. se [Replikera paket](https://docs.adobe.com/content/help/en/experience-manager-65/administering/contentmanagement/package-manager.html#replicating-packages).

<!-- 

Comment Type: annotation
Last Modified By: ims-author-CE1E2CE451D1F0680A490D45@AdobeID
Last Modified Date: 2017-04-17T16:42:59.142-0400

Should we be promoting embedding the core-component package as an artifact in a customer application, reasoning as follows: 1) a customer application is required to leverage core components (at a minimum, proxy components must be defined) 2) a customer application must be updated to leverage new versions of core components (since it requires adjusting the sling:resourceSuperType to point at the new version of the component) It seems the only time theres an advantage to installing a release directly is if a bug-fix (non version-changing) release of core-components is cut, and it doesnt coincide with an application deployment. WDYT? For example, recommend doing this for ACS Commons which has a similar use-case (https://adobe-consulting-services.github.io/acs-aem-commons/pages/maven.html) We can of course keep the instructions for manually deploying, since some will want to do this, or the bug-fix use-case will appear.

 -->

## Skapa proxykomponenter {#create-proxy-components}

Av anledningar som förklaras i avsnittet [Proxykomponentmönster](/help/developing/guidelines.md#proxy-component-pattern) får det inte finnas en direkt referens till kärnkomponenter från innehållet. För att undvika det tillhör de alla en dold komponentgrupp ( `.core-wcm` eller `.core-wcm-form`), vilket förhindrar att de visas direkt i redigeraren.

Istället måste webbplatsspecifika komponenter skapas, som definierar det komponentnamn och den grupp som ska visas för sidförfattare, och referera var och en till en Core Component som supertyp. Dessa platsspecifika komponenter kallas ibland för&quot;proxykomponenter&quot; eftersom de inte behöver innehålla något och i huvudsak används för att definiera vilken version av en komponent som ska användas för webbplatsen. När du anpassar [kärnkomponenterna](/help/developing/customizing.md)spelar dessa proxykomponenter dock en viktig roll för markeringar och logikanpassning.

För varje Core Component som ska användas för en plats måste du:

1. Skapa en motsvarande proxykomponent i platsens komponentmapp.

   **Exempel** Under `/apps/my-site/components` skapar du en namnnod av typen `cq:Component`

1. Peka på motsvarande Core Component-version med supertypen.

   **Exempel**: Lägg till följande egenskap:\
   `sling:resourceSuperType="core/wcm/components/title/v1/title"`

1. Definiera komponentens grupp, titel och eventuellt beskrivning. Dessa värden är projektspecifika och styr hur komponenten exponeras för författare.

   **Exempel**: Lägg till följande egenskaper:

   ```shell
   componentGroup="My Site"
   jcr:title="Title"  
   jcr:description="Section Heading"
   ```

Titta till exempel på [titelkomponenten för referenswebbplatsen](https://github.com/Adobe-Marketing-Cloud/aem-sample-we-retail/blob/master/ui.apps/src/main/content/jcr_root/apps/weretail/components/content/title/.content.xml)We.Retail, som är ett bra exempel på en proxykomponent som är byggd på det sättet.

## Läs in kärnformat {#load-the-core-styles}

<!-- 

Comment Type: annotation
Last Modified By: ims-author-CE1E2CE451D1F0680A490D45@AdobeID
Last Modified Date: 2017-04-17T16:57:16.414-0400

Styles is odd in that most Core Components do not have CSS; very few even have structural CSS (breadcrumbs, list) It may be more apt to title this section: Load the Core JavaScript and CSS or Load the Core Client Libraries ?

 -->

<!-- 

Comment Type: annotation
Last Modified By: ims-author-CE1E2CE451D1F0680A490D45@AdobeID
Last Modified Date: 2017-04-17T17:41:37.115-0400

This section seems to cover the "sites" clientlibs for core components; Do we need a section for ensuring the editor clientlibs are loaded in the Page Editor? Pending: https://github.com/Adobe-Marketing-Cloud/aem-core-wcm-components/issues/15

 -->

<!-- 

Comment Type: annotation
Last Modified By: cotescu
Last Modified Date: 2018-03-09T10:45:52.812-0500

Load the Core Client Libraries sounds way better

 -->

1. Om det inte är klart än skapar du ett [klientbibliotek](https://docs.adobe.com/content/help/en/experience-manager-65/developing/introduction/clientlibs.html) som innehåller alla CSS- och JS-filer som behövs för platsen.
1. Lägg till beroenden till de kärnkomponenter som kan behövas i webbplatsens klientbibliotek. Detta görs genom att en `embed` egenskap läggs till.

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

Kontrollera att dina proxykomponenter och klientbibliotek har distribuerats till din AEM-miljö innan du går vidare till nästa avsnitt.

## Tillåt komponenterna {#allow-the-components}

Följande steg utförs i [mallredigeraren](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html).

1. Markera layoutbehållaren i mallredigeraren och öppna dess profil.
1. I listan över tillåtna komponenter väljer du de proxykomponenter som skapats tidigare, som ska visas under komponentgruppen som de tilldelats. När du är klar tillämpar du ändringarna.
1. Om du vill kan du förkonfigurera komponenter som har en designdialogruta.

Så ja! På de sidor som skapas från den redigerade mallen bör du nu kunna använda de nya komponenterna.

**Läs nästa:**

* [Anpassa kärnkomponenter](/help/developing/customizing.md) för att lära dig hur du formaterar och anpassar kärnkomponenterna.
* [Komponentriktlinjer](/help/developing/guidelines.md) - för att lära dig implementeringsmönstren för kärnkomponenterna.
