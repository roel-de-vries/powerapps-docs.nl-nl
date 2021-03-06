---
title: De functies Collect, Clear en ClearCollect | Microsoft Docs
description: Referentie-informatie, inclusief syntaxis en voorbeelden, voor de functies Collect, Clear en ClearCollect in PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/01/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 8a7c52962c23df5f2efcf76c04aeba528e94217c
ms.sourcegitcommit: 464ee88a958dda11c5de5603c608deab6c9cdcab
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/04/2018
ms.locfileid: "48578737"
---
# <a name="collect-clear-and-clearcollect-functions-in-powerapps"></a>De functies Collect, Clear en ClearCollect in PowerApps
Maakt en wist [verzamelingen](../working-with-data-sources.md#collections) en voegt [records](../working-with-tables.md#records) toe aan elke [gegevensbron](../working-with-data-sources.md).

## <a name="description"></a>Beschrijving
### <a name="collect"></a>Collect
De functie **Collect** voegt records toe aan een gegevensbron. De volgende items kunnen worden toegevoegd:

* Een enkele waarde: de waarde wordt geplaatst in het veld **[Value](function-value.md)** van een nieuwe record.  Alle andere eigenschappen blijven [leeg](function-isblank-isempty.md).
* Een record: elke benoemde eigenschap wordt in de bijbehorende eigenschap van een nieuwe record geplaatst.  Alle andere eigenschappen blijven leeg.
* Een [tabel](../working-with-tables.md): elke record van de tabel wordt toegevoegd als een afzonderlijke record van de gegevensbron, zoals hierboven beschreven. De tabel wordt niet als een geneste tabel aan een record toegevoegd. Om dit te doen, pakt u de tabel eerst in een record in.

Wanneer gebruikt in combinatie met een verzameling, worden er indien nodig aanvullende [kolommen](../working-with-tables.md#columns) gemaakt. De kolommen voor andere gegevensbronnen worden vastgezet door de gegevensbron en er kunnen geen nieuwe kolommen worden toegevoegd.  

Als de gegevensbron nog niet bestaat, wordt er een verzameling gemaakt.

Verzamelingen worden soms gebruikt om globale variabelen te bewaren of een tijdelijke kopie van een gegevensbron te maken. PowerApps zijn gebaseerd op formules die automatisch opnieuw worden berekend terwijl de gebruiker de app gebruikt. Verzamelingen bieden dit voordeel niet en het gebruik ervan kan uw app moeilijker te ontwikkelen en te begrijpen maken. Raadpleeg [Werken met variabelen](../working-with-variables.md) voordat u een collectie op deze manier gebruikt.

U kunt ook de functie **[Patch](function-patch.md)** gebruiken om records in een gegevensbron te maken.

**Collect** retourneert de gewijzigde gegevensbron als een tabel.  **Collect** kan alleen worden gebruikt in een [gedragsformule](../working-with-formulas-in-depth.md).

### <a name="clear"></a>Clear
De functie **Clear** verwijdert alle records van een verzameling.  De kolommen van de verzameling worden behouden.

**Clear** werkt alleen bij verzamelingen en niet bij andere gegevensbronnen.  U kunt hiervoor **[RemoveIf](function-remove-removeif.md)( *DataSource*, true )** gebruiken.  Wees voorzichtig met deze formule. Hiermee worden alle records uit de opslag van de gegevensbron verwijderd, wat van invloed kan zijn op andere gebruikers.

U kunt de functie **[Remove](function-remove-removeif.md)** gebruiken om specifieke records te verwijderen.

**Clear** heeft geen retourwaarde.  Het kan alleen worden gebruikt in een gedragsformule.

### <a name="clearcollect"></a>ClearCollect
De functie **ClearCollect** verwijdert alle records uit een verzameling en voegt vervolgens een andere set records toe aan dezelfde verzameling.  **ClearCollect** biedt de combinatie van **Clear** en **Collect** in één functie.

**ClearCollect** retourneert de gewijzigde verzameling als een tabel.  **ClearCollect** kan alleen worden gebruikt in een gedragsformule.

## <a name="syntax"></a>Syntaxis
**Collect**( *DataSource*, *Item*, ... )

* *DataSource* - vereist. De gegevensbron waaraan u gegevens wilt toevoegen.  Als deze nog niet bestaat, wordt er een nieuwe verzameling gemaakt.
* *Item(s)* - vereist.  Een of meer records of tabellen die u wilt toevoegen aan de gegevensbron.  

**Clear**( *Collection* )

* *Collection* - vereist. De verzameling die u wilt wissen.

**ClearCollect**( *Verzameling*, *Item*, ... )

* *Collection* - vereist. De verzameling die u wilt wissen en vervolgens gegevens aan wilt toevoegen.
* *Item(s)* - vereist.  Een of meer records of tabellen die u wilt toevoegen aan de gegevensbron.  

## <a name="examples"></a>Voorbeelden
### <a name="clearing-and-adding-records-to-a-data-source"></a>Records wissen en toevoegen aan een gegevensbron
In deze voorbeelden gaat u records wissen en toevoegen aan een verzameling met de naam **IJs**.  De gegevensbron begint met deze inhoud:

![](media/function-clear-collect-clearcollect/icecream.png)

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **ClearCollect ( IJs, {&nbsp;Smaak:&nbsp;"Aardbei",&nbsp;Hoeveelheid:&nbsp;300&nbsp;} )** |Hiermee wist u alle gegevens van de verzameling **IJs** en voegt u vervolgens een record toe die een hoeveelheid voor aardbeienijs bevat. |<style> img { max-width: none } </style> ![](media/function-clear-collect-clearcollect/icecream-clearcollect.png)<br><br>De gegevensbron **IJs** is ook gewijzigd. |
| **Collect( IJs, {&nbsp;Smaak:&nbsp;"Pistache",&nbsp;Hoeveelheid:&nbsp;40&nbsp;}, {&nbsp;Smaak:&nbsp;"Sinaasappel",&nbsp;Hoeveelheid:&nbsp;200&nbsp;}  )** |Hiermee worden twee records toegevoegd aan de verzameling **IJs** die hoeveelheden voor pistache- en sinaasappelijs bevatten. |![](media/function-clear-collect-clearcollect/icecream-collect.png)<br><br>De gegevensbron **IJs** is ook gewijzigd. |
| **Clear( IJs )** |Hiermee verwijdert u alle records uit de verzameling **IJs**. |![](media/function-clear-collect-clearcollect/icecream-clear.png)<br><br>De gegevensbron **IJs** is ook gewijzigd. |

### <a name="collect-a-static-list"></a>Een statische lijst verzamelen

1. Voeg een knop toe en stel de eigenschap **[OnSelect](../controls/properties-core.md)** ervan in op deze functie:<br>**Collect(Producten, &quot;Europa&quot;, &quot;Ganymede&quot;, &quot;Callisto&quot;)**
   
    Met deze functie wordt een verzameling met de naam **Producten** gemaakt, die een rij bevat voor elk van de drie productnamen.
    
1. Selecteer de knop terwijl u de Alt-toets ingedrukt houdt.

1. (optioneel) Als u een voorbeeld wilt bekijken van de gemaakte verzameling, selecteert u **Verzamelingen** in het **menu Bestand**.

### <a name="put-a-sharepoint-list-into-a-collection"></a>Een SharePoint-lijst in een verzameling plaatsen

1. [Maak verbinding met een SharePoint-lijst](../connect-to-sharepoint.md). 

1. Voeg een knop toe en stel de eigenschap **[OnSelect](../controls/properties-core.md)** in op deze functie. Vervang *ListName* door de naam van uw SharePoint-lijst:<br>
**Verzamelen**(**MySPCollection**, *ListName*)

    Met deze functie wordt een verzameling met de naam **MySPCollection** gemaakt. De verzameling bevat dezelfde gegevens als de SharePoint-lijst.
    
1. Selecteer de knop terwijl u de Alt-toets ingedrukt houdt.

1. (optioneel) Als u een voorbeeld wilt bekijken van de gemaakte verzameling, selecteert u **Verzamelingen** in het **menu Bestand**.

Zie [Gegevens weergeven in een galerie](../connections/connection-sharepoint-online.md#show-data-in-a-gallery) voor meer informatie over het in een galerie bekijken van gegevens uit een SharePoint-lijst (zoals data, keuzes en mensen). Zie [De formulierbesturingselementen Formulier bewerken en Formulier weergeven](../controls/control-form-detail.md) voor meer informatie over het weergeven van gegevens in een formulier (met vervolgkeuzelijsten, datumkeuze en mensenkeuze).
