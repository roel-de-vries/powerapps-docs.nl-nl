---
title: Functies Links, Midden en Rechts | Microsoft Docs
description: Referentie-informatie, inclusief syntaxis en voorbeelden, voor de functies Links, Midden en Rechts in PowerApps
services: 
suite: powerapps
documentationcenter: na
author: gregli-msft
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 2cf54b1225578b2bb2bdefa8c0bd02dc0c9c0283
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="left-mid-and-right-functions-in-powerapps"></a>Functies Links, Midden en Rechts in PowerApps
Pak het linker, middelste of rechter deel van een tekenreeks met tekst uit.

## <a name="description"></a>Beschrijving
De functies **Links**, **Midden** en **Rechts** retourneren een gedeelte van een tekenreeks.

* **Links** retourneert de begintekens van een tekenreeks.
* **Midden** retourneert de middelste tekens van een tekenreeks.
* **Rechts** retourneert de eindtekens van een tekenreeks.

Als u één tekenreeks als een argument opgeeft, retourneert de functie het gedeelte van de tekenreeks dat u hebt opgevraagd. Als u een [tabel](../working-with-tables.md) met één kolom opgeeft die tekenreeksen bevat, retourneert de functie een tabel met één kolom met de gedeelten die u van deze tekenreeksen hebt opgevraagd. Als u een tabel met meerdere kolommen opgeeft, kunt u deze omvormen tot een tabel met één kolom, zoals in [working with tables (werken met tabellen)](../working-with-tables.md) is beschreven.

Als de beginpositie negatief is of voorbij het einde van de tekenreeks valt, retourneert **Midden** *leeg*.  U kunt de lengte van een tekenreeks controleren door de functie **[Len](function-len.md)** te gebruiken. Als u meer tekens opvraagt dan de tekenreeks bevat, retourneert de functie zo veel mogelijk tekens.

## <a name="syntax"></a>Syntaxis
**Left**( *String*, *NumberOfCharacters* )<br>**Mid**( *String*, *StartingPosition*, *NumberOfCharacters* )<br>**Right**( *String*, *NumberOfCharacters* )

* *String* - vereist. De tekenreeks waarvan het resultaat moet worden uitgepakt.
* *StartingPosition* - vereist (alleen **Mid**).  De beginpositie.  Het eerste teken van de tekenreeks is positie 1.
* *NumberOfCharacters* - vereist.  Het aantal tekens dat moet worden geretourneerd.

**Left**( *SingleColumnTable*, *NumberOfCharacters* )<br>**Mid**( *SingleColumnTable*, *StartingPosition*, *NumberOfCharacters* )<br>**Right**( *SingleColumnTable*, *NumberOfCharacters* )

* *TabelMetEénKolom* - vereist. Een tabel met één kolom met tekenreeksen waarvan de resultaten moeten worden uitgepakt.
* *StartingPosition* - vereist (alleen **Mid**).  De beginpositie.  Het eerste teken van de tekenreeks is positie 1.
* *NumberOfCharacters* - vereist.  Het aantal tekens dat moet worden geretourneerd.

## <a name="examples"></a>Voorbeelden
### <a name="single-string"></a>Eén tekenreeks
De voorbeelden in deze sectie gebruiken een besturingselement voor tekstinvoer als hun [gegevensbron](../working-with-data-sources.md). Het besturingselement wordt **Auteur** genoemd en bevat de tekenreeks "E. E. Cummings".

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **Left( Auteur.Text, 5 )** |Extraheert maximaal vijf tekens vanaf het begin van de tekenreeks. |"E. E." |
| **Mid( Auteur.Text, 7, 4 )** |Extraheert maximaal vier tekens vanaf het zevende teken uit de tekenreeks. |"Cumm" |
| **Right( Auteur.Text, 5 )** |Extraheert maximaal vijf tekens vanaf het einde van de tekenreeks. |"mings" |

### <a name="single-column-table"></a>Tabel met één kolom
Elk voorbeeld in deze sectie pakt tekenreeksen met de naam **Personen** uit de [kolom](../working-with-tables.md#columns) **Adres** van deze gegevensbron uit en retourneert een tabel met één kolom die de resultaten bevat:

![](media/function-left-mid-right/people-table.png)

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **Left( ShowColumns(&nbsp;Personen,&nbsp;"Adres"&nbsp;), 8 )** |Extraheert de eerste acht tekens van elke tekenreeks. |<style> img { max-width: none } </style> ![](media/function-left-mid-right/people-table-left.png) |
| **Mid( ShowColumns(&nbsp;Personen,&nbsp;"Adres"&nbsp;), 5, 7 )** |Extraheert de middelste zeven tekens van elke tekenreeks, beginnend bij het vijfde teken. |![](media/function-left-mid-right/people-table-mid.png) |
| **Right( ShowColumns(&nbsp;Personen,&nbsp;"Adres"&nbsp;), 7 )** |Extraheert de laatste zeven tekens van elke tekenreeks. |![](media/function-left-mid-right/people-table-right.png) |

### <a name="step-by-step-example"></a>Stapsgewijs voorbeeld
1. Importeer of maak een [verzameling](../working-with-data-sources.md#collections) met de naam **Inventaris** en geef deze weer in een galerie, zoals wordt beschreven in de eerste procedure in [Tekst en afbeeldingen weergeven in een galerie](../show-images-text-gallery-sort-filter.md).
2. Stel de eigenschap **[Text](../controls/properties-core.md)** van het onderste label in de galerie in op deze functie:
   
    **Right(ThisItem.Productnaam, 3)**
   
    Het label toont de laatste drie tekens van elke productnaam.

