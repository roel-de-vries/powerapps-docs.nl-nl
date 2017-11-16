---
title: De functie Defaults | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functie Defaults in PowerApps
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
ms.date: 11/01/2015
ms.author: gregli
ms.openlocfilehash: eb1c6b802eff4aa5bd02a2ec52626b8788c42b73
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
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

