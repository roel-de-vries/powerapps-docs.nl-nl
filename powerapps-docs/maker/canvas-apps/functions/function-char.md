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
ms.openlocfilehash: 2e8281f401088f43aa7785ac5dcf7b2f07bb6f96
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
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

