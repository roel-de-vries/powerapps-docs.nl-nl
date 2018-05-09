---
title: 'Besturingselement voor keuzerondje: naslag | Microsoft Docs'
description: Informatie, waaronder eigenschappen en voorbeelden, over het besturingselement Keuzerondje
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
ms.openlocfilehash: f28247ab3fce610571e2d5c27106bcf15c00cc8b
ms.sourcegitcommit: 4710a56d308efe67fe60a7688143e61f5e5f2b44
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="radio-control-in-powerapps"></a>Besturingselement voor keuzerondje in PowerApps
Een lijst met alle beschikbare opties, maar de gebruiker kan maar één optie selecteren.

## <a name="description"></a>Beschrijving
Een besturingselement **Keuzerondje**, inmiddels al tientallen jaren bekend bij veel gebruikers, kan het beste worden gebruikt met een paar opties die elkaar wederzijds uitsluiten.

## <a name="key-properties"></a>Belangrijkste eigenschappen
**[Default](properties-core.md)**: de aanvankelijke waarde van een besturingselement voordat deze door de gebruiker wordt gewijzigd.

**[Items](properties-core.md)**: de gegevensbron die wordt weergegeven in een besturingselement zoals een galerie, een lijst of een grafiek.

[!INCLUDE [long-items](../../../includes/long-items.md)]

**[Value](properties-core.md)**: de waarde van een besturingselement voor invoer.

## <a name="all-properties"></a>Alle eigenschappen
**[Align](properties-text.md)**: de locatie van tekst in verhouding tot het horizontale midden van het besturingselement.

**[BorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement.

**[BorderStyle](properties-color-border.md)**: hiermee wordt aangegeven of de rand van een besturingselement **effen**, **onderbroken** of **gestippeld** is, of dat er **geen** rand is.

**[BorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement.

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

**[HoverColor](properties-color-border.md)**: de kleur van de tekst in een besturingselement wanneer de gebruiker de muisaanwijzer op de tekst plaatst.

**[HoverFill](properties-color-border.md)**: de achtergrondkleur van een besturingselement wanneer de gebruiker de muisaanwijzer op de achtergrond plaatst.

**[Italic](properties-text.md)**: hiermee wordt aangegeven of de tekst in een besturingselement cursief is.

**[LineHeight](properties-text.md)**: de afstand tussen bijvoorbeeld regels tekst of items in een lijst.

**[OnChange](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker de waarde van een besturingselement wijzigt (bijvoorbeeld door een schuifregelaar aan te passen).

**[OnSelect](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker op een besturingselement tikt of klikt.

**[PaddingBottom](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de onderrand van het besturingselement.

**[PaddingLeft](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de linkerrand van het besturingselement.

**[PaddingRight](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de rechterrand van het besturingselement.

**[PaddingTop](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de bovenrand van het besturingselement.

**[PressedColor](properties-color-border.md)**: de kleur van tekst in een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**[PressedFill](properties-color-border.md)**: de achtergrondkleur van een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**RadioBackgroundFill**: de achtergrondkleur van de cirkels in een keuzerondje.

**RadioBorderColor**: de kleur van de cirkel voor elke optie in een keuzerondje.

**RadioSelectionFill**: de kleur die wordt weergegeven in de cirkel van de geselecteerde optie in een keuzerondje.

**RadioSize**: de diameter van de cirkels in een keuzerondje.

**[Reset](properties-core.md)**: of een besturingselement wordt teruggezet op de standaardwaarde.

**[Size](properties-text.md)**: de tekengrootte van de tekst die in een besturingselement wordt weergegeven.

**[Strikethrough](properties-text.md)**: hiermee wordt aangegeven of een streep door de tekst van een besturingselement wordt weergegeven.

**[TabIndex](properties-accessibility.md)**: de navigatievolgorde op het toetsenbord ten opzichte van andere besturingselementen.

**[Tooltip](properties-core.md)**: beschrijvende tekst die wordt weergegeven wanneer de gebruiker een besturingselement aanwijst.

**[Underline](properties-text.md)**: hiermee wordt aangegeven of onder de tekst in een besturingselement een streep wordt weergegeven.

**[Visible](properties-core.md)**: hiermee wordt aangegeven of een besturingselement zichtbaar of verborgen is.

**[Width](properties-size-location.md)**: de afstand tussen de linker- en rechterrand van een besturingselement.

**[X](properties-size-location.md)**: de afstand tussen de linkerrand van een besturingselement en de linkerrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

**[Y](properties-size-location.md)**: de afstand tussen de bovenrand van een besturingselement en de bovenrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

## <a name="related-functions"></a>Verwante functies
[**Distinct**( *Gegevensbron*, *Kolomnaam* )](../functions/function-distinct.md)

## <a name="example"></a>Voorbeeld
1. Voeg een besturingselement **Keuzerondje** toe, geef het de naam **Prijzen** en stel de eigenschap **[Items](properties-core.md)** van het besturingselement in op deze formule:
   <br>**["Normaal", "Premium"]**
   
    Weet u niet hoe u [een besturingselement kunt toevoegen, een naam kunt geven of kunt configureren](../add-configure-controls.md)?
2. Voeg een besturingselement **[Label](control-text-box.md)** toe, plaats dit onder het besturingselement **Keuzerondje** en stel de eigenschap **[Text](properties-core.md)** van het besturingselement **[Label](control-text-box.md)** in op deze formule:
   <br>**If("Premium" in Prijzen.Selected.Value, "€ 200 per dag", "€ 150 per dag")**
   
    Wilt u meer informatie over de functie **[If](../functions/function-if.md)** of [andere functies](../formula-reference.md)?
3. Druk op F5 en kies vervolgens een van beide opties in het besturingselement **Keuzerondje**.
   
    In het besturingselement **[Label](control-text-box.md)** wordt de juiste tekst voor de gekozen optie weergegeven.
4. (Optioneel) Kies in het besturingselement **Keuzerondje** de andere optie om te controleren of de juiste tekst wordt weergegeven.
5. Druk op Esc om terug te gaan naar de standaardwerkruimte.


## <a name="accessibility-guidelines"></a>Richtlijnen voor toegankelijkheid
### <a name="color-contrast"></a>Kleurcontrast
Er moet voldoende kleurcontrast zijn tussen:
* **RadioSelectionFill** en **RadioBackgroundFill**
* **RadioBackgroundFill** en **[Fill](properties-color-border.md)**

Dit komt bovenop de standaardvereisten voor kleurcontrast.

### <a name="screen-reader-support"></a>Ondersteuning voor schermlezers
* Er moet een **[Waarde](properties-core.md)** zijn voor elke optie van de keuzerondjes.
* U kunt een **[Label](control-text-box.md)** toevoegen direct vóór het besturingselement **Radio** dat dient als de kop.

### <a name="keyboard-support"></a>Ondersteuning voor toetsenbord
* **[TabIndex](properties-accessibility.md)** moet nul of groter zijn, zodat toetsenbordgebruikers ernaartoe kunnen navigeren.
* De focusindicatoren moeten duidelijk zichtbaar zijn. Gebruik hiervoor **[FocusedBorderColor](properties-color-border.md)** en **[FocusedBorderThickness](properties-color-border.md)**.
 