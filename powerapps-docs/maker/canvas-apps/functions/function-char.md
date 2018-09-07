---
title: De functie Char | Microsoft Docs
description: Referentie-informatie, inclusief syntaxis en voorbeelden, voor de functie Char in PowerApps
dauthor: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: aec27b788fff8434cfdc4e0e130487f718a42aa6
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42826360"
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

