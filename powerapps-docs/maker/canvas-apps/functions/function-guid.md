---
title: De functie GUID | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis, voor de functie GUID in PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 06/09/2018
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: a45aa397aa65e11ab01e04367d859e11bf552f66
ms.sourcegitcommit: 3aeb9381fbeb66cf08355d9a3d0f00ce2737e256
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/29/2018
ms.locfileid: "43164588"
---
# <a name="guid-function-in-powerapps"></a>De functie GUID in PowerApps
Hiermee wordt een GUID-tekenreeks ([Globally Unique Identifier](https://en.wikipedia.org/wiki/Universally_unique_identifier)) naar een GUID-waarde geconverteerd of wordt een nieuwe GUID-waarde gemaakt.

## <a name="description"></a>Beschrijving
Gebruik de functie **GUID** om een tekenreeks die de hexadecimale waarde van een GUID bevat te converteren naar een GUID-waarde die kan worden doorgegeven aan een database. GUID-waarden worden gebruikt als sleutels door databasesystemen als Common Data Service for Apps en SQL Server.

De doorgegeven tekenreeks mag bestaan uit hoofdletters of kleine letters, maar moet 32 hexadecimale cijfers bevatten in een van deze indelingen:

- **"123e4567-e89b-12d3-a456-426655440000"** (afbreekstreepjes in de standaardlocaties)
- **"123e4567e89b12d3a456426655440000"** (geen streepjes)

Als u geen argument opgeeft, maakt deze functie een nieuwe GUID.

Als u een GUID-waarde wilt converteren naar een tekenreeks, gebruikt u deze eenvoudig in de context van een tekenreeks. De GUID-waarde wordt geconverteerd naar een hexadecimale tekenreeksweergave met afbreekstreepjes en kleine letters. 

> [!NOTE]
> Er is momenteel een bekend probleem waarmee GUID-waarden rechtstreeks met tekenreeksen kunnen worden vergeleken.  Neem geen afhankelijkheid op voor dit gedrag, omdat dit binnenkort wordt gewijzigd, waardoor een foutmelding wordt gegenereerd.  Als u een tekenreeks wilt vergelijken met een GUID-waarde, zet u eerst de tekenreeks om in een GUID-waarde met de GUID-functie en vergelijkt u vervolgens de GUID-waarden.  Hiermee worden beide waarden genormaliseerd voor een schone vergelijking.  Als u dit niet doet, wordt de GUID-waarde automatisch geconverteerd naar een tekenreeks. De vergelijking is dan afhankelijk van de opmaak van de tekenreeks en de hoofdletters en kleine letters van eventuele alfanumerieke tekens in de tekenreeks.

> [!NOTE]
> Er is momenteel geen manier om een GUID-waarde te lezen of schrijven naar een database.  Ondersteuning voor Common Data Service en SQL Server is in de planning. 

## <a name="volatile-functions"></a>Vluchtige functies
**GUID** is een vluchtige functie wanneer deze zonder argument wordt gebruikt. Steeds wanneer de functie wordt geëvalueerd, wordt een andere waarde geretourneerd.  

Wanneer een vluchtige functie in een gegevensstroomformule wordt gebruikt, retourneert deze alleen een andere waarde als de formule waarin deze wordt weergegeven, opnieuw wordt geëvalueerd. Als er niets anders verandert in de formule, heeft deze dezelfde waarde gedurende de uitvoering van uw app.

Een label-besturingselement waarvoor bijvoorbeeld de eigenschap **Tekst** is ingesteld op **GUID()**, wijzigt niet wanneer uw app actief is. Alleen het sluiten en opnieuw openen van de app leidt tot een andere waarde.

De functie wordt opnieuw geëvalueerd als deze deel uitmaakt van een formule waarin iets anders is gewijzigd. Als we de eigenschap **Tekst** van een **Label**-besturingselement bijvoorbeeld instellen op deze formule, wordt steeds een GUID gegenereerd wanneer de gebruiker de waarde van het besturingselement **Tekstinvoer** wijzigt:

**TextInput1.Text & " " & GUID()**

Wanneer de functie wordt gebruikt in een [gedragsformule](../working-with-formulas-in-depth.md), wordt **GUID** steeds geëvalueerd als de formule wordt geëvalueerd. Zie de voorbeelden verderop in dit onderwerp voor meer informatie.

## <a name="syntax"></a>Syntaxis
**GUID**( [ *GUIDString* ] )


* *GUIDString* - optioneel.  Een tekenreeks die de hexadecimale waarde van een GUID bevat. Als er geen tekenreeks is opgegeven, wordt een nieuwe GUID gemaakt.

## <a name="examples"></a>Voorbeelden

#### <a name="basic-usage"></a>Basisgebruik

Een GUID-waarde retourneren op basis van de hexadecimale tekenreeksweergave:

* **GUID( "0f8fad5b-d9cb-469f-a165-70867728950e" )**

U kunt de GUID-tekenreeks ook zonder afbreekstreepjes opgeven. Deze formule retourneert de dezelfde GUID-waarde:

* **GUID( "0f8fad5bd9cb469fa16570867728950e" )**

Voor gebruik in context stelt u het veld **Status** van een nieuwe databaserecord in op een gevestigde waarde:

* **Patch( Products, Default( Products ), { Status: GUID( "F9168C5E-CEB2-4faa-B6BF-329BF39FA1E4" ) } )**

U wilt GUID’s waarschijnlijk niet tonen aan uw gebruikers, maar GUID's kunnen u helpen fouten in uw app op te sporen. Als u de waarde van het veld **Status** wilt weergeven in het record dat u hebt gemaakt in het vorige voorbeeld, stelt u de eigenschap **Tekst** van een **Label**-besturingselement in op deze formule:

* **First( Products ).Status**

Het besturingselement **Label** geeft **f9168c5e-ceb2-4faa-b6bf-329bf39fa1e4** weer.

#### <a name="create-a-table-of-guids"></a>Een tabel met GUID’s maken

1. Stel de eigenschap **[OnSelect](../controls/properties-core.md)** van een besturingselement **[Knop](../controls/control-button.md)** in op deze formule:

    **ClearCollect( NewGUIDs, ForAll( [ 1, 2, 3, 4, 5 ], GUID() ) )**

    Deze formule maakt een tabel met één kolom die wordt gebruikt om vijf keer te herhalen, wat resulteert in vijf GUID’s.

1. Voeg een besturingselement **[Gegevenstabel](../controls/control-data-table.md)** toe, stel de eigenschap **Items** in op **NewGUIDs** en geef het veld **Waarde** weer.

1. Houd de Alt-toets ingedrukt en selecteer de knop door erop te klikken of te tikken.

    De gegevenstabel geeft een overzicht van GUID's weer:

    ![Een scherm met een gegevenstabel met vijf verschillende GUID-waarden](media/function-guid/guid-collection-1.png)

1. Selecteer de knop opnieuw om een andere lijst met GUID’s weer te geven:

    ![Hetzelfde scherm met een gegevenstabel met een nieuwe set van vijf verschillende GUID-waarden](media/function-guid/guid-collection-2.png)

Als u een enkele GUID wilt genereren in plaats van een tabel, gebruikt u deze formule:

**Set( NewGUID, GUID() )**
