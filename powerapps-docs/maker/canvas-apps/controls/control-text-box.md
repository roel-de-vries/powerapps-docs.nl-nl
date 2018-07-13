---
title: 'Besturingselement voor label: naslag | Microsoft Docs'
description: Informatie, waaronder eigenschappen en voorbeelden, over het besturingselement voor label
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
ms.openlocfilehash: cfc47e95cff02dfcbcc2d3ff456e32a4ca2c675e
ms.sourcegitcommit: 79b8842fb0f766a0476dae9a537a342c8d81d3b3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2018
ms.locfileid: "37899429"
---
# <a name="label-control-in-powerapps"></a>Besturingselement voor label in PowerApps
Een vak waarin gegevens zoals tekst, getallen, datums of valuta worden weergegeven.

## <a name="description"></a>Beschrijving
Een label bevat gegevens die u opgeeft als een letterlijke tekenreeks (deze gegevens worden exact weergegeven zoals u deze typt) of als een formule die resulteert in een tekenreeks. Labels worden vaak op zichzelf staand weergegeven (zoals een banner waarin een scherm wordt aangeduid), als een label waarmee een ander besturingselement wordt aangegeven (zoals een besturingselement voor classificatie of audio) of in een galerie om een specifiek type informatie over een item weer te geven.

## <a name="key-properties"></a>Belangrijkste eigenschappen
**[AutoHeight](properties-core.md)**: wordt ingesteld op true opdat het label automatisch in de hoogte kan worden aangepast aan alle geconfigureerde tekst. Wordt ingesteld op false als de tekst op de ingestelde hoogte moet worden afgekapt.

**[Color](properties-color-border.md)**: de kleur van de tekst in een besturingselement.

**[Font](properties-text.md)**: de naam van de lettertypefamilie waarin de tekst wordt weergegeven.

**[Text](properties-core.md)**: de tekst die wordt weergegeven in een besturingselement of die de gebruiker in een besturingselement typt.

**[DelayOutput](properties-core.md)**: ingesteld op true om actie tijdens tekstinvoer te vertragen.

## <a name="additional-properties"></a>Aanvullende eigenschappen
**[Align](properties-text.md)**: de locatie van tekst in verhouding tot het horizontale midden van het besturingselement.

**AutoHeight**: bepaalt of de eigenschap **[Height](properties-size-location.md)** van een label automatisch wordt aangepast als de eigenschap **[Text](properties-core.md)** meer tekens bevat dan het besturingselement in één keer kan weergeven.

