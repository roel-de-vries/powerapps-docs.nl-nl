---
title: Functies GroupBy en Groep opheffen | Microsoft Docs
description: Referentie-informatie, inclusief syntaxis en voorbeelden, voor de functies GroupBy en Groep opheffen in PowerApps
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
ms.date: 04/26/2016
ms.author: gregli
ms.openlocfilehash: 9fcd60593fe89f54dcd65f4d440d9d78b4b220e1
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2018
---
# <a name="groupby-and-ungroup-functions-in-powerapps"></a>Functies GroupBy en Groep opheffen in PowerApps
Groepeert [records](../working-with-tables.md#records) van een [tabel](../working-with-tables.md) en heft deze groep op.

## <a name="description"></a>Beschrijving
De functie **GroupBy** retourneert een tabel met records die zijn gegroepeerd op basis van de waarden in een of meer [kolommen](../working-with-tables.md#columns). Records in dezelfde groep worden in één records geplaatst. Er wordt een kolom toegevoegd die een geneste tabel van de overige kolommen bevat.   

De functie **Groep opheffen** keert het **GroupBy**-proces om. Deze functie retourneert een tabel en breekt alle records die waren gegroepeerd op in afzonderlijke records.

U kunt records groeperen door **GroupBy** te gebruiken, de tabel die hij retourneert wijzigen en de records in de gewijzigde tabel vervolgens met behulp van **Groep opheffen** opsplitsen. U kunt bijvoorbeeld een groep records verwijderen door deze benadering te volgen:

* Gebruik de functie **GroupBy**.
* Gebruik de functie **[Filter](function-filter-lookup.md)** om de hele groep met records te verwijderen.
* Gebruik de functie **Groep opheffen**.  

U kunt ook resultaten samenvoegen op basis van een groepering:

* Gebruik de functie **GroupBy**.
* Gebruik de functie **[AddColumns](function-table-shaping.md)** met **[Som](function-aggregates.md)**, **[Gemiddelde](function-aggregates.md)**, en andere samenvoegingsfuncties om een nieuwe kolom toe te voegen die een samenvoeging van de groepstabellen vormt.
* Gebruik de functie **[DropColumns](function-table-shaping.md)** om de groepstabel te verwijderen.

**Groep opheffen** probeert de oorspronkelijke volgorde van de records die in **GroupBy** werden ingevoerd te behouden.  Dit is niet altijd mogelijk (bijvoorbeeld als de oorspronkelijke tabel *lege* records bevat).

Een tabel is een waarde in PowerApps, net zoals een tekenreeks of getal. U kunt een tabel opgeven als een argument voor een functie en een functie kan een tabel retourneren. **GroupBy** en **Groep opheffen** wijzigen een tabel niet. In plaats daarvan gebruiken ze een tabel als argument en retourneren ze een andere tabel. Zie [working with tables (werken met tabellen)](../working-with-tables.md) voor meer informatie.

## <a name="syntax"></a>Syntaxis
**GroupBy**( *Table*, *ColumnName1* [, *ColumnName2*, ... ], *GroupColumnName* )

* *Tabel* - vereist. Tabel die moet worden gegroepeerd.
* *NaamKolom(men)* - vereist.  De kolomnamen in *Table* waarop records moeten worden gegroepeerd.  Deze kolommen worden kolommen in de resulterende tabel.
* *GroupColumnName* - vereist.  De kolomnaam voor de opslag van recordgegevens die niet in de *ColumnName(s)* zijn.
  
    > [!NOTE]
> Vervang elke spatie in SharePoint- en Excel-gegevensbronnen met kolomnamen met spaties door **‘\_x0020\_’**. Geef **'Naam kolom'** bijvoorbeeld op als **'Naam_x0020_kolom'**.

**Ungroup**( *Table*, *GroupColumnName* )

* *Tabel* - vereist. Tabel waarvan de groep moet worden opgeheven.
* *GroupColumnName* - vereist. De kolom die de recordgegevensconfiguratie met de functie **GroupBy** bevat.
  
    > [!NOTE]
> Vervang elke spatie in SharePoint- en Excel-gegevensbronnen met kolomnamen met spaties door **‘\_x0020\_’**. Geef **'Naam kolom'** bijvoorbeeld op als **'Naam_x0020_kolom'**.

## <a name="examples"></a>Voorbeelden
### <a name="create-a-collection"></a>Een verzameling maken
1. Voeg een knop toe en stel de eigenschap **[Text](../controls/properties-core.md)** zo in dat de knop **Oorspronkelijk** weergeeft.
2. Stel de eigenschap **[OnSelect](../controls/properties-core.md)** van de knop **Origineel** in op deze formule:
   
    **ClearCollect(Inwonersaantallen, {Stad:"Londen", Land:"Engeland", Inwonersaantal:8615000}, {Stad:"Berlijn", Land:"Duitsland", Inwonersaantal:3562000}, {Stad:"Madrid", Land:"Spanje", Inwonersaantal:3165000}, {Stad:"Rome", Land:"Italië", Inwonersaantal:2874000}, {Stad:"Parijs", Land:"Frankrijk", Inwonersaantal:2273000}, {Stad:"Hamburg", Land:"Duitsland", Inwonersaantal:1760000}, {Stad:"Barcelona", Land:"Spanje", Inwonersaantal:1602000}, {Stad:"München", Land:"Duitsland", Inwonersaantal:1494000}, {Stad:"Milaan", Land:"Italië", Inwonersaantal:1344000})**
3. Druk op F5, selecteer de knop **Origineel** en druk vervolgens op Esc.
   
    U hebt zojuist een [verzameling](../working-with-data-sources.md#collections) met de naam **Inwonersaantallen** gemaakt die deze gegevens bevat:
   
    ![](media/function-groupby/cities.png)
4. Selecteer **Verzamelingen** in het menu **Bestand** en selecteer vervolgens de verzameling **Inwonersaantallen** om deze verzameling weer te geven.  De eerste vijf records in de verzameling worden weergegeven:
   
    ![](media/function-groupby/citypopulations-collection.png)

### <a name="group-records"></a>Records groeperen
1. Voeg een andere knop toe en stel de eigenschap **[Text](../controls/properties-core.md)** ervan in op **"Group"**.
2. Stel de eigenschap **[OnSelect](../controls/properties-core.md)** van deze knop in op deze formule:
   
    **ClearCollect( StedenPerLand, GroupBy( Inwonersaantallen, "Land", "Steden" ) )**
3. Druk op F5, selecteer de knop **Group** en druk vervolgens op Esc.
   
    U hebt zojuist een verzameling met de naam **CitiesByCountry** gemaakt, waarin de records van de vorige verzameling zijn gegroepeerd op de kolom **Country**.
   
    ![](media/function-groupby/cities-grouped.png)
4. Selecteer **Verzamelingen** in het menu **Bestand** om de eerste vijf records van deze verzameling weer te geven.
   
    ![](media/function-groupby/citiesbycountry-collection.png)
5. Selecteer het pictogram met de tabel in de kolom **Cities** voor een bepaald land (bijvoorbeeld Duitsland) om de bevolking van steden in dat land weer te geven:
   
    ![](media/function-groupby/population-germany.png)

### <a name="filter-and-ungroup-records"></a>Records filteren en groepen opheffen
1. Voeg nog een knop toe en stel de eigenschap **[Text](../controls/properties-core.md)** zo in dat de knop **"Filter"** weergeeft.
2. Stel de eigenschap **[OnSelect](../controls/properties-core.md)** van deze knop in op deze formule:
   
    **ClearCollect( CitiesByCountryFiltered, Filter( CitiesByCountry, "e" in Country ) )**
3. Druk op F5, selecteer de knop die u hebt toegevoegd en druk vervolgens op Esc.
   
    U hebt zojuist een derde verzameling met de naam **CitiesByCountryFiltered** gemaakt die alleen de landen bevat die een "e" in hun namen hebben (dus niet Duitsland of Frankrijk).
   
    ![](media/function-groupby/cities-grouped-hase.png)
4. Voeg nog een knop toe en stel de eigenschap **[Text](../controls/properties-core.md)** zo in dat de knop **"Ungroup"** weergeeft.
5. Stel de eigenschap **[OnSelect](../controls/properties-core.md)** van deze knop in op deze formule:
   
    **ClearCollect( InwonersaantallenUngrouped, Ungroup( StedenPerLandFiltered, "Steden" ) )**
   
    Dit resulteert in:
   
    ![](media/function-groupby/cities-hase.png)

### <a name="aggregate-results"></a>Resultaten samenvoegen
Een van de andere dingen die we met een gegroepeerde tabel kunnen doen, is het samenvoegen van de resultaten.  In dit voorbeeld zullen we de bevolking van de grote steden in elk land optellen.

1. Voeg nog een knop toe en stel de eigenschap **[Text](../controls/properties-core.md)** zo in dat de knop **"Sum"** weergeeft.
2. Stel de eigenschap **[OnSelect](../controls/properties-core.md)** van de knop **"Sum"** in op deze formule:
   
    **ClearCollect( InwonersaantallenSum, AddColumns( StedenPerLand, "Totale inwonersaantallen steden", Sum( Steden, Inwonersaantal ) ) )**
   
    Dit resulteert in:
   
    ![](media/function-groupby/cities-sum.png)
   
    **[AddColumns](function-table-shaping.md)** start met de basisverzameling **StedenPerLand** en voegt een nieuwe kolom **Totale inwonersaantallen steden** toe.  De waarden van deze kolom worden per rij berekend op basis van de formule **Sum( Cities, Population)**.  **AddColumns** biedt de waarde van de kolom **Steden** (een tabel) voor elke rij en **[Sum](function-aggregates.md)** telt de **Inwonersaantal** voor elke rij van deze subtabel op.
3. Nu we de som hebben die we willen, kunnen we **[DropColumns](function-table-shaping.md)** gebruiken om de subtabellen te verwijderen.  Wijzig de eigenschap **[OnSelect](../controls/properties-core.md)** om deze formule te gebruiken:
   
    **ClearCollect( InwonersaantallenSumOnly, DropColumns( InwonersaantallenSum, "Steden" ) )**
   
    Dit resulteert in:
   
    ![](media/function-groupby/cities-sum-drop-cities.png)
   
    Merk op dat we de groep in deze tabel niet hoefden op te heffen.

