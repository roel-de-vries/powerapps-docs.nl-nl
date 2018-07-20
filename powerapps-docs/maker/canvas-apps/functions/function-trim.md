---
title: Functies Trim en TrimEnds | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functies Trim en TrimEnds in PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 09/09/2016
ms.author: gregli
ms.openlocfilehash: 30a35425fa9abdcaa4cc5300753c111c0fb1c8d2
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/13/2018
ms.locfileid: "39015358"
---
# <a name="trim-and-trimends-functions-in-powerapps"></a>De functies Trim en TrimEnds in PowerApps
Hiermee verwijdert u extra spaties uit een tekenreeks.

## <a name="description"></a>Beschrijving
De functie **Trim** verwijdert alle spaties uit een tekenreeks behalve enkele spaties tussen woorden.  

De functie **TrimEnds** verwijdert alle spaties aan het begin en einde van een tekenreeks, maar spaties tussen woorden blijven intact.

Als u één tekenreeks opgeeft, is de geretourneerde waarde voor beide functies de tekenreeks waarbij eventuele extra spaties zijn verwijderd. Als u een [tabel](../working-with-tables.md) met één kolom opgeeft die tekenreeksen bevat, is de geretourneerde waarde een tabel met één kolom met tekenreeksen waaruit spaties zijn verwijderd. Als u een tabel met meerdere kolommen hebt, kunt u deze omvormen tot een tabel met één kolom, zoals wordt beschreven in [werken met tabellen](../working-with-tables.md).

Doordat de functie **Trim** spaties tussen woorden verwijdert, werkt deze op dezelfde manier als de functie SPATIES.WISSEN in Microsoft Excel. De functie **TrimEnds** komt daarentegen overeen met programmeerfuncties die alleen spaties aan het begin en einde van elke tekenreeks wissen.

## <a name="syntax"></a>Syntaxis
**Trim**( *String* )<br>**TrimEnds**( *String* )

* *String* - vereist. De tekenreeks waaruit spaties moeten worden verwijderd.

**Trim**( *SingleColumnTable* )<br>**TrimEnds**( *SingleColumnTable* )

* *TabelMetEénKolom* - vereist. Een tabel met één kolom met tekenreeksen waaruit spaties moeten worden verwijderd.

## <a name="example"></a>Voorbeeld

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **Trim(&nbsp;"&nbsp;&nbsp;&nbsp;Hallo&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;wereld&nbsp;&nbsp;&nbsp;"&nbsp;)** |Verwijdert alle spaties aan het begin en einde van de tekenreeks en extra spaties in de tekenreeks. |"Hallo wereld" |
| **TrimEnds(&nbsp;"&nbsp;&nbsp;&nbsp;Hallo&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;wereld&nbsp;&nbsp;&nbsp;"&nbsp;)** |Verwijdert alle spaties aan het begin en einde van de tekenreeks. |"Hallo&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;wereld" |

In de volgende voorbeelden wordt een verzameling met één kolom, genaamd **Spaties**, gebruikt die de volgende tekenreeksen bevat:

![](media/function-trim/input-strings.png)

U maakt deze verzameling door de eigenschap **OnSelect** van een besturingselement **[Knop](../controls/control-button.md)** in te stellen op de volgende formule, de voorbeeldmodus te openen en daarna op de knop te klikken of te tikken:
<br>**ClearCollect( Spaties, [ "&nbsp;&nbsp;&nbsp;Jannie&nbsp;&nbsp;&nbsp;Jansen&nbsp;&nbsp;&nbsp;", "&nbsp;&nbsp;&nbsp;&nbsp;Jan&nbsp;&nbsp;&nbsp;en&nbsp;&nbsp;&nbsp;Joke", "Zonder&nbsp;spaties", "&nbsp;&nbsp;&nbsp;Venus,&nbsp;&nbsp;&nbsp;Aarde,&nbsp;&nbsp;&nbsp;Mars&nbsp;&nbsp;", "Olie&nbsp;en&nbsp;Water&nbsp;&nbsp;&nbsp;" ] )**

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **Trim(&nbsp;Spaties&nbsp;)** |Verwijdert alle spaties aan het begin en einde van elke tekenreeks en extra spaties in elke tekenreeks in de verzameling **Spaties**. |<style> img { max-width: none } </style> ![](media/function-trim/output-trim.png) |
| **TrimEnds(&nbsp;Spaties&nbsp;)** |Verwijdert alle spaties aan het begin en einde van elke tekenreeks in de verzameling **Spaties**. |<style> img { max-width: none } </style> ![](media/function-trim/output-trimends.png) |

> [!NOTE]
> Extra spaties worden niet weergegeven als u een verzameling weergeeft door te klikken of tikken op **Verzamelingen** in het menu **Bestand**. Als u de lengte van de tekenreeks wilt controleren, gebruikt u de functie **[Len](function-len.md)**.

