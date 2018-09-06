---
title: De functies Day, Month, Year, Hour, Minute, Second en Weekday | Microsoft Docs
description: Referentie-informatie, inclusief syntaxis en voorbeelden, voor de functies Day, Month, Year, Hour, Minute, Second en Weekday in PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/25/2016
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: ab824432833614ba5b2002375a79e7899a8d7277
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42857898"
---
# <a name="day-month-year-hour-minute-second-and-weekday-functions-in-powerapps"></a>De functies Day, Month, Year, Hour, Minute, Second en Weekday in PowerApps
Retourneert afzonderlijke onderdelen van een datum/tijd-waarde.

## <a name="description"></a>Beschrijving
De functie **Day** retourneert het daggedeelte van een datum/tijd-waarde, met een resultaat tussen 1 en 31.

De functie **Month** retourneert het maandgedeelte van een datum/tijd-waarde, met een resultaat tussen 1 en 12.

De functie **Year** retourneert het jaargedeelte van een datum/tijd-waarde, vanaf 1900.

De functie **Hour** retourneert het uurgedeelte van een datum/tijd-waarde, met een resultaat tussen 0 (00:00 uur) en 23 (23:00 uur).

De functie **Minute** retourneert het minuutgedeelte van een datum/tijd-waarde, met een resultaat tussen 0 en 59.

De functie **Second** retourneert het secondegedeelte van een datum/tijd-waarde, met een resultaat tussen 0 en 59.

De functie **Weekday** retourneert de weekdag van een datum/tijd-waarde.  Standaard ligt het resultaat tussen 1 (zondag) en 7 (zaterdag).  U kunt een ander bereik opgeven met een Microsoft Excel-functiecode voor de weekdag of een opsommingwaarde voor het begin van de week:

| Excel-code | Opsomming BeginVanWeek | Beschrijving |
| --- | --- | --- |
| **1**, **17** |**BeginVanWeek.Zondag** |Getallen van 1 (zondag) tot en met 7 (zaterdag).  Standaard. |
| **2**, **11** |**BeginVanWeek.Maandag** |Getallen van 1 (maandag) tot en met 7 (zondag). |
| **3** |**BeginVanWeek.MaandagNul** |Getallen van 0 (maandag) tot en met 6 (zondag). |
| **12** |**BeginVanWeek.Dinsdag** |Getallen van 1 (dinsdag) tot en met 7 (maandag). |
| **13** |**BeginVanWeek.Woensdag** |Getallen van 1 (woensdag) tot en met 7 (dinsdag). |
| **14** |**BeginVanWeek.Donderdag** |Getallen van 1 (donderdag) tot en met 7 (woensdag). |
| **15** |**BeginVanWeek.Vrijdag** |Getallen van 1 (vrijdag) tot en met 7 (donderdag). |
| **16** |**BeginVanWeek.Zaterdag** |Getallen van 1 (zaterdag) tot en met 7 (vrijdag). |

Alle functies retourneren een getal.

Zie [working with dates and times (werken met datums en tijden)](../show-text-dates-times.md) voor meer informatie.

## <a name="syntax"></a>Syntaxis
**Day**( *DateTime* )<br>**Month**( *DateTime* )<br>**Year**( *DateTime* )<br>**Hour**( *DateTime* )<br>**Minute**( *DateTime* )<br>**Second**( *DateTime* )

* *DateTime* - vereist.  De datum/tijd-waarde waarop de bewerking wordt toegepast.  

**Weekday**( *DateTime* [, *WeekdayFirst* ] )<br>

* *DateTime* - vereist.  De datum/tijd-waarde waarop de bewerking wordt toegepast. 
* *WeekdayFirst* - optioneel.  Excel-code die aangeeft op welke dag de week begint.  Als u dit niet opgeeft, wordt 1 (zondag eerst) gebruikt.

## <a name="examples"></a>Voorbeelden
In het volgende voorbeeld is de huidige tijd **15:59:37 uur** op **donderdag 9 april 2015**.

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **Year(&nbsp;Now()&nbsp;)** |Retourneert het jaargedeelte van de huidige datum en tijd. |2015 |
| **Month(&nbsp;Now()&nbsp;)** |Retourneert het maandgedeelte van de huidige datum en tijd. |4 |
| **Day(&nbsp;Now()&nbsp;)** |Retourneert het daggedeelte van de huidige datum en tijd. |9 |
| **Hour(&nbsp;Now()&nbsp;)** |Retourneert het uurgedeelte van de huidige datum en tijd. |15 |
| **Minute(&nbsp;Now()&nbsp;)** |Retourneert het minuutgedeelte van de huidige datum en tijd. |59 |
| **Second(&nbsp;Now()&nbsp;)** |Retourneert het secondegedeelte van de huidige datum en tijd. |37 |
| **Weekday(&nbsp;Now()&nbsp;)** |Retourneert de weekdag van de huidige tijd en datum op basis van het standaardbegin van de week op zondag. |5 |
| **Weekday(&nbsp;Now(),&nbsp;14&nbsp;)** |Retourneert de weekdag van de huidige tijd en datum met behulp van een Excel-code waarmee het begin van de week op donderdag wordt gezet. |1 |
| **Weekday(&nbsp;Now(),&nbsp;BeginVanWeek.Woensdag&nbsp;)** |Retourneert de weekdag van de huidige tijd en datum met behulp van een **BeginVanWeek**-opsomming waarmee het begin van de week op woensdag wordt gezet. |2 |

