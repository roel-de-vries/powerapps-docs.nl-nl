---
title: Functies DateAdd, DateDiff en TimeZoneOffset | Microsoft Docs
description: Referentie-informatie, inclusief syntaxis en voorbeelden, voor de functies DateAdd, DateDiff en TimeZoneOffset in PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 05/23/2017
ms.author: gregli
ms.openlocfilehash: b07b8435b6068042529540956942a5b36d12db0c
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/13/2018
ms.locfileid: "39015082"
---
# <a name="dateadd-datediff-and-timezoneoffset-functions-in-powerapps"></a>Functies DateAdd, DateDiff en TimeZoneOffset in PowerApps
Zoekt het verschil in datum-/tijdwaarden of voegt deze toe en schakelt tussen lokale tijd en UTC.

## <a name="description"></a>Beschrijving
De functie **DateAdd** voegt een aantal eenheden toe aan een datum-/tijdwaarde. Het resultaat is een nieuwe datum/tijd-waarde. U kunt ook een aantal eenheden van een datum-/tijdwaarde aftrekken door een negatieve waarde op te geven.

De functie **DateDiff** retourneert het verschil tussen twee datum/tijd-waarden. Het resultaat is een aantal eenheden.

Voor beide functies kunnen de eenheden **Milliseconds**, **Seconds**, **Minutes**, **Hours**, **Days**, **Months**, **Quarters** of **Years** worden gebruikt.  Beide functies gebruiken standaard **dagen** als eenheid.

De functie **TimeZoneOffset** retourneert het aantal minuten tussen de lokale tijd van de gebruiker en UTC (Coordinated Universal Time).   

U kunt **DateAdd** gebruiken in combinatie met **TimeZoneOffset** om te schakelen tussen de lokale tijd van de gebruiker en UTC (Coordinated Universal Time).  Als u **TimeZoneOffset** toevoegt, wordt de lokale tijd geconverteerd naar UTC. Als u de TimeZoneOffset aftrekt (negatief getal toevoegen) wordt UTC geconverteerd naar de lokale tijd.

Zie ook [Werken met datums en tijden](../show-text-dates-times.md) voor meer informatie.

## <a name="syntax"></a>Syntaxis
**DateAdd**( *DateTime*, *Addition* [, *Units* ] )

* *DateTime* - vereist. De datum/tijd-waarde waarop de bewerking wordt toegepast.
* *Addition* - vereist. Aantal om toe te voegen aan de *DateTime* in *eenheden*.
* *Units* - optioneel. U kunt de volgende soorten *eenheden* toevoegen: **Milliseconds**, **Seconds**, **Minutes**, **Hours**, **Days**, **Months**, **Quarters**, or **Years**.  Indien u niks opgeeft, wordt **Days** gebruikt.

**DateDiff**( *StartDateTime*, *EndDateTime* [, *Units* ] )

* *StartDateTime* - vereist. Datum/tijd-waarde voor start.
* *EndDateTime* - vereist. Datum/tijd-waarde voor einde.
* *Units* - optioneel. U kunt de volgende soorten *eenheden* toevoegen: **Milliseconds**, **Seconds**, **Minutes**, **Hours**, **Days**, **Months**, **Quarters**, or **Years**.  Indien u niks opgeeft, wordt **Days** gebruikt.

**TimeZoneOffset**( [ *DateTime* ] )

* *DateTime*: optioneel.  Datum-/tijdwaarde waarvoor de offset wordt geretourneerd.  Standaard wordt de huidige datum en tijd gebruikt.

## <a name="examples"></a>Voorbeelden
In al deze voorbeelden wordt ervan uitgegaan dat de huidige datum en tijd **15 juli 2013, 13:02** is.

### <a name="simple-dateadd"></a>Eenvoudige DateAdd

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **Text( DateAdd( Now(), 3 ),<br>"dd-mm-yyyy hh:mm" )** |Voegt drie dagen (standaardeenheden) toe aan de huidige datum en tijd. |'18-07-2013 13:02' |
| **Text( DateAdd( Now(), 4, Hours ),<br>"dd-mm-yyyy hh:mm" )** |Voegt vier uur toe aan de huidige datum en tijd. |'15-07-2013 17:02' |
| **Text( DateAdd( Today(), 1, Months ),<br>"dd-mm-yyyy hh:mm" )** |Voegt één maand toe aan de huidige datum, zonder tijd omdat **Today** geen tijd retourneert. |'15-08-2013 00:00' |
| **Text( DateAdd( Now(), &#8209;30, Minutes ),<br>"dd-mm-yyyy hh:mm" )** |Trekt 30 minuten af van de huidige datum en tijd. |'15-07-2013 12:32' |

### <a name="simple-datediff"></a>Eenvoudige DateDiff

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **DateDiff( Now(), DateValue("1/1/2014") )** |Retourneert het verschil tussen de twee eenheden in de standaardeenheid **dagen** |170 |
| **DateDiff( Now(), DateValue("1/1/2014"), Months )** |Retourneert het verschil tussen de twee waarden in **maanden** |6 |
| **DateDiff( Now(), Today(), Minutes )** |Retourneert het verschil tussen de huidige datum en tijd en de huidige datum (zonder tijd) in minuten.  Aangezien **nu** later is dan **vandaag**, is het resultaat negatief. |-782 |

### <a name="converting-to-utc"></a>Conversie naar UTC
Als u wilt converteren naar UTC (Coordinated Universal Time), voegt u de **TimeZoneOffset** voor de opgegeven tijd toe.  

Later we er als voorbeeld van uitgaan dat de huidige datum en tijd **15 juli 2013, 13:02** is in Pacific Daylight Time (PDT UTC-7).  Om de huidige tijd in UTC te bepalen, gebruikt u:

* **DateAdd( Now(), TimeZoneOffset(), Minutes )**

**TimeZoneOffset** is standaard ingesteld op de huidige tijd, dus u hoeft geen argument te gebruiken.

Als u het resultaat wilt weergeven, gebruikt u de functie **Tekst** met de indeling *dd-mm-jjjj uu:mm*. Hiermee wordt **15-07-2013 20:02** geretourneerd.

### <a name="converting-from-utc"></a>Converteren van UTC
Als u wilt converteren van UTC, trekt u de **TimeZoneOffset** af van de opgegeven tijd (door een negatief getal toe te voegen).

Laten we er als voorbeeld van uitgaan dat UTC-datum en -tijd **15 juli 2013, 20:02** is opgeslagen in een variabele met de naam **StartTime**. Als u de tijd wilt aanpassen aan de tijdzone van de gebruiker, gebruikt u:

* **DateAdd( StartTime, -TimeZoneOffset( StartTime ), Minutes )**

Let op het minteken voor de **TimeZoneOffset** om de offset af te trekken in plaats van toe te voegen.

Als u het resultaat wilt weergeven, gebruikt u de functie **Tekst** met de indeling *dd-mm-jjjj uu:mm*. Hiermee wordt **15-07-2013 13:02** geretourneerd als u zich in de tijdzone Pacific Daylight Time bevindt.

