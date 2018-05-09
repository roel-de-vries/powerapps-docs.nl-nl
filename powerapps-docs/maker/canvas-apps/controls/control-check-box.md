---
title: 'Besturingselement voor keuzelijst met invoervak: naslag | Microsoft Docs'
description: Informatie, waaronder eigenschappen en voorbeelden, over het besturingselement Selectievakje
services: ''
suite: powerapps
documentationcenter: na
author: fikaradz
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/25/2016
ms.author: fikaradz
ms.openlocfilehash: 9b51e1cf59c5df163027e8768c21d6ae544d7ba1
ms.sourcegitcommit: 4710a56d308efe67fe60a7688143e61f5e5f2b44
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="check-box-control-in-powerapps"></a>Besturingselement voor selectievakje in PowerApps
Een besturingselement dat de gebruiker kan in- of uitschakelen om de waarde ervan in te stellen op **true** of **false**.

## <a name="description"></a>Beschrijving
De gebruiker kan een Booleaanse waarde opgeven met behulp van dit vertrouwde besturingselement, dat al tientallen jaren wordt gebruikt in grafische gebruikersinterfaces.

## <a name="key-properties"></a>Belangrijkste eigenschappen
**[Default](properties-core.md)**: de aanvankelijke waarde van een besturingselement voordat deze door de gebruiker wordt gewijzigd.

**[Text](properties-core.md)**: de tekst die wordt weergegeven in een besturingselement of die de gebruiker in een besturingselement typt.

**[Value](properties-core.md)**: de waarde van een besturingselement voor invoer.

