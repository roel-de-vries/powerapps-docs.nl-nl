---
title: 'Besturingselementen voor kolomdiagram en lijndiagram: naslaginformatie | Microsoft Docs'
description: Informatie, waaronder eigenschappen en voorbeelden, over de besturingselementen Kolomdiagram en Lijndiagram
documentationcenter: na
author: fikaradz
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 10/25/2016
ms.author: fikaradz
ms.openlocfilehash: 5397c99d02e824a86147af053e1f907f83ce3543
ms.sourcegitcommit: 79b8842fb0f766a0476dae9a537a342c8d81d3b3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2018
ms.locfileid: "37898262"
---
# <a name="column-chart-and-line-chart-controls-in-powerapps"></a>Besturingselementen Kolomdiagram en Lijndiagram in PowerApps
Besturingselementen die gegevens weergeven als grafieken met x- en y-assen.

## <a name="description"></a>Beschrijving
**Kolomdiagram** en **Lijndiagram** zijn gegroepeerde besturingselementen. Elke groep bevat drie besturingselementen: een **[label](control-text-box.md)** voor de titel, de diagramafbeelding en een **legenda**.

## <a name="chart-key-properties"></a>Belangrijkste eigenschappen voor diagrammen
**[Items](properties-core.md)**: de gegevensbron die wordt weergegeven in een besturingselement zoals een galerie, een lijst of een grafiek.

**NumberOfSeries**: hoeveel kolommen met gegevens er in een kolom- of lijndiagram worden weergegeven.

