---
title: Functie Shuffle | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functie Shuffle in PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 39307e9c7b3de7bfae151709827c409fcc7087ad
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/13/2018
ms.locfileid: "39014231"
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

