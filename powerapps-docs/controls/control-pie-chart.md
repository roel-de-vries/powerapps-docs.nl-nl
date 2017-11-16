---
title: 'Besturingselement voor cirkeldiagram: naslag | Microsoft Docs'
description: Informatie, waaronder eigenschappen en voorbeelden, over het besturingselement Cirkeldiagram
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
ms.openlocfilehash: 1388eac45e5086f677cb83c8db9593fe01a9819f
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="pie-chart-control-in-powerapps"></a>Besturingselement voor cirkeldiagram in PowerApps
Een besturingselement waarin relatieve waarden ten opzichte van elkaar worden vergeleken.

## <a name="description"></a>Beschrijving
Voeg een besturingselement **Cirkeldiagram** toe als u relatieve gegevens wilt weergeven uit een tabel met labels in de meest linkse kolom en waarden in de tweede kolom van links.

## <a name="key-properties"></a>Belangrijkste eigenschappen
**[Items](properties-core.md)**: de gegevensbron die wordt weergegeven in een besturingselement zoals een galerie, een lijst of een grafiek.

**ShowLabels**: bepaalt of in een cirkeldiagram de waarden worden weergegeven die aan de wiggen zijn gekoppeld.

## <a name="additional-properties"></a>Aanvullende eigenschappen
**[BorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement.

**[BorderStyle](properties-color-border.md)**: hiermee wordt aangegeven of de rand van een besturingselement **effen**, **onderbroken** of **gestippeld** is, of dat er **geen** rand is.

**[BorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement.

**[Color](properties-color-border.md)**: de kleur van de tekst in een besturingselement.

**[DisplayMode](properties-core.md)**: of invoer van de gebruiker is toegestaan (**Bewerken**), alleen gegevens worden weergegeven (**Weergeven**) of is uitgeschakeld (**Uitgeschakeld**).

**[DisabledBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**Explode**: de afstand tussen de wiggen in een cirkeldiagram.

**[Font](properties-text.md)**: de naam van de lettertypefamilie waarin de tekst wordt weergegeven.

**[Height](properties-size-location.md)** : de afstand tussen de boven- en onderrand van een besturingselement.

**[HoverBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de gebruiker de muisaanwijzer op dat besturingselement plaatst.

**ItemBorderColor**: de kleur van de rand rond elke wig in een cirkeldiagram.

**ItemBorderThickness**: de dikte van de rand rond elke wig in een cirkeldiagram.

**ItemColorSet**: de kleur van elk gegevenspunt in een diagram.

**LabelPosition**: de locatie van de labels in een cirkeldiagram ten opzichte van de wiggen.

**[OnSelect](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker op een besturingselement tikt of klikt.

**[PressedBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**[Size](properties-text.md)**: de tekengrootte van de tekst die in een besturingselement wordt weergegeven.

**[Visible](properties-core.md)**: hiermee wordt aangegeven of een besturingselement zichtbaar of verborgen is.

**[Width](properties-size-location.md)**: de afstand tussen de linker- en rechterrand van een besturingselement.

**[X](properties-size-location.md)**: de afstand tussen de linkerrand van een besturingselement en de linkerrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

**[Y](properties-size-location.md)**: de afstand tussen de bovenrand van een besturingselement en de bovenrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

## <a name="related-functions"></a>Verwante functies
[**Max**( *Gegevensbron*, *Kolomnaam* )](../functions/function-aggregates.md)

## <a name="example"></a>Voorbeeld
1. Voeg een besturingselement van het type **[Button](control-button.md)** toe en stel de bijbehorende eigenschap **[OnSelect](properties-core.md)** in op deze formule:<br>
   **Collect(Omzet2015, {Product:"Europa", Omzet:27000}, {Product:"Ganymede", Omzet:26300}, {Product:"Callisto", Omzet:29200})**
   
    Weet u niet hoe u [een besturingselement kunt toevoegen of configureren](../add-configure-controls.md)?
   
    Wilt u meer informatie over de functie **[Collect](../functions/function-clear-collect-clearcollect.md)** of [andere functies](../formula-reference.md)?
2. Druk op F5, klik of tik op het besturingselement **[Knop](control-button.md)** en druk vervolgens op Esc om terug te keren naar de standaardwerkruimte.
3. Voeg een besturingselement **Cirkeldiagram** toe en stel de eigenschap **[Items](properties-core.md)** in op **Omzet2015**.
   
    In het besturingselement **Cirkeldiagram** ziet u omzetcijfers voor elk product ten opzichte van andere producten.

