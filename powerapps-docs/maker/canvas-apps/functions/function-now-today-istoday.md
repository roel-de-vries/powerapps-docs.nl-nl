---
title: Functies Now, Today en IsToday | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functies Now, Today en IsToday in PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 06/09/2018
ms.author: gregli
ms.openlocfilehash: 7b0b046c4c18f2f0bbbb8afd63a33aca2c46b340
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/13/2018
ms.locfileid: "39014300"
---
# <a name="now-today-and-istoday-functions-in-powerapps"></a>De functies Now, Today en IsToday in PowerApps
Retourneert de huidige datum en tijd en test of een datum/tijd-waarde vandaag is.

## <a name="description"></a>Beschrijving
De functie **Now** retourneert de huidige datum en tijd als een datum/tijd-waarde.

De functie **Today** retourneert de huidige datum als een datum/tijd-waarde. Het tijdgedeelte is middernacht. **Today** heeft dezelfde waarde gedurende de hele dag, van vandaag middernacht tot morgen middernacht.

De functie **IsToday** test of een datum/tijd-waarde tussen vandaag middernacht en morgen middernacht ligt. Deze functie retourneert een Booleaanse waarde (**true** of **false**).

Al deze functies werken met de lokale tijd van de huidige gebruiker.

Zie [working with dates and times (werken met datums en tijden)](../show-text-dates-times.md) voor meer informatie.

## <a name="volatile-functions"></a>Vluchtige functies
**Now** en **Today** zijn vluchtige functies.  Telkens wanneer een van deze functies wordt geëvalueerd, wordt een andere waarde geretourneerd.  

Wanneer een vluchtige functie in een gegevensstroomformule wordt gebruikt, retourneert deze alleen een andere waarde als de formule waarin deze wordt weergegeven, opnieuw wordt geëvalueerd.  Als er niets anders verandert in de formule, heeft deze dezelfde waarde gedurende de uitvoering van uw app.

Bijvoorbeeld, een label-besturingselement met **Label1.Text = Now()** verandert bijvoorbeeld niet wanneer uw app actief is.  Alleen het sluiten en opnieuw openen van de app leidt tot een nieuwe waarde.

De functie wordt opnieuw geëvalueerd als deze deel uitmaakt van een formule waarin iets anders is gewijzigd.  Als we ons voorbeeld bijvoorbeeld veranderen en een besturingselement van het type schuifregelaar gebruiken met **Label1.Text = DateAdd (Now(), Slider1.Value, Minutes)**, wordt de huidige tijd opgehaald telkens wanneer de waarde van het besturingselement van het type schuifregelaar wijzigt en de teksteigenschap van het label opnieuw wordt geëvalueerd.

Wanneer vluchtige functies worden gebruikt in een [gedragsformule](../working-with-formulas-in-depth.md), worden ze geëvalueerd telkens als de gedragsformule wordt geëvalueerd.  Hieronder vindt u een voorbeeld.

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

#### <a name="display-a-clock-that-updates-in-real-time"></a>Een klok weergeven die in realtime wordt bijgewerkt

1. Voeg een **[Timer](../controls/control-timer.md)**-besturingselement toe, stel de eigenschap **Duration** in op **1000** en stel de eigenschap **Repeat** in op **true**.

    De timer wordt één seconde uitgevoerd, begint automatisch opnieuw en gaat door met dat patroon. 

1. Stel de eigenschap **OnTimerEnd** in op deze formule:

    **Set( CurrentTime, Now() )**

    Telkens wanneer de timer opnieuw begint (na elke seconde) stelt deze formule de globale variabele **CurrentTime** in op de huidige waarde van de functie **Now**.

    ![Een scherm met een besturingselement van het type timer met de formule OnTimerEnd = Set(CurrentTime, Now())](media/function-now-today-istoday/now-set-currenttime.png)

1. Voeg een besturingselement van het type **[Label](../controls/control-text-box.md)** toe en stel de eigenschap **Text** in op deze formule:

    **Text( CurrentTime, LongTime24 )**

    Gebruik de functie **[Text](function-text.md)** om de datum en tijd te formatteren zoals u wilt, of stel deze eigenschap in op alleen **CurrentTime** om uren en minuten weer te geven maar geen seconden.

    ![Een scherm met een besturingselement van het type label met de eigenschap Text ingesteld op Text(CurrentTime, LongTime24)](media/function-now-today-istoday/now-use-currenttime.png)

1. Bekijk een voorbeeld van de app door op F5 te drukken en start de timer door erop te klikken of te tikken.

    Het label geeft voortdurend de huidige tijd weer, tot op de seconde.

    ![Vier schermen met vier tijdwaarden (13:50:22, 13:50:45, 13:51:03 en 13:51:25)](media/function-now-today-istoday/now-four-times.png)

1. Stel de eigenschap **AutoStart** van de timer in op **true** en de eigenschap **Visible** op **false**.

    De timer is onzichtbaar en start automatisch.

1. Stel de eigenschap **[OnStart](../controls/control-screen.md)** van het scherm in zodat de variabele **CurrentTime** een geldige waarde heeft, zoals in dit voorbeeld:

    **Set (CurrentTime, Now())**

    Het label wordt weergegeven zodra de app start (voordat de timer één hele seconde uitvoert).
