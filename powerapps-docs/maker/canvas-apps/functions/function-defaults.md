---
title: De functie Defaults | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functie Defaults in PowerApps
services: ''
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 11/01/2015
ms.author: gregli
ms.openlocfilehash: b62b2b8575d1ff0e5a55a97db6e6650af5a593c1
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "31825804"
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

