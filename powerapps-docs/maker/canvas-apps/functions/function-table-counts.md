---
title: Functies Count, CountA, CountIf en CountRows | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en een voorbeeld, voor de functies Count, CountA, CountIf en CountRows in PowerApps
services: ''
suite: powerapps
documentationcenter: na
author: gregli-msft
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 7849a666f7c4d2639f09f6197974467bbc7f43cc
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2018
---
# <a name="count-counta-countif-and-countrows-functions-in-powerapps"></a>De functies Count, CountA, CountIf en CountRows in PowerApps
Hiermee worden alle [records](../working-with-tables.md#records) in een [tabel](../working-with-tables.md) geteld of worden alle records geteld die aan een voorwaarde voldoen.

## <a name="description"></a>Beschrijving
De functie **Count** telt het aantal records dat een getal bevat in een tabel met één kolom.

De functie **CountA** telt het aantal records dat niet *leeg* is in een tabel met één kolom. Deze functie telt ook [lege](function-isblank-isempty.md) tekst ("") mee.

De functie **CountIf** telt het aantal records in een tabel dat **true** is voor een logische formule.  De formule kan verwijzen naar [kolommen](../working-with-tables.md#columns) in de tabel.

De functie **CountRows** telt het aantal records in een tabel.

Elk van deze functies retourneert een getal.

[!INCLUDE [delegation-no](../../../includes/delegation-no.md)]

## <a name="syntax"></a>Syntaxis
**Count**( *TabelMetEénKolom* )<br>
**CountA**( *TagelMetEénKolom* )

* *TabelMetEénKolom* - vereist.  De kolom met records die moeten worden geteld.  

**CountIf**( *Table*, *LogicalFormula* )

* *Tabel* - vereist.  De tabel met records die moeten worden geteld.
* *LogicalFormula* - vereist.  De formule die moet worden geëvalueerd voor elke record in de tabel.  Records die **true** retourneren voor deze formule worden geteld.  De formule kan verwijzen naar kolommen in de tabel.

**CountRows**( *Table* )

* *Tabel* - vereist.  De tabel met records die moeten worden geteld.

## <a name="example"></a>Voorbeeld
1. Importeer of maak een [verzameling](../working-with-data-sources.md#collections) met de naam **Inventaris**, zoals wordt beschreven in de eerste subprocedure in [Tekst en afbeeldingen weergeven in een galerie](../show-images-text-gallery-sort-filter.md).
2. Voeg een label toe en stel de eigenschap **[Text](../controls/properties-core.md)** in op deze formule:
   
    **CountIf(Inventaris, EenhedenInVoorraad < 30)**
   
    Het label geeft **2** weer omdat er voor twee producten (Ganymedes en Callisto) minder dan 30 eenheden in voorraad zijn.
3. Voeg nog een label toe en stel de eigenschap **[Text](../controls/properties-core.md)** in op deze formule:
   
    **CountA(Inventaris.EenhedenInVoorraad)**
   
    Het label geeft **5** gegeven, het aantal niet-lege cellen in de kolom **Eenheden in voorraad** kolom.
4. Voeg nog een label toe en stel de eigenschap **[Text](../controls/properties-core.md)** in op deze formule:
   
    **CountRows(Inventaris)**
   
    Het label geeft **5** weer omdat de verzameling vijf rijen bevat.

