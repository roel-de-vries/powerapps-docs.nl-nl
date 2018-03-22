---
title: Functies Replace en Substitute | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functies Replace en Substitute in PowerApps
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
ms.openlocfilehash: fe8f1e1cc8e54c3abf4b44bbfe46d9f96a7adfe7
ms.sourcegitcommit: 33099e6197c0139679cd08c42e9e2a5717904c92
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/12/2018
---
# <a name="replace-and-substitute-functions-in-powerapps"></a>De functies Replace en Substitute in PowerApps
Een deel van een tekenreeks vervangen door een andere tekenreeks.

## <a name="description"></a>Beschrijving
De functie **Replace** identificeert de tekst die moet worden vervangen aan de hand van een beginpositie en lengte.  

De functie **Substitute** identificeert de tekst die moet worden vervangen door een tekenreeks te zoeken.  Als meer dan één overeenkomst wordt gevonden, kunt u bepalen welke wordt vervangen.

Als u één tekenreeks doorgeeft, is de geretourneerde waarde de gewijzigde tekenreeks.  Als u een [tabel](../working-with-tables.md) met één kolom doorgeeft die tekenreeksen bevat, is de geretourneerde waarde een tabel met één kolom met gewijzigde tekenreeksen. Als u een tabel met meerdere kolommen hebt, kunt u deze omvormen tot een tabel met één kolom, zoals wordt beschreven in [werken met tabellen](../working-with-tables.md).

## <a name="syntax"></a>Syntaxis
**Replace**( *String*, *StartingPosition*, *NumberOfCharacters*, *NewString* )

* *String* - vereist. De tekenreeks die moet worden vervangen.
* *StartingPosition* - vereist.  De tekenpositie waarop de vervanging moet beginnen. Het eerste teken van *String* bevindt zich op positie 1.
* *NumberOfCharacters* - vereist.  Het aantal tekens dat moet worden vervangen in *String*.
* *NewString* - vereist.  De vervangende tekenreeks. Het aantal tekens in dit argument kan verschillen van het argument *NumberOfCharacters*.

**Substitute**( *String*, *OldString*, *NewString* [, *InstanceNumber* ] )

* *String* - vereist. De tekenreeks die moet worden vervangen.
* *OldString* - vereist.  De tekenreeks die u wilt vervangen.
* *NewString* - vereist.  De vervangende tekenreeks. *OldString* en *NewString* kunnen verschillende lengtes hebben.
* *InstanceNumber* - optioneel. Standaard wordt het eerste exemplaar van *OldString* vervangen. Als *String* meer dan één exemplaar bevat, kunt u opgeven welk exemplaar moet worden vervangen.

**Replace**( *SingleColumnTable*, *StartingPosition*, *NumberOfCharacters*, *NewString* )

* *TabelMetEénKolom* - vereist. Een tabel met één kolom die tekenreeksen bevat die moeten worden vervangen.
* *StartingPosition* - vereist.  De tekenpositie waarop de vervanging moet beginnen.  Het eerste teken van elke tekenreeks in de tabel bevindt zich op positie 1.
* *NumberOfCharacters* - vereist.  Het aantal tekens dat moet worden vervangen in elke tekenreeks.
* *NewString* - vereist.  De vervangende tekenreeks. Het aantal tekens in dit argument kan verschillen van het argument *NumberOfCharacters*.

**Substitute**( *SingleColumnTable*, *OldString*, *NewString* [, *InstanceNumber* ] )

* *TabelMetEénKolom* - vereist. Een tabel met één kolom die tekenreeksen bevat die moeten worden vervangen.
* *OldString* - vereist.  De tekenreeks die u wilt vervangen.
* *NewString* - vereist.  De vervangende tekenreeks. *OldString* en *NewString* kunnen verschillende lengtes hebben.
* *InstanceNumber* - optioneel. Standaard wordt het eerste exemplaar van *OldString* vervangen. Als de tabel meer dan één exemplaar bevat, kunt u opgeven welk exemplaar moet worden vervangen.

