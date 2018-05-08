---
title: Toegankelijke kleuren | Microsoft Docs
description: Richtlijnen voor kleurcontrast voor PowerApps
author: tahoon
ms.service: powerapps
ms.topic: article
ms.date: 04/23/2018
ms.author: tahoon
ms.openlocfilehash: 56a11edcd1c43313e9b380ca8ac1c8a68d85772d
ms.sourcegitcommit: 45fac73f04aa03b5796ae6833d777f4757e67945
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/03/2018
---
# <a name="accessible-colors-in-powerapps"></a>Toegankelijke kleuren in PowerApps
Kleuren die worden gebruikt in een app moeten toegankelijk zijn voor gebruikers die kleurenblind zijn of een beperkt gezichtsvermogen hebben. Alle PowerApps-thema's zijn standaard toegankelijk. Volg wanneer u kleuren wijzigt die in een app worden gebruikt deze richtlijnen om ervoor te zorgen dat ze toegankelijk blijven.

## <a name="minimum-contrast-for-text"></a>Minimumcontrast voor tekst
* Tekst en de achtergrond moeten een contrastverhouding hebben van minimaal 4,5:1
* Grote tekst moet een contrastverhouding hebben van minimaal 3:1
* Voor uitgeschakelde tekst zijn er geen contrastvereisten

In de praktijk moeten alle interactieve besturingselementen voldoende kleurcontrast hebben tussen:
* **[Color](controls/properties-color-border.md)** en **[Fill](controls/properties-color-border.md)**
* **[PressedColor](controls/properties-color-border.md)** en **[PressedFill](controls/properties-color-border.md)**
* **[HoverColor](controls/properties-color-border.md)** en **[HoverFill](controls/properties-color-border.md)**

## <a name="minimum-contrast-for-non-text"></a>Minimumcontrast voor niet-tekst

> [!NOTE]
> Volgens de [WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-contrast.html)-standaard gelden contrastvereisten alleen voor tekst. Voor betere toegankelijkheid kunt u de toekomstige [WCAG 2.1-contrastrichtlijnen](https://www.w3.org/TR/WCAG21/#non-text-contrast) voor essentiële onderdelen van de gebruikersinterface, zoals pictogramknoppen, overwegen. Voor deze onderdelen wordt een minimale verhouding van 3:1 aanbevolen. De richtlijnen die in deze sectie worden beschreven, zijn **optioneel** voor naleving van WCAG 2.0.

### <a name="user-interface-components"></a>Onderdelen van de gebruikersinterface
Alle interactieve besturingselementen moeten voldoende kleurcontrast hebben tussen:
* **[FocusedBorderColor](controls/properties-color-border.md)** en de kleur buiten het besturingselement

Voor besturingselementen waarbij het gehele gebied interactief of informatief is, gelden aanvullende kleurcontrastcontroles. Bijvoorbeeld een **[knop](controls/control-button.md)** of een **[pictogram](controls/control-shapes-icons.md)** dat als een knop wordt gebruikt. Dit zorgt ervoor dat de grenzen van het besturingselement duidelijk zijn en dat gebruikers weten waarop ze kunnen klikken of tikken.

Als dergelijke besturingselementen een rand hebben, moet er voldoende kleurcontrast zijn tussen:
* **[BorderColor](controls/properties-color-border.md)** en de kleur buiten het besturingselement
* **[PressedBorderColor](controls/properties-color-border.md)** en de kleur buiten het besturingselement
* **[HoverBorderColor](controls/properties-color-border.md)** en de kleur buiten het besturingselement

Als er geen rand is, moet er voldoende kleurcontrast zijn tussen:
* **[Fill](controls/properties-color-border.md)** en de kleur buiten het besturingselement
* **[PressedFill](controls/properties-color-border.md)** en de kleur buiten het besturingselement
* **[HoverFill](controls/properties-color-border.md)** en de kleur buiten het besturingselement

### <a name="graphical-objects"></a>Grafische objecten
Als een afbeelding belangrijke informatie geeft, kunt u overwegen deze te controleren op contrastproblemen. Dit geldt voor besturingselementen waarbij een afbeelding kan worden weergegeven: **[Audio](controls/control-audio-video.md)**, **[Afbeelding](controls/control-image.md)**, **[Microfoon ](controls/control-microphone.md)** en **[Video](controls/control-audio-video.md)**.

Voor video-inhoud, kunt u overwegen deze te controleren op contrastproblemen. U kunt ook [ondertiteling](controls/control-audio-video.md) verstrekken die de video beschrijft.

## <a name="provide-other-visual-cues"></a>Andere visuele aanwijzingen geven
Zorg ervoor dat de app geen informatie geeft met alleen kleur. Gebruikers die kleurenblind zijn voor rood/groen kunnen bijvoorbeeld een rood foutbericht niet onderscheiden van een groen succesbericht.

Extra hints, zoals een **[pictogram](controls/control-shapes-icons.md)** of tekststijlen, zoals **[cursief](controls/properties-text.md)** en **[onderstreping](controls/properties-text.md)**, kunnen helpen om de betekenis over te brengen.

## <a name="next-steps"></a>Volgende stappen
Lees meer over [toegankelijkheidseigenschappen](controls/properties-accessibility.md) in PowerApps-besturingselementen.