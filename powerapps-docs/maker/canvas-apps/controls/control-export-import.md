---
title: 'Besturingselementen voor exporteren en importeren: naslaginformatie | Microsoft Docs'
description: Informatie (waaronder eigenschappen en voorbeelden) over de besturingselementen voor exporteren en importeren
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/25/2016
ms.author: fikaradz
ms.openlocfilehash: 9eb0cf33c4bac3553592971409f7c52f199b368b
ms.sourcegitcommit: 0f6d7bb9e524202c065b9a7ef92a7f54bdc4bc7c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/07/2018
ms.locfileid: "39017290"
---
# <a name="export-control-and-import-control-in-powerapps"></a>Besturingselementen voor exporteren en importeren in PowerApps
Besturingselementen waarmee u gegevens naar een lokaal bestand exporteert en die gegevens vervolgens in een andere app in PowerApps importeert.

## <a name="description"></a>Beschrijving
Als u meerdere apps wilt maken die gebruikmaken van dezelfde gegevens maar die gegevens niet buiten deze apps wilt delen, kunt u de gegevens exporteren en importeren met behulp van een **Export**- en een **Import**-besturingselement. Wanneer u gegevens exporteert, maakt u een gecomprimeerd bestand dat u naar een andere computer kunt kopiëren, maar dat niet kan worden gelezen in een ander programma dan PowerApps.

## <a name="warning"></a>Waarschuwing
Als u deze functionaliteit in uw app inschakelt, kan de app worden blootgesteld aan beveiligingsrisico's en gegevenslekken.  U wordt aangeraden gebruikers te adviseren alleen bekende en vertrouwde bestanden te importeren en alleen gegevens te exporteren die niet vertrouwelijk of gevoelig zijn.

## <a name="key-properties"></a>Belangrijkste eigenschappen
**Data**: De naam van een verzameling die u naar een lokaal bestand wilt exporteren.

* De eigenschap **Data** is beschikbaar voor een **Export**-besturingselement, niet voor een **Import**-besturingselement.

**[OnSelect](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker op een besturingselement tikt of klikt.

## <a name="additional-properties"></a>Aanvullende eigenschappen
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

**[HoverBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de gebruiker de muisaanwijzer op dat besturingselement plaatst.

**[HoverColor](properties-color-border.md)**: de kleur van de tekst in een besturingselement wanneer de gebruiker de muisaanwijzer op de tekst plaatst.

**[HoverFill](properties-color-border.md)**: de achtergrondkleur van een besturingselement wanneer de gebruiker de muisaanwijzer op de achtergrond plaatst.

**[Italic](properties-text.md)**: hiermee wordt aangegeven of de tekst in een besturingselement cursief is.

**[Padding](properties-size-location.md)**: de afstand tussen de tekst op een knop voor importeren of exporteren en de randen van die knop.

**[PressedBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**[PressedColor](properties-color-border.md)**: de kleur van tekst in een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**[PressedFill](properties-color-border.md)**: de achtergrondkleur van een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**[RadiusBottomLeft](properties-size-location.md)**: de mate van afronding van de linkerbenedenhoek van een besturingselement.

**[RadiusBottomRight](properties-size-location.md)**: de mate van afronding van de rechterbenedenhoek van een besturingselement.

**[RadiusTopLeft](properties-size-location.md)**: de mate van afronding van de linkerbovenhoek van een besturingselement.

**[RadiusTopRight](properties-size-location.md)**: de mate van afronding van de rechterbovenhoek van een besturingselement.

**[Size](properties-text.md)**: de tekengrootte van de tekst die in een besturingselement wordt weergegeven.

**[Strikethrough](properties-text.md)**: hiermee wordt aangegeven of een streep door de tekst van een besturingselement wordt weergegeven.

**[TabIndex](properties-accessibility.md)**: de navigatievolgorde op het toetsenbord ten opzichte van andere besturingselementen.

**[Text](properties-core.md)**: de tekst die wordt weergegeven in een besturingselement of die de gebruiker in een besturingselement typt.

**[Underline](properties-text.md)**: hiermee wordt aangegeven of onder de tekst in een besturingselement een streep wordt weergegeven.

**[VerticalAlign](properties-text.md)**: de locatie van de tekst in een besturingselement in verhouding tot het verticale midden van dat besturingselement.

**[Visible](properties-core.md)**: hiermee wordt aangegeven of een besturingselement zichtbaar of verborgen is.

**[Width](properties-size-location.md)**: de afstand tussen de linker- en rechterrand van een besturingselement.

**[X](properties-size-location.md)**: de afstand tussen de linkerrand van een besturingselement en de linkerrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

**[Y](properties-size-location.md)**: de afstand tussen de bovenrand van een besturingselement en de bovenrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

## <a name="example"></a>Voorbeeld
1. Voeg een besturingselement van het type **[Button](control-button.md)** toe en stel de bijbehorende eigenschap **[OnSelect](properties-core.md)** in op deze formule:
   <br>**ClearCollect(Products, {Name:"Europa", Price:"10,99"}, {Name:"Ganymede", Price:"12,49"}, {Name:"Callisto", Price:"11,79"})**
   
    Weet u niet hoe u [een besturingselement kunt toevoegen, een naam kunt geven of kunt configureren](../add-configure-controls.md)?
   
    Wilt u meer informatie over de functie **[ClearCollect](../functions/function-clear-collect-clearcollect.md)** of een [andere functie](../formula-reference.md)?
2. Druk op F5, klik of tik op het besturingselement **[Button](control-button.md)** en druk vervolgens op Esc.
3. Voeg een besturingselement van het type **Export** toe en stel de bijbehorende eigenschap **Data** in op **Products**.
4. Druk op F5, tik of klik op het besturingselement **Export** en geef de naam op van het bestand waarnaar u de gegevens wilt exporteren.
5. Klik of tik op **Save** en druk op Esc om terug te gaan naar de standaardwerkruimte.
6. Voeg in een nieuwe of bestaande app een besturingselement van het type **Import** toe, geef dit de naam **MyData** en stel de bijbehorende eigenschap **[OnSelect](properties-core.md)** in op deze formule:<br>
   **Collect(ImportedProducts, MyData.Data)**
7. Druk op F5, tik of klik op **MyData**, klik of tik op het bestand dat u hebt geëxporteerd en klik of tik vervolgens op **Open**.
8. Druk op Esc, tik of klik op **Collections** in het menu **File** en controleer of de huidige app de geëxporteerde gegevens bevat.


## <a name="accessibility-guidelines"></a>Richtlijnen voor toegankelijkheid
Dezelfde richtlijnen als voor **[Button](control-button.md)** zijn van toepassing, omdat **Export** en **Import** eenvoudig gespecialiseerde knoppen zijn.
