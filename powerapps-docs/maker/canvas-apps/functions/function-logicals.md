---
title: Functies En, Of en Niet | Microsoft Docs
description: Referentie-informatie, inclusief syntaxis en voorbeelden, voor de functies En, Of en Not in PowerApps
author: gregli-msft
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
ms.openlocfilehash: 438076c5e1b3e0643af809755078fbc491cea9c5
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42850345"
---
# <a name="and-or-and-not-functions-in-powerapps"></a>Functies En, Of en Niet in PowerApps
Booleaanse logische functies, meestal gebruikt om de resultaten van vergelijkingen en tests te manipuleren.

## <a name="description"></a>Beschrijving
De functie **And** retourneert **true** als alle argumenten **true** zijn.  De **&&**-[operator](operators.md) is gelijk aan **En**.

De functie **Or** retourneert **true** als een van zijn argumenten **true** is.  De **||**-operator is gelijk aan **Of**.

De functie **Not** retourneert **true** als zijn argument **false** is; hij retourneert **false** als zijn argument **true** is.  De operator **!** is gelijk aan **Not**.

Deze functies weken met logische waarden. Er kan niet rechtstreeks een nummer of een tekenreeks worden doorgegeven. In plaats daarvan moet een vergelijking of test worden gedaan. Een vergelijking zoals **x > 1** is bijvoorbeeld een logische formule die de booleaanse waarde **true** oplevert als **x** groter is dan **1**. Als **x** kleiner is dan **1**, levert de formule **false** op.

## <a name="syntax"></a>Syntaxis
**And**( *LogicalFormula1*, *LogicalFormula2* [, *LogicalFormula3*, ... ] )<br>
**Or**( *LogicalFormula1*, *LogicalFormula2* [, *LogicalFormula3*, ... ] )<br>
**Not**( *LogicalFormula* )

* *LogicalFormula(s)* - vereist.  Logische formules die moeten worden geëvalueerd en waarnaar moet worden gehandeld.

## <a name="examples"></a>Voorbeelden
### <a name="step-by-step"></a>Stap voor stap
Gebruik deze functie om te bepalen of de waarde van een schuifregelaar buiten het bereik van 50 tot 100 valt:

**Or(Slider1.Value < 50, Slider1.Value> 100)**

Als een [tabel](../working-with-tables.md) een [kolom](../working-with-tables.md#columns) **Schuld** en een kolom **Salaris** bevat, kunt u deze functie in een kolom **Result** gebruiken om **true** weer te geven in alle rijen waarin de waarde in de kolom **Schuld** **HR** is of waarin de waarde in de kolom **Salaris** groter is dan **200000**:

**Of(Schuld = HR, Salaris >= 200000)**

Gebruik als alternatief de operator II om dezelfde resultaten te krijgen als die de vorige formule retourneert:

**Slider1.Value < 50 || Slider1.Value> 100**

**Schuld = "HR" || Salaris > 200000**

