---
title: De functie Char | Microsoft Docs
description: Referentie-informatie, inclusief syntaxis en voorbeelden, voor de functie Char in PowerApps
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
ms.openlocfilehash: b5d63b26498b94943f5340d9f57f3255390c7c94
ms.sourcegitcommit: 79b8842fb0f766a0476dae9a537a342c8d81d3b3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2018
ms.locfileid: "37895978"
---
# <a name="char-function-in-powerapps"></a>De functie Char in PowerApps
Hiermee wordt een tekencode naar een tekenreeks vertaald.

## <a name="description"></a>Beschrijving
De functie **Char** retourneert een tekenreeks met het juiste ASCII-teken voor uw platform.

## <a name="syntax"></a>Syntaxis
**Char**( *CharacterCode* )

* *CharacterCode* - vereist. ASCII-tekencode om te vertalen.

## <a name="examples"></a>Voorbeelden

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **Char( 65 )** |Retourneert het teken dat overeenkomt met de ASCII-code 65. |A |
| **Char( 105 )** |Retourneert het teken dat overeenkomt met de ASCII-code 105. |i |
| **Char( 35 )** |Retourneert het teken dat overeenkomt met de ASCII-code 35. |# |

