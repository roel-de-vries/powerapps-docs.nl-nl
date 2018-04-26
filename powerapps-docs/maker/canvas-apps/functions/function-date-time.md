---
title: De functies Date en Time | Microsoft Docs
description: Referentie-informatie, inclusief syntaxis en voorbeelden, voor de functies Date en Time in PowerApps
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
ms.openlocfilehash: 1d6c2485a8f54e0676cee5443085fb962f144831
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
---
# <a name="date-and-time-functions-in-powerapps"></a>De functies Date en Time in PowerApps
Hiermee worden datum- en tijdonderdelen omgezet naar een datum/tijd-waarde.

## <a name="description"></a>Beschrijving
De functie **Date** zet afzonderlijke waarden voor Year, Month en Day om naar een datum/tijd-waarde.  Het tijdgedeelte is middernacht.

* Als het jaar tussen 0 en 1899 ligt, voegt de functie die waarde toe aan 1900 om het jaar te berekenen.  **70** wordt **1970**.
* Als Month kleiner dan 1 of groter dan 12 is, wordt de hoeveelheid maanden in het resultaat afgetrokken van of toegevoegd aan het begin van het opgegeven jaar.
* Als Day groter is dan het aantal dagen in de opgegeven maand, voegt de functie de hoeveelheid dagen toe aan de eerste dag van de maand en retourneert deze de overeenkomstige datum van de volgende maand.  Als Day kleiner dan 1 is, trekt de functie het aantal dagen, plus 1, af van de eerste dag van de opgegeven maand.

De functie **Time** zet afzonderlijke waarden voor Hour, Minute en Second om naar een datum/tijd-waarde.  Het resultaat is niet aan een datum gekoppeld.

Zie de functies **[DateValue](function-datevalue-timevalue.md)**, **[TimeValue](function-datevalue-timevalue.md)** en **[DateTimeValue](function-datevalue-timevalue.md)** voor informatie over het omzetten van een tekenreeks naar een waarde.  

Zie ook [Werken met datums en tijden](../show-text-dates-times.md) voor meer informatie.

## <a name="syntax"></a>Syntaxis
**Date**( *Year*, *Month*, *Day* )

* *Year* - vereist.  Cijfers die groter zijn dan 1899 worden geïnterpreteerd als absolute waarden (1980 wordt geïnterpreteerd als 1980). Getallen van 0 t/m 1899 worden geïnterpreteerd in verhouding tot 1900. (80 wordt bijvoorbeeld geïnterpreteerd als 1980.)
* *Month* - vereist.  Een getal van 1 t/m 12.
* *Day* - vereist. Een getal van 1 t/m 31.

**Time**( *Hour*, *Minute*, *Second* )

* *Hour* - vereist.  Een getal van 0 (00:00 uur) t/m 23 (23:00 uur).
* *Minute* - vereist. Een getal van 0 t/m 59.
* *Second* - vereist. Een getal van 0 t/m 59.

## <a name="examples"></a>Voorbeelden
### <a name="date"></a>Date
Als een gebruiker **1979** heeft getypt in een besturingselement voor tekstinvoer met de naam **Beginjaar**, **3** in een besturingselement voor tekstinvoer met de naam **Beginmaand** en **17** in een besturingselement voor tekstinvoer met de naam **Begindag**, retourneert deze functie **17-3-1979**:

**Date(Value(Beginjaar.Text), Value(Beginmaand.Text), Value(Begindag.Text))**

### <a name="time"></a>Time
Als een gebruiker **14** heeft getypt in een besturingselement voor tekstinvoer met de naam **GeboorteUur**, **50** in een besturingselement voor tekstinvoer met de naam **Geboorteminuut** en **24** in een besturingselement voor tekstinvoer met de naam **Geboorteseconde**, retourneert deze functie **14:50:24**.

**Text(Time(Value(GeboorteUur.Text), Value(Geboorteminuut.Tekst), Value(Geboorteseconde.Text)), "hh:mm:ss a/p")**

