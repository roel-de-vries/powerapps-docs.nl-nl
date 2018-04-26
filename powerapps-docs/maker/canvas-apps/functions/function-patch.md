---
title: De functie Patch | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functie Patch in PowerApps
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 10/21/2015
ms.author: gregli
ms.openlocfilehash: d0b2ff351f7026967359f1b4d386a71d7ed5441f
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
---
# <a name="patch-function-in-powerapps"></a>De functie Patch in PowerApps
Wijzigt of maakt een of meer [records](../working-with-tables.md#records) in een [gegevensbron](../working-with-data-sources.md) of voegt records buiten een gegevensbron samen.

Gebruik de functie **Patch** om records te wijzigen in complexe situaties, zoals bij het uitvoeren van updates waarvoor geen gebruikersinteractie is vereist of bij het gebruik van formulieren die meerdere schermen beslaan.

In minder complexe situaties kunt u het besturingselement **Formulier bewerken** gebruiken om records in een gegevensbron gemakkelijker bij te kunnen werken. Wanneer u een besturingselement **Formulier bewerken** toevoegt, biedt u gebruikers de mogelijkheid een formulier in te vullen en worden de wijzigingen vervolgens in een gegevensbron opgeslagen. Zie [Gegevensformulieren begrijpen](../working-with-forms.md) voor meer informatie.

## <a name="overview"></a>Overzicht
Gebruik de functie **Patch** om een of meer records in een gegevensbron te wijzigen.  De waarden van specifieke [velden](../working-with-tables.md#elements-of-a-table) worden gewijzigd zonder dat dit van invloed is op andere eigenschappen. Met deze formule wijzigt u bijvoorbeeld het telefoonnummer van een klant met de naam Contoso:

**Patch( Klanten, First( Filter( Klanten, Naam = "Contoso" ) ), {Telefoon: "1-212-555-1234" } )**

Gebruik **Patch** met de functie **[Defaults](function-defaults.md)** om records te maken. Gebruik dit gedrag om [één scherm](../working-with-data-sources.md) te maken voor zowel het maken als het bewerken van records. Met deze formule maakt u bijvoorbeeld een record voor een klant met de naam Contoso:

**Patch( Klanten, Defaults( Klant ), { Naam: “Contoso” } )**

Zelfs als u niet met een gegevensbron werkt, kunt u **Patch** gebruiken om twee of meer records samen te voegen. Met deze formule worden bijvoorbeeld twee records samengevoegd tot één record met zowel het telefoonnummer als de locatie van Contoso:

**Patch( { Naam: "Contoso", Telefoon: “1-212-555-1234” }, { Naam: "Contoso", Locatie: “Amsterdam”  } )**

## <a name="description"></a>Beschrijving
### <a name="modify-or-create-a-record-in-a-data-source"></a>Een record in een gegevensbron wijzigen of maken
Als u deze functie wilt gebruiken met een gegevensbron, geeft u de gegevensbron op en geeft u vervolgens een basisrecord op:

* Als u een record wilt wijzigen, moet het basisrecord afkomstig zijn van een gegevensbron.  De basisrecord kan afkomstig zijn van de eigenschap **[Items](../controls/properties-core.md)** van een galerie, in een [contextvariabele](../working-with-variables.md#create-a-context-variable) zijn geplaatst of via een ander pad worden aangeleverd. U moet de basisrecord echter kunnen terugleiden naar de gegevensbron.  Dit is belangrijk aangezien de record aanvullende informatie bevat die het mogelijk maakt de record terug te vinden wanneer deze moet worden gewijzigd.  
* Als u een record wilt maken, gebruikt u de functie **[Default](function-defaults.md)** om een basisrecord met standaardwaarden te maken.  

Vervolgens geeft u een of meer wijzigingsrecords op die elk nieuwe eigenschapswaarden bevatten die eigenschapswaarden in het basisrecord overschrijven. Wijzigingsrecords worden verwerkt in de volgorde waarin ze in de lijst met argumenten staan (van het begin naar het eind), waarbij latere eigenschapswaarden eerdere overschrijven.

De geretourneerde waarde van **Patch** is de record die u hebt gewijzigd of gemaakt.  Als u een record hebt gemaakt, kan de retourwaarde eigenschappen bevatten die de gegevensbron automatisch heeft gegenereerd.

Wanneer u een gegevensbron bijwerkt, kunnen zich een of meer problemen voordoen. Gebruik de functie **[Errors](function-errors.md)** om problemen op te sporen en te onderzoeken, zoals wordt beschreven in [Werken met gegevensbronnen](../working-with-data-sources.md).

Gerelateerde functies zijn de functie **[Update](function-update-updateif.md)** , die u kunt gebruiken om een hele record te vervangen, en de functie **[Collect](function-clear-collect-clearcollect.md)**, die u kunt gebruiken om een record te maken.  U kunt de functie **[UpdateIf](function-update-updateif.md)** gebruiken om specifieke eigenschappen van meerdere records te wijzigen op basis van een voorwaarde.

### <a name="modify-or-create-a-set-of-records-in-a-data-source"></a>Een set records in een gegevensbron wijzigen of maken
**Patch** kan ook worden gebruikt om meerdere records met één aanroep te maken of te wijzigen.

In plaats van één basisrecord door te geven, kunt u een tabel met basisrecords opgeven in het tweede argument.  Wijzigingsrecords worden ook aangeleverd in een tabel, waarbij ze één op één moeten overeenkomen met de basisrecords.  Het aantal records in elke wijzigingstabel moet gelijk zijn aan het aantal records in de basistabel.

Wanneer u **Patch** op deze manier gebruikt, is de geretourneerde waarde ook een tabel waarin elke record één op één overeenkomt met de basis- en wijzigingsrecords.

### <a name="merge-records-outside-of-a-data-source"></a>Records samenvoegen buiten een gegevensbron
Geef twee of meer records op die u wilt samenvoegen. Records worden verwerkt in de volgorde waarin ze in de lijst met argumenten staan (van het begin naar het eind), waarbij latere eigenschapswaarden eerdere overschrijven.

**Patch** retourneert de samengevoegde record en wijzigt argumenten of records in gegevensbronnen niet.

## <a name="syntax"></a>Syntaxis
#### <a name="modify-or-create-a-record-in-a-data-source"></a>Een record in een gegevensbron wijzigen of maken
**Patch**( *DataSource*, *BaseRecord*, *ChangeRecord1* [, *ChangeRecord2*, … ])

* *DataSource* - vereist. De gegevensbron die de record bevat die u wilt wijzigen of de record zal bevatten die u gaat maken.
* *BaseRecord* - vereist. De record die moet worden gemaakt of gewijzigd.  Als de record afkomstig van een gegevensbron, wordt de record gezocht en gewijzigd. Als het resultaat van **[Defaults](function-defaults.md)** wordt gebruikt, wordt een record gemaakt.
* *ChangeRecord(s)* - vereist.  Een of meer records die eigenschappen bevatten die moeten worden gewijzigd in de *BaseRecord*.  Wijzigingsrecords worden verwerkt in de volgorde waarin ze in de lijst met argumenten staan (van het begin naar het eind), waarbij latere eigenschapswaarden eerdere overschrijven.

#### <a name="modify-or-create-a-set-of-records-in-a-data-source"></a>Een set records in een gegevensbron wijzigen of maken
**Patch**( *DataSource*, *BaseRecordsTable*, *ChageRecordTable1*, [, *ChangeRecordTable2*, … ] )

* *DataSource* - vereist. De gegevensbron die de records bevat die u wilt wijzigen of de records zal bevatten die u gaat maken.
* *BaseRecordTable* - vereist. Een tabel met records die u wilt maken of wijzigen.  Als de record afkomstig van een gegevensbron, wordt de record gezocht en gewijzigd. Als het resultaat van **[Defaults](function-defaults.md)** wordt gebruikt, wordt een record gemaakt.
* *ChangeRecordTable(s)* - vereist.  Een of meer tabellen met records die eigenschappen bevatten die u wilt wijzigen voor elke record in de *BaseRecordTable*.  Wijzigingsrecords worden verwerkt in de volgorde waarin ze in de lijst met argumenten staan (van het begin naar het eind), waarbij latere eigenschapswaarden eerdere overschrijven.

#### <a name="merge-records"></a>Records samenvoegen
**Patch**( *Record1*, *Record2* [, …] )

* *Record(s)* - vereist.  Ten minste twee records die u wilt samenvoegen. Records worden verwerkt in de volgorde waarin ze in de lijst met argumenten staan (van het begin naar het eind), waarbij latere eigenschapswaarden eerdere overschrijven.

## <a name="examples"></a>Voorbeelden
#### <a name="modify-or-create-a-record-in-a-data-source"></a>Een record wijzigen of maken (in een gegevensbron)
In deze voorbeelden wijzigt of maakt u een record in een gegevensbron genaamd **IJs** die de gegevens in deze [tabel](../working-with-tables.md) bevat en automatisch de waarden in de [kolom](../working-with-tables.md#columns) **ID** genereert:

![](media/function-patch/icecream.png)

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **Patch(&nbsp;IJs,<br>First( Filter( IJs, Smaak="Chocolade") ), {&nbsp;Aantal:&nbsp;400&nbsp;} )** |Wijzigt een record in de gegevensbron **IJs**:<ul><li> De kolom **ID** van de record die moet worden gewijzigd bevat de waarde **1**. (De record **Chocolade** heeft die id.)</li><li>De waarde in de kolom **Aantal** wordt gewijzigd in **400**. |{&nbsp;ID:&nbsp;1, Smaak:&nbsp;"Chocolade", Aantal:&nbsp;400 }<br><br>De vermelding **Chocolade** in de gegevensbron **IJs** is gewijzigd. |
| **Patch( IJs, Defaults(&nbsp;IJs), {&nbsp;Smaak:&nbsp;“Aardbeien”&nbsp;}&nbsp;)** |Maakt een record in de gegevensbron **IJs**:<ul><li>De kolom **ID** bevat de waarde **3**, die de gegevensbron automatisch genereert.</li><li>De kolom **Aantal** bevat **0**, de standaardwaarde voor die kolom in de gegevensbron **IJs**, zoals wordt bepaald door de functie **[Defaults](function-defaults.md)**.<li>De kolom **Smaak** bevat de waarde **Aardbeien**.</li> |{ ID:&nbsp;3, Smaak:&nbsp;“Aardbeien”, Aantal:&nbsp;0&nbsp;}<br><br>De vermelding **Aardbeien** in de gegevensbron **IJs** is gemaakt. |

Nadat de vorige formules zijn geëvalueerd, eindigt de gegevensbron op deze waarden:

![](media/function-patch/icecream-after.png)

#### <a name="merge-records-outside-of-a-data-source"></a>Records samenvoegen (buiten een gegevensbron)
| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **Patch(&nbsp;{&nbsp;Naam:&nbsp;"James",&nbsp;Score:&nbsp;90&nbsp;}, {&nbsp;Naam:&nbsp;"Jim",&nbsp;Geslaagd:&nbsp;true&nbsp;} )** |Voegt twee records buiten een gegevensbron samen:<br><ul><li>De waarden in de kolom **Naam** van elke record komen niet overeen. Het resultaat bevat de waarde (**Jim**) in de record die dichter bij het einde van de lijst met argumenten staat in plaats van de waarde (**James**) in de record die dichter bij het begin staat.</li><li>De eerste record bevat een kolom (**Score**) die niet bestaat in de tweede record. Het resultaat bevat die kolom met de waarde (**90**).</li><li>De tweede record bevat een kolom (**Geslaagd**) die niet bestaat in de eerste record. Het resultaat bevat die kolom met de waarde (**true**). |{&nbsp;Naam:&nbsp;"Jim", Score:&nbsp;90, Geslaagd:&nbsp;true&nbsp;} |

