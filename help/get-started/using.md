---
title: Använda kärnkomponenter
description: "För att komma igång med Core Components i ditt eget projekt finns det tre steg att följa: ladda ned och installera, skapa proxykomponenter, läsa in huvudformaten och tillåt komponenterna i dina mallar."
role: Architect, Developer, Admin, User
exl-id: ee2d25e4-e2b8-4ecc-a62c-f0066de2bf2d
source-git-commit: 8beae61676340e8aafaee469018d865ea7ed934e
workflow-type: tm+mt
source-wordcount: '948'
ht-degree: 0%

---

# Använda kärnkomponenter{#using-core-components}

För att komma igång med Core Components i ditt eget projekt finns det fyra steg, som beskrivs individuellt i avsnitten nedan:

1. [Hämta och installera](#download-and-install)
1. [Skapa proxykomponenter](#create-proxy-components)
1. [Läs in kärnformat](#load-the-core-styles)
1. [Aktivera komponenterna](#allow-the-components)

>[!TIP]
>
>För mer omfattande instruktioner om hur du kommer igång från grunden med projektkonfigurationen, kärnkomponenter, redigerbara mallar, klientbibliotek och komponentutveckling kan följande självstudiekurs i flera delar vara av intresse:\
>[Komma igång med AEM Sites - WKND-självstudiekurs](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)

>[!TIP]
>
>Om du använder [AEM Project Archetype](/help/developing/archetype/overview.md) inkluderas kärnkomponenterna automatiskt i ditt projekt baserat på rekommendationer om bästa praxis för Adobe.

## Hämta och installera {#download-and-install}

En av de drivande idéerna bakom kärnkomponenterna är flexibilitet. Genom att lansera nya versioner av de centrala komponenterna oftare kan Adobe bli mer flexibelt när det gäller att leverera nya funktioner. Utvecklarna kan i sin tur vara flexibla när det gäller vilka komponenter de väljer att integrera i sina projekt och hur ofta de vill uppdatera dem. Detta resulterar i en separat versionsprocess för både AEM och kärnkomponenterna.

Därför avgör installationsstegen om du kör AEM som en molntjänst eller en lokal tjänst.

### AEM as a Cloud Service {#aemaacs}

Det finns inget steg ett! AEM as a Cloud Service har automatiskt den senaste versionen av Core Components. Precis som AEMaaCS erbjuder de senaste funktionerna i AEM håller AEMaaCS automatiskt dig uppdaterad med den senaste versionen av Core Components.

Tänk på några saker när du använder kärnkomponenterna i AEMaaCS:

* Kärnkomponenterna ingår i `/libs`.
* Projektets pipeline genererar varningar i loggen om den innehåller kärnkomponenterna igen som en del av `/apps` och ignorerar den version som är inbäddad som en del av ditt projekt.
   * I en kommande version, inklusive Core Components igen, kommer pipeline-bygget att misslyckas.
* Om ditt projekt tidigare innehöll kärnkomponenterna i `/apps` kan [du behöva justera ditt projekt.](/help/developing/overview.md#via-aemaacs)
* Även om kärnkomponenterna nu finns i `/libs` rekommenderar vi inte att du skapar någon övertäckning med samma sökväg i `/apps`. [Proxykomponentmönstret ](/help/developing/guidelines.md#proxy-component-pattern) bör användas i stället om någon aspekt av komponenterna behöver anpassas.
* För att komponenten [Innehållsförteckning](/help/components/tableofcontents.md) ska kunna återge sitt innehåll måste ett filter konfigureras i OSGi.
   * [Mer information finns i GitHub-dokumentationen för komponenten](https://adobe.com/go/aem_cmp_tech_tableofcontents_v1).

### AEM 6.5 och tidigare {#aem-65}

Kärnkomponenterna är inte en del av snabbstarten när de startas i produktionsläge (utan exempelinnehåll). Därför är det första steget att [hämta det senaste släppta innehållspaketet från GitHub](https://github.com/adobe/aem-core-wcm-components/releases/latest) och installera det i dina AEM miljöer.

Det finns flera sätt att automatisera detta, men det enklaste sättet att snabbt installera ett innehållspaket på en instans är att använda pakethanteraren. Se [Installera paket](https://experienceleague.adobe.com/docs/experience-manager-65/administering/contentmanagement/package-manager.html#installing-packages). När du dessutom kör en publiceringsinstans måste du replikera paketet till utgivaren. Se [Replikera paket](https://experienceleague.adobe.com/docs/experience-manager-65/administering/contentmanagement/package-manager.html#replicating-packages).

## Skapa proxykomponenter {#create-proxy-components}

Av orsaker som förklaras i avsnittet [Proxykomponentmönster](/help/developing/guidelines.md#proxy-component-pattern) får inte kärnkomponenter refereras direkt från innehållet. För att undvika det tillhör de alla en dold komponentgrupp ( `.core-wcm` eller `.core-wcm-form`), vilket förhindrar att de visas direkt i redigeraren.

Istället måste webbplatsspecifika komponenter skapas, som definierar det komponentnamn och den grupp som ska visas för sidförfattare, och referera var och en till en Core Component som supertyp. Dessa platsspecifika komponenter kallas ibland för&quot;proxykomponenter&quot; eftersom de inte behöver innehålla något och i huvudsak används för att definiera vilken version av en komponent som ska användas för webbplatsen. När du anpassar [kärnkomponenterna](/help/developing/customizing.md) spelar de här proxykomponenterna dock en viktig roll för markering och logikanpassning.

För varje Core Component som ska användas för en plats måste du:

1. Skapa en motsvarande proxykomponent i platsens komponentmapp.

   **Exempel**
Under `/apps/my-site/components` skapar du en titelnod av typen `cq:Component`

1. Peka på motsvarande Core Component-version med supertypen.

   **Exempel**
Lägg till följande egenskap:\
   `sling:resourceSuperType="core/wcm/components/title/v1/title"`

1. Definiera komponentens grupp, titel och eventuellt beskrivning. Dessa värden är projektspecifika och styr hur komponenten exponeras för författare.

   **Exempel**
Lägg till följande egenskaper:

   ```shell
   componentGroup="My Site"
   jcr:title="Title"  
   jcr:description="Section Heading"
   ```

Titta till exempel på [titelkomponenten för WKND-webbplatsen](https://github.com/adobe/aem-guides-wknd/blob/master/ui.apps/src/main/content/jcr_root/apps/wknd/components/title/.content.xml), som är ett bra exempel på en proxykomponent som är byggd på det sättet.

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

Följande steg utförs i [mallredigeraren](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html).

1. Markera layoutbehållaren i mallredigeraren och öppna dess profil.
1. I listan över tillåtna komponenter väljer du de proxykomponenter som skapats tidigare, som ska visas under komponentgruppen som de tilldelats. När du är klar tillämpar du ändringarna.
1. Om du vill kan du förkonfigurera komponenter som har en designdialogruta.

Så ja! På de sidor som skapas från den redigerade mallen bör du nu kunna använda de nya komponenterna.

**Läs nästa:**

* [Anpassa kärnkomponenter](/help/developing/customizing.md) - för att lära dig hur du formaterar och anpassar kärnkomponenterna.
* [Riktlinjer för komponenter](/help/developing/guidelines.md) - om du vill lära dig implementeringsmönstren för kärnkomponenterna.
