---
title: Functies EndsWith en StartsWith | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functies EndsWith en StartsWith in PowerApps
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
ms.date: 07/24/2017
ms.author: gregli
ms.openlocfilehash: 2ffc183221e399ee978ac9a600b400e96a00f704
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/23/2018
---
# <a name="endswith-and-startswith-functions-in-powerapps"></a>Functies EndsWith en StartsWith in PowerApps
Test of een tekenreeks begint of eindigt met een andere tekenreeks.

## <a name="description"></a>Beschrijving
De functie **EndsWith** test of een tekenreeks eindigt met een andere tekenreeks.

De functie **StartsWith** test of een tekenreeks begint met een andere tekenreeks.    

De tests zijn voor beide functies niet hoofdlettergevoelig.  De resulterende waarde van beide is de booleaanse waarde **true** of **false**.  

Gebruik **EndsWith** en **StartsWith** met de functie **[Filter](function-filter-lookup.md)** om te zoeken naar de gegevens in uw app. U kunt ook de operator **[in](operators.md#in-and-exactin-operators)** of de functie **[Search](function-filter-lookup.md)** gebruiken om ergens in tekenreeksen te zoeken, niet alleen aan het begin of einde.  Uw keuze van functies is afhankelijk van de behoeften van uw app en de functie die kan worden [gedelegeerd](../delegation-overview.md) voor uw specifieke gegevensbron.  Als een van deze functies kan niet worden gedelegeerd, wordt er tijdens het ontwerpen een blauwe stip weergegeven om u te waarschuwen over deze beperking.

## <a name="syntax"></a>Syntaxis
**EndsWith**( *Text*, *EndText* )

* *Text* – vereist.  De tekst die moet worden getest.
* *EndText* – Vereist.  De tekst waarnaar moet worden gezocht aan het einde van *Text*.  Als *EndText* een lege tekenreeks is, geeft **EndsWith** de uitkomst *true*.

**StartsWith**( *Text*, *StartText* )

* *Text* – vereist.  De tekst die moet worden getest.
* *StartText* - vereist.  De tekst waarnaar moet worden gezocht aan het begin van *Text*.  Als *StartText* een lege tekenreeks is, geeft **StartsWith** de uitkomst *true*.

## <a name="examples"></a>Voorbeelden
| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **EndsWith( "Hallo wereld", "wereld" )** |Test of **"Hallo wereld"** eindigt met **"wereld"**.  De test is niet hoofdlettergevoelig. |**true** |
| **EndsWith( "Tot ziens", "tot" )** |Test of **"Tot ziens"** eindigt met **"tot"**.  Het *EndText*-argument (**"tot"**) komt voor in de tekst, maar niet aan het einde. |**false** |
| **EndsWith( "Zeg altijd hallo", "hallo" )** |Test of **"Zeg altijd hallo"** eindigt met **"hallo"**. |**true** |
| **Endswith( "Doei doei", "" )** |Test of **"Doei doei"** eindigt met een lege tekenreeks (**Len** retourneert 0).  **EndsWith** vereenvoudigt het gebruik ervan in **Filter**-expressies en is gedefinieerd om in dit geval **true** te retourneren. |**true** |

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **StartsWith ("Hallo wereld", "hallo")** |Test of **"Hallo wereld"** begint met **"hallo"**.  De test is niet hoofdlettergevoelig. |**true** |
| **StartsWith( "Tot ziens", "hallo" )** |Test of **"Tot ziens"** begint met **"hallo"**. |**false** |
| **StartsWith("Zeg altijd hallo", "hallo")** |Test of **"Zeg altijd hallo"** begint met **"hallo"**.  Hoewel **"hallo"** deel uitmaakt van de tekst, staat het niet aan het begin. |**false** |
| **StartsWith( "Doei doei", "" )** |Test of **"Doei doei"** begint met een lege tekenreeks (**Len** retourneert 0).  **StartsWith** vereenvoudigt het gebruik ervan in **Filter**-expressies en is gedefinieerd om in dit geval **true** te retourneren. |**true** |

### <a name="search-user-experience"></a>Gebruikerservaring met betrekking tot zoeken
In veel apps kunt u een of meer tekens in een zoekvak typen om een lijst met records in een grote gegevensset te filteren. Terwijl u typt, geeft de lijst alleen die records weer die overeenkomen met de zoekcriteria.

De voorbeelden in de rest van dit onderwerp tonen de resultaten van het doorzoeken van de lijst genaamd **Klanten** die deze gegevens bevat:

![](media/function-startswith/customers.png)

Maak een besturingselement **[Knop](../controls/control-button.md)** en stel de eigenschap **OnSelect** ervan in op de volgende formule om deze gegevensbron als een verzameling te maken:

**ClearCollect( Klanten, Table( { Naam: "Fred Garcia", Bedrijf: "Northwind Traders" }, { Naam: "Cole Miller", Bedrijf: "Contoso" }, { Naam: "Glenda Johnson", Bedrijf: "Contoso" }, { Naam: "Mike Collins", Bedrijf: "Adventure Works" }, { Naam: "Colleen Jones", Bedrijf: "Adventure Works" } ) )**

Net als in dit voorbeeld kunt u een lijst met records in een [**galeriebesturingselement**](../controls/control-gallery.md) onder aan het scherm maken. U kunt aan de bovenkant van het scherm een besturingselement [**Tekstinvoer**](../controls/control-text-input.md) met de naam **Zoekinvoer** toevoegen, zodat gebruikers kunnen opgeven in welke records ze geïnteresseerd zijn.

![](media/function-startswith/customers-ux-unfiltered.png)

Wanneer de gebruiker tekens in **Zoekinvoer** typt, worden de resultaten in de galerie automatisch gefilterd. In dit geval is de galerie geconfigureerd om records weer te geven waarin de naam van de klant (niet de naam van het bedrijf) begint met de reeks tekens in **Zoekinvoer**. Als de gebruiker **co** typt in het zoekvak, toont de galerie deze resultaten:

![](media/function-startswith/customers-ux-startswith-co.png)

U kunt filteren op basis van de kolom **Naam** door de eigenschap **Items** in het galeriebesturingselement op een van deze formules in te stellen:

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **Filter( Klanten, StartsWith( Naam, SearchInput.Text ) )** |Filtert de gegevensbron **Klanten** voor records waarin de zoektekenreeks aan het begin van de kolom **Naam** wordt weergegeven. De test is niet hoofdlettergevoelig. Als de gebruiker **co** in het zoekvak typt, toont de galerie **Colleen Jones** en **Cole Miller**. De galerie toont **Mike Collins** niet omdat de kolom **Naam** voor die record niet met de tekenreeks begint. |<style> img { max-width: none } </style> ![](media/function-startswith/customers-name-co-startswith.png) |
| **Filter( Klanten, Zoekinvoer.Text in Naam )** |Filtert de gegevensbron **Klanten** voor records waarin de zoektekenreeks op een willekeurige plaats in de kolom **Naam** wordt weergegeven. De test is niet hoofdlettergevoelig. Als de gebruiker **co** in het zoekvak typt, toont de galerie **Colleen Jones,** **Cole Miller** en **Mike Collins** omdat de zoektekenreeks op een willekeurige plaats in de kolom **Naam** van al deze records verschijnt. |<style> img { max-width: none } </style> ![](media/function-startswith/customers-name-co-contains.png) |
| **Search( Klanten, SearchInput.Text, "Naam" )** |De functie **Search** zoekt, net als de operator **in**, naar een overeenkomst op een willekeurige plaats in de kolom **Naam** voor elke record. Houd er rekening mee dat u de naam van de kolom tussen dubbele aanhalingstekens moet plaatsen. |<style> img { max-width: none } </style> ![](media/function-startswith/customers-name-co-contains.png) |

U kunt uw zoekopdracht uitbreiden om de kolom **Bedrijf** naast de kolom **Naam** op te nemen:

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **Filter( Klanten, StartsWith( Naam, SearchInput.Text ) &#124;&#124; StartsWith( Bedrijf, SearchInput.Text ) )** |Filtert de gegevensbron **Klanten** op records waarin ofwel de kolom **Naam** ofwel de kolom **Bedrijf** met de zoektekenreeks (bijvoorbeeld **co**) begint.  De operator [**&#124;&#124;**](operators.md) is *true* als een van beide **StartsWith**-functies *true* is. |<style> img { max-width: none } </style> ![](media/function-startswith/customers-all-co-startswith.png) |
| **Filter( Klanten, SearchInput.Text in Naam &#124;&#124; SearchInput.Text in Bedrijf )** |Filtert de gegevensbron **Klanten** op records waarin ofwel de kolom **Naam** ofwel de kolom **Bedrijf** de zoektekenreeks (bijvoorbeeld **co**) op een willekeurige positie bevat. |<style> img { max-width: none } </style> ![](media/function-startswith/customers-all-co-contains.png) |
| **Search( Klanten, SearchInput.Text, "Naam", "Bedrijf" )** |Net als de operator **in** zoekt de functie **Search** in de gegevensbron **Klanten** naar records waarin ofwel de kolom **Naam** ofwel de kolom **Bedrijf** de zoektekenreeks (bijvoorbeeld **co**) op een willekeurige plaats bevat. De functie **Search** is eenvoudiger te lezen en te schrijven dan **Filter** als u meerdere kolommen en meerdere **in**-operators wilt opgeven. Houd er rekening mee dat u de namen van de kolommen tussen dubbele aanhalingstekens moet plaatsen. |<style> img { max-width: none } </style> ![](media/function-startswith/customers-all-co-contains.png) |

