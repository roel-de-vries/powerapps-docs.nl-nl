---
title: Functies AddColumns, DropColumns RenameColumns en ShowColumns | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functies AddColumns, DropColumns, RenameColumns en ShowColumns in PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 08/24/2018
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 056c5e1142b3a34776e72f788f5b2cef9e3b2a27
ms.sourcegitcommit: 3dc330d635aaf5bc689efa6bd39826d6e396c832
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/09/2018
ms.locfileid: "48875894"
---
# <a name="addcolumns-dropcolumns-renamecolumns-and-showcolumns-functions-in-powerapps"></a>De functies AddColumns, DropColumns RenameColumns en ShowColumns in PowerApps
Hiermee geeft u een [tabel](../working-with-tables.md) vorm door [kolommen](../working-with-tables.md#columns) op te nemen, uit te sluiten, te selecteren of door de naam ervan te wijzigen.

## <a name="overview"></a>Overzicht
Met deze functies bepaalt u de vorm van een tabel door de kolommen aan te passen:

* Een tabel met meerdere kolommen terugbrengen tot één kolom voor gebruik met functies die één kolom ondersteunen, zoals **[Lower](function-lower-upper-proper.md)** of **[Abs](function-numericals.md)**.  
* Een berekende kolom toevoegen aan een tabel (bijvoorbeeld de kolom **Totaalprijs** met de uitkomst van de vermenigvuldiging van **Aantal** met **Prijs per eenheid**).
* Een kolom een zinvollere naam geven die wordt weergegeven aan gebruikers of gebruikt in formules.

Een tabel is een waarde in PowerApps, net zoals een tekenreeks of getal.  U kunt een tabel opgeven als argument in een formule en functies kunnen een tabel retourneren als resultaat. De functies die in dit onderwerp worden beschreven veranderen een tabel niet. In plaats daarvan nemen van een tabel als argument en retourneren ze een nieuwe tabel waarop een transformatie is toegepast.  Zie [Werken met tabellen](../working-with-tables.md) voor meer informatie.  

U kunt de kolommen van een [gegevensbron](../working-with-data-sources.md) niet wijzigen met behulp van deze functies. U moet de gegevens bij de bron wijzigen. U kunt kolommen toevoegen aan een [verzameling](../working-with-data-sources.md#collections) met de functie **[Collect](function-clear-collect-clearcollect.md)**.  Zie [Werken met gegevensbronnen](../working-with-data-sources.md) voor meer informatie.  

## <a name="description"></a>Beschrijving
De functie **AddColumns** voegt een kolom toe aan een tabel en een formule definieert de waarden in die kolom. Bestaande kolommen blijven ongewijzigd.

De formule wordt geëvalueerd voor elke record in de tabel.
[!INCLUDE [record-scope](../../../includes/record-scope.md)]

De functie **DropColumns** sluit kolommen uit van een tabel.  Alle andere kolommen blijven ongewijzigd. **DropColumns** sluit kolommen uit en **ShowColumns** neemt kolommen op.

Gebruik de functie **RenameColumns** om één of meer kolommen van een tabel een nieuwe naam te geven door ten minste één argumentpaar op te geven dat de naam van een kolom in de tabel opgeeft (de oude naam die u wilt vervangen) en de naam van een kolom dat niet in de tabel staat (de nieuwe naam die u wilt gebruiken). De oude naam moet bestaan in de tabel, de nieuwe naam juist niet. Elke kolomnaam mag slechts één keer voorkomen in de argumentenlijst, hetzij als oude kolomnaam, hetzij als nieuwe kolomnaam. Als u een kolom de naam wilt geven van een bestaande kolom, moet u eerst de bestaande kolom verwijderen met **DropColumns**, of de bestaande kolom een nieuwe naam geven door de functie **RenameColumns** in te nesten in een andere kolom.

De functie **ShowColumns** neemt kolommen uit een tabel op en sluit alle andere kolommen uit. U kunt de functie **ShowColumns** gebruiken om een tabel met één kolom te maken van een tabel met meerdere kolommen.  **ShowColumns** neemt kolommen op en **DropColumns** sluit kolommen uit.  

Voor al deze functies is het resultaat een nieuwe tabel waarop de transformatie is toegepast.  De oorspronkelijke tabel wordt niet gewijzigd.

[!INCLUDE [delegation-no](../../../includes/delegation-no.md)]

## <a name="syntax"></a>Syntaxis
**AddColumns**( *Table*, *ColumnName1*, *Formula1* [, *ColumnName2*, *Formula2*, ... ] )

* *Tabel* - vereist.  De tabel waarop de bewerking wordt toegepast.
* *NaamKolom(men)* - vereist. Namen van een of meer kolommen die moeten worden toegevoegd.  Voor dit argument moet u een tekenreeks opgeven (bijvoorbeeld **"Naam"**, inclusief dubbele aanhalingstekens).
* *Formula(s)* - vereist.  De formule(s) die moet(en) worden geëvalueerd voor elke record. Het resultaat wordt toegevoegd als de waarde van de bijbehorende nieuwe kolom. In deze formule kunt u verwijzen naar andere kolommen in de tabel.

**DropColumns**( *Table*, *ColumnName1* [, *ColumnName2*, ... ] )

* *Tabel* - vereist.  De tabel waarop de bewerking wordt toegepast.
* *Kolomnaam* - vereist. Namen van een of meer kolommen die moeten worden verwijderd. Voor dit argument moet u een tekenreeks opgeven (bijvoorbeeld **"Naam"**, inclusief dubbele aanhalingstekens).

**RenameColumns**( *Tabel*, *OldColumneName1*, *NewColumnName1* [, *OldColumnName2*, *NewColumnName2*, ... ] )

* *Tabel* - vereist.  De tabel waarop de bewerking wordt toegepast.
* *OldColumnName* - vereist. Naam van een kolom in de originele tabel die een nieuwe naam moet krijgen. Dit element verschijnt als eerst in het argumentpaar (of als eerst in ieder argumentpaar als de formule meer dan één paar bevat). Deze naam moet een tekenreeks zijn (bijvoorbeeld **"Name"**, inclusief de dubbele aanhalingstekens).
* *NewColumnName* - vereist. Vervangende naam. Dit element verschijnt als laatst in het argumentpaar (of als laatst in ieder argumentpaar als de formule meer dan één paar bevat). Voor dit argument moet u een tekenreeks opgeven (bijvoorbeeld **"Klantnaam"**, inclusief dubbele aanhalingstekens).

**ShowColumns**( *Table*, *ColumnName1* [, *ColumnName2*, ... ] )

* *Tabel* - vereist.  De tabel waarop de bewerking wordt toegepast.
* *NaamKolom(men)* - vereist. Namen van een of meer kolommen die moeten worden opgenomen. Voor dit argument moet u een tekenreeks opgeven (bijvoorbeeld **"Naam"**, inclusief dubbele aanhalingstekens).

## <a name="examples"></a>Voorbeelden
In de voorbeelden in deze sectie wordt de gegevensbron **IJsverkoop** gebruikt, die de gegevens in deze tabel bevat:

![](media/function-table-shaping/icecream.png)

Geen van deze voorbeelden wijzigt de gegevensbron **IJsverkoop**. Elke functie transformeert de waarde van de gegevensbron als een tabel en retourneert die waarde als resultaat.

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **AddColumns( IJsverkoop, "Omzet", PrijsPerEenheid * AantalVerkocht)** |Voegt de kolom **Omzet** toe aan het resultaat.  Voor elke record wordt **PrijsPerEenheid * AantalVerkocht** geëvalueerd en het resultaat wordt in de nieuwe kolom geplaatst. |<style> img { max-width: none; } </style> ![](media/function-table-shaping/icecream-add-revenue.png) |
| **DropColumns( IJsverkoop, "PrijsPerEenheid" )** |Sluit de kolom **PrijsPerEenheid** uit van het resultaat. Gebruik deze functie om kolommen uit te sluiten en gebruik de functie **ShowColumns** om kolommen op te nemen. |![](media/function-table-shaping/icecream-drop-price.png) |
| **ShowColumns( IJsverkoop, "Smaak" )** |Neemt alleen de kolom **Smaak** op in het resultaat. Gebruik deze functie om kolommen op te nemen en gebruik de functie **DropColumns** om kolommen uit te sluiten. |![](media/function-table-shaping/icecream-select-flavor.png) |
| **RenameColumns( IJsverkoop, "PrijsPerEenheid", "Prijs")** |Verandert de naam van de kolom **PrijsPerEenheid** in het resultaat. |![](media/function-table-shaping/icecream-rename-price.png) |
| **RenameColumns( IJsverkoop, "PrijsPerEenheid", "Prijs", "AantalVerkocht", "Nummer")** |Geeft de kolommen **PrijsPerEenheid** en **AantalVerkocht** in het resultaat een andere naam. |![](media/function-table-shaping/icecream-rename-price-quant.png) |
| **DropColumns(<br>RenameColumns(<br>AddColumns( IJsverkoop, "Omzet",<br>PrijsPerEenheid * AantalVerkocht),<br>"PrijsPerEenheid", "Prijs" ),<br>"Aantal" )** |Voert de volgende tabeltransformaties op volgorde uit, waarbij de formule van binnen naar buiten wordt verwerkt: <ol><li>Voegt de kolom **Omzet** toe op basis van de berekening per record van **PrijsPerEenheid * Aantal**.<li>Wijzigt de naam van **PrijsPerEenheid** in **Prijs**.<li>Sluit de kolom **Aantal** uit.</ol>  Let erop dat de volgorde belangrijk is. U kunt bijvoorbeeld niet rekenen met de kolom **PrijsPerEenheid** nadat de naam ervan is gewijzigd. |![](media/function-table-shaping/icecream-all-transforms.png) |

### <a name="step-by-step"></a>Stap voor stap
1. Importeer of maak een verzameling met de naam **Inventaris**, zoals wordt beschreven in de eerste subprocedure in [Tekst en afbeeldingen weergeven in een galerie](../show-images-text-gallery-sort-filter.md).
2. Voeg een knop toe en stel de eigenschap **[BijSelecteren](../controls/properties-core.md)** ervan in op deze formule:
   
    **ClearCollect(Inventaris2, RenameColumns(Inventaris, "Productnaam", "Jasnaam"))**
3. Druk op F5, selecteer de knop die u zojuist hebt gemaakt en druk op Esc om terug te keren naar de ontwerpwerkruimte.
4. Selecteer **Verzamelingen** in het menu **Bestand**.
5. Bevestig dat u een verzameling genaamd **Inventaris2** hebt gemaakt. De nieuwe verzameling bevat dezelfde informatie als **Inventaris** , behalve dat de kolom genaamd **Productnaam** in **Inventaris** nu **Jasnaam** heet in **Inventaris2**.

