---
title: De functie Defaults | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functie Defaults in PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/01/2015
ms.author: gregli
ms.openlocfilehash: fe49a14a350e52da1282b1d6e3a41462e87de305
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/13/2018
ms.locfileid: "39014898"
---
# <a name="defaults-function-in-powerapps"></a>De functie Defaults in PowerApps
Retourneert de standaardwaarden voor een [gegevensbron](../working-with-data-sources.md).  

## <a name="description"></a>Beschrijving
Gebruik de functie **Defaults** om een formulier voor gegevensinvoer vooraf in te vullen, waardoor het gemakkelijker in te vullen is.

Deze functie retourneert een [record](../working-with-tables.md#records) die de standaardwaarden voor de gegevensbron bevat.  Als een [kolom](../working-with-tables.md#columns) binnen de gegevensbron geen standaardwaarde bevat, is er geen eigenschap aanwezig.

Gegevensbronnen variëren in de hoeveelheid standaardinformatie die ze leveren en soms leveren ze deze informatie helemaal niet.  Wanneer u werkt met een [verzameling](../working-with-data-sources.md#collections) of een andere gegevensbron die geen ondersteuning voor standaardwaarden biedt, retourneert de functie **Defaults** een [lege](function-isblank-isempty.md) record.

U kunt de functie **Defaults** combineren met de functie **[Patch](function-patch.md)** om [een record te maken](../working-with-data-sources.md).

## <a name="syntax"></a>Syntaxis
**Defaults**( *DataSource* )

* *DataSource* - vereist. De gegevensbron waarvoor u standaardwaarden wilt ophalen.

## <a name="examples"></a>Voorbeelden

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **Defaults(&nbsp;Scores&nbsp;)** |Retourneert de standaardwaarden voor de gegevensbron **Scores**. |**{Score: 0}** |

