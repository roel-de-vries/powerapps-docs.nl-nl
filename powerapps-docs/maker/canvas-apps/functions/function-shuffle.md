---
title: Functie Shuffle | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functie Shuffle in PowerApps
services: ''
suite: powerapps
documentationcenter: na
author: gregli-msft
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 672caee3b683bb0222b15a65cdad4edce78c4fe4
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2018
---
# <a name="shuffle-function-in-powerapps"></a>De functie Shuffle in PowerApps
Hiermee worden de [records](../working-with-tables.md#records) in een [tabel](../working-with-tables.md) in willekeurige volgorde geplaatst.

## <a name="description"></a>Beschrijving
De functie **Shuffle** wijzigt de volgorde van de records in een tabel.

**Shuffle** retourneert een tabel met dezelfde [kolommen](../working-with-tables.md#columns) en hetzelfde aantal rijen als het argument.

## <a name="syntax"></a>Syntaxis
**Shuffle**( *Table* )

* *Tabel* - vereist.  Tabel waarvan u de volgorde wilt wijzigen.

## <a name="example"></a>Voorbeeld
Als u informatie over speelkaarten hebt opgeslagen in een [verzameling](../working-with-data-sources.md#collections) genaamd **Kaarten**, retourneert deze formule een kopie van die verzameling in willekeurige volgorde.

**Shuffle(Kaarten)**

