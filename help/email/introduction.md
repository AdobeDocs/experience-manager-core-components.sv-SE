---
title: Introduktion till viktiga e-postkomponenter
description: Skapa övertygande e-postinnehåll med flexibiliteten i E-postkärnkomponenterna och leverera det med kraften i Adobe Campaign.
role: Architect, Developer, Admin, User
exl-id: 0a411f28-bd6a-4bad-b473-6bc27c1d1055
source-git-commit: 6fbc781db555bc6abaed1d122a9a8756e3d53222
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 0%

---


# Introduktion till viktiga e-postkomponenter {#email-core-components-introduction}

Skapa övertygande e-postinnehåll med flexibiliteten i E-postkärnkomponenterna och leverera det med kraften i Adobe Campaign.

## Ökning {#overview}

E-postkärnkomponenterna är byggda på samma kraftfulla grund som kärnkomponenterna. De gör det enkelt och flexibelt att dra och släppa e-postinnehåll som sedan kan levereras till er målgrupp med hjälp av Adobe Campaign kraftfulla funktioner.

## Fördelar {#benefits}

E-post är en del av varumärkesupplevelsen och kundresan. Med e-postkärnkomponenterna kan författarna skapa e-postinnehåll inifrån AEM, som ger en enhetlig varumärkesupplevelse och därmed ökar innehållets hastighet.

* Precis som när du redigerar sidor med de centrala komponenterna gör e-postkomponenterna det möjligt för skribenterna att sammanställa e-postmeddelanden utan tekniska kunskaper samtidigt som de ser till att de följer riktlinjerna för varumärken.
* Möjligheten att återanvända resurser och innehåll uppmuntrar också författare att följa riktlinjer för varumärken och optimera processen för att skapa innehåll.

## Funktioner {#features}

* De centrala e-postkomponenterna är baserade på [kärnkomponenterna](/help/introduction.md) och stöder därför även [redigerbara mallar](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html) och [formatsystemet.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/style-system.html)
* Det finns [tio e-postoptimerade produktionsklara komponenter](#components) som kan användas för att skapa e-postinnehåll.
* De centrala e-postkomponenterna erbjuder avancerad personalisering tack vare infogningen av [Adobe Campaign-variabler](campaign-variables.md) i de flesta dialogrutefält.
* Den flexibla [segmenteringskomponenten](/help/email/components/segmentation.md) möjliggör avancerad segmentering av ditt innehåll.
* De centrala e-postkomponenterna ger optimala e-postanpassade HTML-utdata tack vare [CSS-formatets inliner,](https://github.com/adobe/aem-core-email-components/wiki/CSS-Styles-Inliner:-Technical-documentation) [HTML-attributets inliner,](https://github.com/adobe/aem-core-email-components/wiki/HTML-Inliner) och [HTML-sanpassaren.](https://github.com/adobe/aem-core-email-components/wiki/HTML-Sanitizing)
* Du kan skapa e-postinnehåll var som helst under `/content`.
* E-postkärnkomponenterna är [öppen källkod.](https://github.com/adobe/aem-core-email-components)

## Krav {#requirements}

E-postkärnkomponenterna har följande krav.

| AEM | Adobe Campaign | Kärnkomponenter |
|---|---|---|
| AEM 6.5.14.0+ eller AEM 6.5 LTS GA<br>On lokalt eller AMS | Adobe Campaign Classic<br>Adobe Campaign Standard | [Version 2.21.2](/help/versions.md)+ |

>[!NOTE]
>
>Eftersom Adobe Campaign-integreringar inte stöds i AEM as a Cloud Service stöds inte heller e-postkärnkomponenterna i AEM as a Cloud Service.

## E-postkomponenterna {#components}

Den aktuella versionen av E-postkärnkomponenterna innehåller följande komponenter.

* [Sida](components/page.md)
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

Se dokumentet [Använda E-postkärnkomponenter](using.md) för mer information om hur du installerar E-postkärnkomponenter.
