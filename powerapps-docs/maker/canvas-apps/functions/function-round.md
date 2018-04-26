---
title: De functies Round, RoundDown en RoundUp | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functies Round, RoundDown en RoundUp in PowerApps
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
ms.openlocfilehash: 07771027ea728d65bfb35d79fb67bdef1ac80f1a
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
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

