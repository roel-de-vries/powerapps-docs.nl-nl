---
title: 'Besturingselement voor wisselknop: naslag | Microsoft Docs'
description: Informatie, waaronder eigenschappen en voorbeelden, over het besturingselement Wisselknop
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/25/2016
ms.author: fikaradz
ms.openlocfilehash: a2361e2572d62ca4a2574cd668ba0f1834d04ab9
ms.sourcegitcommit: 0f6d7bb9e524202c065b9a7ef92a7f54bdc4bc7c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/07/2018
ms.locfileid: "39022445"
---
# <a name="toggle-control-in-powerapps"></a>Besturingselement voor wisselknop in PowerApps
Een besturingselement dat de gebruiker in- of uit kan schakelen door het verplaatsen van een greep.

## <a name="description"></a>Beschrijving
Een wisselknop is een besturingselement dat is ontworpen voor recente gebruikersinterfaces, maar gedraagt zich op dezelfde manier als een selectievakje.

## <a name="key-properties"></a>Belangrijkste eigenschappen
**[Default](properties-core.md)**: de aanvankelijke waarde van een besturingselement voordat deze door de gebruiker wordt gewijzigd.

**[Value](properties-core.md)**: de waarde van een besturingselement voor invoer.

## <a name="additional-properties"></a>Aanvullende eigenschappen
**[AccessibleLabel](properties-accessibility.md)**: label voor schermlezers.

