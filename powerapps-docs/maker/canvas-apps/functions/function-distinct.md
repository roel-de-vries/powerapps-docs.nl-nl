---
title: De functie Distinct | Microsoft Docs
description: Referentie-informatie, inclusief syntaxis en voorbeelden, voor de functie Distinct in PowerApps
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
ms.openlocfilehash: 17a2f2cfca16c5589f74ac434b36326037146b16
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42843193"
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

