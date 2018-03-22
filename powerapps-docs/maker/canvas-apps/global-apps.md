---
title: Wereldwijde ondersteuning | Microsoft Docs
description: Ontwikkel apps die overal ter wereld worden gebruikt.
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
ms.date: 10/25/2016
ms.author: gregli
ms.openlocfilehash: 57f2b9a23207c2c866738ac40f46a37747fcd54d
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2018
---
# <a name="global-support"></a>Wereldwijde ondersteuning
PowerApps is een wereldwijd product.  Hiermee kunt u apps in verschillende talen en voor verschillende regio's maken en gebruiken.

De tekst die u in PowerApps ziet tijdens de ontwikkeling en de uitvoering van apps, is vertaald in verschillende talen.  Menu-items, dialoogvensters, linttabbladen en andere teksten worden in uw eigen taal weergegeven.  De invoer en weergave van datums en getallen zijn ook aangepast aan uw taal en regio.  Zo gebruiken sommige delen van de wereld '.' als decimaalteken, terwijl in andere delen ',' wordt gebruikt.  

Ook de apps die u maakt, kunnen worden aangepast aan de taal en regio.  Gebruik **[Language](functions/function-language.md)**, **[Text](functions/function-text.md)**, **[Value](functions/function-value.md)**, **[DateValue](functions/function-datevalue-timevalue.md)** en andere functies om te bepalen wat wordt weergegeven en gebruikt als invoer in verschillende talen.   

## <a name="language-settings"></a>Taalinstellingen
Wanneer u de systeemeigen studio of een systeemeigen speler gebruikt, wordt de gebruikte taal bepaald door het hostbesturingssysteem.  In Windows gaat u naar Alle instellingen en vervolgens naar Tijd en taal.  U kunt in Windows ook een teken opgeven om te gebruiken als decimaalteken en hiermee de taalinstelling overschrijven.  

Wanneer u via het web werkt, wordt de gebruikte taal bepaald door de browser.  De meeste browsers gebruiken de standaardinstelling van het hostbesturingssysteem en in sommige browsers kan de taal ook handmatig worden ingesteld.

## <a name="authoring-environment"></a>Ontwerpomgeving
De ontwerpomgeving wordt automatisch aangepast aan de taalinstelling van de auteur.  De app zelf wordt 'taalneutraal' opgeslagen, zodat auteurs die een andere taal gebruiken toch dezelfde app kunnen bewerken.

### <a name="names-in-formulas"></a>Namen in formules
De meeste elementen in formules zijn altijd in het Engels:

* Functienamen: **If**, **Navigate**, **Collect**,...
* Eigenschapsnamen van besturingselementen: **Screen.Fill**, **Button.OnSelect**, **Textbox.Font**,...
* Inventarisatienamen: **Color.Aqua**, **DataSourceInfo.MaxValue**, **FontWeight.Bold**,...
* Signaalrecords: **Compass.Heading**, **Location. Latitude**, **App.ActiveScreen**,...
* Operators: **Parent**, **in**, **exactIn**,...

Omdat de ontwerpomgeving is vertaald, worden namen van besturingselementen en andere objecten weergegeven in de eigen taal van de auteur.  In het Spaans zien de namen van besturingselementen er bijvoorbeeld als volgt uit:

![](media/global-apps/insert-controls-es.png)

Wanneer u een van deze elementen in uw app invoegt, wordt de naam standaard in het Engels weergegeven.  Dit zorgt voor consistentie met de eigenschapsnamen van besturingselementen en de rest van de formule.  Zo wordt **Casilla** hierboven ingevoegd als **Checkbox1**.  

Nadat een besturingselement is ingevoegd, kunt u de naam wijzigen in wat u maar wilt.  Wanneer het element is geselecteerd, wordt links in het lint Inhoud de naam van het besturingselement weergegeven.  Als u deze naam selecteert, wordt een tekstvak geopend waarin u de naam kunt bewerken:

![](media/global-apps/control-rename.png)

Hier kunt u de naam van het besturingselement desgewenst wijzigen in **Casilla1**.  De rode kronkellijn, in dit geval door een browser weergegeven, geeft aan dat de naam geen Spaans woord is, maar is verder niet relevant.

U kunt de namen van de volgende elementen aanpassen:

* Namen van besturingselementen
* Namen van verzamelingen
* Namen van contextvariabelen

