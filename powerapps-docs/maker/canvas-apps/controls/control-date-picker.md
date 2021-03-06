---
title: 'Besturingselement voor datumkiezer: naslag | Microsoft Docs'
description: Informatie, waaronder eigenschappen en voorbeelden, over het besturingselement Datumkiezer
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/25/2016
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: ddb15340c9532e82d95f1bea70959dc59cdc7283
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42853814"
---
# <a name="date-picker-control-in-powerapps"></a>Besturingselement voor datumkiezer in PowerApps
Een besturingselement waarop de gebruiker kan klikken of tikken om een datum op te geven.

## <a name="description"></a>Beschrijving
Als u een besturingselement **Datumkiezer** toevoegt in plaats van een besturingselement **[Tekstinvoer](control-text-input.md)**, weet u zeker dat de gebruiker een datum met de juiste indeling gaat invoeren.

## <a name="key-properties"></a>Belangrijkste eigenschappen
**DefaultDate**: de aanvankelijke waarde van een datumbesturingselement tenzij deze door de gebruiker wordt gewijzigd.

**SelectedDate**: de datum die op dat moment is geselecteerd in een datumbesturingselement.

**Format**: de tekstindeling waarin het besturingselement de datum weergeeft en de gebruiker de datum opgeeft. U kunt deze eigenschap instellen op **ShortDate** (standaard) of **LongDate** om de datum weer te geven op basis van de eigenschap **Language** van dit besturingselement. U kunt deze eigenschap ook instellen op een expressie, zoals **jjjj/mm/dd**, als u wilt dat dezelfde indeling wordt gebruikt, ongeacht de taal. Bijvoorbeeld:

* Het besturingselement geeft **12/31/2017** weer als de gebruiker klikt of tikt op de laatste dag van 2017, de eigenschap **Format** is ingesteld op **ShortDate** en de eigenschap **Language** is ingesteld op **en-us**.
* Het besturingselement geeft **dimanche 31 decembre 2017** weer als de gebruiker klikt of tikt op de laatste dag van 2017, de eigenschap **Format** is ingesteld op **LongDate** en de eigenschap **Language** is ingesteld op **fr-fr**.

**Language**: bepaalt de taal die wordt gebruikt voor de indeling van datums, waaronder de namen van maanden. Als deze eigenschap niet is opgegeven, bepaalt de apparaatinstelling van de gebruiker de taal.

## <a name="additional-properties"></a>Aanvullende eigenschappen
**[AccessibleLabel](properties-accessibility.md)**: label voor schermlezers.

**[BorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement.

**[BorderStyle](properties-color-border.md)**: hiermee wordt aangegeven of de rand van een besturingselement **effen**, **onderbroken** of **gestippeld** is, of dat er **geen** rand is.

**[BorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement.

**[Color](properties-color-border.md)**: de kleur van de tekst in een besturingselement.

**[DisplayMode](properties-core.md)**: of invoer van de gebruiker is toegestaan (Bewerken), alleen gegevens worden weergegeven (Weergeven) of is uitgeschakeld (Uitgeschakeld).

**[DisabledBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**[DisabledColor](properties-color-border.md)**: de kleur van tekst in een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**[DisabledFill](properties-color-border.md)**: de achtergrondkleur van een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**EndYear**: het laatste jaar waarop de gebruiker de waarde van een datumkiezer kan instellen.

**[Fill](properties-color-border.md)**: de achtergrondkleur van een besturingselement.

**[FocusedBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de focus op het besturingselement is.

**[FocusedBorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement wanneer de focus op het besturingselement is.

**[Font](properties-text.md)**: de naam van de lettertypefamilie waarin de tekst wordt weergegeven.

**[FontWeight](properties-text.md)**: het gewicht van de tekst in een besturingselement: **Bold**, **Semibold**, **Normal** of **Lighter**.

**[Height](properties-size-location.md)** : de afstand tussen de boven- en onderrand van een besturingselement.

**IconFill**: de voorgrondkleur van het datumkiezerpictogram.

**IconBackground**: de achtergrondkleur van het datumkiezerpictogram.

**[Italic](properties-text.md)**: hiermee wordt aangegeven of de tekst in een besturingselement cursief is.

**[OnSelect](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker op een besturingselement tikt of klikt.

**[PaddingBottom](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de onderrand van het besturingselement.

**[PaddingLeft](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de linkerrand van het besturingselement.

**[PaddingRight](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de rechterrand van het besturingselement.

**[PaddingTop](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de bovenrand van het besturingselement.

**[Size](properties-text.md)**: de tekengrootte van de tekst die in een besturingselement wordt weergegeven.

**StartYear**: het eerste jaar waarop de gebruiker de waarde van een datumkiezer kan instellen.

**[TabIndex](properties-accessibility.md)**: de navigatievolgorde op het toetsenbord ten opzichte van andere besturingselementen.

**[Visible](properties-core.md)**: hiermee wordt aangegeven of een besturingselement zichtbaar of verborgen is.

**[Width](properties-size-location.md)**: de afstand tussen de linker- en rechterrand van een besturingselement.

**[X](properties-size-location.md)**: de afstand tussen de linkerrand van een besturingselement en de linkerrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

**[Y](properties-size-location.md)**: de afstand tussen de bovenrand van een besturingselement en de bovenrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

## <a name="related-functions"></a>Verwante functies
**[Year](../functions/function-datetime-parts.md)**( *DatumTijd* )

## <a name="example"></a>Voorbeeld
1. Voeg een besturingselement **Datumkiezer** toe en geef het de naam **Deadline**.

    Weet u niet hoe u [een besturingselement kunt toevoegen, een naam kunt geven of kunt configureren](../add-configure-controls.md)?
2. Voeg een besturingselement van het type **[Label](control-text-box.md)** toe en stel de eigenschap **[Text](properties-core.md)** in op deze formule:
   <br>**DateDiff(Today(), Deadline.SelectedDate) & " dagen nog!"**

    Wilt u meer informatie over de functie **[DateDiff](../functions/function-dateadd-datediff.md)** of [andere functies](../formula-reference.md)?
3. Druk op F5, kies een datum in het besturingselement **Deadline**, en klik of tik op **OK**.

    In het besturingselement **[Label](control-text-box.md)** wordt het aantal dagen weergegeven tussen vandaag en de datum die u hebt gekozen.
4. Druk op Esc om terug te gaan naar de standaardwerkruimte.


## <a name="accessibility-guidelines"></a>Richtlijnen voor toegankelijkheid
### <a name="color-contrast"></a>Kleurcontrast
* [De standaardvereisten voor kleurcontrast](../accessible-apps-color.md) zijn van toepassing.

### <a name="screen-reader-support"></a>Ondersteuning voor schermlezers
* **[AccessibleLabel](properties-accessibility.md)** moet aanwezig zijn.

### <a name="keyboard-support"></a>Ondersteuning voor toetsenbord
* **[TabIndex](properties-accessibility.md)** moet nul of groter zijn, zodat toetsenbordgebruikers ernaartoe kunnen navigeren.
* De focusindicatoren moeten duidelijk zichtbaar zijn. Gebruik hiervoor **[FocusedBorderColor](properties-color-border.md)** en **[FocusedBorderThickness](properties-color-border.md)**.