**[BorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement.

**[BorderStyle](properties-color-border.md)**: hiermee wordt aangegeven of de rand van een besturingselement **effen**, **onderbroken** of **gestippeld** is, of dat er **geen** rand is.

**[BorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement.

**[DisplayMode](properties-core.md)**: of invoer van de gebruiker is toegestaan (**Bewerken**), alleen gegevens worden weergegeven (**Weergeven**) of is uitgeschakeld (**Uitgeschakeld**).

**[DisabledBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**FalseFill**: de opvulkleur bij wisselen wanneer de wisselknop is uitgeschakeld.

**FalseHoverFill**: de opvulkleur van de muisaanwijzer bij wisselen wanneer de wisselknop is uitgeschakeld.

**FalseTekst**: de tekst die wordt weergegeven wanneer de wisselknop is uitgeschakeld.

**[Fill](properties-color-border.md)**: de achtergrondkleur van een besturingselement.

**[FocusedBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de focus op het besturingselement is.

**[FocusedBorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement wanneer de focus op het besturingselement is.

**HandleFill**: de opvulkleur van de greep van de wisselknop.

**[Height](properties-size-location.md)** : de afstand tussen de boven- en onderrand van een besturingselement.

**[HoverBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de gebruiker de muisaanwijzer op dat besturingselement plaatst.

**[OnChange](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker de waarde van een besturingselement wijzigt (bijvoorbeeld door een schuifregelaar aan te passen).

**OnCheck**: hoe een app reageert wanneer de waarde van een selectievakje of wisselknop in **true** verandert.

**[OnSelect](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker op een besturingselement tikt of klikt.

**OnUncheck**: de manier waarop de app reageert wanneer de waarde van een selectievakje of wisselknop in **false** verandert.

**[PressedBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**RailFill**: de achtergrondkleur van de rechthoek in een wisselknop als de waarde daarvan **false** is, of de kleur van de lijn, rechts van de schuifknop van een schuifregelaar.

**RailHoverFill**: als u de muis boven een wisselknop of schuifregelaar houdt, is dit de achtergrondkleur van de rechthoek in een wisselknop als de waarde daarvan **false** is, of de kleur van de lijn, rechts van de schuifknop van een schuifregelaar.

**[Reset](properties-core.md)**: of een besturingselement wordt teruggezet op de standaardwaarde.

**ShowLabel**: geeft aan of een tekstlabel moet worden weergegeven naast het besturingselement van de wisselknop.

**[TabIndex](properties-accessibility.md)**: de navigatievolgorde op het toetsenbord ten opzichte van andere besturingselementen.

**TextPosition**: geeft aan of het label links of rechts moet worden weergegeven naast het besturingselement van de wisselknop.

**[Tooltip](properties-core.md)**: beschrijvende tekst die wordt weergegeven wanneer de gebruiker een besturingselement aanwijst.

**TrueFill**: de opvulkleur bij wisselen wanneer de wisselknop is ingeschakeld.

**TrueHoverFill**: de opvulkleur van de muisaanwijzer bij wisselen wanneer de wisselknop is ingeschakeld.

**TrueTekst**: de tekst die wordt weergegeven wanneer de wisselknop is ingeschakeld.

**ValueFill**: de achtergrondkleur van de rechthoek in een wisselknop als de waarde daarvan **true** is, of de kleur van de lijn, links van de schuifknop van een schuifregelaar.

**ValueHoverFill**: als u de muisaanwijzer boven een wisselknop of schuifregelaar houdt, is dit de achtergrondkleur van de rechthoek in een wisselknop als de waarde daarvan **true** is, of de kleur van de lijn, links van de schuifknop van een schuifregelaar.

**[Visible](properties-core.md)**: hiermee wordt aangegeven of een besturingselement zichtbaar of verborgen is.

**[Width](properties-size-location.md)**: de afstand tussen de linker- en rechterrand van een besturingselement.

**[X](properties-size-location.md)**: de afstand tussen de linkerrand van een besturingselement en de linkerrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

**[Y](properties-size-location.md)**: de afstand tussen de bovenrand van een besturingselement en de bovenrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

## <a name="related-functions"></a>Verwante functies
[**If**( *Voorwaarde*, *Resultaat* )](../functions/function-if.md)

## <a name="example"></a>Voorbeeld
1. Voeg een wisselknop toe en geef deze de naam **Ledenkorting**.

    Weet u niet hoe u [een besturingselement kunt toevoegen, een naam kunt geven of kunt configureren](../add-configure-controls.md)?
2. Voeg een label toe en stel de eigenschap **[Text](properties-core.md)** in op deze formule:
   <br>**If(Ledenkorting.Value = true, "Prijs: € 75", "Prijs: € 100")**

    Wilt u meer informatie over de functie **[If](../functions/function-if.md)** of [andere functies](../formula-reference.md)?
3. Druk op F5 en wijzig de waarde van **Ledenkorting**.

    In het label ziet u een andere prijs, afhankelijk van of **Ledenkorting** is in- of uitgeschakeld.
4. Druk op Esc om terug te gaan naar de standaardwerkruimte.


## <a name="accessibility-guidelines"></a>Richtlijnen voor toegankelijkheid
### <a name="color-contrast"></a>Kleurcontrast
Er moet voldoende kleurcontrast zijn tussen:
* **HandleFill** en **FalseFill**
* **HandleFill** en **FalseHoverFill**
* **HandleFill** en **TrueFill**
* **HandleFill** en **TrueHoverFill**
* **FalseFill** en de kleur buiten het besturingselement
* **FalseHoverFill** en de kleur buiten het besturingselement
* **TrueFill** en de kleur buiten het besturingselement
* **TrueHoverFill** en de kleur buiten het besturingselement

Dit komt bovenop de [standaardvereisten voor kleurcontrast](../accessible-apps-color.md).

### <a name="screen-reader-support"></a>Ondersteuning voor schermlezers
* **[AccessibleLabel](properties-accessibility.md)** moet aanwezig zijn.
* **FalseText** moet aanwezig zijn.
* **TrueText** moet aanwezig zijn.

### <a name="low-vision-support"></a>Ondersteuning voor gebruikers met beperkt gezichtsvermogen
* U kunt **ShowLabel** instellen op **true**, zodat gebruikers snel de waarde van de wisselknop kunnen bepalen.

### <a name="keyboard-support"></a>Ondersteuning voor toetsenbord
* **[TabIndex](properties-accessibility.md)** moet nul of groter zijn, zodat toetsenbordgebruikers ernaartoe kunnen navigeren.
* De focusindicatoren moeten duidelijk zichtbaar zijn. Gebruik hiervoor **[FocusedBorderColor](properties-color-border.md)** en **[FocusedBorderThickness](properties-color-border.md)**.
