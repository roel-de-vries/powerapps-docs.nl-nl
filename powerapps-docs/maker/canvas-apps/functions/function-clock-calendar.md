---
title: De functies Calendar en Clock | Microsoft Docs
description: Referentie-informatie, inclusief syntaxis en voorbeelden, voor de functies Calendar en Clock in PowerApps
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
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: d04899e4557379f07b9f434b928b35e406a9e9ca
ms.sourcegitcommit: 33099e6197c0139679cd08c42e9e2a5717904c92
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/12/2018
---
# <a name="calendar-and-clock-functions-in-powerapps"></a>De functies Calendar en Clock in PowerApps
Haalt informatie op over de kalender en klok voor de huidige landinstelling.

## <a name="description"></a>Beschrijving
De functies **Calendar** en **Clock** halen informatie op over de huidige landinstelling.

U kunt deze functies gebruiken om datums en tijden weer te geven in de taal van de huidige gebruiker.  De tabellen met één kolom die worden geretourneerd door de functies **Calendar** en **Clock** kunnen rechtstreeks worden gebruikt met de eigenschap **[Items](../controls/properties-core.md)** van de besturingselementen voor vervolgkeuzelijst en lijstvak.

| Functie | Beschrijving |
| --- | --- |
| **Calendar.MonthsLong()** |Tabel met één kolom met de volledige naam van elke maand, beginnend met "Januari". |
| **Calendar.MonthsShort()** |Tabel met één kolom met de afgekorte naam van elke maand, beginnend met "Jan" voor januari. |
| **Calendar.WeekdaysLong()** |Tabel met één kolom met de volledige naam van elke weekdag, beginnend met "Zondag". |
| **Calendar.WeekdaysShort()** |Tabel met één kolom met de volledige naam van elke weekdag, beginnend met "Zo" voor zondag. |
| **Clock.AmPm()** |Tabel met één kolom met de lange aanwijzingen met "AM" en "PM" in hoofdletters.  Als de taal gebruikmaakt van een 24-uurs klok, is de tabel leeg. |
| **Clock.AmPmShort()** |Tabel met één kolom met de korte aanduidingen "A" en "P" in hoofdletters.  Als de taal gebruikmaakt van een 24-uurs klok, is de tabel leeg. |
| **Clock.IsClock24()** |Booleaanse waarde die aangeeft of een 24-uurs klok wordt gebruikt op deze locatie. |

Gebruik de functie **[Text](function-text.md)** om datum- en tijdwaarden in te delen met behulp van dezelfde informatie.  De functie **[Language](function-language.md)** retourneert de huidige taal- en regiocode.

## <a name="syntax"></a>Syntaxis
**Calendar.MonthsLong**()

**Calendar.MonthsShort**()

**Calendar.WeekdaysLong**()

**Calendar.WeekdaysShort**()

**Clock.AmPm**()

**Clock.AmPmShort**()

**Clock.IsClock24**()

## <a name="examples"></a>Voorbeelden
1. Voeg een besturingselement voor de vervolgkeuzelijst in.
2. Stel de formule voor de eigenschap **[Items](../controls/properties-core.md)** in op:
   
   * **Calendar.MonthsLong()**
3. Gebruikers van uw app kunnen nu in hun eigen taal een maand selecteren.  **MonthsLong** kan worden vervangen door een van de tabellen met één kolom die worden geretourneerd door **Calendar** om kiezers voor weekdag en tijd te maken.

In de Verenigde Staten, waar **[Language](function-language.md)** "en-US" retourneert, wordt het volgende geretourneerd door de functie **Calendar**:

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **Calendar.MonthsLong()** |De geretourneerde waarde bevat de volledige naam van elke maand, beginnend met "Januari". |[ "Januari","Februari", "Maart", "April", "Mei", "Juni", "Juli", "Augustus", "September", "Oktober", "November", "December" ] |
| **Calendar.MonthsShort()** |De geretourneerde waarde bevat de afgekorte naam van elke maand, beginnend met januari. |[ "Jan", "Feb", "Mrt", "Apr", "Mei", "Jun", "Jul", "Aug", "Sep", "Okt", "Nov", "Dec" ] |
| **Calendar.WeekdaysLong()** |De geretourneerde waarde bevat de volledige naam van elke weekdag, beginnend met "Zondag". |[ "Zondag", "Maandag", "Dinsdag", "Woensdag", "Donderdag", "Vrijdag", "Zaterdag" ] |
| **Calendar.WeekdaysShort()** |De geretourneerde waarde bevat de afgekorte naam van elke weekdag, beginnend met zondag. |["Zo", "Ma", "Di", "Wo", "Do", "Vrij", "Za"] |
| **Clock.AmPm()** |Deze taal gebruikt een 12-uurs klok.  De geretourneerde waarde bevat de volledige aanwijzingen met AM en PM in hoofdletters. |[ "AM", "PM" ] |
| **Clock.AmPmShort()** |Deze taal gebruikt een 12-uurs klok.  De geretourneerde waarde bevat de afgekorte aanwijzingen met am en pm in kleine letters. |[ "A", "P" ] |
| **Clock.IsClock24()** |Deze taal gebruikt een 12-uurs klok. |**false** |