**[BorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement.

**[BorderStyle](properties-color-border.md)**: hiermee wordt aangegeven of de rand van een besturingselement **effen**, **onderbroken** of **gestippeld** is, of dat er **geen** rand is.

**[BorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement.

**[DisplayMode](properties-core.md)**: of invoer van de gebruiker is toegestaan (**Bewerken**), alleen gegevens worden weergegeven (**Weergeven**) of is uitgeschakeld (**Uitgeschakeld**).

**[DisabledBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**[DisabledColor](properties-color-border.md)**: de kleur van tekst in een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**[DisabledFill](properties-color-border.md)**: de achtergrondkleur van een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**[Fill](properties-color-border.md)**: de achtergrondkleur van een besturingselement.

**[FocusedBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de focus op het besturingselement is.

**[FocusedBorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement wanneer de focus op het besturingselement is.

**[FontWeight](properties-text.md)**: het gewicht van de tekst in een besturingselement: **Bold**, **Semibold**, **Normal** of **Lighter**.

**[Height](properties-size-location.md)** : de afstand tussen de boven- en onderrand van een besturingselement.

**[HoverBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de gebruiker de muisaanwijzer op dat besturingselement plaatst.

**[HoverColor](properties-color-border.md)**: de kleur van de tekst in een besturingselement wanneer de gebruiker de muisaanwijzer op de tekst plaatst.

**[HoverFill](properties-color-border.md)**: de achtergrondkleur van een besturingselement wanneer de gebruiker de muisaanwijzer op de achtergrond plaatst.

**[Italic](properties-text.md)**: hiermee wordt aangegeven of de tekst in een besturingselement cursief is.

**[LineHeight](properties-text.md)**: de afstand tussen bijvoorbeeld regels tekst of items in een lijst.

**[OnSelect](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker op een besturingselement tikt of klikt.

**Overflow**: bepaalt of een schuifbalk in een label wordt weergegeven als de eigenschap **Wrap** is ingesteld op **true** en de waarde van de eigenschap **[Text](properties-core.md)** van het besturingselement meer tekens bevat dan het besturingselement in één keer kan weergeven.

**[PaddingBottom](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de onderrand van het besturingselement.

**[PaddingLeft](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de linkerrand van het besturingselement.

**[PaddingRight](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de rechterrand van het besturingselement.

**[PaddingTop](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de bovenrand van het besturingselement.

**[PressedBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**[PressedColor](properties-color-border.md)**: de kleur van tekst in een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**[PressedFill](properties-color-border.md)**: de achtergrondkleur van een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**[Size](properties-text.md)**: de tekengrootte van de tekst die in een besturingselement wordt weergegeven.

**[Strikethrough](properties-text.md)**: hiermee wordt aangegeven of een streep door de tekst van een besturingselement wordt weergegeven.

**[TabIndex](properties-accessibility.md)**: de navigatievolgorde op het toetsenbord ten opzichte van andere besturingselementen.

**[Tooltip](properties-core.md)**: beschrijvende tekst die wordt weergegeven wanneer de gebruiker een besturingselement aanwijst.

**[Underline](properties-text.md)**: hiermee wordt aangegeven of onder de tekst in een besturingselement een streep wordt weergegeven.

**[VerticalAlign](properties-text.md)**: de locatie van de tekst in een besturingselement in verhouding tot het verticale midden van dat besturingselement.

**[Visible](properties-core.md)**: hiermee wordt aangegeven of een besturingselement zichtbaar of verborgen is.

**[Width](properties-size-location.md)**: de afstand tussen de linker- en rechterrand van een besturingselement.

**Wrap**: bepaalt of tekst die te lang is voor een label, terugloopt naar de volgende regel.

**[X](properties-size-location.md)**: de afstand tussen de linkerrand van een besturingselement en de linkerrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

**[Y](properties-size-location.md)**: de afstand tussen de bovenrand van een besturingselement en de bovenrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

## <a name="related-functions"></a>Verwante functies
[**Text**( *Getal*, "*Opmaakcodes*" )](../functions/function-text.md)

## <a name="examples"></a>Voorbeelden
### <a name="show-a-literal-string"></a>Een letterlijke tekenreeks weergeven
* Voeg een label toe en stel de eigenschap **[Text](properties-core.md)** van het vak in op **"Hallo wereld"** (inclusief de dubbele aanhalingstekens).
  
    Weet u niet hoe u [een besturingselement kunt toevoegen of configureren](../add-configure-controls.md)?

### <a name="show-the-result-of-a-formula"></a>Het resultaat van een formule weergeven
* Voeg een label toe en stel de eigenschap **[Text](properties-core.md)** van de label in op een formule zoals deze:<br>
  **Today()**
  
    > [!NOTE]
  > Wanneer u een formule opgeeft, gebruikt u alleen aanhalingstekens als een argument van de formule bestaat uit een letterlijke tekenreeks. In dat geval zet u het argument, niet de formule, tussen dubbele aanhalingstekens.
  
    Wilt u meer weten over de functie **[Today](../functions/function-now-today-istoday.md)** of [andere functies](../formula-reference.md)?

### <a name="show-data-in-a-gallery"></a>Gegevens weergeven in een galerie
In deze procedure maakt u een verzameling met de naam **Inwonersaantallen**, met daarin gegevens van de aantallen inwoners van verschillende steden in Europa. Vervolgens toont u die gegevens in een galerie met drie labels en u stelt het type gegevens in dat in elk label wordt weergegeven.

1. Voeg een knop toe en stel de eigenschap **[BijSelecteren](properties-core.md)** ervan in op deze formule:<br>
   **ClearCollect(Inwonersaantallen, {Stad:"Londen", Land:"Engeland", Inwonersaantal:8615000}, {Stad:"Berlijn", Land:"Duitsland", Inwonersaantal:3562000}, {Stad:"Madrid", Land:"Spanje", Inwonersaantal:3165000}, {Stad:"Rome", Land:"Italië", Inwonersaantal:2874000}, {Stad:"Parijs", Land:"Frankrijk", Inwonersaantal:2273000}, {Stad:"Hamburg", Land:"Duitsland", Inwonersaantal:1760000}, {Stad:"Barcelona", Land:"Spanje", Inwonersaantal:1602000}, {Stad:"München", Land:"Duitsland", Inwonersaantal:1494000}, {Stad:"Milaan", Land:"Italië", Inwonersaantal:1344000})**
2. Druk op F5, selecteer de knop en druk op Esc.
3. Voeg een tekstgalerie toe en stel de eigenschap **[Items](properties-core.md)** ervan in op **Inwonersaantallen**.
   
    Als u de galerie selecteert, ziet u in het deelvenster aan de rechterkant de opties voor de galerie.
4. Stel in het deelvenster **Galerie1** de bovenste lijst in op **Inwonersaantal**, de middelste lijst op **Stad** en de onderste lijst op **Land**.


## <a name="accessibility-guidelines"></a>Richtlijnen voor toegankelijkheid
Ongeacht wat de naam doet vermoeden, hoeft een besturingselement voor **label** niet te worden gebruikt als een label voor een ander besturingselement. Het kan worden gebruikt om elke tekst weer te geven.

Een **label** kan worden gebruikt als een knop of koppeling door het gedrag van **[OnSelect](properties-core.md)** op te geven. Daarom gelden voor dit besturingselement dezelfde aandachtspunten als voor knoppen.

### <a name="color-contrast"></a>Kleurcontrast
Er moet voldoende kleurcontrast zijn tussen:
* **[Color](properties-color-border.md)** en **[Fill](properties-color-border.md)**
* Andere [standaardvereisten voor kleurcontrast zijn van toepassing](../accessible-apps-color.md) (indien gebruikt als een knop of koppeling)

### <a name="screen-reader-support"></a>Ondersteuning voor schermlezers
* **[Text](properties-core.md)** moet aanwezig zijn.

    > [!NOTE]
  > Schermlezers beschouwen **label**s als knoppen wanneer **[TabIndex](properties-accessibility.md)** groter dan of gelijk aan nul is.

### <a name="low-vision-support"></a>Ondersteuning voor gebruikers met beperkt gezichtsvermogen
* **Label** moet eruitzien als een koppeling als deze wordt gebruikt als een koppeling.
    * Stel **[Underline](properties-text.md)** in op **true**
    * **[HoverColor](properties-color-border.md)** moet verschillen van **[Color](properties-color-border.md)**

### <a name="keyboard-support"></a>Ondersteuning voor toetsenbord
* **[TabIndex](properties-accessibility.md)** moet nul of groter zijn als de tekst wordt gebruikt als een knop of koppeling. Hierdoor kunnen toetsenbordgebruikers ernaartoe navigeren.
* Focusindicatoren moet duidelijk zichtbaar zijn als de tekst wordt gebruikt als een knop of koppeling. Gebruik hiervoor **[FocusedBorderColor](properties-color-border.md)** en **[FocusedBorderThickness](properties-color-border.md)**.
