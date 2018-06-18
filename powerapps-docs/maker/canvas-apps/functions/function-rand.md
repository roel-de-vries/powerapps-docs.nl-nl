---
title: De functie Rand | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis, voor de functie Rand in PowerApps
author: gregli-msft
ms.service: powerapps
ms.topic: reference
ms.component: canvas
ms.date: 06/09/2018
ms.author: gregli
ms.openlocfilehash: 3bf29a3df235d669de2f2862f11b19f428378123
ms.sourcegitcommit: 6bfb002180148a3f22a4d1d8d750fc442489ebe4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/11/2018
ms.locfileid: "35291761"
---
# <a name="rand-function-in-powerapps"></a>De functie Rand in PowerApps
Retourneert een pseudo-willekeurig getal.

## <a name="description"></a>Beschrijving
De functie **Rand** retourneert een pseudo-willekeurig getal dat groter is dan of gelijk is aan 0 en kleiner dan 1.

## <a name="volatile-functions"></a>Vluchtige functies
**Rand** is een vluchtige functie.  Telkens wanneer de functie wordt geëvalueerd, wordt een andere waarde geretourneerd.  

Wanneer een vluchtige functie in een gegevensstroomformule wordt gebruikt, retourneert deze alleen een andere waarde als de formule waarin deze wordt weergegeven, opnieuw wordt geëvalueerd.  Als er niets anders verandert in de formule, heeft deze dezelfde waarde gedurende de uitvoering van uw app.

Bijvoorbeeld, een label-besturingselement met **Label1.Text = Rand()** verandert bijvoorbeeld niet wanneer uw app actief is.  Alleen het sluiten en opnieuw openen van de app leidt tot een nieuwe waarde.

De functie wordt opnieuw geëvalueerd als deze deel uitmaakt van een formule waarin iets anders is gewijzigd.  Als we ons voorbeeld bijvoorbeeld veranderen en een besturingselement van het type schuifregelaar gebruiken met **Label1.Text = Slider1.Value + Rand()**, wordt een nieuw willekeurig nummer gegenereerd telkens wanneer de waarde van het besturingselement van het type schuifregelaar wijzigt en de teksteigenschap van het label opnieuw wordt geëvalueerd.  Hieronder vindt u dit voorbeeld.

Wanneer de functie wordt gebruikt in een [gedragsformule](../working-with-formulas-in-depth.md), wordt **Rand** geëvalueerd telkens als de gedragsformule wordt geëvalueerd.  Hieronder vindt u een voorbeeld.

## <a name="syntax"></a>Syntaxis
**Rand**()

## <a name="examples"></a>Voorbeelden

#### <a name="display-a-different-random-number-as-user-input-changes"></a>Een ander willekeurig getal weergeven wanneer gebruikersinvoer wijzigt
1. Voeg een besturingselement van het type **[Slider](../controls/control-slider.md)** toe en geef dit de naam **Slider1** als het een andere naam heeft.

1. Voeg een besturingselement van het type **[Label](../controls/control-text-box.md)** toe en stel de eigenschap **Text** in op deze formule:

    **Slider1.Value + Rand()**

    Het label geeft **50** (de standaardwaarde voor de schuifregelaar) weer plus een willekeurige decimaal:

    ![Een scherm dat een labelbesturingselement met 50.741 weergeeft](media/function-rand/rand-slider-1.png)

1. Wijzig de waarde van de schuifregelaar terwijl u de Alt-toets ingedrukt houdt.

    Telkens wanneer u de waarde van de schuifregelaar wijzigt, geeft het decimale gedeelte van het label een ander willekeurig getal weer:

    ![Vier schermen die een labelbesturingselement weergeven met vier verschillende willekeurige decimale waarden voor elk van de vier verschillende schuifregelaarinstellingen 70.899, 84.667, 90.134, 99.690](media/function-rand/rand-slider-results.png)

#### <a name="create-a-table-of-random-numbers"></a>Een tabel met willekeurige getallen maken
1. Voeg een besturingselement van het type **[Button](../controls/control-button.md)** toe en stel de bijbehorende eigenschap **[OnSelect](../controls/properties-core.md)** in op deze formule:

    **ClearCollect( RandomNumbers, ForAll( [ 1, 2, 3, 4, 5 ], Rand() ))**

    Deze formule maakt een tabel met één kolom die wordt gebruikt om vijf keer te worden herhaald, wat resulteert in vijf willekeurige getallen.

1. Voeg een **[gegevenstabel](../controls/control-data-table.md)** toe, stel de eigenschap **Items** in op **RandomNumbers** en geef het veld **Value** weer.

    ![Een scherm met een gegevenstabel met vijf verschillende decimale waarden 0.857, 0.105, 0.979, 0.167, 0.814](media/function-rand/set-show-data.png)

1. Houd de Alt-toets ingedrukt en selecteer de knop door erop te klikken of te tikken.

    De gegevenstabel geeft vijf willekeurige decimale getallen weer:

    ![Een scherm met een gegevenstabel met vijf verschillende decimale waarden 0.857, 0.105, 0.979, 0.167, 0.814](media/function-rand/rand-collection-1.png)

1. Selecteer de knop opnieuw om een andere lijst met willekeurige getallen weer te geven:

    ![Hetzelfde scherm met een gegevenstabel met een nieuwe set van vijf verschillende decimale waarden 0.414, 0.128, 0.860, 0.303, 0.568](media/function-rand/rand-collection-2.png)

Gebruik **Set( RandomNumber, Rand() )** om een enkel willekeurig getal te genereren in plaats van een tabel.
