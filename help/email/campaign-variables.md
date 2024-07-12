---
title: Kampanjvariabler
description: Använd kampanjvariabler som platshållare för att skapa personaliserat e-postinnehåll.
role: Architect, Developer, Admin, User
exl-id: 124ff5bf-6612-4baf-b0ff-6b1a95b455c1
source-git-commit: 33976c0e745ad091a142109f70541f01a31edc5b
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 0%

---


# Kampanjvariabler {#campaign-variables}

Använd kampanjvariabler för att skapa personaliserat e-postinnehåll. Kampanjvariabler fungerar som platshållare för Adobe Campaign-värden som du kan infoga i ditt e-postinnehåll. När innehållet skickas via Adobe Campaign ersätter Campaign dessa variabler med mottagarens personaliserade innehåll.

## Användning {#usage}

Med e-postkärnkomponenterna blir kampanjvariablerna enkelt tillgängliga via personaliseringsknappar bredvid vanliga textfält. När du trycker på det visas en dialogruta där du kan välja ett anpassningsfält.

Listan med tillgängliga anpassningsfält synkroniseras med din Adobe Campaign-instans. Fälten hanteras i Adobe Campaign i schemat `nms:seedMember`. Alla fält i `nms:seedMember` måste också finnas i mottagartabellen.

## Välj Adobe Campaign Variable Dialog {#dialog}

Dialogrutan Välj Adobe Campaign-variabel är tillgänglig i många redigeringsdialogrutor för e-postkärnkomponenter. Om du vill använda den klickar du på ikonen **Välj Adobe Campaign-variabel** bredvid det aktuella fältet. Den här ikonen kan ha två former.

![Adobe Campaign-knapp](/help/email/assets/campaign-button.png)
![Välj Adobe Campaign-variabelikon ](/help/email/assets/select-adobe-campaign-variable-icon.png)

Om du klickar på båda ikonerna öppnas dialogrutan **Välj Adobe Campaign-variabel**.

![Dialogrutan Välj Adobe Campaign-variabel](assets/select-campaign-variable-dialog.png)

Använd kolumnvyn för att hitta variabeln som du vill infoga. Om du klickar på en nod i en kolumn visas dess underordnade noder i en ny kolumn till höger. På så sätt kan du navigera i variabelinnehållsstrukturen.

Markera variabeln som du vill infoga och klicka sedan på bockmarkeringen i dialogrutans övre högra hörn.

![Adobe Campaign-variabel vald](assets/select-campaign-variable-dialog-selected.png)

Variabeln infogas sedan i fältet i redigeringsdialogrutan för e-postkärnkomponenten.

![Kampanjvariabel infogad i redigeringsdialogrutan](assets/campaign-variable.png)

Klicka på X längst upp till vänster i dialogrutan när som helst för att avbryta och stänga dialogrutan.
