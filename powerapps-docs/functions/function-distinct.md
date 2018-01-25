---
title: De functie Distinct | Microsoft Docs
description: Referentie-informatie, inclusief syntaxis en voorbeelden, voor de functie Distinct in PowerApps
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
ms.openlocfilehash: b4e2a7c44696a57d01db5ac39da65ad782f0edac
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/23/2018
---
# <a name="distinct-function-in-powerapps"></a>De functie Distinct in PowerApps
Geeft een overzicht van de [records](../working-with-tables.md#records) in een [tabel](../working-with-tables.md) en verwijdert dubbele gegevens.

## <a name="description"></a>Beschrijving
De functie **Distinct** evalueert een formule voor elke record van een tabel. **Distinct** retourneert een tabel met één kolom die de resultaten bevat, waaruit dubbele waarden zijn verwijderd.  

[!INCLUDE [record-scope](../includes/record-scope.md)]

## <a name="syntax"></a>Syntaxis
**Distinct**( *Table*, *Formula* )

* *Tabel* - vereist.  De tabel om te evalueren.
* *Formule* - vereist.  De formule die moet worden geëvalueerd voor elke record.

## <a name="example"></a>Voorbeeld
Als u een tabel **Werknemers** hebt met een kolom **Afdeling**, toont deze functie elke unieke afdelingsnaam in die kolom, ongeacht hoe vaak elke naam in de kolom voorkomt:

**Distinct(Werknemers, Afdeling)**

