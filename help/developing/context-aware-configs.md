---
title: Sling Context-Aware Configurations and Core Components
description: Core Components använder kontextmedvetna Sling-konfigurationer för vissa funktioner
role: Architect, Developer, Admin
exl-id: d35210f7-a65d-4768-ab9e-f12ec406da2d
source-git-commit: b72defe1bbe6cb286730ac3f508f7d6c14b3fc33
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 0%

---

# Sling Context-Aware Configurations and Core Components {#sling-context-aware-configurations}

Kontextmedvetna konfigurationer är [Sling-funktionen](https://sling.apache.org/documentation/bundles/context-aware-configuration/context-aware-configuration.html). De är konfigurationer som är relaterade till en innehållsresurs eller ett resursträd och som utnyttjas av kärnkomponenterna för att tillåta platsomfattande konfigurationer.

## Sling Context-Aware Configurations {#context-aware-configurations}

Din plats kan behöva olika konfigurationer för olika webbplatsregioner, till exempel där vissa parametrar kan delas, vilket kräver arv för kapslade kontexter och globala reservvärden. AEM utnyttjar konfigurationer som är anpassade till Sling-kontext, vilket möjliggör detta.

Mer information om konfigurationer i AEM finns i [Mer information finns i dokumentationen för konfigurationer och Configuration Browser.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/configurations.html)

## Använd i kärnkomponenterna {#core-components}

Ett antal grundkomponentfunktioner utnyttjar kontextmedvetna konfigurationer. Alla sådana konfigurationer finns under följande nod:

* `/conf/<my-site>/sling:configs/<my-configuration>`

Enskilda konfigurationer beror på den specifika komponenten eller funktionen. Funktioner för de kärnkomponenter som använder kontextmedvetna konfigurationer är bland annat:

* [Sidkomponenten](https://github.com/adobe/aem-core-wcm-components/tree/main/content/src/content/jcr_root/apps/core/wcm/components/page/v3/page#loading-of-context-aware-cssjs) är beroende av sammanhangsberoende konfiguration vid återgivning `link`, `script` och `meta` -taggar.
* [PDF Viewer Component](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/pdfviewer/v1/pdfviewer#context-aware-config)
* [Adobe-klientdatalager](/help/developing/data-layer/overview.md#installation-activation)
* [Stöd för AMP](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)
