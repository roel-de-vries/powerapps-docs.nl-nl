---
title: Over gedragsformules | Microsoft Docs
description: Naslaginformatie voor het werken met gedragsformules
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/10/2015
ms.author: gregli
ms.openlocfilehash: 8ac9cfc2a949cf059d84b5338220e0366094e24b
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/13/2018
ms.locfileid: "39015588"
---
# <a name="understand-behavior-formulas-in-powerapps"></a>Over gedragsformules in PowerApps

Met de meeste formules wordt een waarde berekend.  Net als bij een Excel-werkblad vindt de herberekening automatisch plaats wanneer er waarden worden gewijzigd.  Stel dat u bijvoorbeeld de waarde in een besturingselement **[Label](controls/control-text-box.md)** rood wilt weergeven als de waarde lager is dan nul en zwart in andere gevallen. U kunt de eigenschap **[Color](controls/properties-color-border.md)** van dat besturingselement instellen op deze formule:
<br>**If( Value(TextBox1.Text) >= 0, Color.Black, Color.Red )**

Wat betekent het in deze context wanneer de gebruiker een besturingselement **[Knop](controls/control-button.md)** selecteert?  Er is geen waarde gewijzigd, dus is er niets nieuws om te berekenen. Excel heeft geen equivalent van een **[knop](controls/control-button.md)** besturingselement.  

Door een besturingselement **[Knop](controls/control-button.md)** te selecteren, initieert de gebruiker een reeks acties of gedrag waarmee de status van de app wordt gewijzigd:

* Een ander scherm weergeven: de functies **[Back](functions/function-navigate.md)** en **[Navigate](functions/function-navigate.md)**.
* Een [signaal](functions/signals.md) beheren: de functies **[Enable](functions/function-enable-disable.md)** en **[Disable](functions/function-enable-disable.md)**.
* Items vernieuwen, bijwerken of verwijderen in een [gegevensbron](working-with-data-sources.md): de functies **[Refresh](functions/function-refresh.md)**, **[Update](functions/function-update-updateif.md)**, **[UpdateIf](functions/function-update-updateif.md)**, **[Patch](functions/function-patch.md)**, **[Remove](functions/function-remove-removeif.md)** en **[RemoveIf](functions/function-remove-removeif.md)**.
* Een [contextvariabele](working-with-variables.md#create-a-context-variable) bijwerken: de functie **[UpdateContext](functions/function-updatecontext.md)**.
* Items maken, bijwerken of verwijderen in een [verzameling](working-with-data-sources.md#collections): de functies **[Collect](functions/function-clear-collect-clearcollect.md)**, **[Clear](functions/function-clear-collect-clearcollect.md)** en **[ClearCollect](functions/function-clear-collect-clearcollect.md)**.

Omdat deze functies de status van de app wijzigen, kunnen ze niet automatisch opnieuw worden berekend. U kunt deze functies gebruiken in de formules voor de eigenschappen **[OnSelect](controls/properties-core.md)**, **[OnVisible](controls/control-screen.md)**,  **[OnHidden](controls/control-screen.md)** en andere **On...** -eigenschappen die gedragsformules worden genoemd.

### <a name="more-than-one-action"></a>Meer dan één actie
Gebruik puntkomma's om een lijst met acties te maken die moeten worden uitgevoerd. Stel dat u bijvoorbeeld een contextvariabele wilt bijwerken en daarna wilt terugkeren naar het vorige scherm:

* **UpdateContext( { x: 1 } ); Back()**

Acties worden uitgevoerd in de volgorde waarin ze worden weergegeven in de formule.  De volgende functie start pas nadat de huidige functie is voltooid. Als er een fout optreedt, worden volgende functies mogelijk niet gestart.

