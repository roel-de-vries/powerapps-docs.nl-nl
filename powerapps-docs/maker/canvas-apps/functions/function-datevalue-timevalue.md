---
title: De functies DateValue, TimeValue en DateTimeValue | Microsoft Docs
description: Referentie-informatie, inclusief syntaxis en voorbeelden, voor de functies DateValue, TimeValue en DateTimeValue in PowerApps
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: a0f55de520a180a646e1e73aac423abc74bfed1d
ms.sourcegitcommit: 79b8842fb0f766a0476dae9a537a342c8d81d3b3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2018
ms.locfileid: "37896231"
---
# <a name="datevalue-timevalue-and-datetimevalue-functions-in-powerapps"></a>De functies DateValue, TimeValue en DateTimeValue in PowerApps
Hiermee kunt u een datum, tijd of beide in een tekenreeks converteren naar een datum/tijd-waarde.

## <a name="description"></a>Beschrijving
De functie **DateValue** converteert een tekenreeks met een datum (bijvoorbeeld "10/01/2014") naar een datum/tijd-waarde.

De functie **TimeValue** converteert een tekenreeks met een tijd (bijvoorbeeld "12:15 PM") naar een datum/tijd-waarde.

De functie **DateTimeValue** converteert een tekenreeks met een datum en tijd (bijvoorbeeld "January 10, 2013 12:13 AM") naar een datum/tijd-waarde.

De functie **DateValue** negeert alle tijdinformatie in de datumreeks, en de functie **TimeValue** negeert alle datuminformatie in de tijdreeks.

De gebruikte taal is standaard die van de huidige gebruiker, maar u kunt dit overschrijven om ervoor te zorgen dat tekenreeksen correct worden geïnterpreteerd. "10/1/1920" wordt bijvoorbeeld geïnterpreteerd als 1 oktober<sup> </sup>in "en" en als 10 januari<sup> </sup>in "fr".

Datums moeten in een van de volgende indelingen staan:

* MM/DD/JJJJ
* DD/MM/JJJJ
* DD mnd JJJJ
* Maand DD, JJJJ

Zie de functies**[Date](function-date-time.md)** en **[Time](function-date-time.md)** om datum, maand en jaar en uur, minuut en seconde van numerieke componenten te converteren.

Zie ook [Werken met datums en tijden](../show-text-dates-times.md) voor meer informatie.

Als u getallen wilt converteren, gebruikt u de functie **[Value](function-value.md)**.

## <a name="syntax"></a>Syntaxis
**DateValue**( *String* [, *Language* ])<br>**DateTimeValue**( *String* [, *Language* ])<br>**TimeValue**( *String* [, *Language* ])

* *String* - vereist.  Een tekenreeks die een datum, tijd of combinatie van datum en tijd bevat.
* *Language* - optioneel.  Een taaltekenreeks, zoals wordt geretourneerd door de eerste twee tekens uit de functie **[Language](function-language.md)**.  Indien niet opgegeven, wordt de taal van de huidige gebruiker gebruikt.  

## <a name="examples"></a>Voorbeelden
### <a name="datevalue"></a>DateValue
U typt **11/10/2014** in een besturingselement voor tekstinvoer met de naam **Startdatum** en stelt vervolgens de eigenschap **[Text](../controls/properties-core.md)** van een label in op deze functie:

* **Text(DateValue(Startdatum.Text), DateTimeFormat.LongDate)**
  
    Het label toont **Saturday, October 11, 2014** als uw computer is ingesteld op de landinstelling **en**.
  
    > [!NOTE]
  > U kunt met de **DateTimeFormat**-parameter verschillende andere opties dan **LongDateTime** gebruiken. Als u een lijst van deze opties wilt weergeven, typt u de parameter onmiddellijk gevolgd door een uitroepteken in het functievak.
* **Text(DateValue(Startdatum.Text), "fr"), DateTimeFormat.LongDate)**
  
    Het label toont **maandag 10 november 2014**.

Als u hetzelfde deed op **20 oktober 2014**:

* **DateDiff(DateValue(Startdatum.Text), Vandaag())**
  
    Als uw computer is ingesteld op de taal **en**, toont het label **9**, wat het aantal dagen tussen 11 oktober en 20 oktober aangeeft. De functie **[DateDiff](function-dateadd-datediff.md)** kan ook het verschil in maanden, kwartalen of jaar tonen.

### <a name="datetimevalue"></a>DateTimeValue
U typt **10/11/2014 1:50:24.765 PM** in een besturingselement voor tekstinvoer met de naam **Start** en stelt vervolgens de eigenschap **[Text](../controls/properties-core.md)** van een label in op deze functie:

* **Text(DateTimeValue(Start.Text), DateTimeFormat.LongDateTime)**
  
    Het label toont **Saturday, October 11, 2014 1:50:24 PM** als uw computer is ingesteld op de landinstelling "en".
  
    > [!NOTE]
  > U kunt met de **DateTimeFormat**-parameter verschillende andere opties dan **LongDateTime** gebruiken. Als u een lijst van deze opties wilt weergeven, typt u de parameter onmiddellijk gevolgd door een uitroepteken in het functievak.
* **Text(DateTimeValue(Start.Text, "fr"), DateTimeFormat.LongDateTime)**
  
    Het label toont **Monday, November 10, 2014 1:50:24 PM**.
* **Text(DateTimeValue(Start.Text), "dddd, mmmm dd, yyyy hh:mm:ss.fff AM/PM")**
  
    Het label toont **Saturday, October 11, 2014 01:50:24:765 PM** als uw computer is ingesteld op de landinstelling **en**.
  
    Als u de tijd wilt afronden naar de dichtstbijzijnde tiende of honderdste van een seconde, voert u in de formule **hh:mm:ss.f** of **hh:mm:ss.ff** in.

### <a name="timevalue"></a>TimeValue
Noem een besturingselement voor tekstinvoer **FinishedAt** en stel de eigenschap **[Text](../controls/properties-core.md)** van een label in op deze functie:

**Als(TimeValue(FinishedAt.Text)<TimeValue("5:00:00.000 PM"), "Gehaald!", "Te laat!")**

* Als u **4:59:59.999 PM** typt in het besturingselement **FinishedAt** toont het label "Gehaald!"
* Als u **5:00:00.000 PM** typt in het besturingselement **FinishedAt** toont het label "Te laat!"

