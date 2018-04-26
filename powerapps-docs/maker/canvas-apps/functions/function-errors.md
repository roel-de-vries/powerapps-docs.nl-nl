---
title: De functie Errors | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functie Errors in PowerApps
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 11/11/2015
ms.author: gregli
ms.openlocfilehash: 9e68b7580092c70f7e40ddd1d0b57118f6d592d8
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
---
# <a name="errors-function-in-powerapps"></a>De functie Errors in PowerApps
Biedt foutinformatie voor eerdere wijzigingen in een [gegevensbron](../working-with-data-sources.md).

## <a name="overview"></a>Overzicht
Fouten kunnen ontstaan wanneer een [record](../working-with-tables.md#records) van een gegevensbron is gewijzigd.  Er zijn veel oorzaken mogelijk, zoals netwerkstoringen, ontoereikende machtigingen en bewerkingsconflicten.  

De functie **[Patch](function-patch.md)** en andere gegevensfuncties retourneren niet rechtstreeks fouten. In plaats daarvan retourneren ze het resultaat van hun bewerking. Nadat een gegevensfunctie is uitgevoerd, kunt u de functie **Errors** gebruiken om de details van fouten op te halen.  U kunt controleren of er sprake is van fouten met de functie **[IsEmpty]** in de formule **IsEmpty ( Errors (...) )**.

U kunt bepaalde fouten voorkomen voordat ze plaatsvinden met behulp van de functies **[Validate](function-validate.md)** en **[DataSourceInfo](function-datasourceinfo.md)**.  Zie [Werken met gegevensbronnen](../working-with-data-sources.md) voor meer suggesties voor het werken met en voorkomen van fouten.

## <a name="description"></a>Beschrijving
De functie **Errors** retourneert een [tabel](../working-with-tables.md) met fouten die de volgende [kolommen](../working-with-tables.md#columns) bevat:

* **Record**.  De record in de gegevensbron waarin de fout optrad.  Als de fout is opgetreden tijdens het maken van een record, is deze kolom *leeg*.
* **Column**.  De kolom die de fout veroorzaakt heeft, indien de fout kan worden toegeschreven aan één kolom. Zo niet, dan is deze kolom *leeg*.
* **Message**.  Een beschrijving van de fout.  Deze fouttekenreeks kan worden weergegeven voor de eindgebruiker.  Let erop dat dit bericht mogelijk is gegenereerd door de gegevensbron en lang kan zijn en onbewerkte kolomnamen kan bevatten die mogelijk onduidelijk zijn voor de gebruiker.
* **Error**.  Een foutcode die kan worden gebruikt in formules om te helpen bij het oplossen van de fout:

| ErrorKind | Beschrijving |
| --- | --- |
| ErrorKind.Conflict |Er is nog een wijziging gemaakt in dezelfde record, wat leidt tot een conflict.  Gebruik de functie **[Refresh](function-refresh.md)** om de record opnieuw te laden en probeer de wijziging vervolgens opnieuw. |
| ErrorKind.ConstraintViolation |Er zijn een of meer beperkingen overtreden. |
| ErrorKind.CreatePermission |Er is een poging gedaan om een record te maken en de huidige gebruiker is niet gemachtigd om records te maken. |
| ErrorKind.DeletePermission |Er is een poging gedaan om een record te verwijderen en de huidige gebruiker is niet gemachtigd om records te verwijderen. |
| ErrorKind.EditPermission |Er is een poging gedaan om een record te bewerken en de huidige gebruiker is niet gemachtigd om records te bewerken. |
| ErrorKind.GeneratedValue |Er is een poging gedaan om een kolom te wijzigen die de gegevensbron automatisch genereert. |
| ErrorKind.MissingRequired |De waarde voor een vereiste kolom ontbreekt in de record. |
| ErrorKind.None |Er is geen fout. |
| ErrorKind.NotFound |Er is een poging gedaan om een record te bewerken of te verwijderen, maar de record kan niet worden gevonden.  De record is mogelijk door een andere gebruiker gewijzigd. |
| ErrorKind.ReadOnlyValue |Er is een poging gedaan om een kolom te wijzigen die alleen-lezen is. |
| ErrorKind.Sync |Er is een fout gerapporteerd door de gegevensbron.  Controleer de kolom Bericht voor meer informatie. |
| ErrorKind.Unknown |Er is een onbekend type fout opgetreden. |
| ErrorKind.Validation |Er is een algemeen validatieprobleem gedetecteerd dat niet binnen een van de andere categorieën past. |

Fouten kunnen worden geretourneerd voor de gehele gegevensbron of alleen voor een geselecteerde rij door het argument *Record* te verstrekken aan de functie.  

**[Patch](function-patch.md)** of een andere gegevensfunctie retourneert mogelijk een *lege* waarde als bijvoorbeeld een record niet kan worden gemaakt. U kunt *leeg* doorgeven naar **Fouten** waarna het in dergelijke gevallen de juiste foutinformatie retourneert.  Als u opnieuw een gegevensfunctie voor dezelfde gegevensbron gebruikt, worden deze foutgegevens gewist.

Als er geen fouten zijn, is de tabel die door **Fouten** wordt geretourneerd [leeg](function-isblank-isempty.md) en kan deze worden getest met de functie **[IsEmpty](function-isblank-isempty.md)**.

## <a name="syntax"></a>Syntaxis
**Fouten**( *DataSource* [, *Record* ] )

* *DataSource* - vereist. De gegevensbron waarvoor u fouten wilt ophalen.
* *Record* - optioneel.  Een specifieke record waarvoor u fouten wilt ophalen. Als u dit argument niet opgeeft, retourneert de functie fouten voor de gehele gegevensbron.

## <a name="examples"></a>Voorbeelden
### <a name="step-by-step"></a>Stap voor stap
In dit voorbeeld werken we met de gegevensbron **IJs**:

![](media/function-errors/icecream.png)

Via de app laadt een gebruiker de record Chocolade in een formulier voor gegevensinvoer en wijzigt vervolgens de waarde van **Hoeveelheid** in 90.  De record waarmee moet worden gewerkt is geplaatst in de [contextvariabele](../working-with-variables.md#create-a-context-variable) **RecordBewerken**:

* **UpdateContext( { RecordBewerken: Eerste( Filteren( IJs, Smaak = "Chocolade" ) ) } )**

Gebruik de functie **[Patch](function-patch.md)** om deze wijziging door te voeren in de gegevensbron:

* **Patch( IJs, RecordBewerken, Gallery.Updates )**

waarbij **Gallery.Updates** resulteert in **{ Hoeveelheid: 90 }**, aangezien alleen de eigenschap **Quantity** is gewijzigd.

Helaas heeft iemand anders net voordat de functie **[Patch](function-patch.md)** werd aangeroepen de **Hoeveelheid** voor Chocolade gewijzigd in 80.  PowerApps detecteert dit en staat de conflicterende wijziging niet toe.  U kunt hierop controleren met de volgende formule:

* **IsEmpty( Errors ( IJs, RecordBewerken ) )**

Deze retourneert **false**, omdat de functie **Errors** de volgende tabel heeft geretourneerd:

| Record | Column | Message | Error |
| --- | --- | --- | --- |
| { Smaak: "Chocolade", Hoeveelheid: 100 } |*leeg* |"Een andere gebruiker heeft de record gewijzigd die u probeert te wijzigen. Laad de record opnieuw en probeer het nogmaals." |ErrorKind.Conflict |

U kunt een label op het formulier plaatsen om de gebruiker deze fout te tonen.

* Om de fout te tonen, stelt u de eigenschap **[Text](../controls/properties-core.md)** van het label in op deze formule:<br>
  **Label.Text = First(Errors( IceCream, EditRecord )).Message**

U kunt ook een knop **Opnieuw laden** aan het formulier toevoegen, zodat de gebruiker efficiënt het conflict kan oplossen.

* Als u wilt dat de knop alleen wordt weergegeven wanneer er een conflict is opgetreden, stelt u de eigenschap **[Visible](../controls/properties-core.md)** in op deze formule:<br>
    **!IsEmpty( Lookup( Errors( IJs, RecordBewerken ), Error = ErrorKind.Conflict ) )**
* Om de wijziging terug te draaien wanneer de gebruiker de knop selecteert, stelt u de eigenschap **[OnSelect](../controls/properties-core.md)** van de knop in op deze formule:<br>
    **ReloadButton.OnSelect = Revert( IJs, RecordBewerken )**

