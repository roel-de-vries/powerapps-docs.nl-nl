---
title: 'Besturingselement voor datumkiezer: naslag | Microsoft Docs'
description: Informatie, waaronder eigenschappen en voorbeelden, over het besturingselement Datumkiezer
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
ms.openlocfilehash: f2605680c7b6e8f7102fd3459230344863a93f55
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
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
**[BorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement.

**[BorderStyle](properties-color-border.md)**: hiermee wordt aangegeven of de rand van een besturingselement **effen**, **onderbroken** of **gestippeld** is, of dat er **geen** rand is.

**[BorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement.

**[FocusedBorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement wanneer deze de toetsenbordfocus heeft.

**[Color](properties-color-border.md)**: de kleur van de tekst in een besturingselement.

**[DisplayMode](properties-core.md)**: of invoer van de gebruiker is toegestaan (Bewerken), alleen gegevens worden weergegeven (Weergeven) of is uitgeschakeld (Uitgeschakeld).

**[DisabledBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**[DisabledColor](properties-color-border.md)**: de kleur van tekst in een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**[DisabledFill](properties-color-border.md)**: de achtergrondkleur van een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**EndYear**: het laatste jaar waarop de gebruiker de waarde van een datumkiezer kan instellen.

**[Fill](properties-color-border.md)**: de achtergrondkleur van een besturingselement.

**[Font](properties-text.md)**: de naam van de lettertypefamilie waarin de tekst wordt weergegeven.

**[FontWeight](properties-text.md)**: het gewicht van de tekst in een besturingselement: **Bold**, **Semibold**, **Normal** of **Lighter**.

**[Height](properties-size-location.md)** : de afstand tussen de boven- en onderrand van een besturingselement.

**[Italic](properties-text.md)**: hiermee wordt aangegeven of de tekst in een besturingselement cursief is.

**[OnSelect](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker op een besturingselement tikt of klikt.

**[PaddingBottom](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de onderrand van het besturingselement.

**[PaddingLeft](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de linkerrand van het besturingselement.

**[PaddingRight](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de rechterrand van het besturingselement.

**[PaddingTop](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de bovenrand van het besturingselement.

**[Size](properties-text.md)**: de tekengrootte van de tekst die in een besturingselement wordt weergegeven.

**StartYear**: het eerste jaar waarop de gebruiker de waarde van een datumkiezer kan instellen.

**[TabIndex](properties-accessibility.md)**: past de tabvolgorde van besturingselementen tijdens runtime aan wanneer hier een andere waarde dan nul is ingesteld.

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

