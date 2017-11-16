---
title: 'Besturingselement voor waardering: naslag | Microsoft Docs'
description: Informatie, waaronder eigenschappen en voorbeelden, over het besturingselement Waardering
services: 
suite: powerapps
documentationcenter: na
author: fikaradz
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/25/2016
ms.author: fikaradz
ms.openlocfilehash: 4dd23b8c94ee4760e40b4513e7a88667f85c3a4b
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="rating-control-in-powerapps"></a>Besturingselement voor waardering in PowerApps
Een besturingselement waarmee gebruikers een waarde kunnen opgeven tussen 1 en een maximumwaarde die u instelt.

## <a name="description"></a>Beschrijving
In dit besturingselement kan de gebruiker bijvoorbeeld aangeven wat ze van iets vinden door een aantal sterren te selecteren.

## <a name="key-properties"></a>Belangrijkste eigenschappen
**[Default](properties-core.md)**: de aanvankelijke waarde van een besturingselement voordat deze door de gebruiker wordt gewijzigd.

**Max**: de maximale waarde waarop de gebruiker een schuifregelaar of een waardering kan instellen.

## <a name="additional-properties"></a>Aanvullende eigenschappen
**[BorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement.

**[BorderStyle](properties-color-border.md)**: hiermee wordt aangegeven of de rand van een besturingselement **effen**, **onderbroken** of **gestippeld** is, of dat er **geen** rand is.

**[BorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement.

**[FocusedBorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement wanneer deze de toetsenbordfocus heeft.

**[DisplayMode](properties-core.md)**: of invoer van de gebruiker is toegestaan (**Bewerken**), alleen gegevens worden weergegeven (**Weergeven**) of is uitgeschakeld (**Uitgeschakeld**).

**[Fill](properties-color-border.md)**: de achtergrondkleur van een besturingselement.

**[Height](properties-size-location.md)** : de afstand tussen de boven- en onderrand van een besturingselement.

**[OnChange](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker de waarde van een besturingselement wijzigt (bijvoorbeeld door een schuifregelaar aan te passen).

**[OnSelect](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker op een besturingselement tikt of klikt.

**RatingFill**: de kleur van de sterren in een besturingselement voor waardering.

**ReadOnly**: bepaalt of een gebruiker de waarde van een schuifregelaar of besturingselement voor waardering mag wijzigen.

**[Reset](properties-core.md)**: of een besturingselement wordt teruggezet op de standaardwaarde.

**ShowValue**: bepaalt of de waarde van een schuifregelaar of waardering wordt weergegeven wanneer de gebruiker die waarde verandert of het besturingselement aanwijst.

**[TabIndex](properties-accessibility.md)**: past de tabvolgorde van besturingselementen tijdens runtime aan wanneer hier een andere waarde dan nul is ingesteld.

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

