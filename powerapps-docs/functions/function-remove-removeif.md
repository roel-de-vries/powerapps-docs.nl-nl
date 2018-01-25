---
title: Functies Remove en RemoveIf | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functies Remove en RemoveIf in PowerApps
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
ms.date: 10/21/2015
ms.author: gregli
ms.openlocfilehash: 736d634e9db5bc97ceb69852c59b229c7478863b
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/23/2018
---
# <a name="remove-and-removeif-functions-in-powerapps"></a>De functies Remove en RemoveIf in PowerApps
Hiermee verwijdert u [records](../working-with-tables.md#records) uit een [gegevensbron](../working-with-data-sources.md).

## <a name="description"></a>Beschrijving
### <a name="remove-function"></a>De functie Remove
Gebruik de functie **Remove** als u een of meer specifieke records uit een gegevensbron wilt verwijderen.  

Voor [verzamelingen](../working-with-data-sources.md#collections) moet de hele record overeenkomen. U kunt het argument **All** gebruiken om alle exemplaren van een record te verwijderen. Anders wordt slechts één exemplaar van de record verwijderd.

### <a name="removeif-function"></a>De functie RemoveIf
Gebruik de functie **RemoveIf** om een of meer records te verwijderen op basis van een voorwaarde of een reeks voorwaarden. Elke voorwaarde kan elke formule zijn die resulteert in **true** of **false** en kan verwijzen naar [kolommen](../working-with-tables.md#columns) in de gegevensbron, waarbij de naam van de kolom wordt gebruikt. Elke voorwaarde wordt afzonderlijk geëvalueerd voor elke record en de record wordt verwijderd als alle voorwaarden **true** zijn.

**Remove** en **RemoveIf** retourneren de gewijzigde gegevensbron als een [tabel](../working-with-tables.md). U kunt beide functies alleen in [gedragsformules](../working-with-formulas-in-depth.md) gebruiken.

U kunt ook de functie **[Clear](function-clear-collect-clearcollect.md)** gebruiken om alle records uit een gegevensbron te verwijderen.

### <a name="delegation"></a>Delegering
[!INCLUDE [delegation-no](../includes/delegation-no.md)]

## <a name="syntax"></a>Syntaxis
**Remove**( *DataSource*, *Record1* [, *Record2*, ... ] [, **All** ] )

* *DataSource* - vereist. De gegevensbron met de record of records die u wilt verwijderen.
* *Record(s)* - vereist. De record of records die u wilt verwijderen.
* **All** - optioneel. In een verzameling kan een record meerdere keren voorkomen.  U kunt het argument **All** toevoegen als u alle exemplaren van de record wilt verwijderen.

**Remove**( *DataSource*, *Table* [, **All** ] )

* *DataSource* - vereist. De gegevensbron met de records die u wilt verwijderen.
* *Table* - vereist. Een tabel met records die moeten worden verwijderd.
* **All** - optioneel. In een verzameling kan een record meerdere keren voorkomen.  U kunt het argument **All** toevoegen als u alle exemplaren van de record wilt verwijderen.

**RemoveIf**( *DataSource*, *Condition* [, ... ] )

* *DataSource* - vereist. De gegevensbron met de record of records die u wilt verwijderen.
* *Condition(s)* - vereist. Een formule die evalueert als **true** voor de records die u wilt verwijderen.  U kunt kolomnamen uit de *DataSource* gebruiken in de formule.  Als u meerdere *Conditions* opgeeft, moeten alle voorwaarden evalueren als **true** voor de record of records die u wilt verwijderen.

## <a name="examples"></a>Voorbeelden
In deze voorbeelden verwijdert u een of meer records in een gegevensbron genaamd **IJs** die begint met de gegevens in deze tabel:

![](media/function-remove-removeif/icecream.png)

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **Remove(&nbsp;IJs,<br>First(&nbsp;Filter (&nbsp;IJs,&nbsp;Smaak="Chocolade"&nbsp;)&nbsp;) )** |Hiermee verwijdert u de record **Chocolade** uit de gegevensbron. |<style> img { max-width: none } </style> ![](media/function-remove-removeif/icecream-no-chocolate.png)<br><br>De gegevensbron **IJs** is gewijzigd. |
| **Remove(&nbsp;IJs,<br>First(&nbsp;Filter(&nbsp;IJs,&nbsp;Smaak="Chocolade"&nbsp;)&nbsp;) First(&nbsp;Filter(&nbsp;IJs,&nbsp;Smaak="Aardbeien"&nbsp;)&nbsp;) )** |Verwijdert twee records uit de gegevensbron. |![](media/function-remove-removeif/icecream-only-vanilla.png)<br><br>De gegevensbron **IJs** is gewijzigd. |
| **RemoveIf(&nbsp;IJs, Aantal&nbsp;>&nbsp;150)** |Hiermee verwijdert u records waarvan **Aantal** groter is dan **150**. |![](media/function-remove-removeif/icecream-only-chocolate.png)<br><br>De gegevensbron **IJs** is gewijzigd. |
| **RemoveIf(&nbsp;IJs, Aantal&nbsp;>&nbsp;150, Left(&nbsp;Smaak,&nbsp;1&nbsp;) = "S" )** |Hiermee verwijdert u records waarvan **Aantal** groter is dan 150 en **Smaak** begint met een **S**. |![](media/function-remove-removeif/icecream-no-strawberry.png)<br><br><br>De gegevensbron **IJs** is gewijzigd. |
| **RemoveIf(&nbsp;IJs, true )** |Verwijdert alle records uit de gegevensbron. |![](media/function-remove-removeif/icecream-empty.png)<br><br>De gegevensbron **IJs** is gewijzigd. |

### <a name="step-by-step"></a>Stap voor stap
1. Importeer of maak een verzameling met de naam **Inventaris** en geef deze weer in een galerie, zoals wordt beschreven in [Gegevens weergeven in een galerie](../show-images-text-gallery-sort-filter.md).
2. In de galerie, stelt u de eigenschap **[OnSelect](../controls/properties-core.md)** van de afbeelding in op deze expressie:<br>**Remove(Inventaris, ThisItem)**
3. Druk op F5 en selecteer vervolgens een afbeelding in de galerie.<br>Het item wordt verwijderd uit de galerie en de verzameling.

