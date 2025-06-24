---
title: Adaptiv Forms Core Component - Review Component
description: Använda eller anpassa den adaptiva Forms Review Core-komponenten.
role: Architect, Developer, Admin, User
hide: true
hidefromtoc: true
exl-id: acd230ed-284b-4df2-98e0-a0090cd73611
source-git-commit: 6725784bd4c94d433c91d6bd65d14d03cbefd954
workflow-type: tm+mt
source-wordcount: '742'
ht-degree: 0%

---


# Granskningskomponent

Med Review Component in Adaptive Forms kan man granska och verifiera den information man angett innan man skickar in blanketten. Det fungerar som en sammanfattningssida och ger en skrivskyddad vy över alla fält och deras värden i ett strukturerat och användarvänligt format. Med den här funktionen kan användare identifiera och korrigera fel och utelämnanden innan de skickar in formuläret, vilket förbättrar den övergripande formulärupplevelsen. Genom att klicka på redigeringsikonen kan de ändra den angivna informationen innan formuläret skickas.

{{traditional-aem}}

**Exempel**

![Granska komponent](/help/adaptive-forms/assets/review-component.png){width=50%, align=center}

## Användning

Nedan följer skälen till att du använder komponenten Review i ett adaptivt format:

- **Förbättrad datakvalitet**: Med Review Component kan användare granska alla data de har angett innan de skickas. Det minskar risken för fel eller utelämnanden och säkerställer att inlämnade data är korrekta.
- **Förbättrad användarupplevelse**: Användarna får en tydlig och ordnad sammanfattning av all information de fyllt i, vilket ger dem förtroende för att formuläret är fullständigt och korrekt innan det skickas in, vilket förbättrar den övergripande upplevelsen.
- **Felidentifiering och korrigering**: Det går att redigera information på panelnivå eller fältnivå så att användare kan korrigera misstag utan att gå tillbaka mellan flera flikar. Om du klickar på ikonen **Redigera** bredvid en panel eller ett fält är det enkelt att gå tillbaka och åtgärda eventuella problem.
- **Ökat användarförtroende**: Användarna kan granska de data som anges och försäkra dem om att informationen de skickar är korrekt, vilket leder till färre inskickningsfel och större förtroende för formulärets funktioner.
- **Förhindra oavsiktliga överföringar**: Användare klickar ofta på **Skicka** utan att granska all information. Komponenten **Review** ger dem en sista chans att verifiera sina data, vilket minskar sannolikheten för oavsiktliga överföringar.


## Teknisk information {#technical-details}

Hämta den senaste informationen om den adaptiva Forms Review Core-komponenten i den tekniska dokumentationen för [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/textinput/v1/textinput). Mer information om hur du utvecklar kärnkomponenter finns i [dokumentationen för kärnkomponentutvecklare](/help/developing/overview.md).

## Konfigurera dialogruta {#configure-dialog}

Du kan enkelt anpassa upplevelsen för besökare med dialogrutan Konfigurera för en smidig användarupplevelse.

![Konfigurera dialogruta](/help/adaptive-forms/assets/review-component-configure-dialog.png)

- **Namn** - Du kan enkelt identifiera en formulärkomponent med dess unika namn både i formuläret och i regelredigeraren, men namnet får inte innehålla blanksteg eller specialtecken.

- **Titel** - Med titeln kan du enkelt identifiera en komponent i ett formulär. Som standard visas titeln ovanpå komponenten. Om du inte lägger till en titel visas komponentens namn i stället för rubriktexten.
- **Dölj titel** - Välj alternativet för att dölja komponentens titel.
- **Aktivera redigeringslägesåtgärder för** - Med alternativen **Aktivera redigeringslägesåtgärder för** kan användare ändra den angivna informationen. Användarna kan redigera informationen antingen på fältnivå eller panelnivå.
   - När användare väljer alternativet **Fält** kan de redigera enskilda formulärfält under granskningen.
   - När användare väljer alternativet **Panel** kan de redigera alla fält i ett visst avsnitt (panelen).
   - När användare väljer alternativet **Fält och panel** kan de klicka på redigeringsikonen bredvid ett fält för att ändra specifik information eller bredvid en panel för att redigera alla fält på den panelen.
   - När användare väljer alternativet **Inget** kan de redigera alla fält och paneler i hela formuläret.

  Som standard är alternativet **Panel** markerat.

- **Länkpaneler** - Med alternativet **Länkpaneler** kan användarna välja paneler för granskning. När panelerna är länkade kan användarna granska den angivna informationen på de valda panelerna och ändra den innan de skickas.

## Usecase

Ta ett exempel på ett **låneansökningsformulär** som består av fyra flikar där varje flik samlar in specifik information om användaren:

- **Personuppgifter**: Samlar in användarens grundläggande personliga information, som namn, födelsedatum, kontaktinformation och adress.

- **Lånedetaljer**: Samlar in information om lånet, inklusive typ av lån, önskat belopp, återbetalningsperiod och automatiskt beräknade fält som ränta och månatlig EMI.

- **Ytterligare dokument**: Tillåter användaren att överföra nödvändiga dokument, som ID-bevis, adressbevis och inkomstbevis. Den innehåller även en kryssruta för att bekräfta att du godkänner villkoren.

- **Granska och skicka formulär**: Innehåller en granskningskomponent som sammanfattar alla indata från föregående flikar. Användarna kan verifiera och redigera sina data innan de skickar in formuläret. På den här fliken finns även knappen **Skicka** för att skicka programmet.

I videon nedan visas hur du konfigurerar komponenten **Review** så att användaren kan redigera information på ett flexibelt sätt:

## Relaterade artiklar {#related-articles}

{{more-like-this}}

## Se även {#see-also}

{{see-also}}
