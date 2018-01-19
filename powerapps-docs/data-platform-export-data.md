---
title: Gegevens importeren of exporteren | Microsoft Docs
description: Een entiteit importeren of exporteren.
services: powerapps
documentationcenter: na
author: kfend
manager: kfend
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/06/2016
ms.author: kfend
ms.openlocfilehash: 880881b31362d38ed0d44126245dd96d2a74150f
ms.sourcegitcommit: 33099e6197c0139679cd08c42e9e2a5717904c92
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/12/2018
---
# <a name="import-or-export-data-from-the-common-data-service"></a>Gegevens importeren in of exporteren uit Common Data Service
U kunt gegevens op twee manieren naar of uit Common Data Service verplaatsen:

* Als u een eenmalige bulkimport- of bulkexportbewerking wilt uitvoeren, kunt u Microsoft Excel gebruiken voor meerdere entiteiten.
* Als u doorlopend gegevens voor een enkele entiteit wilt importeren of exporteren naar een andere service, zoals Dynamics 365 of Salesforce, of zelfs naar een Excel-bestand. U kunt [Microsoft Flow](https://flow.microsoft.com) gebruiken om een doorlopende import- of exportbewerking in te stellen.

## <a name="import-or-export-data-once"></a>Gegevens eenmalig importeren of exporteren
### <a name="import-data-from-excel"></a>Gegevens importeren uit Excel
1. Vouw op [powerapps.com](https://web.powerapps.com) de sectie **Common Data Service** uit en klik of tik op **Entiteiten** in het linkernavigatiedeelvenster.
2. Klik of tik naast **Nieuwe entiteit** op het beletselteken en klik of tik vervolgens op **Gegevens importeren**.
3. Selecteer de entiteit waarin u de gegevens wilt importeren en klik of tik op **Volgende**.
4. Klik of tik op **Zoeken**. Selecteer het bestand waaruit u de gegevens wilt importeren.
5. Als de **toewijzingsstatus** niet **Overeenkomst** met een groen vinkje is, moet u de toewijzing opgeven tussen de entiteitsvelden en de kolommen in het Excel-bestand. U wijst de kolommen als volgt toe:
   1. Klik of tik op **Toewijzen weergeven**.
   2. Selecteer voor elk entiteitsveld de overeenkomende kolom in het Excel-bestand.
   3. Klik of tik op **Wijzigingen opslaan**.
6. Klik op **Importeren**.

### <a name="export-data-to-excel"></a>Gegevens exporteren naar Excel
U kunt eenmalig gegevens exporteren van een standaardentiteit of aangepaste entiteit, en u kunt gegevens exporteren van meerdere entiteiten tegelijk. Als u gegevens exporteert uit meer dan één entiteit, worden de gegevens van elke entiteit geëxporteerd naar een apart Excel-bestand.

1. Klik of tik in het linkernavigatiedeelvenster op [powerapps.com](https://web.powerapps.com) op **Entiteiten**.
2. Klik of tik naast **Nieuwe entiteit** op het beletselteken en klik of tik vervolgens op **Gegevens exporteren**.
3. Selecteer de entiteiten waaruit u de gegevens wilt exporteren en klik of tik op **Exporteren naar Excel**.
4. Wanneer **Het exporteren is voltooid** wordt weergegeven, klikt of tikt u op **Geëxporteerde gegevens downloaden** om de gegevens te downloaden.

## <a name="use-microsoft-flow-to-set-up-ongoing-import-or-export"></a>Microsoft Flow gebruiken om een doorlopende import of export in te stellen
U kunt een doorlopende import- of exportbewerking instellen voor één standaardentiteit of aangepaste entiteit tegelijk. De mogelijke locaties waarmee u verbinding kunt maken, zijn onder andere:

* Dynamics 365
* Salesforce
* Microsoft Excel-bestanden die zijn opgeslagen bij een cloudbestandprovider
* Een Microsoft SQL-database, zowel in de cloud als on-premises
* Een aangepaste connector die u definieert om verbinding te maken met uw eigen systemen

Als u momenteel Microsoft Flow gebruikt om gegevens te importeren of exporteren, werkt deze toepassing niet als een volledige synchronisatieservice. Wanneer een object aan de ene service wordt toegevoegd, wordt het geïmporteerd in het andere systeem. Maar als een object wordt verwijderd uit het ene systeem, wordt het niet verwijderd uit het andere systeem.

De manier waarop u het importeren instelt, is afhankelijk van of er al een sjabloon bestaat voor het object dat u wilt importeren. Als er al een sjabloon aanwezig is, kunt u dat instellen voor het kopiëren van gegevens van het ene systeem naar het andere. Zie [Een stroom maken die gebruikmaakt van de Microsoft Common Data Service](https://flow.microsoft.com/documentation/common-data-model-intro/) voor meer informatie. Als er echter niet zo'n sjabloon bestaat, moet u een stroom maken die de database kan gebruiken. Raadpleeg [Een stroom maken vanaf het begin](https://flow.microsoft.com/documentation/get-started-logic-flow/) voor meer informatie.

