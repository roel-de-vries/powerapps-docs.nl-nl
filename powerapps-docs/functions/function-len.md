---
title: De functie Len | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functie Len in PowerApps
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
ms.openlocfilehash: 06f8e7a80adc7a2175f2da7ab98fb1966d8cf015
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="len-function-in-powerapps"></a>De functie Len in PowerApps
Retourneert de lengte van een teksttekenreeks.

## <a name="description"></a>Beschrijving
Als u één tekenreeks als argument opgeeft, vormt de geretourneerde waarde de lengte als een getal.  Als u een [tabel](../working-with-tables.md) met één kolom opgeeft die tekenreeksen bevat, is de geretourneerde waarde een tabel met één kolom die de lengte van elke tekenreeks bevat. Als u een tabel met meerdere kolommen hebt, kunt u deze omvormen tot een tabel met één kolom, zoals in [working with tables (werken met tabellen)](../working-with-tables.md) is beschreven.

Als u een [lege](function-isblank-isempty.md) tekenreeks opgeeft, retourneert **Len** 0.

## <a name="syntax"></a>Syntaxis
**Len**( *Tekenreeks* )

* *String* - vereist. De tekenreeks die moet worden gemeten.

**Len**( *TabelMetEénKolom* )

* *TabelMetEénKolom* - vereist. Een tabel met één kolom met tekenreeksen die moeten worden gemeten.

## <a name="examples"></a>Voorbeelden
### <a name="single-string"></a>Eén tekenreeks
De [gegevensbron](../working-with-data-sources.md) bestaat voor de voorbeelden in deze sectie uit een besturingselement voor tekstinvoer met de naam **Auteur** en de tekenreeks "E. E. Cummings".

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **Len( Author.Text )** |Meet de lengte van de tekenreeks in het besturingselement **Auteur**. |14 |
| **Len( "" )** |Meet de lengte van een lege tekenreeks. |0 |

### <a name="single-column-table"></a>Tabel met één kolom
De gegevensbron in het eerste voorbeeld in deze sectie heeft **Personen** en bevat deze gegevens:

![](media/function-len/people-table.png)

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **Len( ShowColumns(&nbsp;Personen,&nbsp;"Adres"&nbsp;) )** |In de [kolom](../working-with-tables.md#columns) **Adres** van de tabel **Personen**:<br><ul><li>Meet de lengte van elke tekenreeks.</li><li>Retourneert een tabel met één kolom die de lengte van elke tekenreeks bevat.</li> |<style> img { max-width: none } </style> ![](media/function-len/people-table-len.png) |
| **Len( [ "Hallo", "aan de", "wereld", "" ] )** |In de kolom **[Waarde](function-value.md)** van de interne tabel:<br><ul><li>Meet de lengte van elke tekenreeks.</li><li>Retourneert een tabel met één kolom die de lengte van elke tekenreeks bevat.</li> |![](media/function-len/people-table-len-inline.png) |