## <a name="additional-properties"></a>Aanvullende eigenschappen
**[BorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement.

**[BorderStyle](properties-color-border.md)**: hiermee wordt aangegeven of de rand van een besturingselement **effen**, **onderbroken** of **gestippeld** is, of dat er **geen** rand is.

**[BorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement.

**CheckboxBackgroundFill**: de achtergrondkleur van het vakje rond het vinkje in een selectievakje.

**CheckboxBorderColor**: de kleur van de rand rondom het vinkje in een selectievakje.

**CheckboxSize**: de breedte en hoogte van het vakje rond het vinkje in een selectievakje.

**CheckmarkFill**: de kleur van het vinkje in een selectievakje.

**[Color](properties-color-border.md)**: de kleur van de tekst in een besturingselement.

**[DisplayMode](properties-core.md)**: of invoer van de gebruiker is toegestaan (**Bewerken**), alleen gegevens worden weergegeven (**Weergeven**) of is uitgeschakeld (**Uitgeschakeld**).

**[DisabledBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**[DisabledColor](properties-color-border.md)**: de kleur van tekst in een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**[DisabledFill](properties-color-border.md)**: de achtergrondkleur van een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**[Fill](properties-color-border.md)**: de achtergrondkleur van een besturingselement.

**[FocusedBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de focus op het besturingselement is.

**[FocusedBorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement wanneer de focus op het besturingselement is.

**[Font](properties-text.md)**: de naam van de lettertypefamilie waarin de tekst wordt weergegeven.

**[FontWeight](properties-text.md)**: het gewicht van de tekst in een besturingselement: **Bold**, **Semibold**, **Normal** of **Lighter**.

**[Height](properties-size-location.md)** : de afstand tussen de boven- en onderrand van een besturingselement.

**[HoverBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de gebruiker de muisaanwijzer op dat besturingselement plaatst.

**[HoverColor](properties-color-border.md)**: de kleur van de tekst in een besturingselement wanneer de gebruiker de muisaanwijzer op de tekst plaatst.

**[HoverFill](properties-color-border.md)**: de achtergrondkleur van een besturingselement wanneer de gebruiker de muisaanwijzer op de achtergrond plaatst.

**[Italic](properties-text.md)**: hiermee wordt aangegeven of de tekst in een besturingselement cursief is.

**OnCheck**: hoe een app reageert wanneer de waarde van een selectievakje of wisselknop in **true** verandert.

**[OnSelect](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker op een besturingselement tikt of klikt.

**OnUncheck**: de manier waarop de app reageert wanneer de waarde van een selectievakje of wisselknop in **false** verandert.

**[PaddingBottom](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de onderrand van het besturingselement.

**[PaddingLeft](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de linkerrand van het besturingselement.

**[PaddingRight](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de rechterrand van het besturingselement.

**[PaddingTop](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de bovenrand van het besturingselement.

**[PressedBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**[PressedColor](properties-color-border.md)**: de kleur van tekst in een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**[PressedFill](properties-color-border.md)**: de achtergrondkleur van een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**[Reset](properties-core.md)**: of een besturingselement wordt teruggezet op de standaardwaarde.

**[Size](properties-text.md)**: de tekengrootte van de tekst die in een besturingselement wordt weergegeven.

**[Strikethrough](properties-text.md)**: hiermee wordt aangegeven of een streep door de tekst van een besturingselement wordt weergegeven.

**[TabIndex](properties-accessibility.md)**: de navigatievolgorde op het toetsenbord ten opzichte van andere besturingselementen.

**[Tooltip](properties-core.md)**: beschrijvende tekst die wordt weergegeven wanneer de gebruiker een besturingselement aanwijst.

**[Underline](properties-text.md)**: hiermee wordt aangegeven of onder de tekst in een besturingselement een streep wordt weergegeven.

**[VerticalAlign](properties-text.md)**: de locatie van de tekst in een besturingselement in verhouding tot het verticale midden van dat besturingselement.

**[Visible](properties-core.md)**: hiermee wordt aangegeven of een besturingselement zichtbaar of verborgen is.

**[Width](properties-size-location.md)**: de afstand tussen de linker- en rechterrand van een besturingselement.

**[X](properties-size-location.md)**: de afstand tussen de linkerrand van een besturingselement en de linkerrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

**[Y](properties-size-location.md)**: de afstand tussen de bovenrand van een besturingselement en de bovenrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

## <a name="related-functions"></a>Verwante functies
[**If**( *Voorwaarde*, *Resultaat* )](../functions/function-if.md)

## <a name="example"></a>Voorbeeld
1. Voeg een besturingselement **Selectievakje** toe, geef het de naam **chkReserveren** en stel de eigenschap **[Tekst](properties-core.md)** ervan in op **Nu reserveren**.
   
    Weet u niet hoe u [een besturingselement kunt toevoegen, een naam kunt geven of kunt configureren](../add-configure-controls.md)?
2. Voeg een besturingselement  **[Datumkiezer](control-date-picker.md)** toe en stel de eigenschap **[Visible](properties-core.md)** ervan in op deze formule:
   <br>**If(chkReserveren.Value = true, true)**
   
    Wilt u meer informatie over de functie **[If](../functions/function-if.md)** of [andere functies](../formula-reference.md)?
3. Druk op F5, klik of tik op **chkReserveren** om de eigenschap **[Value](properties-core.md)** in te stellen op **true** en klik of tik vervolgens nogmaals op **chkReserveren** om de eigenschap **[Value](properties-core.md)** in te stellen op **false**.
   
    Het besturingselement **[Datumkiezer](control-date-picker.md)** wordt weergegeven wanneer de eigenschap **[Value](properties-core.md)** van **chkReserveren** de waarde **true** heeft, maar niet wanneer de waarde **false** is.
4. Druk op Esc om terug te gaan naar de standaardwerkruimte.


## <a name="accessibility-guidelines"></a>Richtlijnen voor toegankelijkheid
### <a name="color-contrast"></a>Kleurcontrast
Er moet voldoende kleurcontrast zijn tussen:
* **CheckmarkFill** en **CheckboxBackgroundFill**
* **CheckboxBackgroundFill** en **[Fill](properties-color-border.md)**
* **CheckboxBackgroundFill** en **[PressedFill](properties-color-border.md)**
* **CheckboxBackgroundFill** en **[HoverFill](properties-color-border.md)**

Dit komt bovenop de standaardvereisten voor kleurcontrast.

### <a name="screen-reader-support"></a>Ondersteuning voor schermlezers
* **[Text](properties-core.md)** moet aanwezig zijn.

### <a name="keyboard-support"></a>Ondersteuning voor toetsenbord
* **[TabIndex](properties-accessibility.md)** moet nul of groter zijn, zodat toetsenbordgebruikers ernaartoe kunnen navigeren.
* De focusindicatoren moeten duidelijk zichtbaar zijn. Gebruik hiervoor **[FocusedBorderColor](properties-color-border.md)** en **[FocusedBorderThickness](properties-color-border.md)**.
 