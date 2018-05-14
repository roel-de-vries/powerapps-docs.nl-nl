---
title: 'Besturingselement voor waardering: naslag | Microsoft Docs'
description: Informatie, waaronder eigenschappen en voorbeelden, over het besturingselement Waardering
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
ms.openlocfilehash: 1df75e5de1f0d8a2515b4dcf761593145d72f70a
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
---
# <a name="rating-control-in-powerapps"></a>Besturingselement voor waardering in PowerApps
Een besturingselement waarmee gebruikers een waarde kunnen opgeven tussen 1 en een maximumwaarde die u instelt.

## <a name="description"></a>Beschrijving
In dit besturingselement kan de gebruiker bijvoorbeeld aangeven wat ze van iets vinden door een aantal sterren te selecteren.

## <a name="key-properties"></a>Belangrijkste eigenschappen
**[Default](properties-core.md)**: de aanvankelijke waarde van een besturingselement voordat deze door de gebruiker wordt gewijzigd.

**Max**: de maximale waarde waarop de gebruiker een schuifregelaar of een waardering kan instellen.

## <a name="additional-properties"></a>Aanvullende eigenschappen
**[AccessibleLabel](properties-accessibility.md)**: label voor schermlezers.

**[BorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement.

**[BorderStyle](properties-color-border.md)**: hiermee wordt aangegeven of de rand van een besturingselement **effen**, **onderbroken** of **gestippeld** is, of dat er **geen** rand is.

**[BorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement.

**[DisplayMode](properties-core.md)**: of invoer van de gebruiker is toegestaan (**Bewerken**), alleen gegevens worden weergegeven (**Weergeven**) of is uitgeschakeld (**Uitgeschakeld**).

**[Fill](properties-color-border.md)**: de achtergrondkleur van een besturingselement.

**[FocusedBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de focus op het besturingselement is.

**[FocusedBorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement wanneer de focus op het besturingselement is.

**[Height](properties-size-location.md)** : de afstand tussen de boven- en onderrand van een besturingselement.

**[OnChange](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker de waarde van een besturingselement wijzigt (bijvoorbeeld door een schuifregelaar aan te passen).

**[OnSelect](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker op een besturingselement tikt of klikt.

**RatingFill**: de kleur van de sterren in een besturingselement voor waardering.

**ReadOnly**: bepaalt of een gebruiker de waarde van een schuifregelaar of besturingselement voor waardering mag wijzigen.

**[Reset](properties-core.md)**: of een besturingselement wordt teruggezet op de standaardwaarde.

**ShowValue**: bepaalt of de waarde van een schuifregelaar of waardering wordt weergegeven wanneer de gebruiker die waarde verandert of het besturingselement aanwijst.

**[TabIndex](properties-accessibility.md)**: de navigatievolgorde op het toetsenbord ten opzichte van andere besturingselementen.

**[Tooltip](properties-core.md)**: beschrijvende tekst die wordt weergegeven wanneer de gebruiker een besturingselement aanwijst.

**[Visible](properties-core.md)**: hiermee wordt aangegeven of een besturingselement zichtbaar of verborgen is.

**[Width](properties-size-location.md)**: de afstand tussen de linker- en rechterrand van een besturingselement.

**[X](properties-size-location.md)**: de afstand tussen de linkerrand van een besturingselement en de linkerrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

**[Y](properties-size-location.md)**: de afstand tussen de bovenrand van een besturingselement en de bovenrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

## <a name="related-functions"></a>Verwante functies
[**Average**( *Waarde1*, *Waarde2* ... )](../functions/function-aggregates.md)

## <a name="example"></a>Voorbeeld
1. Voeg een besturingselement **Waardering** toe en geef het de naam **Kwantitatief**.
   
    Weet u niet hoe u [een besturingselement kunt toevoegen, een naam kunt geven of kunt configureren](../add-configure-controls.md)?
2. Voeg een besturingselement **[Tekstinvoer](control-text-input.md)** toe, geef het de naam **Kwalitatief** en plaats het onder het besturingselement **Waardering**.
3. Stel de eigenschap **[Default](properties-core.md)** van het besturingselement **[Tekstinvoer](control-text-input.md)** in op **""** en de eigenschap **HintText** op deze formule:
   <br>**If(Kwantitatief.Value > 3, "Wat vindt u heel goed?", "Wat kan er beter?")**
   
    Wilt u meer informatie over de functie **[If](../functions/function-if.md)** of [andere functies](../formula-reference.md)?
4. Druk op F5, en klik of tik op vier of vijf sterren in het besturingselement **Waardering**.
   
    De tekst van de hint in het besturingselement **[Tekstinvoer](control-text-input.md)** wordt aangepast aan de hoge waardering.
5. Klik of tik op minder dan vier sterren in het besturingselement **Kwantitatief**.
   
    De tekst van de hint in het besturingselement **[Tekstinvoer](control-text-input.md)** wordt aangepast aan de lage waardering.
6. Druk op Esc om terug te gaan naar de standaardwerkruimte.


## <a name="accessibility-guidelines"></a>Richtlijnen voor toegankelijkheid
### <a name="color-contrast"></a>Kleurcontrast
Er moet voldoende kleurcontrast zijn tussen:
* **RatingFill** en**[Fill](properties-color-border.md)**

Dit komt bovenop de [standaardvereisten voor kleurcontrast](../accessible-apps-color.md).

### <a name="screen-reader-support"></a>Ondersteuning voor schermlezers
* **[AccessibleLabel](properties-accessibility.md)** moet aanwezig zijn.

    > [!NOTE]
> Schermlezers behandelen het besturingselement **Waardering** als keuzerondjes.

### <a name="keyboard-support"></a>Ondersteuning voor toetsenbord
* **[TabIndex](properties-accessibility.md)** moet nul of groter zijn, zodat toetsenbordgebruikers ernaartoe kunnen navigeren.
* De focusindicatoren moeten duidelijk zichtbaar zijn. Gebruik hiervoor **[FocusedBorderColor](properties-color-border.md)** en **[FocusedBorderThickness](properties-color-border.md)**.
* U kunt ook een ander besturingselement gebruiken als er te veel sterren zijn. Het kan omslachtig zijn om te navigeren met een toetsenbord en lastig om nauwkeurig te selecteren met een aanraakscherm.

    > [!NOTE]
> Dezelfde toetsenbordinteracties voor keuzerondjes kunnen worden gebruikt voor **Waardering**.
