---
title: De functie Split | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functie Split in PowerApps
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
ms.date: 08/28/2017
ms.author: gregli
ms.openlocfilehash: e1953767c40edbe27a232678bdeaab8cebfdea17
ms.sourcegitcommit: 33099e6197c0139679cd08c42e9e2a5717904c92
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/12/2018
---
# <a name="split-function-in-powerapps"></a>De functie Split in PowerApps
Gebruik deze functie om een teksttekenreeks te splitsen in een tabel met subtekenreeksen.

## <a name="description"></a>Beschrijving
Gebruik de functie **Split** om een teksttekenreeks te splitsen in een tabel met subtekenreeksen.  De functie**Split**is handig als u door komma's gescheiden lijsten wilt verbreken, datums die gebruikmaken van een slash tussen onderdelen en in andere situaties waarin een goed gedefinieerd scheidingsteken wordt gebruikt.  

Er wordt een reeks met scheidingstekens gebruikt om de tekenreeks te splitsen.  De reeks met scheidingstekens kan bestaan uit nul, één of meer tekens die als geheel aanwezig moeten zijn in de tekenreeks.  Als u een tekenreeks met de lengte nul of een *lege* reeks gebruikt, worden alle tekens afzonderlijk uitgesplitst.  De overeenkomende scheidingstekens worden niet in het resultaat opgenomen.  Als er geen scheidingsteken wordt gevonden, wordt de gehele tekenreeks geretourneerd als één resultaat.

Gebruik de functie **[Concat](function-concatenate.md)** om de tekenreeks weer te herstellen (zonder de scheidingstekens).  

## <a name="syntax"></a>Syntaxis
**Split**( *Tekst*, *Scheidingsteken* )

* *Tekst* - vereist.  De tekst die u wilt splitsen.
* *Scheidingsteken* - vereist.  Het scheidingsteken dat moet worden gebruikt bij het splitsen van de tekenreeks.  Kan bestaan uit nul, één of meer tekens.

## <a name="examples"></a>Voorbeelden
| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **Split( "Apples,&nbsp;Oranges,&nbsp;Bananas", "," )** |Hiermee worden de verschillende fruitsoorten gesplitst, met de komma als scheidingsteken.  De splitsing wordt uitgevoerd op basis van alleen de komma en niet de spatie erna, wat resulteert in een spatie vóór "&nbsp;Oranges" en "&nbsp;Bananas". |<style> img { max-width: none; } </style> ![](media/function-split/fruit1.png) |
| **TrimEnds( Split( "Apples,&nbsp;Oranges,&nbsp;Bananas", "," ) )** |Hetzelfde als het vorige voorbeeld, maar in dit geval wordt de spatie verwijderd door de [**TrimEnds**-functie](function-trim.md). De bewerking wordt uitgevoerd op de tabel met één kolom die het resultaat is van **Split**. We zouden ook het scheidingsteken **",&nbsp;"'** kunnen hebben gebruikt, waarin de spatie al is opgenomen na de komma, maar dat zou niet het gewenste resultaat hebben opgeleverd als er geen spatie staat of als er twee spaties staan. |<style> img { max-width: none; } </style> ![](media/function-split/fruit2.png) |
| **Split( "08/28/17", "/" )** |Hiermee wordt de datum uit elkaar gehaald, met een slash als scheidingsteken. |<style> img { max-width: none; } </style> ![](media/function-split/date.png) |
| **Split( "Hello,&nbsp;World", "," )** |Hiermee worden de woorden uit elkaar gehaald, met een komma als scheidingsteken.  Het tweede resultaat begint met een spatie, aangezien dit het teken was direct na de komma. |<style> img { max-width: none; } </style> ![](media/function-split/comma.png) |
| **Split( "Hello,&nbsp;World", "o" )** |Hiermee wordt de tekenreeks gesplitst met behulp van het teken 'o' als het scheidingsteken. |<style> img { max-width: none; } </style> ![](media/function-split/o.png) |
| **Split( "Hello,&nbsp;World", "l" )** |Hiermee wordt de tekenreeks gesplitst met behulp van het teken 'l' als het scheidingsteken. Aangezien er geen tekens staan tussen de twee **l**'s in **Hello**, wordt er een *lege* waarde geretourneerd. |<style> img { max-width: none; } </style> ![](media/function-split/l.png) |
| **Split( "Hello,&nbsp;World", "ll" )** |Hiermee wordt de tekenreeks gesplitst met behulp van de dubbele tekens 'l' als het scheidingsteken. |<style> img { max-width: none; } </style> ![](media/function-split/ll.png) |
| **Split( "Hello,&nbsp;World", "%" )** |Hiermee wordt de tekenreeks gesplitst met het procentteken als het scheidingsteken. Aangezien dit scheidingsteken niet voorkomt in de tekenreeks, wordt de gehele tekenreeks als een resultaat geretourneerd. |<style> img { max-width: none; } </style> ![](media/function-split/percent.png) |
| **Split( "Hello,&nbsp;World", "" )** |Hiermee wordt de tekenreeks uit elkaar gehaald met behulp van een lege tekenreeks als het scheidingsteken (nul tekens). Hierdoor worden alle afzonderlijke tekens van de reeks uit elkaar gehaald. |<style> img { max-width: none; } </style> ![](media/function-split/none.png) |

