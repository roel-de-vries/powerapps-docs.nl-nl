---
title: Functies Filter, Zoeken en Opzoeken | Microsoft Docs
description: Referentie-informatie, inclusief syntaxis en voorbeelden, voor de functies Filter, Zoeken en Opzoeken in PowerApps
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
ms.date: 02/05/2017
ms.author: gregli
ms.openlocfilehash: 2a9fa8c08423cfdfb5094547602041b8dda571f2
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2018
---
# <a name="filter-search-and-lookup-functions-in-powerapps"></a>Functies Filter, Zoeken en LookUp in PowerApps
Zoekt een of meer [records](../working-with-tables.md#records) in een [tabel](../working-with-tables.md).

## <a name="description"></a>Beschrijving
De functie **Filter** zoekt records in een tabel die aan een formule voldoen.  Gebruik **Filter** om een reeks records te vinden die overeenkomen met een of meer criteria en om criteria die niet overeenkomen te verwijderen.

De functie **LookUp** vindt de eerste record in een tabel die aan een formule voldoet.  Gebruik **LookUp** om één record te vinden die met een of meer criteria overeenkomt.

De formule wordt in beide gevallen geëvalueerd voor elke record in de tabel.  Records die resulteren in *true* worden in het resultaat opgenomen.  Naast de normale [operators](operators.md) van de formule kunt u de operators **[in](operators.md#in-and-exactin-operators)** en **[exactin](operators.md#in-and-exactin-operators)** gebruiken voor overeenkomsten in subtekenreeksen.

[!INCLUDE [record-scope](../../../includes/record-scope.md)]

De functie **Search** zoekt records in een tabel met een tekenreeks in een van de kolommen. De tekenreeks kan op een willekeurige plaats in de kolom voorkomen. Zoeken naar "rob" of "bert" levert bijvoorbeeld een overeenkomst op in een kolom die "Robert" bevat. Zoeken is niet hoofdlettergevoelig. De functie **Search** gebruikt, in tegenstelling tot **Filter** en **LookUp**, een tekenreeks voor een overeenkomst in plaats van een formule.

**Filter** en **Search** retourneren een tabel die dezelfde kolommen bevat als de oorspronkelijke tabel, evenals de records die met de criteria overeenkomen. **LookUp** retourneert alleen de eerste record die wordt gevonden nadat een formule is toegepast om de record tot één waarde te beperken. Als er geen records worden gevonden, retourneren **Filter** en **Search** een [lege](function-isblank-isempty.md) tabel en retourneert **LookUp** *leeg*.  

[Tabellen](../working-with-tables.md) vormen een waarde in PowerApps, net als een tekenreeks of getal. Ze kunnen worden doorgegeven aan en geretourneerd uit functies.  **Filter**, **Search** en **LookUp** wijzigen een tabel niet. In plaats daarvan nemen ze een tabel als een argument en retourneren ze een tabel of een record of enkele waarde eruit. Zie [working with tables (werken met tabellen)](../working-with-tables.md) voor meer informatie.

[!INCLUDE [delegation](../../../includes/delegation.md)]

## <a name="syntax"></a>Syntaxis
**Filter**( *Table*, *Formula1* [, *Formula2*, ... ] )

* *Tabel* - vereist. Te doorzoeken tabel.
* *Formula(s)* - vereist. De formule waarmee elke record van de tabel wordt geëvalueerd. De functie retourneert alle records die resulteren in **true**. U kunt verwijzen naar kolommen in de tabel. Als u meer dan een formule opgeeft, worden de resultaten van alle formules gecombineerd met de functie **[And](function-logicals.md)**.

**Search**( *Table*, *SearchString*, *Column1* [, *Column2*, ... ] )

* *Tabel* - vereist. Te doorzoeken tabel.
* *SearchString* - vereist. De tekenreeks waarnaar moet worden gezocht. Bij *leeg* of een lege tekenreeks worden alle records geretourneerd.
* *Column(s)* - vereist. De namen van de kolommen in de *tabel* waarbinnen moet worden gezocht. Kolommen waarbinnen moet worden gezocht, moeten tekst bevatten. Kolomnamen moeten tekenreeksen zijn en worden omsloten door dubbele aanhalingstekens. De kolomnamen moeten echter statisch zijn en kunnen niet worden berekend met een formule. Als *SearchString* als gedeeltelijke overeenkomst binnen de gegevens van een van deze kolommen wordt gevonden, zal de volledige record worden geretourneerd.

> [!NOTE]
> Vervang elke spatie in SharePoint- en Excel-gegevensbronnen met kolomnamen met spaties door **‘\_x0020\_’**. Geef **'Naam kolom'** bijvoorbeeld op als **'Naam_x0020_kolom'**.

**LookUp**( *Table*, *Formula* [, *ReductionFormula* ] )

* *Tabel* - vereist. Te doorzoeken tabel. De syntaxis wordt in de gebruikersinterface als *bron* boven het functievak weergegeven.
* *Formule* - vereist.
  De formule waarmee elke record van de tabel wordt geëvalueerd. De functie retourneert de eerste record die resulteert in **true**. U kunt verwijzen naar kolommen in de tabel. De syntaxis wordt in de gebruikersinterface als *voorwaarde* boven het functievak weergegeven.
* *ReductionFormula* - optioneel. Deze formule wordt geëvalueerd voor de record die is gevonden en reduceert de record vervolgens tot één waarde. U kunt verwijzen naar kolommen in de tabel. Als u deze parameter niet gebruikt, retourneert de functie de volledige record uit de tabel. De syntaxis wordt in de gebruikersinterface als *resultaat* boven het functievak weergegeven.

## <a name="examples"></a>Voorbeelden
De volgende voorbeelden gebruiken de [gegevensbron](../working-with-data-sources.md) **IJs**:

![](media/function-filter-lookup/icecream.png)

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **Filter( IJs, InBestelling > 0 )** |Retourneert records waarin **InBestelling** groter is dan nul. |<style> img { max-width: none; } </style> ![](media/function-filter-lookup/icecream-onorder.png) |
| **Filter( IJs, Hoeveelheid + InBestelling > 225 )** |Retourneert records waarin de som van de kolommen **Hoeveelheid** en **InBestelling** groter is dan 225. |![](media/function-filter-lookup/icecream-overstock.png) |
| **Filter( IJs, "chocola" in Lower( Smaak ) )** |Retourneert records waarin het woord "chocola" in de naam **Smaak** voorkomt, onafhankelijk van hoofdletters of kleine letters. |![](media/function-filter-lookup/icecream-chocolate.png) |
| **Filter( IJs, Hoeveelheid < 10  && InBestelling < 20 )** |Retourneert records waarin **Hoeveelheid** minder is dan 10 en **InBestelling** is minder is dan 20.  Er zijn geen records die met deze criteria overeenkomen. Daarom wordt een lege tabel geretourneerd. |![](media/function-filter-lookup/icecream-empty.png) |
| **Search( IJs, "choc", "Smaak" )** |Retourneert records waarin de tekenreeks "choc" in de naam **Smaak** voorkomt, onafhankelijk van hoofdletters of kleine letters. |![](media/function-filter-lookup/icecream-chocolate.png) |
| **Search( IJs, "", "Smaak" )** |Omdat de zoekterm leeg is, worden alle records geretourneerd. |![](media/function-filter-lookup/icecream.png) |
| **LookUp( IJs, Smaak = "Chocola", Hoeveelheid )** |Zoekt naar een record waarvan **Smaak** gelijk is aan "Chocola"; daarvan is er één.  Retourneert de **Hoeveelheid** voor de eerste record die wordt gevonden. |100 |
| **LookUp( IJs, Hoeveelheid > 150, Hoeveelheid + InBestelling )** |Zoekt naar een record waarvan **Hoeveelheid** groter is dan 100; daarvan zijn er meerdere.  Retourneert voor de eerste record die wordt gevonden, dat is de **Smaak** "Vanille", de som van de kolommen **Hoeveelheid** en **InBestelling**. |250 |
| **LookUp( IJs, Smaak = "Pistache", InBestelling )** |Zoekt naar een record waarvan **Smaak** gelijk is aan "Pistache"; daarvan zijn er geen.  Omdat er geen records zijn gevonden, retourneert **Lookup** *leeg*. |*leeg* |
| **LookUp( IJs, Smaak = "Vanille" )** |Zoekt naar een record waarvan **Smaak** gelijk is aan "Vanille"; daarvan is er één.  Omdat er geen verminderingsformule werd opgegeven, wordt de volledige record geretourneerd. |{ Smaak: "Vanille", Hoeveelheid: 200, InBestelling: 75 } |

### <a name="search-user-experience"></a>Gebruikerservaring met betrekking tot zoeken
In veel apps kunt u een of meer tekens in een zoekvak typen om een lijst met records in een grote gegevensset te filteren. Terwijl u typt, geeft de lijst alleen die records weer die overeenkomen met de zoekcriteria.

De voorbeelden in de rest van dit onderwerp tonen de resultaten van het doorzoeken van een lijst met de naam **Klanten** die deze gegevens bevat:

![](media/function-filter-lookup/customers.png)

Maak een besturingselement **[Knop](../controls/control-button.md)** en stel de eigenschap **OnSelect** ervan in op de volgende formule om deze gegevensbron als een verzameling te maken:

**ClearCollect( Klanten, Table( { Naam: "Fred Garcia", Bedrijf: "Northwind Traders" }, { Naam: "Cole Miller", Bedrijf: "Contoso" }, { Naam: "Glenda Johnson", Bedrijf: "Contoso" }, { Naam: "Mike Collins", Bedrijf: "Adventure Works" }, { Naam: "Colleen Jones", Bedrijf: "Adventure Works" } ) )**

Net als in dit voorbeeld kunt u een lijst met records in een [**galeriebesturingselement**](../controls/control-gallery.md) onder aan het scherm maken. U kunt aan de bovenkant van het scherm een besturingselement [**Tekstinvoer**](../controls/control-text-input.md) met de naam **Zoekinvoer** toevoegen, zodat gebruikers kunnen opgeven in welke records ze geïnteresseerd zijn.

![](media/function-filter-lookup/customers-ux-unfiltered.png)

Wanneer de gebruiker tekens in **Zoekinvoer** typt, worden de resultaten in de galerie automatisch gefilterd. In dit geval is de galerie geconfigureerd om records weer te geven waarin de naam van de klant (niet de naam van het bedrijf) begint met de reeks tekens in **Zoekinvoer**. Als de gebruiker **co** in het zoekvak typt, toont de galerie deze resultaten:

![](media/function-filter-lookup/customers-ux-startswith-co.png)

U kunt filteren op basis van de kolom **Naam** door de eigenschap **Items** in het galeriebesturingselement op een van deze formules in te stellen:

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **Filter( Klanten, StartsWith( Naam, SearchInput.Text ) )** |Filtert de gegevensbron **Klanten** voor records waarin de zoektekenreeks aan het begin van de kolom **Naam** wordt weergegeven. De test is niet hoofdlettergevoelig. Als de gebruiker **co** in het zoekvak typt, toont de galerie **Colleen Jones** en **Cole Miller**. De galerie toont **Mike Collins** niet omdat de kolom **Naam** voor die record niet met de tekenreeks begint. |<style> img { max-width: none } </style> ![](media/function-filter-lookup/customers-name-co-startswith.png) |
| **Filter( Klanten, Zoekinvoer.Text in Naam )** |Filtert de gegevensbron **Klanten** voor records waarin de zoektekenreeks op een willekeurige plaats in de kolom **Naam** wordt weergegeven. De test is niet hoofdlettergevoelig. Als de gebruiker **co** in het zoekvak typt, toont de galerie **Colleen Jones,** **Cole Miller** en **Mike Collins** omdat de zoektekenreeks op een willekeurige plaats in de kolom **Naam** van al deze records verschijnt. |<style> img { max-width: none } </style> ![](media/function-filter-lookup/customers-name-co-contains.png) |
| **Search( Klanten, SearchInput.Text, "Naam" )** |De functie **Search** zoekt, net als de operator **in**, naar een overeenkomst op een willekeurige plaats in de kolom **Naam** voor elke record. Houd er rekening mee dat u de naam van de kolom tussen dubbele aanhalingstekens moet plaatsen. |<style> img { max-width: none } </style> ![](media/function-filter-lookup/customers-name-co-contains.png) |

U kunt uw zoekopdracht uitbreiden om de kolom **Bedrijf** naast de kolom **Naam** op te nemen:

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **Filter( Klanten, StartsWith( Naam, SearchInput.Text ) &#124;&#124; StartsWith( Bedrijf, SearchInput.Text ) )** |Filtert de gegevensbron **Klanten** op records waarin ofwel de kolom **Naam** ofwel de kolom **Bedrijf** met de zoektekenreeks (bijvoorbeeld **co**) begint.  De operator [**&#124;&#124;**](operators.md) is *true* als een van beide **StartsWith**-functies *true* is. |<style> img { max-width: none } </style> ![](media/function-filter-lookup/customers-all-co-startswith.png) |
| **Filter( Klanten, SearchInput.Text in Naam &#124;&#124; SearchInput.Text in Bedrijf )** |Filtert de gegevensbron **Klanten** op records waarin ofwel de kolom **Naam** ofwel de kolom **Bedrijf** de zoektekenreeks (bijvoorbeeld **co**) op een willekeurige positie bevat. |<style> img { max-width: none } </style> ![](media/function-filter-lookup/customers-all-co-contains.png) |
| **Search( Klanten, SearchInput.Text, "Naam", "Bedrijf" )** |Net als de operator **in** zoekt de functie **Search** in de gegevensbron **Klanten** naar records waarin ofwel de kolom **Naam** ofwel de kolom **Bedrijf** de zoektekenreeks (bijvoorbeeld **co**) op een willekeurige plaats bevat. De functie **Search** is eenvoudiger te lezen en te schrijven dan **Filter** als u meerdere kolommen en meerdere **in**-operators wilt opgeven. Houd er rekening mee dat u de namen van de kolommen tussen dubbele aanhalingstekens moet plaatsen. |<style> img { max-width: none } </style> ![](media/function-filter-lookup/customers-all-co-contains.png) |

