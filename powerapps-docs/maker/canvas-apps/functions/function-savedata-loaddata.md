---
title: Functies SaveData en LoadData | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functies SaveData en LoadData in PowerApps
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
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: aa62882841ee4d585720a2241dff8b9f35c88059
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2018
---
# <a name="savedata-and-loaddata-functions-in-powerapps"></a>Functies SaveData en LoadData in PowerApps
Hiermee wordt een [verzameling](../working-with-data-sources.md#collections) opgeslagen en opnieuw geladen.

## <a name="description"></a>Beschrijving
De functie **SaveData** slaat een verzameling voor later gebruik op onder een naam.  

Met de functie **LoadData** wordt een verzameling die eerder is opgeslagen met **SaveData**, opnieuw geladen aan de hand van de naam van de verzameling. U kunt deze functie niet gebruiken om een verzameling van een andere bron te laden.  

**LoadData** maakt de verzameling niet. Deze functie vult enkel een bestaande verzameling. U moet eerst de verzameling met de juiste [kolommen](../working-with-tables.md#columns) maken met behulp van  **[Verzamelen](function-clear-collect-clearcollect.md)**.

De opslag wordt gecodeerd en bevindt zich op een persoonlijke locatie op het lokale apparaat, geïsoleerd van andere gebruikers en andere apps.  

## <a name="syntax"></a>Syntaxis
**SaveData**( *Collection*, *Name* )<br>**LoadData**( *Collection*, *Name* [, *IgnoreNonexistentFile* ])

* *Collection* - vereist.  De verzameling die moet worden opgeslagen of geladen.
* *Name* - vereist.  De naam van de opslag. U moet dezelfde naam gebruiken om dezelfde set gegevens op te slaan en te laden. De naamruimte wordt niet gedeeld met andere apps of gebruikers.
* *IgnoreNonexistentFile* - optioneel. Booleaanse waarde (**true**/**false**) die aangeeft of de functie **LoadData** fouten moet weergeven of negeren wanneer een overeenkomend bestand niet wordt gevonden. Als u **false** opgeeft, worden fouten weergegeven. Als u **true** opgeeft, worden fouten genegeerd, wat nuttig is voor offlinescenario's. Met **SaveData** kan een bestand worden gemaakt als het apparaat offline is (als **Connection.Connected** de status **false** heeft).

## <a name="examples"></a>Voorbeelden
| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **If(Connection.Connected, ClearCollect(LocalTweets, Twitter.SearchTweet("PowerApps", {maxResults: 100})),LoadData(LocalTweets, "Tweets", true))** |Als het apparaat is verbonden, wordt de verzameling LocalTweets uit de Twitter-service geladen. Anders wordt de verzameling uit de lokale bestandscache geladen. |De inhoud wordt weergegeven, ongeacht of het apparaat online of offline is. |
| **SaveData(LocalTweets, "Tweets")** |De verzameling LocalTweets wordt als lokale bestandscache op het apparaat opgeslagen. |Gegevens worden lokaal opgeslagen, zodat **LoadData** in een verzameling kan laden. |

