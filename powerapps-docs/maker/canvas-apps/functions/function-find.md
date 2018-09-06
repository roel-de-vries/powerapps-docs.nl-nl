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
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 04f257b40e778d3611203f2bdc17aad5554a4ac6
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42865947"
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