### <a name="formula-separators-and-chaining-operator"></a>Scheidingstekens voor formules en chainingoperators
Sommige [scheidingstekens en operators](functions/operators.md) gebruiken het decimaalteken van de taal van de auteur:

| Decimaalteken van taal van auteur | PowerApps-scheidingsteken | PowerApps-lijstscheidingsteken | PowerApps-chainingoperator |
| --- | --- | --- | --- |
| **,** (punt) |**,** (punt) |**,** (komma) |**;** (puntkomma) |
| **,** (komma) |**,** (komma) |**;** (puntkomma) |**;;** (dubbele puntkomma) |

De wijziging van het PowerApps-lijstscheidingsteken komt overeen met de wijziging van het Excel-lijstscheidingsteken.  Dit heeft invloed op:

* Argumenten in functieaanroepen
* Velden in een [record](working-with-tables.md#elements-of-a-table)
* Records in een [waardetabel](working-with-tables.md#inline-syntax)

Zie het volgende voorbeeld van een formule in 'en-US':

**If( Slider1.Value > 12.59, UpdateContext( { Validation: true, MovingOn: 1 } ); Navigate( "NextScreen", "" ), UpdateContext( { Validation: false } ) )**

Als in een taal ',' wordt gebruikt als decimaalteken, ziet dit er in de ontwerpomgeving als volgt uit:

**If( Slider1.Value > 12,59; UpdateContext( { Validation: true; MovingOn: 1 } );; Navigate( "NextScreen", "" ); UpdateContext( { Validation: false } ) )**

U ziet dat de eigenschapselectieoperator **.** in **Slider1.Value** altijd hetzelfde is, ongeacht het decimaalteken.

Inhoudelijk verandert de formule niet. Het enige wat anders is, is hoe deze wordt weergegeven en bewerkt door de auteur.  Twee verschillende auteurs die een andere taal gebruiken, kunnen dezelfde formule weergeven en bewerken, waarbij ze de juiste scheidingstekens en operators zien voor de gebruikte taal.

## <a name="creating-a-global-app"></a>Een wereldwijde app maken
De app die u maakt, kan worden aangepast aan verschillende talen, zodat gebruikers over de hele wereld een optimale ervaring hebben.

### <a name="language-function"></a>Functie Language
De functie **[Language](functions/function-language.md)** retourneert de taalcode van de huidige gebruiker.  Zo retourneert deze functie **en-GB** voor gebruikers in Engeland en **de-DE** voor gebruikers in Duitsland.  

U kunt **Language** onder andere gebruiken om vertaalde tekst aan uw gebruikers weer te geven.  U kunt een tabel met vertaalde waarden in uw app opnemen:

![](media/global-apps/loc-table.png)

Vervolgens haalt u de vertaalde strings op uit de tabel met een formule, zoals die hieronder:

**LookUp( Table1, TextID = "Hello" && (LanguageTag = Left( Language(), 2 ) || IsBlank( LanguageTag ))).LocalizedText**  

Wees u ervan bewust dat vertaalde tekenreeksen in andere talen aanzienlijk langer kunnen zijn dan in uw eigen taal.  De labels en andere elementen waarin de tekenreeksen in uw gebruikersinterface worden weergegeven, moeten daarom in veel gevallen breder zijn, zodat er ruimte is voor langere teksten.

Zie voor meer informatie de documentatie voor de functie **[Language](functions/function-language.md)**.

### <a name="formatting-numbers-dates-and-times"></a>Notatie van getallen, datums en tijden
Getallen, datums en tijden hebben een andere notatie in verschillende delen van de hele wereld.  Het gebruik van puntkomma's en decimaaltekens en de volgorde van dag, maand en jaar variëren per locatie.   

De functie **[Text](functions/function-text.md)** noteert getallen en datums volgens de taalinstelling van de gebruiker.

Voor **Text** is een tekenreeks voor notatie vereist om de gewenste notatie van een getal of datum te gebruiken.  Deze tekenreeks voor notatie kan twee vormen aannemen:

* **Een taalgevoelige inventarisatie.**  Bijvoorbeeld **Text( Now(), DateTimeFormat.LongDate )**.  Met deze formule krijgt de huidige datum de juiste notatie voor de taal.  Dit is de beste manier om de tekenreeks voor notatie op te geven.
* **Een tekenreeks met aangepaste notatie.**  **Text( Now(), "[$-en-US]dddd, mmmm dd, yyyy" )** geeft bijvoorbeeld dezelfde tekst weer als de inventarisatie bij gebruik in de taal 'en-US'.  Het voordeel van de tekenreeks met aangepaste notatie is dat u precies kunt opgeven wat u wilt.

De '[$-en-US]' vooraan de tekenreeks met aangepaste notatie laat **Tekst** weten in welke taal de tekenreeks met aangepaste notatie moet worden geïnterpreteerd.  Deze wordt voor u ingevoegd en verandert automatisch in uw ontwerptaal.  U hoeft deze doorgaans niet te wijzigen.  Dit is handig wanneer auteurs in verschillende talen dezelfde app bewerken.

Het derde argument van **Text** geeft aan welke taal moet worden gebruikt voor het resultaat van de functie.  De standaardwaarde is de taalinstelling van de huidige gebruiker.

Zie voor meer informatie de documentatie voor de functie **[Text](functions/function-text.md)**.      

### <a name="reading-numbers-dates-and-times"></a>Getallen, datums en tijden lezen
Er zijn vier functies voor het lezen van getallen, datums en tijden die zijn opgegeven door de gebruiker:

* **[Value](functions/function-value.md)**: converteert een getal in een teksttekenreeks naar een getalwaarde.
* **[DateValue](functions/function-datevalue-timevalue.md)**: converteert een datumwaarde in een teksttekenreeks naar een datum/tijd-waarde.  Tijden in de teksttekenreeks worden genegeerd.
* **[TimeValue](functions/function-datevalue-timevalue.md)**: converteert een tijdwaarde in een teksttekenreeks naar een datum/tijd-waarde.  Datums in de teksttekenreeks worden genegeerd.
* **[DateTimeValue](functions/function-datevalue-timevalue.md)**: converteert een datum- en tijdwaarde in een teksttekenreeks naar een datum/tijd-waarde.  

Als u Excel hebt gebruikt, worden al deze functies gecombineerd in de waarde **Value**.  Omdat PowerApps verschillende typen heeft voor datum/tijd-waarden en getallen, worden ze hier opgedeeld.

Al deze functies hebben dezelfde argumenten:

* *Tekenreeks, vereist*: een tekenreeks van de gebruiker. Een tekenreeks wordt bijvoorbeeld in het besturingselement **Tekstinvoer** ingevoerd en uit het besturingselement gelezen met de eigenschap **Text**.
* *Language, optioneel*: de taal waarin de *tekenreeks* moet worden geïnterpreteerd.  Standaard wordt de taalinstelling van de gebruiker gebruikt.

Bijvoorbeeld:

* **Value( "12,345.678", "en-US" )** of **Value( "12,345.678" )** in regio's waar 'en-US' de taal van de gebruiker is, retourneert het getal **12345.678**, dat direct kan worden gebruikt voor berekeningen.
* **DateValue( "1/2/01", "es-ES" )** of **DateValue( "1/2/01" )** in regio's waar 'es-ES' de taal van de gebruiker is, retourneert de datum/tijd-waarde **1 februari 2001 om middernacht**.
* **TimeValue( "11:43:02", "fr-FR" )** of **DateValue( "11:43:02" )** in regio's waar 'fr-FR' de taal van de gebruiker is, retourneert de datum/tijd-waarde **1 januari 1970 om 11:43:02**.
* **TimeDateValue( "11:43:02 1/2/01", "de-DE" )** of **DateValue( "11:43:02" )** in regio's waar 'de-DE' de taal van de gebruiker is, retourneert de datum/tijd-waarde **1 februari 2001 om 11:43:02**.

Zie voor meer informatie de documentatie voor de functies **[Value](functions/function-value.md)** en **[DateValue, TimeValue en DateTimeValue](functions/function-datevalue-timevalue.md)** en over [werken met datums en tijden](show-text-dates-times.md).

### <a name="calendar-and-clock-information"></a>Agenda- en klokinformatie
Met de functies **[Calendar](functions/function-clock-calendar.md)** en **[Clock](functions/function-clock-calendar.md)** haalt u agenda- en klokinformatie op voor de huidige taal van de gebruiker.  

Hiermee kunt u onder andere een besturingselement **Vervolgkeuzelijst** opgeven met een lijst van opties.  

Zie voor meer informatie de documentatie voor de functies **[Calendar](functions/function-clock-calendar.md)** en **[Clock](functions/function-clock-calendar.md)**.
