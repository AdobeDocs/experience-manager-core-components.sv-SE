---
title: Introduktion till viktiga e-postkomponenter
description: Skapa övertygande e-postinnehåll med flexibiliteten i E-postkärnkomponenterna och leverera det med kraften i Adobe Campaign.
role: Architect, Developer, Admin, User
hidefromtoc: true
index: false
source-git-commit: 8bebe3ca036557f3f7c6b8ec0e65d6d104d5ffae
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 1%

---


# Introduktion till viktiga e-postkomponenter {#email-core-components-introduction}

Skapa övertygande e-postinnehåll med flexibiliteten i E-postkärnkomponenterna och leverera det med kraften i Adobe Campaign.

## Översikt {#overview}

E-postkärnkomponenterna bygger på samma kraftfulla grund som kärnkomponenterna. De gör det enkelt och flexibelt att dra och släppa e-postinnehåll som sedan kan levereras till er målgrupp med hjälp av Adobe Campaign kraftfulla funktioner.

## Fördelar {#benefits}

E-post är en del av varumärkesupplevelsen och kundresan. Med e-postkärnkomponenterna kan författarna skapa e-postinnehåll inifrån AEM, vilket ger en enhetlig varumärkesupplevelse och därmed ökar innehållets hastighet.

* Precis som när du redigerar sidor med de centrala komponenterna gör e-postkomponenterna det möjligt för skribenterna att sammanställa e-postmeddelanden utan tekniska kunskaper samtidigt som de ser till att de följer riktlinjerna för varumärken.
* Möjligheten att återanvända resurser och innehåll uppmuntrar också författare att följa riktlinjer för varumärken och optimera processen för att skapa innehåll.

## Funktioner {#features}

* De centrala e-postkomponenterna är baserade på [Kärnkomponenter,](/help/introduction.md) och därför även [Redigerbara mallar](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html) och [Formatsystem.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/style-system.html)
* Det finns [tio e-postoptimerade produktionsklara komponenter](#components) för att skapa e-postinnehåll.
* De centrala e-postkomponenterna erbjuder avancerad personalisering tack vare infogning av Adobe Campaign-variabler i de flesta dialogrutefält.
* Den flexibla segmenteringskomponenten möjliggör avancerad segmentering av innehållet.
* De centrala e-postkomponenterna ger optimala e-postanpassade HTML-utdata tack vare [Inline för CSS-format,](https://github.com/adobe/aem-core-email-components/wiki/CSS-Styles-Inliner) [Inliner för HTML-attribut.](https://github.com/adobe/aem-core-email-components/wiki/HTML-Inliner) och [HTML saneringsföretaget.](https://github.com/adobe/aem-core-email-components/wiki/HTML-Sanitizer)
* Du kan skapa e-postinnehåll var som helst nedan `/content`.
* E-postkärnkomponenterna är [öppen källkod.](https://github.com/adobe/aem-core-email-components)

## Krav {#requirements}

E-postkärnkomponenterna har följande krav.

| AEM | Adobe Campaign | Kärnkomponenter |
|---|---|---|
| AEM 6.5.x.y (på plats eller i AMS) | Adobe Campaign Classic vX<br>eller<br>Adobe Campaign Standard | [Frigör x](/help/versions.md) eller högre |

>[!NOTE]
>
>Eftersom Adobe Campaign-integreringar inte stöds i AEM as a Cloud Service stöds inte heller E-postkärnkomponenterna i AEM as a Cloud Service.

## E-postkomponenterna {#components}

Den aktuella versionen av E-postkärnkomponenterna innehåller följande komponenter.

* [Sidan](components/page.md)
* [Behållare](components/container.md)
* [Titel](components/title.md)
* [Text](components/text.md)
* [Bild](components/image.md)
* [Knapp](components/button.md)
* [Teaser](components/teaser.md)
* [Experience Fragment](components/experience-fragment.md)
* [Innehållsfragment](components/content-fragment.md)
* [Segmentering](components/segmentation.md)

## Installation och användning {#installation-usage}

Se [Använda e-postkärnkomponenter](using.md) om du vill ha information om hur du installerar e-postkärnkomponenterna.
