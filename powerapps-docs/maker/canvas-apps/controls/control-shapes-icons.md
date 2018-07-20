---
title: 'Besturingselementen voor vormen en pictogrammen: naslag | Microsoft Docs'
description: Informatie, waaronder eigenschappen en voorbeelden, over besturingselementen voor vormen en pictogrammen
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/25/2016
ms.author: fikaradz
ms.openlocfilehash: 12865bf432ed31f0964add63fa024182680fb7aa
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/13/2018
ms.locfileid: "39022396"
---
# <a name="shape-controls-and-icon-controls-in-powerapps"></a>Besturingselementen voor vormen en pictogrammen in PowerApps
Grafische elementen waarvan u het uiterlijk en gedrag kunt configureren met behulp van verschillende eigenschappen.

## <a name="description"></a>Beschrijving
Het gaat hier om besturingselementen zoals pijlen, geometrische vormen, actiepictogrammen en symbolen waarvoor u eigenschappen zoals opvulling, grootte en locatie kunt configureren. U kunt ook de eigenschap **[OnSelect](properties-core.md)** configureren, zodat de app reageert als de gebruiker op het besturingselement klikt of tikt.

## <a name="key-properties"></a>Belangrijkste eigenschappen
**[Fill](properties-color-border.md)**: de achtergrondkleur van een besturingselement.

**[OnSelect](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker op een besturingselement tikt of klikt.

## <a name="additional-properties"></a>Aanvullende eigenschappen
**[AccessibleLabel](properties-accessibility.md)**: label voor schermlezers.

**[DisplayMode](properties-core.md)**: of invoer van de gebruiker is toegestaan (**Bewerken**), alleen gegevens worden weergegeven (**Weergeven**) of is uitgeschakeld (**Uitgeschakeld**).

**[FocusedBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de focus op het besturingselement is.

**[FocusedBorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement wanneer de focus op het besturingselement is.

**[Height](properties-size-location.md)** : de afstand tussen de boven- en onderrand van een besturingselement.

**[HoverFill](properties-color-border.md)**: de achtergrondkleur van een besturingselement wanneer de gebruiker de muisaanwijzer op de achtergrond plaatst.

**[PressedBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**[PressedFill](properties-color-border.md)**: de achtergrondkleur van een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**[TabIndex](properties-accessibility.md)**: de navigatievolgorde op het toetsenbord ten opzichte van andere besturingselementen.

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
3. Voeg aan **Bron** een besturingselement **Vorm** toe en stel de eigenschap **[OnSelect](properties-core.md)** van het besturingselement in op deze formule:<br>**Navigate(Doel, Schermovergang.Fade)**
4. Druk op F5 en klik of tik op het besturingselement **Vorm**.

    Het scherm **Doel** wordt weergegeven.

5. (Optioneel) Druk op Esc om terug te gaan naar de standaardwerkruimte, voeg een besturingselement **Vorm** toe aan **Doel** en stel de eigenschap **[OnSelect](properties-core.md)** van het besturingselement **Vorm** in op deze formule:
   <br>**Navigate(Bron, Schermovergang.Fade)**


## <a name="accessibility-guidelines"></a>Richtlijnen voor toegankelijkheid

### <a name="color-contrast"></a>Kleurcontrast

Het volgende geldt alleen voor afbeeldingen die worden gebruikt als knoppen en voor afbeeldingen die niet alleen voor de sier zijn.

Voor pictogrammen:
* **[Color](properties-color-border.md)** en **[Fill](properties-color-border.md)**
* Andere [standaardvereisten voor kleurcontrast](../accessible-apps-color.md) zijn van toepassing (indien gebruikt als een knop)

Voor vormen met randen:
* **[BorderColor](properties-color-border.md)** en de kleur buiten het besturingselement
* **[FocusedBorderColor](properties-color-border.md)** en de kleur buiten het besturingselement (indien gebruikt als een knop)

Voor vormen zonder randen:
* **[Fill](properties-color-border.md)** en de kleur buiten het besturingselement
* **[PressedFill](properties-color-border.md)** en de kleur buiten het besturingselement (indien gebruikt als een knop)
* **[HoverFill](properties-color-border.md)** en de kleur buiten het besturingselement (indien gebruikt als een knop)

### <a name="screen-reader-support"></a>Ondersteuning voor schermlezers
* **[AccessibleLabel](properties-accessibility.md)** moet aanwezig zijn als de afbeelding wordt gebruikt als een knop of als de afbeelding niet alleen voor de sier is.
* **[AccessibleLabel](properties-accessibility.md)** moet leeg zijn of de lege tekenreeks **""** bevatten als de afbeelding alleen voor de sier is. Hierdoor wordt de afbeelding genegeerd door de schermlezer.
* **[AccessibleLabel](properties-accessibility.md)** kan leeg zijn of de lege tekenreeks **""** bevatten als de afbeelding redundante informatie bevat.

    Bijvoorbeeld: een pictogram **Instellingen** waarvoor **[AccessibleLabel](properties-accessibility.md)** is ingesteld op **Instellingen**. Dit pictogram wordt niet gebruikt als een knop. Het staat naast een **[label](control-text-box.md)** dat ook **Instellingen** heet. Het pictogram wordt door schermlezers gelezen als **Instellingen** en het label ook als **Instellingen**. Dit is onnodig. In dit geval heeft het pictogram geen **[AccessibleLabel](properties-accessibility.md)** nodig.

    > [!IMPORTANT]
    > Schermlezers lezen alle pictogrammen of vormen waarvoor **[TabIndex](properties-accessibility.md)** nul of groter is, zelfs als **[AccessibleLabel](properties-accessibility.md)** leeg is. Dit is omdat deze als knoppen worden weergegeven. Als er geen **[AccessibleLabel](properties-accessibility.md)** is opgegeven, lezen schermlezers de afbeelding als een **knop**.

### <a name="keyboard-support"></a>Ondersteuning voor toetsenbord
* **[TabIndex](properties-accessibility.md)** moet nul of groter zijn als de afbeelding wordt gebruikt als een knop. Hierdoor kunnen toetsenbordgebruikers naar de afbeelding navigeren.
* Focusindicatoren moet duidelijk zichtbaar zijn als de afbeelding wordt gebruikt als een knop. Gebruik hiervoor **[FocusedBorderColor](properties-color-border.md)** en **[FocusedBorderThickness](properties-color-border.md)**.

    > [!NOTE]
  > Wanneer **[TabIndex](properties-accessibility.md)** nul of groter is, wordt het pictogram of de vorm weergegeven als een knop. Het uiterlijk van de afbeelding verandert niet, maar de afbeelding wordt door schermlezers juist geïdentificeerd als een knop. Wanneer **[TabIndex](properties-accessibility.md)** kleiner is dan nul, wordt het pictogram of de vorm geïdentificeerd als een afbeelding.
