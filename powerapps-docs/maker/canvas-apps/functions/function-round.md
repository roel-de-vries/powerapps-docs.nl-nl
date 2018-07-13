---
title: De functies Round, RoundDown en RoundUp | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functies Round, RoundDown en RoundUp in PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 182106097fb08d6ba2a3689048e9e33c5383ff57
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/13/2018
ms.locfileid: "39016416"
---
# <a name="round-rounddown-and-roundup-functions-in-powerapps"></a>De functies Round, RoundDown en RoundUp in PowerApps
Deze functies ronden een getal af.

## <a name="description"></a>Beschrijving
De functies**Round**, **RoundDown** en **RoundUp** ronden een getal af op het opgegeven aantal decimalen:

* **Round** rondt af naar boven als het volgende cijfer een 5 of hoger is. Anders rondt deze functie af naar beneden.
* **RoundDown** rondt altijd af naar beneden op het vorige lagere getal.
* **RoundUp** rondt altijd af naar boven op het volgende hogere getal.

Als u één getal doorgeeft, is de resulterende waarde de afgeronde versie van dit getal.  Als u een [tabel](../working-with-tables.md) met één kolom doorgeeft die getallen bevat, is de geretourneerde waarde een tabel met één kolom met afgeronde getallen. Als u een tabel met meerdere kolommen hebt, kunt u deze omvormen tot een tabel met één kolom, zoals wordt beschreven in [werken met tabellen](../working-with-tables.md).

## <a name="syntax"></a>Syntaxis
**Round**( *Number*, *DecimalPlaces* )<br>**RoundDown**( *Number*, *DecimalPlaces* )<br>**RoundUp**( *Number*, *DecimalPlaces* )

* *Getal* is vereist. Het getal dat moet worden afgerond.
* *DecimalPlaces* - vereist.  Het aantal posities rechts van het decimaalteken waarop moet worden afgerond.  Gebruik 0 als u wilt afronden op een geheel getal.  

