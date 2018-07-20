---
title: De functies First, FirstN, Last en LastN | Microsoft Docs
description: Referentie-informatie, inclusief syntaxis en voorbeelden, voor de functies First, FirstN, Last en LastN in PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 3d94a3a250041ec7524460640f0bca4351ddcacf
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/13/2018
ms.locfileid: "39021108"
---
# <a name="first-firstn-last-and-lastn-functions-in-powerapps"></a>De functies First, FirstN, Last en LastN in PowerApps
Retourneert de eerste of laatste set [records](../working-with-tables.md#records) van een tabel.

## <a name="description"></a>Beschrijving
De functie **First** retourneert de eerste record van een [tabel](../working-with-tables.md).

De functie **FirstN** retourneert de eerste set records van een tabel. Het tweede argument specificeert het aantal records dat moet worden geretourneerd.

De functie **Last** retourneert de laatste record van een tabel.

De functie **LastN** retourneert de laatste set records van een tabel. Het tweede argument specificeert het aantal records dat moet worden geretourneerd.

**First** en **Last** retourneren één record.  **FirstN** en **LastN** retourneren een tabel, zelfs als u slechts één record opgeeft.

[!INCLUDE [delegation-no](../../../includes/delegation-no.md)]

## <a name="syntax"></a>Syntaxis
**First**( *Table* )<br>**Last**( *Table* )

* *Table* - vereist. De tabel waarop de bewerking wordt toegepast.

**FirstN**( *Table* [, *NumberOfRecords* ] )<br>**LastN**( *Table* [, *NumberOfRecords* ] )

* *Tabel* - vereist. De tabel waarop de bewerking wordt toegepast.
* *NumberOfRecords* - optioneel.  Het aantal te retourneren records. Als u dit argument niet opgeeft, retourneert de functie één record.

## <a name="examples"></a>Voorbeelden
Deze formule retourneert de eerste record van een tabel met de naam **Werknemers**:<br>
**First(Werknemers)**

Deze formule retourneert de laatste 15 records van een tabel met de naam **Werknemers**:<br>
**LastN(Werknemers, 15)**

