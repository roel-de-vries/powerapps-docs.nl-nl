---
title: Informatie over versnelling, apps, kompasrichting, verbindingen en locatiesignalen | Microsoft Docs
description: In PowerApps verwijzen naar informatie over versnelling, apps, kompasrichting, verbindingen en locatiesensoren, inclusief syntaxis en voorbeelden
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 50f69d03df40499c187b7602d66af6e0b362abe2
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/13/2018
ms.locfileid: "39019038"
---
# <a name="acceleration-app-compass-connection-and-location-signals-in-powerapps"></a>Informatie over versnelling, apps, kompasrichting, verbindingen en locatiesignalen in PowerApps
Retourneert informatie over de app-omgeving, zoals waar ter wereld de gebruiker zich bevindt en welk venster wordt weergegeven.  

## <a name="description-and-syntax"></a>Beschrijving en syntaxis
Alle signalen retourneren een [record](../working-with-tables.md#records) met gegevens. U kunt deze gegevens gebruiken en opslaan als een record of u kunt afzonderlijke eigenschappen ophalen met behulp van de **.**- [operator](operators.md).

### <a name="acceleration"></a>Versnelling
Het signaal **Versnelling** retourneert de versnelling van het apparaat, in drie dimensies ten opzichte van het scherm van het apparaat. De versnelling wordt gemeten in de eenheid *g*, oftewel 9,81 m/seconde<sup>2</sup> of 32,2 ft/seconde<sup>2</sup> (de versnelling die de aarde door de zwaartekracht uitoefent op objecten op het oppervlak).

| Signaaleigenschap | Beschrijving |
| --- | --- |
| **Acceleration.X** |Links en rechts.  Recht is een positief getal. |
| **Acceleration.Y** |Vooruit en achteruit.  Vooruit is een positief getal. |
| **Acceleration.Z** |Omhoog en omlaag.  Omhoog is een positief getal. |

### <a name="app"></a>App
Het signaal **App** retourneert informatie over de app die wordt uitgevoerd.

| Signaaleigenschap | Beschrijving |
| --- | --- |
| **App.ActiveScreen** |Venster dat wordt weergegeven. Retourneert een vensterobject, dat u kunt gebruiken om te verwijzen naar eigenschappen van het venster of om te vergelijken met een ander scherm, zodat u kunt bepalen welk venster wordt weergegeven.  Met behulp van de functies **[Back](function-navigate.md)** en **[Navigate](function-navigate.md)** kunt u het weergegeven venster wijzigen. |

### <a name="compass"></a>Kompas
Het signaal **Kompas** retourneert de kompasrichting van de bovenkant van het scherm. De kompasrichting wordt gebaseerd op het magnetische noorden.

| Signaaleigenschap | Beschrijving |
| --- | --- |
| **Compass.Heading** |Kompasrichting in graden.  Retourneert een getal van 0 tot 360, waarbij 0 Noord is. |

### <a name="connection"></a>Verbinding
Het signaal **Verbinding** retourneert informatie over de netwerkverbinding. Wanneer u gebruikmaakt van een verbinding met een datalimiet, kan het wenselijk zijn om te beperken hoeveel gegevens u via het netwerk verzendt en ontvangt.

| Signaaleigenschap | Beschrijving |
| --- | --- |
| **Connection.Connected** |Retourneert een booleaanse waarde, **true** of **false**, die aangeeft of het apparaat is verbonden met een netwerk. |
| **Connection.Metered** |Retourneert een booleaanse waarde, **true** of **false**, die aangeeft of de verbinding een datalimiet heeft. |

### <a name="location"></a>Locatie
Het signaal **Locatie** retourneert de locatie van het apparaat, gebaseerd op het Global Positioning System (GPS) en andere apparaatinformatie, zoals communicatie met zendmasten en het IP-adres.

Wanneer een gebruiker voor het eerst gebruikmaakt van de locatie-informatie, kan het apparaat de gebruiker vragen om toegang tot deze informatie.

Wanneer de locatie verandert, blijven processen die gebruikmaken van de locatie continu actief, wat energie uit de accu onttrekt. Om de accuduur te vergroten, kunt u de functies **[Enable](function-enable-disable.md)** en **[Disable](function-enable-disable.md)** gebruiken om locatie-updates in en uit te schakelen. Locatie wordt automatisch uitgeschakeld als het weergegeven venster niet afhankelijk is van de locatie-informatie.

| Signaaleigenschap | Beschrijving |
| --- | --- |
| **Location.Altitude** |Retourneert een getal dat de hoogte aangeeft, gemeten in voet boven zeeniveau. |
| **Location.Latitude** |Retourneert een getal tussen-90 en 90 dat de breedtegraad aangeeft, gemeten in graden van de evenaar. Een positief nummer geeft een locatie ten noorden van de evenaar aan. |
| **Location.Longitude** |Retourneert een getal tussen 0 en 180 dat de lengtegraad aangeeft, gemeten in graden ten westen van Greenwich, Engeland. |

## <a name="examples"></a>Voorbeelden
Een pitcher staat op de werpheuvel van Safeco Field in Seattle, Washington, en gooit een telefoon naar een catcher op de thuisplaat. De telefoon ligt plat, ten opzichte van de grond, de bovenkant van het scherm is naar de catcher gericht. De pitcher geeft de telefoon geen spin mee. Op deze locatie heeft de telefoon wel verbinding met een mobiel netwerk met een datalimiet, maar geen wifi. Het venster **PlayBall** wordt weergegeven.   

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **Location.Latitude** |Retourneert de breedtegraad van de huidige locatie.  Safeco Field bevindt zich op kaartcoördinaten 47,591 N 122,333 W. |47,591<br><br>De breedtegraad blijft continu veranderen zolang het apparaat van de pitcher naar de catcher vliegt. |
| **Location.Longitude** |Retourneert de lengtegraad van de huidige locatie. |122,333<br><br>De lengtegraad blijft continu veranderen zolang het apparaat van de pitcher naar de catcher vliegt. |
| **Locatie** |Retourneert de breedtegraad en lengtegraad van de huidige locatie, als een record. |{&nbsp;Breedtegraad:&nbsp;47,591, lengtegraad:&nbsp;122,333&nbsp;} |
| **Compass.Heading** |Retourneert de kompasrichting van de bovenkant van het scherm. De thuisplaat van Safeco Field bevindt zich ongeveer ten zuidwesten van de werpheuvel. |230,25 |
| **Acceleration.X** |Retourneert de zijwaartse versnelling van het apparaat. De werper gooit de telefoon recht vooruit, ten opzichte van de bovenkant van het scherm, dus er is geen zijwaartse versnelling. |0 |
| **Acceleration.Y** |Retourneert de voorwaartse versnelling van het apparaat. De pitcher geeft het apparaat in eerste instantie een grote versnelling, als hij het apparaat gooit, waarbij de telefoon in een halve seconde versnelt van 0 tot 145 km per uur (40 meter per seconde). Zodra het apparaat door de lucht vliegt, versnelt het niet verder (we negeren in dit voorbeeld voor het gemak de luchtweerstand). Het apparaat wordt vertraagd wanneer de catcher het vangt, zodat het apparaat direct tot stilstand komt. |De waarde is dus 8.2 als de pitcher het apparaat gooit.<br><br>De waarde is 0 zolang het apparaat zich in de lucht bevindt.<br><br>De waarde is -8.2 als de catcher het apparaat vangt. |
| **Acceleration.Z** |Retourneert de neerwaartse versnelling van het apparaat. In de lucht wordt er zwaartekracht op het apparaat uitgeoefend. |De waarde is 0 voordat de pitcher het apparaat gooit.<br><br>De waarde is 1 zolang het apparaat zich in de lucht bevindt.<br><br>De waarde is 0 nadat de catcher het apparaat vangt. |
| **Versnelling** |Retourneert de acceleration als een record. |De waarde is dus { X: 0, Y: 264, Z: 0 } als de pitcher het apparaat gooit. |
| **Connection.Connected** |Retourneert een booleaanse waarde die aangeeft of het apparaat is verbonden met een netwerk. |**true** |
| **Connection.Metered** |Retourneert een booleaanse waarde die aangeeft of de verbinding een datalimiet heeft. |**true** |
| **App.ActiveScreen = PlayBall** |Retourneert een booleaanse waarde die aangeeft of **PlayBall** wordt weergegeven. |**true** |
| **App.ActiveScreen.Fill** |Retourneert de achtergrondkleur van het weergegeven venster. |**Color.Green** |

