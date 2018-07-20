---
title: De functie Table | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functie Table in PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta anneta
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 94354c2e96a61f3f64362ced99d0bc27e1463c2f
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/13/2018
ms.locfileid: "39015059"
---
# <a name="table-function-in-powerapps"></a>De functie Table in PowerApps
Hiermee maakt u een tijdelijke [tabel](../working-with-tables.md).

## <a name="description"></a>Beschrijving
De functie **Table** maakt een tabel van een argumentlijst met [records](../working-with-tables.md#records).

De [kolommen](../working-with-tables.md#columns) van de tabel vormen de samenvoeging van de eigenschappen van alle records in het argument. Een *lege* waarde wordt toegevoegd aan elke kolom waarvoor een record geen waarde bevat.

Een tabel is een waarde in PowerApps, net zoals een tekenreeks of getal. U kunt een tabel opgeven als een argument voor een functie en functies kunnen een tabel retourneren als resultaat. **Table** maakt geen permanente tabel. In plaats daarvan wordt een tijdelijke tabel geretourneerd, bestaande uit de argumenten.  U kunt deze tijdelijke tabel opgeven als argument voor een andere functie of de tabel visualiseren in een galerie of insluiten in een andere tabel.  Zie [werken met tabellen](../working-with-tables.md) voor meer informatie.

U kunt ook een tabel met één kolom maken met de syntaxis **[ waarde1, waarde2,... ]**.

## <a name="syntax"></a>Syntaxis
**Table**( *Record1* [, *Record2*, ... ] )

* *Record(s)* - vereist. De records die aan de tabel moeten worden toegevoegd.

## <a name="examples"></a>Voorbeelden
* Stel de eigenschap **[Items](../controls/properties-core.md)** van een keuzelijst in op deze formule:
  <br>**Table({Kleur:"rood"}, {Kleur:"groen"}, {Kleur:"blauw"})**
  
    In de keuzelijst wordt elke kleur weergegeven als een optie.
* Voeg een tekstgalerie toe en stel de eigenschap **[Items](../controls/properties-core.md)** ervan in op deze functie:<br>
  **Table({Item:"Violin123", Location:"France", Owner:"Fabrikam"}, {Item:"Violin456", Location:"Chile"})**
  
    De galerie bevat twee records die beide de naam en de locatie van een item bevatten. Slechts één record bevat de naam van de eigenaar.

