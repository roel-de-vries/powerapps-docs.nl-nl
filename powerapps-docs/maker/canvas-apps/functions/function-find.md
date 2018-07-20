---
title: De functie Find | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functie Find in PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: cd2028434fb9199595360ddafdb2e41d32e6cf3a
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/13/2018
ms.locfileid: "39019521"
---
# <a name="find-function-in-powerapps"></a>De functie Find in PowerApps
Hiermee zoekt u een tekenreeks met tekst, als deze bestaat, binnen een andere tekenreeks.

## <a name="description"></a>Beschrijving
De functie **Find** zoekt naar een tekenreeks binnen een andere tekenreeks en is hoofdlettergevoelig. Als u het hoofdlettergebruik wilt negeren, gebruikt u eerst de functie **[Lower](function-lower-upper-proper.md)** voor de argumenten.

**Find** retourneert de beginpositie van de gevonden tekenreeks.  Het eerste teken van de tekenreeks is positie 1. **Find** retourneert *leeg* als de tekenreeks waarin u zoekt niet de tekenreeks bevat die u zoekt.

## <a name="syntax"></a>Syntaxis
**Find**( *FindString*, *WithinString* [, *StartingPosition* ] )

* *FindString* - vereist.  De tekenreeks die moet worden gevonden.
* *WithinString* - vereist.  De tekenreeks waarin moet worden gezocht.
* *StartingPosition* - optioneel.  De beginpositie vanaf waar moet worden gezocht.  Het eerste teken is positie 1.

