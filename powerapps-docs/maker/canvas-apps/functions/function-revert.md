---
title: De functie Revert | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functie Revert in PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/21/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: a1a9a02917ed5202e24ce0228b8b581e2f45b8b9
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42831556"
---
# <a name="revert-function-in-powerapps"></a>De functie Revert in PowerApps
Herstelt de [records](../working-with-tables.md#records) in een [gegevensbron](../working-with-data-sources.md) en wist fouten.

## <a name="description"></a>Beschrijving
De functie **Revert** herstelt een hele gegevensbron of één record in die gegevensbron. U ziet dan wijzigingen die andere gebruikers hebben aangebracht.

Voor de herstelde records wist **Revert** ook eventuele fouten in de [tabel](../working-with-tables.md) die de functie **[Errors](function-errors.md)** retourneert.

Als de functie **[Errors](function-errors.md)** een conflict meldt nadat **[Patch](function-patch.md)** of een andere gegevensbewerking is uitgevoerd, kunt u **Revert** gebruiken om de conflicterende versie van de record te herstellen en de wijziging opnieuw toepassen.

**Revert** heeft geen retourwaarde. U kunt deze functie alleen gebruiken in een [gedragsformule](../working-with-formulas-in-depth.md).

## <a name="syntax"></a>Syntaxis
**Revert**( *DataSource* [, *Record* ] )

* *DataSource* - vereist. De gegevensbron die u wilt herstellen.
* *Record* - optioneel.  De record die u wilt herstellen.  Als u geen record opgeeft, wordt de hele gegevensbron hersteld.

## <a name="example"></a>Voorbeeld
In dit voorbeeld herstelt u de gegevensbron met de naam **IJs** die begint met de gegevens in deze tabel:

![](media/function-revert/icecream.png)

Een gebruiker op een ander apparaat wijzigt de eigenschap **Aantal** van de record **Aardbeien** in **400**.  Rond dezelfde tijd wijzigt u dezelfde eigenschap van dezelfde record in **500** aangezien u niet op de hoogte bent van de andere wijziging.

U gebruikt de functie **[Patch](function-patch.md)** om de record bij te werken:<br>
**Patch( IJs, First( Filter( IJs, Smaak = "Aardbeien" ) ), { Aantal: 500 } )**

U controleert de tabel **[Fouten](function-errors.md)** en vindt een fout:

| Record | [Kolom](../working-with-tables.md#columns) | Bericht | Fout |
| --- | --- | --- | --- |
| **{ ID: 1, Smaak: "Aardbeien", Aantal: 300 }** |*leeg* |**"De record die u probeert te wijzigen, is gewijzigd door een andere gebruiker.  Herstel de record en probeer het opnieuw."** |**ErrorKind.Conflict** |

Op basis van de kolom **Fout** is er een knop **Opnieuw laden** waarvoor de eigenschap **[OnSelect](../controls/properties-core.md)** ingesteld op deze formule:<br>
**Revert( IJs, First( Filter( IJs, Smaak = "Aardbeien" ) ) )**

Nadat u de knop **Opnieuw laden** hebt geselecteerd, is de tabel **[Fouten](function-errors.md)** [leeg](function-isblank-isempty.md) en is de nieuwe waarde voor **Aardbeien** geladen:

![](media/function-revert/icecream-after.png)

U past uw wijziging toe boven op de vorige wijziging en de wijziging lukt omdat het conflict is opgelost.

![](media/function-revert/icecream-success.png)

