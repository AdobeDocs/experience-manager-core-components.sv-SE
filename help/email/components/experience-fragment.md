---
title: E-postupplevelsefragmentkomponent
description: Med e-postupplevelsefragmentkomponenten kan innehållsförfattaren placera en Experience Fragment-variant i sitt innehåll samtidigt som den stöder en lokaliserad innehållsstruktur.
role: Architect, Developer, Admin, User
hidefromtoc: true
index: false
source-git-commit: 8bebe3ca036557f3f7c6b8ec0e65d6d104d5ffae
workflow-type: tm+mt
source-wordcount: '927'
ht-degree: 0%

---


# E-postupplevelsefragmentkomponent {#email-experience-fragment-component}

Med e-postupplevelsefragmentkomponenten kan innehållsförfattaren placera en Experience Fragment-variant i sitt innehåll samtidigt som den stöder en lokaliserad innehållsstruktur.

## Användning {#usage}

Med e-postupplevelsefragmentkomponenten kan innehållsförfattaren välja bland befintliga Experience Fragment-varianter och placera en i innehållet. En Experience Fragment är en grupp innehåll som innehåller både innehåll och layout och som kan återanvändas i alla kanaler.

* Komponentens egenskaper kan definieras i [konfigurera dialogruta](#configure-dialog).
* Standardvärden för komponenten när den läggs till i innehållet kan definieras i [designdialogruta](#design-dialog).

Komponenten för e-postupplevelsefragment stöder en lokaliserad platsstruktur.

## Version och kompatibilitet {#version-and-compatibility}

Den aktuella versionen av e-postupplevelsefragmentkomponenten är v1, som introducerades med version X av e-postkärnkomponenterna i oktober 2022, och som beskrivs i det här dokumentet.

Följande tabell visar alla versioner av komponenten som stöds, de AEM versionerna som komponenterna är kompatibla med och länkar till dokumentation för tidigare versioner.

| Komponentversion | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | Kompatibel | Kompatibel |

Mer information om versionerna och versionerna av E-postkärnkomponenten finns i dokumentet [E-postkärnkomponentversioner.](/help/email/versions.md)

## Lokaliserat stöd för webbplatsstruktur {#localized-site-structure}

Komponenten för e-postupplevelsefragment anpassar sig till lokaliserade innehållsstrukturer och återger rätt Experience Fragment baserat på innehållets lokalisering. För att göra detta måste Experience Fragment uppfylla följande villkor.

* E-postupplevelsefragmentkomponenten läggs till i en [sidmall.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/templates.html)
* Den mallen används för att skapa en ny innehållssida som är en del av en lokaliserad struktur nedan `/content/<site>`.
* Experience Fragment som refereras på en innehållssida är en del av en lokaliserad Experience Fragment-struktur nedan `/content/experience-fragments` som följer samma mönster som webbplatsen nedan `/content/<site>` och använda samma komponentnamn.

I det här fallet är fragmentet med samma lokalisering ([språk, utkast eller live-kopia](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/administering/reusing-content/msm-and-translation.html)) som den aktuella sidan återges som en del av mallen.

Det här beteendet är begränsat till e-postupplevelsefragmentkomponenter som lagts till i mallar. Experience Fragment Components som lagts till på enskilda innehållssidor återger exakt de Experience Fragment-återgivningar som konfigurerats i komponenten.

* Ett exempel på hur lokaliseringsfunktionerna i Experience Fragment-komponenten fungerar finns i [avsnittet nedan](#example).
* Ett exempel på hur lokaliseringsfunktionerna för kärnkomponenterna fungerar tillsammans finns i [Lokaliseringsfunktioner för sidan Core Components](/help/get-started/localization.md).

### Exempel {#example}

Låt oss säga att innehållet ser ut ungefär så här:

```
/content
+-- experience-fragments
   \-- wknd
      +-- language-masters
      +-- us
         +-- en
            +-- footerTextXf
            \-- headerTextXf
         \-- es
            +-- footerTextXf
            \-- headerTextXf
      \-- ch
         +-- de
            +-- footerTextXf
            \-- headerTextXf
         +-- fr
            +-- footerTextXf
            \-- headerTextXf
         \-- it
            +-- footerTextXf
            \-- headerTextXf
+-- wknd
   +-- language-masters
   +-- us
      +-- en
      \-- es
   +-- ch
      +-- de
      +-- fr
      \-- it
+-- wknd-events
\-- wknd-shop
```

Observera att strukturen nedan `/content/experience-fragments/wknd` speglar strukturen i `/content/wknd`.

I det här fallet, om e-postupplevelsefragmentkomponenten `/content/experience-fragments/wknd/us/en/footerTextXf` placeras i en mall, kommer de lokaliserade sidor som skapas baserat på den mallen automatiskt att återge det lokaliserade Experience Fragment som motsvarar den lokaliserade innehållssidan.

Så om du navigerar till en innehållssida under `/content/wknd/ch/de` som använder samma mall, `/content/experience-fragments/wknd/ch/de/footerTextXf` återges i stället för `/content/experience-fragments/wknd/us/en/footerTextXf`.

### Reserv {#fallback}

Komponenten för e-postupplevelsefragment försöker hitta en motsvarande lokaliserad komponent i följande ordning.

1. Först försöker den hitta en språkrot.
1. Om den inte hittas försöker den hitta en plan.
1. Om den inte hittas försöker den hitta en live-kopia.
1. Om den inte hittas används som standard det Experience Fragment som konfigurerats i komponenten.

## Exempel på komponentutdata {#sample-component-output}

Om du vill se både e-postupplevelsefragmentkomponenten och exempel på dess konfigurationsalternativ samt HTML och JSON-utdata går du till [Komponentbibliotek.](https://adobe.com/go/aem_cmp_library_email_xf)

## Teknisk information {#technical-details}

Den senaste tekniska dokumentationen om Experience Fragment-komponenten [finns på GitHub.](https://adobe.com/go/aem_cmp_email_tech_xf_v1)

Mer information om hur du utvecklar kärnkomponenterna finns i [Dokumentation för grundkomponentens utvecklare.](/help/developing/overview.md)

## Konfigurera dialogruta {#configure-dialog}

I dialogrutan Konfigurera kan innehållsförfattaren välja den Experience Fragment-variant som ska återges i innehållet.

![Redigeringsdialogrutan för e-postupplevelsefragmentkomponenten](/help/email/assets/email-experience-fragment-edit.png)

Använd **Öppna dialogrutan Markering** för att öppna komponentväljaren och välja vilken Experience Fragment-komponentvariation som ska läggas till på innehållssidan.

Om du lägger till e-postupplevelsefragmentkomponenten i en mall lokaliseras den automatiskt, förutsatt att Experience Fragments är lokaliserade, så det som återges på sidan kan variera från den komponent som du uttryckligen väljer. [Se exemplet ovan](#example) för mer information.

Du kan också definiera en **ID**. Med det här alternativet kan du kontrollera den unika identifieraren för komponenten i HTM.

* Om du inte anger något värde genereras ett unikt ID automatiskt och du hittar det genom att kontrollera innehållet.
* Om ett ID anges är det författarens ansvar att se till att det är unikt.
* Om du ändrar ID:t kan det påverka CSS.

### Fliken Format {#styles-tab-edit}

E-postupplevelsefragmentkomponenten stöder AEM [Formatsystem.](/help/get-started/authoring.md#component-styling)

Använd listrutan för att välja de format som du vill använda på komponenten. Markeringar som görs i redigeringsdialogrutan har samma effekt som de som väljs i komponentverktygsfältet.

Format måste konfigureras för den här komponenten i [designdialogruta](#design-dialog) för att fliken ska vara tillgänglig.

## Designdialogruta {#design-dialog}

I designdialogrutan kan mallskaparen definiera de alternativ som är tillgängliga för den som använder e-postupplevelsefragmentkomponenten och de standardvärden som anges när e-postupplevelsefragmentkomponenten placeras.

### Fliken Format {#styles-tab}

E-postupplevelsefragmentkomponenten stöder AEM [Formatsystem.](/help/get-started/authoring.md#component-styling)