## <a name="additional-chart-properties"></a>Aanvullende diagrameigenschappen
**[BorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement.

**[BorderStyle](properties-color-border.md)**: hiermee wordt aangegeven of de rand van een besturingselement **effen**, **onderbroken** of **gestippeld** is, of dat er **geen** rand is.

**[BorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement.

**[Color](properties-color-border.md)**: de kleur van de tekst in een besturingselement.

**[DisabledBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**[DisplayMode](properties-core.md)**: of invoer van de gebruiker is toegestaan (**Bewerken**), alleen gegevens worden weergegeven (**Weergeven**) of is uitgeschakeld (**Uitgeschakeld**).

**[Font](properties-text.md)**: de naam van de lettertypefamilie waarin de tekst wordt weergegeven.

**GridStyle**: bepaalt of de x-as, y-as, beide of geen enkele as wordt weergegeven in een kolom- of lijndiagram.

**[Height](properties-size-location.md)** : de afstand tussen de boven- en onderrand van een besturingselement.

**[HoverBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de gebruiker de muisaanwijzer op dat besturingselement plaatst.

**ItemColorSet**: de kleur van elk gegevenspunt in een diagram.

**ItemsGap**: de afstand tussen kolommen in een kolomdiagram.

* De eigenschap **ItemsGap** is beschikbaar voor het besturingselement **Kolomdiagram**, maar niet voor het besturingselement **Lijndiagram**.

**Markers**: bepaalt of in een kolom- of lijndiagram de waarde van elk gegevenspunt wordt weergegeven.

**MarkerSuffix**: tekst die wordt weergegeven na elke waarde in een kolomdiagram waarvoor de eigenschap **Markers** is ingesteld op **true**.

* De eigenschap **MarkerSuffix** is beschikbaar voor het besturingselement **Kolomdiagram**, maar niet voor het besturingselement **Lijndiagram**.

**MinimumBarWidth**: de smalst mogelijke breedte van kolommen in een kolomdiagram.

* De eigenschap **MinimumBarWidth** is beschikbaar voor het besturingselement **Kolomdiagram**, maar niet voor het besturingselement **Lijndiagram**.

**[OnSelect](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker op een besturingselement tikt of klikt.

**[PaddingBottom](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de onderrand van het besturingselement.

**[PaddingLeft](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de linkerrand van het besturingselement.

**[PaddingRight](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de rechterrand van het besturingselement.

**[PaddingTop](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de bovenrand van het besturingselement.

**[PressedBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**SeriesAxisMax**: de maximumwaarde van de y-as voor een kolom- of lijndiagram.

* De eigenschap **SeriesAxisMax** is beschikbaar voor het besturingselement **Kolomdiagram**, maar niet voor het besturingselement **Lijndiagram**.

**SeriesAxisMin**: een getal dat de minimumwaarde bepaalt van de y-as voor een kolomdiagram.

* De eigenschap **SeriesAxisMin** is beschikbaar voor het besturingselement **Kolomdiagram**, maar niet voor het besturingselement **Lijndiagram**.

**[Size](properties-text.md)**: de tekengrootte van de tekst die in een besturingselement wordt weergegeven.

**[TabIndex](properties-accessibility.md)**: de navigatievolgorde op het toetsenbord ten opzichte van andere besturingselementen.

**[Visible](properties-core.md)**: hiermee wordt aangegeven of een besturingselement zichtbaar of verborgen is.

**[Width](properties-size-location.md)**: de afstand tussen de linker- en rechterrand van een besturingselement.

**[X](properties-size-location.md)**: de afstand tussen de linkerrand van een besturingselement en de linkerrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

**XLabelAngle**: de hoek van de labels onder de x-as van een kolom- of lijndiagram.

**[Y](properties-size-location.md)**: de afstand tussen de bovenrand van een besturingselement en de bovenrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

**YAxisMax**: de maximumwaarde van de y-as voor een lijndiagram.

* De eigenschap **YAxisMax** is beschikbaar voor het besturingselement **Kolomdiagram**, maar niet voor het besturingselement **Lijndiagram**.

**YAxisMin**: de minimumwaarde van de y-as voor een lijndiagram.

* De eigenschap **YAxisMin** is beschikbaar voor het besturingselement **Kolomdiagram**, maar niet voor het besturingselement **Lijndiagram**.

**YLabelAngle**: de hoek van de labels naast de y-as van een lijn- of kolomdiagram.

## <a name="related-functions"></a>Verwante functies
[**Max**( *Gegevensbron*, *Kolomnaam* )](../functions/function-aggregates.md)

## <a name="example"></a>Voorbeeld
1. Voeg een besturingselement van het type **[Button](control-button.md)** toe en stel de bijbehorende eigenschap **[OnSelect](properties-core.md)** in op deze formule:<br>
   **Collect(Revenue, {Year:"2013", Europa:24000, Ganymede:22300, Callisto:21200}, {Year:"2014", Europa:26500, Ganymede:25700, Callisto:24700},{Year:"2014", Europa:27900, Ganymede:28300, Callisto:25600})**
   
    Weet u niet hoe u [een besturingselement kunt toevoegen of configureren](../add-configure-controls.md)?
   
    Wilt u meer informatie over de functie **[Collect](../functions/function-clear-collect-clearcollect.md)** of [andere functies](../formula-reference.md)?
2. Druk op F5, klik of tik op het besturingselement **[Knop](control-button.md)** en druk vervolgens op Esc om terug te keren naar de standaardwerkruimte.
3. Voeg een besturingselement **Kolomdiagram** of **Lijndiagram** toe, stel de eigenschap **[Items](properties-core.md)** van het besturingselement in op **Omzet** en stel de eigenschap **NumberOfSeries** in op **3**.
   
    Het besturingselement toont per product de omzet voor een periode van drie jaar.


## <a name="accessibility-guidelines"></a>Richtlijnen voor toegankelijkheid
### <a name="color-contrast"></a>Kleurcontrast
Er moet voldoende kleurcontrast zijn tussen:
* elk item in **ItemColorSet**
* elk item in **ItemColorSet** en de achtergrondkleur
* **[Color](properties-color-border.md)** en de achtergrondkleur

### <a name="screen-reader-support"></a>Ondersteuning voor schermlezers
* Er moet een **[label](control-text-box.md)** direct vóór het diagram aanwezig zijn dat fungeert als de titel.
* U kunt een samenvatting van de grafiekafbeelding toevoegen. Bijvoorbeeld: Het lijndiagram toont een gestage toename van de verkoopcijfers tussen maart en augustus van dit jaar.

    > [!NOTE]
  > Diagramafbeeldingen en **legenda** zijn verborgen voor gebruikers van schermlezers. In plaats daarvan wordt een tabelweergave van de gegevens weergegeven. Ze kunnen ook door de knoppen gaan waarmee gegevens in het diagram worden geselecteerd.

### <a name="low-vision-support"></a>Ondersteuning voor gebruikers met beperkt gezichtsvermogen
* Er moet een **legenda** zijn als meer dan één reeks wordt weergegeven.
* U kunt **GridStyle** instellen op GridStyle.All, die beiden assen weergeeft. Hierdoor kunnen alle gebruikers de schaal van de gegevens nauwkeurig bepalen.
* Voor **Kolomdiagram**, kunt u **Markeringen** instellen op **true**. Hierdoor kunnen gebruikers met een beperkt gezichtsvermogen de waarde van een kolom bepalen.

### <a name="keyboard-support"></a>Ondersteuning voor toetsenbord
* **[TabIndex](properties-accessibility.md)** moet nul of groter zijn, zodat toetsenbordgebruikers ernaartoe kunnen navigeren.

    > [!NOTE]
  > Als gebruikers naar het diagram navigeren, kunnen ze door de knoppen gaan waarmee gegevens in het diagram worden geselecteerd.
