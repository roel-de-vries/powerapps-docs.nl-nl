---
title: De functies Abs, Exp Ln, Macht en Wortel | Microsoft Docs
description: Referentie-informatie, inclusief syntaxis en voorbeelden, voor de functies Abs, Wortel en andere functies in PowerApps
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 09/13/2016
ms.author: gregli
ms.openlocfilehash: 15d458142bc1077b1bf55ae6e358c826f813ecb2
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "31829505"
---
# <a name="abs-exp-ln-power-and-sqrt-functions-in-powerapps"></a>De functies Abs, Exp Ln, Macht en Wortel in PowerApps
Berekent absolute waarden, natuurlijke logaritmen, vierkantswortels en het resultaat van het machtsverheffen van *e* of een willekeurig getal tot opgegeven machten.

## <a name="description"></a>Beschrijving
De functie **Abs** retourneert de niet-negatieve waarde van het argument. Als een getal negatief is, retourneert **Abs** het positieve equivalent.

De functie **Exp** retourneert *e* verheven tot de macht van het argument.  Het transcendente getal *e* begint met 2,7182818...

De functie **Ln** retourneert de natuurlijke logaritme (grondtal *e*) van het argument.

Met de functie **Macht** wordt een getal geretourneerd dat tot een macht is verheven.  Dit komt overeen met het gebruik van de [**^**-operator](operators.md).

De functie **Wortel** retourneert het getal dat, wanneer vermenigvuldigd met zichzelf, gelijk is aan het argument.

Als u één getal doorgeeft, is de resulterende waarde één resultaat op basis van de aangeroepen functie.  Als u een [tabel](../working-with-tables.md) met één kolom doorgeeft die getallen bevat, is de geretourneerde waarde een tabel met één kolom met resultaten (één resultaat voor elke record in de tabel voor het argument). Als u een tabel met meerdere kolommen hebt, kunt u deze omvormen tot een tabel met één kolom, zoals wordt beschreven in [werken met tabellen](../working-with-tables.md).  

Als een argument tot een niet-gedefinieerde waarde zou leiden, is het resultaat *leeg*.  Dit kan bijvoorbeeld gebeuren met vierkantswortels en logaritmen van negatieve getallen.

## <a name="syntax"></a>Syntaxis
**Abs**( *getal* )<br>**Exp**( *getal* )<br>**Ln**( *getal* )<br>**Wortel**( *getal* )

* *Getal* is vereist. Getal om bewerking op uit te voeren.

**Macht**( *Grondtal*, *Exponent* )

* *Grondtal* - vereist. Te verheffen grondtal.
* *Exponent* - vereist. De exponent waarmee het grondtal wordt verheven.

**Abs**( *TabelMetEénKolom* )<br>**Exp**( *TabelMetEénKolom* )<br>**Ln**( *TabelMetEénKolom* )<br>**Wortel**( *TabelMetEénKolom* )

* *TabelMetEénKolom* - vereist. Een tabel met één kolom die getallen bevat om bewerkingen op uit te voeren.

## <a name="examples"></a>Voorbeelden
### <a name="single-number"></a>Eén getal
| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **Abs( -55 )** |Retourneert het getal zonder het minteken. |55 |
| **Exp( 2 )** |Retourneert *e* verheven tot de macht van 2, of *e* \* *e*. |7,389056... |
| **Ln( 100 )** |Retourneert de natuurlijke logaritme (grondtal *e*) van het getal 100. |4,605170... |
| **Macht( 5, 3 )** |Retourneert 5 tot de macht 3, of 5 \* 5 \* 5. |125 |
| **Wortel( 9 )** |Retourneert het getal dat, wanneer vermenigvuldigd met zichzelf, resulteert in 9. |3 |

### <a name="single-column-table"></a>Tabel met één kolom
In de voorbeelden in deze sectie wordt een [gegevensbron](../working-with-data-sources.md) met de naam **WaardeTabel** gebruikt die deze gegevens bevat:

![](media/function-numericals/values.png)

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **Abs(&nbsp;WaardeTabel&nbsp;)** |Retourneert de absolute waarde van elk getal uit de tabel. |<style> img { max-width: none } </style> ![](media/function-numericals/values-abs.png) |
| **Exp(&nbsp;WaardeTabel&nbsp;)** |Retourneert *e* verheven tot de macht van elk getal uit de tabel. |<style> img { max-width: none } </style> ![](media/function-numericals/values-exp.png) |
| **Ln(&nbsp;WaardeTabel&nbsp;)** |Retourneert de natuurlijke logaritme van elk getal uit de tabel. |<style> img { max-width: none } </style> ![](media/function-numericals/values-ln.png) |
| **Wortel(&nbsp;WaardeTabel&nbsp;)** |Retourneert de vierkantswortel van elk getal uit de tabel. |![](media/function-numericals/values-sqrt.png) |

### <a name="step-by-step-example"></a>Stapsgewijs voorbeeld
1. Voeg een besturingselement **[Tekstinvoer](../controls/control-text-input.md)** toe en geef het de naam **Bron**.
2. Voeg een besturingselement van het type **Label** toe en stel de eigenschap **[Text](../controls/properties-core.md)** in op deze formule:
   <br>
   **Sqrt( Value( Source.Text ) )**
3. Typ een getal in **Bron** en bevestig dat het besturingselement **Label** de vierkantswortel bevat van het getal dat u hebt getypt.

