---
title: De functie Distinct | Microsoft Docs
description: Referentie-informatie, inclusief syntaxis en voorbeelden, voor de functie Distinct in PowerApps
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
ms.openlocfilehash: 101c28f2b4ac8135a9b4def9421f886f373105bf
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
---
# <a name="distinct-function-in-powerapps"></a>De functie Distinct in PowerApps
Geeft een overzicht van de [records](../working-with-tables.md#records) in een [tabel](../working-with-tables.md) en verwijdert dubbele gegevens.

## <a name="description"></a>Beschrijving
De functie **Distinct** evalueert een formule voor elke record van een tabel. **Distinct** retourneert een tabel met één kolom die de resultaten bevat, waaruit dubbele waarden zijn verwijderd.  

[!INCLUDE [record-scope](../../../includes/record-scope.md)]

## <a name="syntax"></a>Syntaxis
**Distinct**( *Table*, *Formula* )

* *Tabel* - vereist.  De tabel om te evalueren.
* *Formule* - vereist.  De formule die moet worden geëvalueerd voor elke record.

## <a name="example"></a>Voorbeeld
Als u een tabel **Werknemers** hebt met een kolom **Afdeling**, toont deze functie elke unieke afdelingsnaam in die kolom, ongeacht hoe vaak elke naam in de kolom voorkomt:

**Distinct(Werknemers, Afdeling)**

