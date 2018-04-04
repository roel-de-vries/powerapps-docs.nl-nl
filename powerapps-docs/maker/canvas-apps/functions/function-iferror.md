---
title: De functie IfError | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functie IfError in PowerApps
services: ''
suite: powerapps
documentationcenter: na
author: gregli-msft
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/21/2018
ms.author: gregli
ms.openlocfilehash: c0da6a00f1176c8f44db6e508cca92b0cbf99beb
ms.sourcegitcommit: a9d33322228c398d29964429602dc3fe19fa67d2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/28/2018
---
# <a name="iferror-function-in-powerapps"></a>De functie IfError in PowerApps
Hiermee worden fouten gedetecteerd en wordt er een alternatieve waarde opgegeven of actie ondernomen.

## <a name="description"></a>Beschrijving
> [!NOTE]
> Deze functie maakt deel uit van een experimenteel onderdeel van de software en kan worden gewijzigd.  Het gedrag dat hier wordt beschreven, is alleen beschikbaar als de functie *Foutbeheer op formuleniveau* is ingeschakeld.  Dit is een instelling op app-niveau die standaard is uitgeschakeld.  Als u deze functie wilt inschakelen, gaat u naar het tabblad *Bestand*, de optie *App-instellingen* in het menu links en vervolgens *Experimentele functies*.  Uw feedback is zeer waardevol. Laat via de [PowerApps-communityfora](https://powerusers.microsoft.com/t5/Expressions-and-Formulas/bd-p/How-To) weten wat u denkt.

Met de functie **IfError** worden alle argumenten getest om te controleren of er een foutwaarde wordt geretourneerd. Er wordt gestopt wanneer de eerste niet-foutwaarde is gevonden.  De argumenten ná het argument met de niet-foutwaarde worden genegeerd en niet geëvalueerd.

Gebruik **IfError** om foutwaarden door een geldige waarde te vervangen.  Als het bijvoorbeeld mogelijk is dat de invoer van een gebruiker wordt gedeeld door nul, vervangt u de waarde door een 0 of een andere geldige waarde die geschikt is voor uw app. Op die manier kunnen de downstreamberekeningen doorgaan.

Gebruik **IfError** in [gedragsformules](../working-with-formulas-in-depth.md) om acties uit te voeren, de resultaten te controleren op fouten en indien nodig verdere actie te ondernemen of een foutbericht weer te geven aan de gebruiker met [ **ShowError**](function-showerror.md).

Als alle argumenten voor **IfError** resulteren in een fout, wordt de waarde van het laatste argument geretourneerd (een foutwaarde). 

## <a name="syntax"></a>Syntaxis
**IfError**( *Value*, *Fallback1* [, *Fallback2*, ... ] )

* *Value*: vereist. Formule(s) om te controleren op foutwaarden. 
* *Fallback(s)*: vereist. De formules om de evalueren en waarden om te retourneren als er met eerdere argumenten een fout is geretourneerd.  *Fallback*-argumenten worden in de bestaande volgorde geëvalueerd tot er een niet-foutwaarde wordt gevonden.

## <a name="examples"></a>Voorbeelden

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **IfError( 1, 2 )** |Het eerste argument retourneert geen foutwaarde.  Het wordt geretourneerd en de volgende argumenten worden niet geëvalueerd.   | 1 |
| **IfError( 1/0, 2 )** | Het eerste argument retourneert een foutwaarde (als gevolg van een deling door nul).  Het tweede argument wordt geëvalueerd, wat erin resulteert dat een niet-foutwaarde wordt geretourneerd. | 2 | 
| **IfError( 1/0, ShowError( "Division by Zero" ) )** | Het eerste argument retourneert een foutwaarde (als gevolg van een deling door nul).  Het tweede argument wordt geëvalueerd. Hiermee worden berichten aan de gebruiker weergegeven.  De retourwaarde van **IfError** is de retourwaarde van **ShowError**, veranderd in hetzelfde type als bij het eerste argument voor **IfError** (een getal). | 1 |
| **IfError( 1/0, 1/0, 2, 1/0, 3 )** | Het eerste argument retourneert een foutwaarde (als gevolg van een deling door nul).  Het tweede argument wordt geëvalueerd, waardoor ook een foutwaarde wordt geretourneerd (nog een deling door nul).  Het derde argument wordt geëvalueerd. Hierbij wordt er geen foutwaarde geretourneerd.  Het vierde en vijfde argument worden genegeerd.  | 2 |

### <a name="step-by-step"></a>Stap voor stap

1. Voeg een **[Text input](../controls/control-text-input.md)**-besturingselement toe en noem het **TextInput1** als het die naam niet standaard al heeft.

2. Voeg een **[Label](../controls/control-text-box.md)**-besturingselement toe en noem het **Label1** als het die naam niet standaard al heeft.

3. Stel de formule voor de eigenschap **Text** van **Label1** in op:

    **IfError( Value( TextInput1.Text ), -1 )**

4. In **TextInput1** typt u **1234**.  

    Label1 toont de waarde **1234** omdat dit geldige invoer is voor de functie Value.

5. In **TextInput1** typt u **ToInfinity**.

    Label1 toont de waarde **-1** omdat dit geen geldige invoer is voor de functie Value.  Als u de functie Value niet laat teruglopen met IfError, wordt voor het label geen waarde weergegeven omdat de foutwaarde wordt behandeld als zijnde *leeg*. 

