---
title: Functies SaveData en LoadData | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functies SaveData en LoadData in PowerApps
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
ms.openlocfilehash: c916784df877b1228fd8d9322a80ccccdc61967f
ms.sourcegitcommit: 79b8842fb0f766a0476dae9a537a342c8d81d3b3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2018
ms.locfileid: "37897887"
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

