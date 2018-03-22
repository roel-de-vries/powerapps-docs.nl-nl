---
title: De functie Value | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis, voor de functie Value in PowerApps
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
ms.openlocfilehash: ce377c87347b2ee027271b94eb623a58d7f58bd1
ms.sourcegitcommit: 33099e6197c0139679cd08c42e9e2a5717904c92
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/12/2018
---
# <a name="value-function-in-powerapps"></a>De functie Value in PowerApps
Converteert een tekenreeks naar een getal.

## <a name="description"></a>Beschrijving
De functie **Value** converteert een tekenreeks met numerieke tekens naar een getal. Gebruik deze functie wanneer u berekeningen wilt uitvoeren met getallen die door een gebruiker zijn ingevoerd als tekst.

Verschillende talen interpreteren **,** en **.** verschillend.  Standaard wordt de tekst geïnterpreteerd in de taal van de huidige gebruiker.  U kunt opgeven welke taal u wilt gebruiken met een taalcode, waarbij u dezelfde codes gebruikt die worden geretourneerd door de functie **[Language](function-language.md)**.

Opmerkingen bij de notatie van de tekenreeks:

* De tekenreeks kan worden voorafgegaan door het valutasymbool voor de huidige taal.  Het valutasymbool wordt genegeerd.  Valutasymbolen voor andere talen worden niet genegeerd.
* De tekenreeks kan een procentteken (**%**) aan het einde bevatten om aan te geven dat het een percentage is.  Het getal wordt gedeeld door 100 voordat het wordt geretourneerd.  Percentages en valutasymbolen kunnen niet worden gecombineerd.
* De tekenreeks heeft mogelijk een wetenschappelijke notatie, waarbij 12 x 10<sup>3</sup> wordt uitgedrukt als '12e3'.

Als het getal niet de juiste notatie heeft, retourneert **Value** de waarde *leeg*.

Als u datum- en tijdwaarden wilt omzetten, gebruikt u de functie [**DateValue**](function-datevalue-timevalue.md), [**TimeValue**](function-datevalue-timevalue.md) of [**DateTimeValue**](function-datevalue-timevalue.md).

## <a name="syntax"></a>Syntaxis
**Value**( *Tekenreeks* [, *Taalcode* ])

* *String* - vereist. De tekenreeks die u wilt converteren naar een numerieke waarde.
* *LanguageTag* - optioneel.  De code van de taal waarin de tekenreeks moet worden geparseerd.  Als de code niet is opgegeven, wordt de taal van de huidige gebruiker gebruikt.

## <a name="examples"></a>Voorbeelden
De gebruiker die deze formules uitvoert, bevindt zich in de Verenigde Staten en Engels is geselecteerd als taal.  De functie **Taal** retourneert "en-US".

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **Value( "123.456" )** |De standaardtaal 'en-US' wordt gebruikt, waarin een punt als decimaalteken wordt gebruikt. |123.456 |
| **Value("123.456", "es-ES")** |'es-ES' is de taalcode voor Spaans in Spanje.  In Spanje wordt een punt gebruikt als scheidingsteken voor duizendtallen. |123456 |
| **Value( "123,456" )** |De standaardtaal 'en-US' wordt gebruikt, waarin een komma wordt gebruikt als scheidingsteken voor duizendtallen. |123456 |
| **Value( "123,456", "es-ES" )** |'es-ES' is de taalcode voor Spaans in Spanje.  In Spanje is de komma het decimaalteken. |123.456 |
| **Value( "12.34%" )** |Het procentteken aan het einde van de tekenreeks geeft aan dat dit een percentage is. |0.1234 |
| **Value( "$ 12.34" )** |Het valutasymbool voor de huidige taal wordt genegeerd. |12.34 |
| **Value( "24e3" )** |Wetenschappelijke notatie voor 12 x 10<sup>3</sup>. |24000 |

