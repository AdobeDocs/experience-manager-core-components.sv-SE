---
title: Lokaliseringsfunktioner för kärnkomponenterna
description: Lokaliseringsfunktioner för kärnkomponenterna
role: Architect, Developer, Administrator, Business Practitioner
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '730'
ht-degree: 0%

---


# Lokaliseringsfunktioner för kärnkomponenterna {#localization-features-of-the-core-components}

Många webbplatser kräver att innehåll levereras i ett lokaliserat format på flera språk och i olika länder. De valda kärnkomponenterna har en smart referensupplösning som gör det enkelt att skapa en enhetlig mall för allt lokaliserat innehåll som automatiskt anpassas baserat på den lokaliserade webbplatsstrukturen.

## Exempel - Lokaliserad sida med navigering och sidfötter {#example}

De flesta webbplatser kräver att det finns en sidfot på alla sidor. Dessa sidfötter är i allmänhet konsekventa för allt innehåll på sidan. För en lokaliserad innehållssida måste dock en lokaliserad version av sidhuvudet eller sidfoten visas.

På samma sätt måste en navigeringskomponent vanligtvis visas på alla sidor. Det måste dock även återspegla innehållet på de lokaliserade sidorna.

Det här blir en enkel uppgift med lokaliseringsfunktionerna i [kärnkomponenten för navigering](/help/components/navigation.md) och [kärnkomponenten för upplevelsefragment](/help/components/experience-fragment.md) tillsammans med de redigerbara mallarna för [AEM](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html). Exemplet kan utökas ytterligare för att även använda [språknavigeringskomponenten](/help/components/language-navigation.md).

## Innehållsstrukturen {#content-structure}

Alla lokaliseringsfunktioner i AEM och dess kärnkomponenter är beroende av en tydlig och logisk innehållsstruktur för ditt lokaliserade innehåll.

Säg att din webbplats bara heter `my-site` och finns här:

```
/content/my-site
```

Låt oss också säga att du skriver din webbplats på engelska och erbjuder den på franska också. Om du har en enkel sida med namnet `my-page` finns den i två lokaliseringsgrenar i webbplatsens innehållsträd:

```
/content
\-- my-site
   +-- en
       \-- my-page
   \-- fr
       \-- my-page
```

Det finns under dessa lokaliseringsgrenar där du kan skapa ytterligare webbplatssidor.

Sidfötter görs vanligtvis med Experience Fragments så att du behöver en engelsk och fransk version precis som på dina sidor. Upplevelsefragment är emellertid inte sidor, utan snarare delar av sidor som kan återanvändas över sidor, så de lever inte direkt under `/content` som resten av sidorna. Istället bor de i sin egen mapp, men eftersom de också måste lokaliseras måste deras struktur spegla platsens lokaliseringsstruktur.

```
/content
+-- experience-fragments
   +-- en
      \-- footer
   \-- fr
      \-- footer
\-- my-site
   +-- en
      \-- my-page
   \-- fr
      \-- my-page
```

Det är via den speglade lokaliseringsstrukturen som kärnkomponenterna kan hitta det lokaliserade innehåll som krävs för en motsvarande sida.

## Sidfot - Upplevelsefragment {#xf-footer}

Experience Fragment Component är mycket flexibelt och passar bra för sidhuvud och sidfot.

Eftersom vår hypotetiska webbplats finns på engelska och franska måste vi skapa två Experience Fragments som båda kallas `footer` [på de platser vi beskrev tidigare.](#content-structure)

![](/help/assets/screen-shot-2019-09-09-11.08.28.png)

## Sidmall {#template}

Eftersom sidfoten visas på varje sida måste vi lägga till Experience Fragment i vår standardsidmall.

Vår mall heter bara `my-template` och finns med i våra andra mallar:

```
/conf/my-site/settings/wcm/templates/my-template
```

Till den här mallen ska vi lägga till de grundläggande komponenter som vi vill att våra sidor ska baseras på.

* [Navigeringskomponent](/help/components/navigation.md)
   * Navigeringskomponenten visas överst på varje sida.
   * I navigeringskomponenten definierar vi navigeringsroten och anger den komponent där navigeringsstrukturen börjar.
   * Baserat på navigeringsroten kan komponenten automatiskt hitta motsvarande lokaliserat innehåll.
* [Behållarkomponent](/help/components/container.md)
   * Varje sida kommer att innehålla en redigerbar behållarkomponent så att författare kan placera ytterligare innehåll på sidan.
* [Experience Fragment](/help/components/experience-fragment.md)
   * Vi pekar Experience Fragment-komponenten mot fragmentsökvägen i vårt redigeringsspråk för det fragment som representerar sidfoten.
   * Baserat på fragmentets sökväg och strukturen för de upplevelsefragment som speglar den lokaliserade sidstrukturen, kan komponenten automatiskt hitta motsvarande lokaliserade innehåll.

   ![](/help/assets/screen-shot-2019-09-09-11.20.10.png)

## Sidor {#pages}

Genom att göra det hårda arbetet med att konfigurera webbplatsens struktur och mall behöver innehållsförfattaren bara lägga till nödvändigt innehåll på sidorna. Tack vare mallarna och komponenternas lokaliseringslogik läggs navigering och sidfötter automatiskt till på sidan och lokaliseras.

Författaren behöver till exempel bara lägga till innehåll som en textkomponent på de engelska och franska sidorna (visas i blått nedan).

Navigeringskomponenten och Experience Fragment-komponenten kommer från sidmallen och vet att automatiskt visa rätt innehåll baserat på lokaliseringsstrukturen och platsen för sidan (visas i vitt nedan).

![](/help/assets/screen-shot-2019-09-09-11.22.14.png)

## Passar in allt tillsammans {#fitting-it-all-together}

Här är en komplett bild av hur dessa enkla, men kraftfulla element samverkar för att leverera lokaliserade sidor till innehållsförfattarna.

![](/help/assets/screen-shot-2019-09-09-11.27.58.png)
