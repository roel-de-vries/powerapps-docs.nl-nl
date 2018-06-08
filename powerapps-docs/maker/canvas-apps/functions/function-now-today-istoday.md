---
title: Functies Now, Today en IsToday | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functies Now, Today en IsToday in PowerApps
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
ms.openlocfilehash: 410e9be47b4356a97292eb5de17c5dc10885fae3
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "31829135"
---
# <a name="now-today-and-istoday-functions-in-powerapps"></a>De functies Now, Today en IsToday in PowerApps
Retourneert de huidige datum en tijd en test of een datum/tijd-waarde vandaag is.

## <a name="description"></a>Beschrijving
De functie **Now** retourneert de huidige datum en tijd als een datum/tijd-waarde.

De functie **Today** retourneert de huidige datum als een datum/tijd-waarde. Het tijdgedeelte is middernacht. **Today** heeft dezelfde waarde gedurende de hele dag, van vandaag middernacht tot morgen middernacht.

De functie **IsToday** test of een datum/tijd-waarde tussen vandaag middernacht en morgen middernacht ligt. Deze functie retourneert de Booleaanse waarde **true** of **false**.

Al deze functies werken met de lokale tijd van de huidige gebruiker.

Zie [working with dates and times (werken met datums en tijden)](../show-text-dates-times.md) voor meer informatie.

## <a name="syntax"></a>Syntaxis
**Now**()

**Today**()

**IsToday**( *DateTime* )

* *DateTime* - vereist.  De datum/tijd-waarde die moet worden getest.

## <a name="examples"></a>Voorbeelden
Voor de voorbeelden in deze sectie is de huidige tijd **3:59 uur** op **12 februari 2015** en is de taal **nl-nl**.

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **Text( Now(), "dd-mm-yyyy hh:mm:ss" )** |Hiermee worden de huidige datum en tijd opgehaald en weergegeven als een tekenreeks. |"12-02-2015 03:59:00" |
| **Text( Today(), "dd-mm-yyyy hh:mm:ss" )** |Hiermee wordt alleen de huidige datum opgehaald, wordt als tijd middernacht gebruikt en wordt het resultaat weergegeven als een tekenreeks. |"12-02-2015 00:00:00" |
| **IsToday( Now() )** |Test of de huidige datum en tijd tussen vandaag middernacht en morgen middernacht valt. |**true** |
| **IsToday( Today() )** |Test of de huidige datum tussen vandaag middernacht en morgen middernacht valt. |**true** |
| **Text( DateAdd( Now(), 12 ), "dd-mm-yyyy hh:mm:ss" )** |Hiermee worden de huidige datum en tijd opgehaald, worden 12 dagen opgeteld bij het resultaat en wordt het resultaat weergegeven als een tekenreeks. |"24-02-2015 03:59:00" |
| **Text( DateAdd( Today(), 12 ), "dd-mm-yyyy hh:mm:ss" )** |Hiermee wordt de huidige datum opgehaald, worden 12 dagen opgeteld bij het resultaat en wordt het resultaat weergegeven als een tekenreeks. |"24-02-2015 00:00:00" |
| **IsToday( DateAdd( Now(), 12 ) )** |Test of de huidige datum en tijd, plus 12 dagen, tussen vandaag middernacht en morgen middernacht valt. |**false** |
| **IsToday( DateAdd( Today(), 12 ) )** |Test of de huidige datum, plus 12 dagen, tussen vandaag middernacht en morgen middernacht valt. |**false** |

