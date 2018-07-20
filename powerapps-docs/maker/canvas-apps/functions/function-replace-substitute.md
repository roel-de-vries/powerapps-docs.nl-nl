---
title: Functies Replace en Substitute | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functies Replace en Substitute in PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: d368114a52f428e3bb9403b71adb6557a432e880
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/13/2018
ms.locfileid: "39014507"
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

