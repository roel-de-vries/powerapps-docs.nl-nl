---
title: 'Besturingselementen voor vormen en pictogrammen: naslag | Microsoft Docs'
description: Informatie, waaronder eigenschappen en voorbeelden, over besturingselementen voor vormen en pictogrammen
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
ms.openlocfilehash: 7a71695460453816dd5c63dad8477cb7ccc703d7
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="shape-controls-and-icon-controls-in-powerapps"></a>Besturingselementen voor vormen en pictogrammen in PowerApps
Grafische elementen waarvan u het uiterlijk en gedrag kunt configureren met behulp van verschillende eigenschappen.

## <a name="description"></a>Beschrijving
Het gaat hier om besturingselementen zoals pijlen, geometrische vormen, actiepictogrammen en symbolen waarvoor u eigenschappen zoals opvulling, grootte en locatie kunt configureren. U kunt ook de eigenschap **[OnSelect](properties-core.md)** configureren, zodat de app reageert als de gebruiker op het besturingselement klikt of tikt.

## <a name="key-properties"></a>Belangrijkste eigenschappen
**[Fill](properties-color-border.md)**: de achtergrondkleur van een besturingselement.

**[OnSelect](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker op een besturingselement tikt of klikt.

## <a name="additional-properties"></a>Aanvullende eigenschappen
**[DisplayMode](properties-core.md)**: of invoer van de gebruiker is toegestaan (**Bewerken**), alleen gegevens worden weergegeven (**Weergeven**) of is uitgeschakeld (**Uitgeschakeld**).

**[Height](properties-size-location.md)** : de afstand tussen de boven- en onderrand van een besturingselement.

**[HoverFill](properties-color-border.md)**: de achtergrondkleur van een besturingselement wanneer de gebruiker de muisaanwijzer op de achtergrond plaatst.

**[PressedBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**[FocusedBorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement wanneer deze de toetsenbordfocus heeft.

**[Visible](properties-core.md)**: hiermee wordt aangegeven of een besturingselement zichtbaar of verborgen is.

**[Width](properties-size-location.md)**: de afstand tussen de linker- en rechterrand van een besturingselement.

**[X](properties-size-location.md)**: de afstand tussen de linkerrand van een besturingselement en de linkerrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

**[Y](properties-size-location.md)**: de afstand tussen de bovenrand van een besturingselement en de bovenrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

## <a name="related-functions"></a>Verwante functies
[**Navigate**( *Schermnaam*, *Schermovergang* )](../functions/function-navigate.md)

## <a name="example"></a>Voorbeeld
1. Geef het standaardbesturingselement **[Scherm](control-screen.md)** de naam **Doel**, voeg een besturingselement **[Label](control-text-box.md)** toe en stel de eigenschap **[Text](properties-core.md)** van het vak in op **Doel**.
   
    Weet u niet hoe u [een besturingselement kunt toevoegen of configureren](../add-configure-controls.md)?
2. Voeg een besturingselement **[Scherm](control-screen.md)** toe en geef het de naam **Bron**.
3. Voeg aan **Bron** een besturingselement **Vorm** toe en stel de eigenschap **[OnSelect](properties-core.md)** van het besturingselement in op deze formule:
   <br>**Navigate(Doel, Schermovergang.Fade)**
4. Druk op F5 en klik of tik op het besturingselement **Vorm**.
   
    Het scherm **Doel** wordt weergegeven.
5. (Optioneel) Druk op Esc om terug te gaan naar de standaardwerkruimte, voeg een besturingselement **Vorm** toe aan **Doel** en stel de eigenschap **[OnSelect](properties-core.md)** van het besturingselement **Vorm** in op deze formule:
   <br>**Navigate(Bron, Schermovergang.Fade)**

