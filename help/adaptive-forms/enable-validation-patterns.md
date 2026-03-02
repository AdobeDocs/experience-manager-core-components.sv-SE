---
title: Aktivera och använda valideringsmönster för textindata i Adobe Experience Manager Adaptive Forms
description: Lär dig hur du konfigurerar mallprofiler för att visa valideringsmönster som telefonnummer, personnummer och postnummer och sedan använda dem i din adaptiva Forms.
hide: true
hidefromtoc: true
source-git-commit: 1ac3d987337f8279e762ab5357d32bb732dea0be
workflow-type: tm+mt
source-wordcount: '861'
ht-degree: 0%

---


# Aktivera och använda valideringsmönster för textindata i Adobe Experience Manager Adaptive Forms

## Ökning

I Adobe Experience Manager (Adobe Experience Manager) Forms styrs specifika valideringsformat (som personnummer, e-postadresser eller postkoder) för textindatakomponenter på mallpolicynivå. Den här guiden förklarar hur du:

1. Gå till mallredigeraren och konfigurera principen för textinmatningskomponenten så att valideringsmönster visas.
2. Skapa ett adaptivt formulär och tillämpa dessa valideringsmönster på en textindatakomponent.

## Förutsättningar

- Åtkomst till en Adobe Experience Manager-instans med Forms aktiverat.
- Behörigheter att redigera mallar (ingår vanligtvis i gruppen `template-authors`).
- Behörighet att skapa och redigera adaptiva Forms.

## Del 1: Aktivera valideringsmönster i mallen

>[!VIDEO](https://video.tv.adobe.com/v/3480390/)

### Steg 1: Gå till Mallkonsolen

1. På startskärmen i Adobe Experience Manager klickar du på **Verktyg** (hammikonen) i det vänstra sidofältet.
2. Navigera till **Allmänt > Mallar**.
3. Välj den mapp som innehåller dina projektmallar (till exempel Core Components Examples).
4. Leta reda på den mall som du vill ändra (till exempel AF Blank) och markera den.
5. Klicka på **Redigera** (eller öppna mallen direkt).

### Steg 2: Gå till komponentstrukturen

1. Se till att du är i vyn **Struktur** (välj Struktur i listrutan Läge i det övre högra hörnet om det behövs).
2. Leta reda på **huvudbehållaren för layout** eller den behållare där textinmatningskomponenten är tillåten.
3. Klicka på behållaren för att visa listan över tillåtna komponenter.
4. Leta reda på komponenten **Adaptiv textruta** i listan.
5. Klicka på ikonen **Policy** (som representeras av en fil-/byråsymbol) bredvid komponentnamnet.

### Steg 3: Konfigurera principen för textinmatningskomponenten

1. Klicka på fliken **Format** till höger i fönstret i principredigeraren.
2. En lista med tillgängliga valideringsmönster visas. Markera rutorna för de format som du vill aktivera:
   - Telefonnummer
   - Personnummer
   - Alfanumerisk e-post
   - Postnummer

### Steg 4: Definiera och spara profilen

1. Växla tillbaka till fliken **Princip** (eller kontrollera vänsterinställningarna).
2. I fältet **Principtitel** anger du ett tydligt namn (till exempel `new-textinput-default-policy`).
3. Klicka på ikonen **Klar** (bockmarkering) i det övre högra hörnet för att spara ändringarna.

## Del 2: Skapa ett formulär och använda valideringsmönster

Nu när valideringsmönster är aktiverade i mallen kan du skapa ett adaptivt formulär och tillämpa dem på textinmatningskomponenter.

>[!VIDEO](https://video.tv.adobe.com/v/3480391/)

### Steg 1: Skapa ett anpassat formulär

1. Navigera till gränssnittet **Forms &amp; Documents**.
2. Klicka på knappen **Skapa** längst upp till höger.
3. Välj **Anpassat formulär** i listrutan.
4. Välj den mall där du aktiverade valideringsmönstren (till exempel **Tom**) och klicka på **Nästa**.
5. På skärmen Lägg till egenskaper:
   - Ange en **titel** för formuläret (till exempel &quot;testPolicy&quot;). Fältet **Namn** fylls i automatiskt baserat på titeln.
   - Kontrollera att rätt **temaklientbibliotek** har valts (till exempel `adaptiveform.theme.canvas3`).
6. Klicka på **Skapa**. Ett meddelande om att åtgärden lyckades visas.
7. Klicka på **Redigera** för att öppna formuläret i redigeraren.

### Steg 2: Lägg till en textindatakomponent

1. Leta reda på webbläsaren **Komponenter** i den vänstra sidofältet i formulärredigeraren.
2. Använd sökfältet för att hitta komponenten **Adaptiv textruta** för formulär. När du skriver&quot;text&quot; filtreras listan.
3. Klicka på och dra komponenten **Adaptiv textruta** till huvudarbetsytan.

### Steg 3: Konfigurera komponentformatering

1. Klicka på den nya **textinmatningskomponenten** för att markera den.
2. Klicka på ikonen **Konfigurera** (representeras av en skiftnyckel) i verktygsfältet som visas ovanför komponenten.
3. Gå till fliken **Format** i dialogrutan Egenskaper.
4. Leta upp listrutan **Typ** och ändra urvalet till **Telefonnummer** (eller något annat aktiverat format).

### Steg 4: Konfigurera dataverifiering

1. Gå till fliken **Validering** medan du fortfarande är i dialogrutan för komponentkonfiguration.
2. Leta reda på avsnittet **Valideringsmönster**.
3. Klicka på listrutan **Typ**.
4. Välj **Telefonnummer** i listan över valideringsmönster. Detta garanterar att formuläret genererar ett fel om användaren matar in text som inte matchar ett giltigt telefonnummerformat.
5. Klicka på ikonen **Klar** (bockmarkering) i dialogrutans övre högra hörn för att spara ändringarna.

## Verifiering

Så här kontrollerar du att valideringsmönster fungerar som de ska:

1. Förhandsgranska formuläret i redigeraren.
2. Ange testdata i komponenten **Textindata**.
3. Bekräfta att:
   - De aktiverade valideringsmönstren visas på komponentens flikar Format och Validering.
   - Ogiltiga indata utlöser lämpliga felmeddelanden.
   - Giltiga indata accepteras utan fel.

## Felsökning

- **Utgåva:** Valideringsmönstren visas inte i formulärkomponenten.
   - **Lösning:** Kontrollera att mallprincipen har sparats korrekt och att du använder rätt mall när du skapar formuläret.

- **Problem:** Det går inte att komma åt mallredigeraren.
   - **Lösning:** Kontrollera att du har behörighet att redigera mallar (medlemskap i gruppen `template-authors`).

- **Problem:** Textindatakomponenten verifierar inte indata korrekt.
   - **Lösning:** Kontrollera inställningarna för valideringsmönster på komponentens valideringsflik och se till att rätt mönster är valt.

## Nästa steg

När du har aktiverat och använt valideringsmönster för textinmatning i din Adobe Experience Manager Adaptive Forms:

- Konfigurera ytterligare valideringsmönster för andra datatyper.
- Utforska andra komponentprofiler för att anpassa formulärbeteenden.
- Ställ in formulärhantering och databearbetningslogik.
