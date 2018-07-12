---
title: Functie Validate | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functie Validate in PowerApps
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 11/01/2015
ms.author: gregli
ms.openlocfilehash: d1c0a8bdcab3f8a3ba74414ab902092432a34fff
ms.sourcegitcommit: 79b8842fb0f766a0476dae9a537a342c8d81d3b3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2018
ms.locfileid: "37899198"
---
# <a name="validate-function-in-powerapps"></a>De functie Validate in PowerApps
De functie **Validate** controleert of de waarde van één [kolom](../working-with-tables.md#columns) of een volledige [record](../working-with-tables.md#records) geldig is voor een [gegevensbron](../working-with-data-sources.md).  

## <a name="description"></a>Beschrijving
Voordat een gebruiker een gegevenswijziging doorvoert, kunt u direct feedback geven over de geldigheid van die bijdrage, wat resulteert in een betere gebruikerservaring.

Gegevensbronnen kunnen informatie bieden over wat geldige waarden binnen een record zijn. Deze informatie kan bestaan uit diverse beperkingen, zoals deze voorbeelden:

* of een kolom een waarde vereist
* hoe lang een tekenreeks mag zijn
* hoe hoog en hoe laag een getal mag zijn
* hoe vroeg en hoe laat een datum mag zijn

De functie **Validate** gebruikt deze informatie om te bepalen of een waarde geldig is en moet een geschikt foutbericht retourneren als dat niet het geval is. U kunt de functie **[DataSourceInfo](function-datasourceinfo.md)** gebruiken om dezelfde informatie weer te geven die **Validate** gebruikt.

Gegevensbronnen variëren in de hoeveelheid validatie-informatie die ze leveren en soms leveren ze deze informatie helemaal niet. **Validate** kan alleen waarden verifiëren op basis van deze informatie. Zelfs als **Validate** geen probleem vindt, kan het toepassen van de gegevenswijziging mislukken. U kunt de functie **[Errors](function-errors.md)** gebruiken om informatie over de fout te verkrijgen.

Als **Validate** een probleem vindt, retourneert de functie een foutbericht dat u kunt weergeven aan de gebruiker van de app. Als alle waarden geldig zijn, retourneert **Validate** de waarde [leeg](function-isblank-isempty.md). Wanneer u werkt met een [verzameling](../working-with-data-sources.md#collections) die geen validatie-informatie bevat, zijn waarden altijd geldig.

## <a name="syntax"></a>Syntaxis
**Validate**( *DataSource*, *Column*, *Value* )

* *DataSource* - vereist. De gegevensbron waarmee moet worden gevalideerd.
* *Column* - vereist. De kolom die moet worden gevalideerd.
* *Value* - vereist. De waarde die voor de geselecteerde kolom moet worden gevalideerd.

**Validate**( *DataSource*, *OriginalRecord*, *Updates* )

* *DataSource* - vereist. De gegevensbron waarmee moet worden gevalideerd.
* *OriginalRecord* - vereist.  De record waarvan updates moeten worden gevalideerd.
* *Updates* - vereist.  De wijzigingen die worden toegepast op de oorspronkelijke record.

## <a name="examples"></a>Voorbeelden
Voor deze voorbeelden moeten de waarden in de kolom **Percentage** van de gegevensbron **Scores** een getal tussen 0 en 100 inclusief zijn. De functie retourneert *leeg* als de gegevens slagen voor de validatie. Anders retourneert de functie een foutbericht.

### <a name="validate-with-a-single-column"></a>Valideren met één kolom

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **Validate( Scores, Percentage, 10 )** |Controleert of **10** een geldige waarde is voor de kolom **Percentage** in de gegevensbron **Scores**. |*leeg* |
| **Validate( Scores, Percentage, 120 )** |Controleert of **120** een geldige waarde is voor de kolom **Percentage** in de gegevensbron **Scores**. |"Waarden moeten tussen 0 en 100 liggen." |

### <a name="validate-with-a-complete-record"></a>Valideren met een volledige record

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **Validate( Scores, EditRecord, Gallery.Updates )** |Controleert of **10** een geldige waarde is voor de kolom **Percentage** in de gegevensbron **Scores**. |*leeg* |
| **Validate( Scores, EditRecord, Gallery.Updates )** |Controleert of **120** een geldige waarde is voor de kolom **Percentage** in de gegevensbron **Scores**. |"Waarden moeten tussen 0 en 100 liggen." |

