---
title: Functie Shuffle | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functie Shuffle in PowerApps
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
ms.openlocfilehash: 6d981c410b22dd9db52cdf077a00e6eaae83be75
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "31827362"
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

