---
title: De functie Find | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functie Find in PowerApps
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
ms.openlocfilehash: f43575fbe84173485ef39f3988bf6a049a4b9417
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
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

