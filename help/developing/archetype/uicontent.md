---
title: ui.content Module för AEM Project Archetype
description: ui.content Module för AEM Project Archetype
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# ui.content Module för AEM Project Archetype {#uicontent-module}

Modul ui.content maven (`<src-directory>/<project>/ui.content`) innehåller baslinjeinnehåll och konfigurationer under `/content` och `/conf`. ui.content kompileras till ett AEM-paket ungefär som ui.apps. Den största skillnaden är att noderna som lagras i ui.content kan ändras direkt på AEM-instansen. Detta inkluderar sidor, DAM-resurser och redigerbara mallar. Modulen ui.content kan användas för att lagra exempelinnehåll för en ren instans och/eller för att skapa vissa baslinjekonfigurationer som ska hanteras i källkontrollen.

## filter.xml {#filter}

Filen `filter.xml` för modulen ui.content finns på `<src>/<project>/ui.content/src/main/content/META-INF/vault/filter.xml` och innehåller sökvägarna som ska inkluderas och installeras med paketet ui.content. Observera att ett `mode="merge"` attribut läggs till i sökvägen. Detta garanterar att konfigurationer som distribueras med en koddistribution inte automatiskt åsidosätter innehåll eller konfigurationer som har skapats direkt på AEM-instansen.

## ui.content/pom.xml

Modulen ui.content, liksom modulen ui.apps, använder plugin-programmet FileVault Package. Ui.content pom (`<src>/<project>/ui.content/pom.xml`) innehåller emellertid en extra konfigurationsegenskap som heter `acHandling`, inställd på `merge_preserve`. Detta ingår eftersom modulen ui.content innehåller åtkomstkontrollistor (ACL) som är behörigheter, som avgör vem som kan redigera mallarna. Egenskapen behövs för att dessa ACL:er ska kunna importeras till AEM `acHandling` .