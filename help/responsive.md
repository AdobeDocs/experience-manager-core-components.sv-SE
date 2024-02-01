---
title: Responsiv design av kärnkomponenterna
description: Lär dig mer om den responsiva designen av kärnkomponenterna och hur den kan påverka ditt projekt.
role: Architect, Developer, Admin, User
source-git-commit: d39fe0084522f67664203a026340b23d325c1883
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 0%

---


# Responsiv design av kärnkomponenterna {#responsive-design}

Alla kärnkomponenter är utformade för att vara fullt responsiva och ger en sömlös upplevelse på alla enheter. Det är viktigt att komma ihåg att vissa avancerade komponenter, till exempel [Carousel,](/help/components/carousel.md) [Tabbar,](/help/components/tabs.md) och [dragspelskomponenter,](/help/components/accordion.md) kan kräva särskild hänsyn inom ramen för genomförandeprojektet för att kunna vara lyhörd under alla förhållanden.

Med tanke på de många olika sätten som dessa komponenter kan uppvisa responsiva beteenden, och i Adobe åtagande att hålla kärnkomponenterna enkla att använda, lämnas ansvaret för att implementera detaljerade responsiva aspekter avsiktligt till projektet.

På smala skärmar kan till exempel Tabbar-komponenten anpassa sig genom att dela upp breda tabbar på nya rader, genom att tillåta vertikal rullning, genom att omforma tabbar till listrutor eller genom att använda ett dragspelsformat. På grund av den potentiella inverkan på prestanda som implementering av alla dessa beteenden skulle ge upphov till, kan [klientlibs](/help/developing/including-clientlibs.md#provided) är avsedda som en startpunkt för implementerare i stället för en heltäckande lösning.
