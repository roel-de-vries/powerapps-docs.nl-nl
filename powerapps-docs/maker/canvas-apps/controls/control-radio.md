---
title: 'Besturingselement voor keuzerondje: naslag | Microsoft Docs'
description: Informatie, waaronder eigenschappen en voorbeelden, over het besturingselement Keuzerondje
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 07/06/2018
ms.author: fikaradz
ms.openlocfilehash: b09f2ef174ecea79c0a4297bf700ba84b96bccbe
ms.sourcegitcommit: 0f6d7bb9e524202c065b9a7ef92a7f54bdc4bc7c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/07/2018
ms.locfileid: "39016048"
---
# <a name="radio-control-in-powerapps"></a>Besturingselement voor keuzerondje in PowerApps

Een besturingselement voor invoer dat meerdere opties toont, waarvan gebruikers slechts één bewerking tegelijk kunnen selecteren.

## <a name="description"></a>Beschrijving

Een **Radio**-besturingselement, een standaard HTML-besturingselement voor invoer, kan het beste worden gebruikt met maar enkele, elkaar uitsluitende, opties.

Het besturingselement kan een horizontale of verticale indeling hebben.

## <a name="key-properties"></a>Belangrijkste eigenschappen

**[Standaard](properties-core.md)**: de waarde van een besturingselement voordat de gebruiker het wijzigt.

**[Items](properties-core.md)**: de gegevensbron die wordt weergegeven in een besturingselement zoals een galerie, een lijst of een grafiek.

**Lay-out**: bepaalt of de opties verticaal of horizontaal worden weergegeven.

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

    **["Normaal", "Premium"]**

    Weet u niet hoe u [een besturingselement kunt toevoegen, een naam kunt geven of kunt configureren](../add-configure-controls.md)?

2. Voeg een besturingselement **[Label](control-text-box.md)** toe, plaats dit onder het besturingselement **Keuzerondje** en stel de eigenschap **[Text](properties-core.md)** van het besturingselement **[Label](control-text-box.md)** in op deze formule:

    **If("Premium" in Prijzen.Selected.Value, "€ 200 per dag", "€ 150 per dag")**

    Wilt u meer informatie over de functie **[If](../functions/function-if.md)** of [andere functies](../formula-reference.md)?

3. Houd de Alt-toets ingedrukt en selecteer een van beide opties in het besturingselement **Radio**.

    In het besturingselement **[Label](control-text-box.md)** wordt de juiste tekst voor de gekozen optie weergegeven.

4. (Optioneel) Houd de Alt-toets ingedrukt en selecteer de andere optie om te controleren of de juiste tekst wordt weergegeven.

## <a name="accessibility-guidelines"></a>Richtlijnen voor toegankelijkheid

### <a name="color-contrast"></a>Kleurcontrast

Naast de [standaardvereisten voor kleurcontrast](../accessible-apps-color.md) moet u zorgen voor voldoende kleurcontrast tussen:

* **RadioSelectionFill** en **RadioBackgroundFill**
* **RadioBackgroundFill** en **[Fill](properties-color-border.md)**

### <a name="screen-reader-support"></a>Ondersteuning voor schermlezers

* Controleer of elke optie heeft een **[waarde](properties-core.md)** heeft.
* U kunt een **[Label](control-text-box.md)** toevoegen direct vóór het besturingselement **Radio** dat dient als de kop.

### <a name="keyboard-support"></a>Ondersteuning voor toetsenbord

* Stel de eigenschap **[TabIndex](properties-accessibility.md)** in op nul of groter, zodat toetsenbordgebruikers ernaartoe kunnen navigeren.
* Stel de eigenschappen **[FocusedBorderColor](properties-color-border.md)** en **[FocusedBorderThickness](properties-color-border.md)** in, zodat focusindicatoren duidelijk zichtbaar zijn.