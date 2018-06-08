---
title: De functie Find | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functie Find in PowerApps
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
ms.openlocfilehash: 8e95f03c934e0989269ff9ec21b432f609cb13ad
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "31826080"
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

