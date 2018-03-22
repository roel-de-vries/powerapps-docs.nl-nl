---
title: De functie Char | Microsoft Docs
description: Referentie-informatie, inclusief syntaxis en voorbeelden, voor de functie Char in PowerApps
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
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 7ce510840845b1a1df2d590c4f3ffdddfc5bfb9c
ms.sourcegitcommit: 33099e6197c0139679cd08c42e9e2a5717904c92
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/12/2018
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

