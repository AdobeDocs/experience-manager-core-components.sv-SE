---
title: Responsiv design av kärnkomponenterna
description: Lär dig mer om den responsiva designen av kärnkomponenterna och hur den kan påverka ditt projekt.
role: Architect, Developer, Admin, User
exl-id: c0eff174-6803-4b44-aeb1-eae3bc8a36ea
source-git-commit: 5f49fb45869d1721e16a787a2c6ff927b6ad49fe
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 0%

---

# Responsiv design av kärnkomponenterna {#responsive-design}

Alla kärnkomponenter är utformade för att vara fullt responsiva och ger en sömlös upplevelse på alla enheter. Det är viktigt att notera att vissa avancerade komponenter, som till exempel [Carousel,](/help/components/carousel.md) [Tabs,](/help/components/tabs.md) och [dragspelskomponenter,](/help/components/accordion.md), kan kräva särskild hänsyn i det implementerande projektet för att kunna behålla svarstiderna under alla förhållanden.

Med tanke på de många olika sätten som dessa komponenter kan uppvisa responsiva beteenden, och i Adobe åtagande att hålla kärnkomponenterna enkla att använda, lämnas ansvaret för att implementera detaljerade responsiva aspekter avsiktligt till projektet.

På smala skärmar kan till exempel Tabbar-komponenten anpassa sig genom att dela upp breda tabbar på nya rader, genom att tillåta vertikal rullning, genom att omforma tabbar till listrutor eller genom att använda ett dragspelsformat. På grund av den potentiella inverkan på prestanda som implementering av alla dessa beteenden skulle ge, är [clientlibs](/help/developing/including-clientlibs.md#provided) avsedd som startpunkt för implementerare i stället för en fullständig lösning.
