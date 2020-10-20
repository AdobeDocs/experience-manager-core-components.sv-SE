---
title: Sling Context-Aware Configurations and Core Components
description: Core Components använder kontextmedvetna Sling-konfigurationer för vissa funktioner
translation-type: tm+mt
source-git-commit: 11e2c6da0fa93084b601437fd45fd65dd8d73231
workflow-type: tm+mt
source-wordcount: '194'
ht-degree: 0%

---


# Sling Context-Aware Configurations and Core Components {#sling-context-aware-configurations}

Kontextmedvetna konfigurationer är en funktion i Sling och är konfigurationer som är relaterade till en innehållsresurs eller ett resursträd och som utnyttjas av kärnkomponenterna för att tillåta platsomfattande konfigurationer.

## Sling Context-Aware Configurations {#context-aware-configurations}

Din plats kan behöva olika konfigurationer för olika webbplatsregioner, till exempel där vissa parametrar kan delas, vilket kräver arv för kapslade kontexter och globala reservvärden. AEM utnyttjar konfigurationer som är anpassade till Sling-kontext, vilket möjliggör detta.

Mer information om konfigurationer i AEM [finns i dokumentationen för konfigurationer och Configuration Browser.](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/developing/configurations.html)

## Använd i kärnkomponenterna {#core-components}

Ett antal grundkomponentfunktioner utnyttjar kontextmedvetna konfigurationer. Alla sådana konfigurationer finns under följande nod:

* `/conf/<my-site>/sling:configs/<my-configuration>`

Enskilda konfigurationer beror på den specifika komponenten eller funktionen. Funktioner för de kärnkomponenter som använder kontextmedvetna konfigurationer är:

* [PDF Viewer-komponent](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/pdfviewer/v1/pdfviewer#context-aware-config)
* [Adobe-klientdatalager](/help/developing/data-layer/overview.md#installation-activation)
* [Stöd för AMP](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)
