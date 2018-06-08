---
title: Functies Kleine letters, Hoofdletters en Juiste | Microsoft Docs
description: Referentie-informatie, inclusief syntaxis en voorbeelden, voor de functies Kleine letters, Hoofdletters en Juiste in PowerApps
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: e57ea9208f0ea3b7dd9ada7ebd9055a99ddc141c
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "31831772"
---
# <a name="lower-upper-and-proper-functions-in-powerapps"></a>Functies Kleine letters, Hoofdletters en Juiste in PowerApps
Converteert letters in een tekenreeks met tekst naar allemaal kleine letters, allemaal hoofdletters of een beginhoofdletter, gevolgd door allemaal kleine letters.

## <a name="description"></a>Beschrijving
De functies **Kleine letters**, **Hoofdletters** en **Juiste** zetten de weergave van letters in tekenreeksen om.

* **Kleine letters** converteert alle hoofdletters naar kleine letters.
* **Hoofdletters** converteert alle kleine letters naar hoofdletters.
* **Juiste** converteert de eerste letter in elk woord naar een hoofdletter als het een kleine letter is; eventuele andere hoofdletters worden omgezet in kleine letters.

Alle drie de functies negeren tekens die geen letters zijn.

Als u één tekenreeks doorgeeft, is de resulterende waarde de omgezette versie van die tekenreeks.  Als u een [tabel](../working-with-tables.md) met één kolom doorgeeft die tekenreeksen bevat, is de geretourneerde waarde een tabel met één kolom met geconverteerde tekenreeksen. Als u een tabel met meerdere kolommen hebt, kunt u deze omvormen tot een tabel met één kolom, zoals wordt beschreven in [werken met tabellen](../working-with-tables.md).

## <a name="syntax"></a>Syntaxis
**Lower**( *String* )<br>**Upper**( *String* )<br>**Proper**( *String* )

* *String* - vereist. De tekenreeks die moet worden geconverteerd.

**Lower**( *SingleColumnTable* )<br>**Upper**( *SingleColumnTable* )<br>**Proper**( *SingleColumnTable* )

* *TabelMetEénKolom* - vereist. Een tabel met één kolom die tekenreeksen bevat om te converteren.

## <a name="examples"></a>Voorbeelden
### <a name="single-string"></a>Eén tekenreeks
In de voorbeelden in deze sectie wordt een besturingselement voor tekstinvoer, **Auteur** genaamd, gebruikt als [gegevensbron](../working-with-data-sources.md). Het besturingselement bevat de tekenreeks "E. E. CummINGS".

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **Lower(&nbsp;Auteur.Text&nbsp;)** |Converteert alle hoofdletters in de tekenreeks naar kleine letters. |"e. e. cummings" |
| **Upper(&nbsp;Auteur.Text&nbsp;)** |Converteert alle kleine letters in de tekenreeks naar hoofdletters. |"E. E. CUMMINGS" |
| **Proper(&nbsp;Auteur.Text&nbsp;)** |Converteert de eerste letter van elk woord naar een hoofdletter als het een kleine letter is; eventuele andere hoofdletters worden omgezet in kleine letters. |"E. E. Cummings" |

### <a name="single-column-table"></a>Tabel met één kolom
De voorbeelden in deze sectie converteren tekenreeksen uit de [kolom](../working-with-tables.md#columns) **Adres** in de gegevensbron **Personen**; deze bevat de volgende gegevens:

![](media/function-lower-upper-proper/people-table.png)

Elke formule retourneert een tabel met één kolom die de geconverteerde tekenreeksen bevat.

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **Lower( ShowColumns(&nbsp;Personen,&nbsp;"Adres"&nbsp;) )** |Converteert elke kleine letter in een hoofdletter. |<style> img { max-width:none; } </style> ![](media/function-lower-upper-proper/people-table-lower.png) |
| **Upper( ShowColumns(&nbsp;Personen,&nbsp;"Adres"&nbsp;) )** |Converteert elke kleine letter in een hoofdletter. |![](media/function-lower-upper-proper/people-table-upper.png) |
| **Proper( ShowColumns(&nbsp;Personen,&nbsp;"Adres"&nbsp;) )** |Converteert elke eerste letter van een woord dat met een kleine letter begint naar een hoofdletter; eventuele andere hoofdletters worden geconverteerd naar kleine letters. |![](media/function-lower-upper-proper/people-table-proper.png) |

### <a name="step-by-step-example"></a>Stapsgewijs voorbeeld
1. Voeg een besturingselement **[Tekstinvoer](../controls/control-text-input.md)** toe en geef het de naam **Bron**.
2. Voeg een label toe en stel de eigenschap **[Text](../controls/properties-core.md)** in op deze functie:<br>**Proper(Source.Text)**
3. Druk op F5 en typ vervolgens **WIJ ZIJN DE BESTE!** in het vak **Bron**.<br>Het label geeft **Wij Zijn De Beste!** weer.

