---
title: Sling Context-Aware Configurations and Core Components
description: Core Components använder kontextmedvetna Sling-konfigurationer för vissa funktioner
translation-type: tm+mt
source-git-commit: 24a810ff634f8846881dfa0095e879476d0f16f0
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 0%

---


# Sling Context-Aware Configurations and Core Components {#sling-context-aware-configurations}

Kontextmedvetna konfigurationer är en funktion i Sling och är konfigurationer som är relaterade till en innehållsresurs eller ett resursträd och som utnyttjas av kärnkomponenterna för att tillåta platsomfattande konfigurationer.

## Sling Context-Aware Configurations {#context-aware-configurations}

Din plats kan behöva olika konfigurationer för olika webbplatsregioner, till exempel där vissa parametrar kan delas, vilket kräver arv för kapslade kontexter och globala reservvärden. Kontextmedvetna konfigurationer för att dela innehåll aktiverar detta.

Mer information om Sling-kontextmedvetna konfigurationer [finns i Apache-dokumentationen.](https://sling.apache.org/documentation/bundles/context-aware-configuration/context-aware-configuration.html)

## Använd i kärnkomponenterna {#core-components}

Ett antal grundkomponentfunktioner utnyttjar kontextmedvetna konfigurationer. Alla sådana konfigurationer finns under följande nod:

* `/conf/<my-site>/sling:configs/<my-configuration>`

Enskilda konfigurationer beror på den specifika komponenten eller funktionen. Funktioner för de kärnkomponenter som använder kontextmedvetna konfigurationer är:

* [PDF Viewer-komponent](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/pdfviewer/v1/pdfviewer#context-aware-config)
* [Adobe-klientdatalager](/help/developing/data-layer/overview.md#installation-activation)
* [Stöd för AMP](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)
