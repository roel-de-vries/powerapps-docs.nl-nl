---
title: Snelstartgids voor het verwijderen van een aangepaste entiteit en het wissen van gegevens | Microsoft Docs
description: Snelstartgids om een aangepaste entiteit te verwijderen en alle gegevens te wissen
services: powerapps
documentationcenter: na
author: clwesene
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 3/21/2018
ms.author: clwesene
ms.openlocfilehash: 399d3e8bac215df7612ac12d922dfe644dc59f96
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2018
---
# <a name="quickstart-delete-a-custom-entity"></a>Snelstartgids: Een aangepaste entiteit verwijderen
U kunt aangepaste entiteiten verwijderen, maar u kunt standaardentiteiten niet verwijderen.

1. Vouw op [powerapps.com](https://web.powerapps.com) de sectie **Gegevens** uit en klik of tik op **Entiteiten** in het linkernavigatiedeelvenster.

    ![Entiteitsgegevens](./media/data-platform-cds-create-entity/entitylist.png "Entiteitslijst")

2. Klik of tik in de lijst met entiteiten op de entiteit die u wilt verwijderen en klik of tik vervolgens op de optie **Entiteit verwijderen** in de opdrachtbalk.
3. Klik of tik in het dialoogvenster dat verschijnt op **Verwijderen** om de entiteit te verwijderen.

>[!NOTE]
>Als u een entiteit verwijdert, verwijdert u zowel de definitie van de entiteit als alle gegevens die de entiteit bevat. Entiteiten en de gegevens daarin kunnen niet worden hersteld als deze zijn verwijderd.

>[!NOTE]
>Een app of stroom kan mogelijk defect raken als u een entiteit verwijdert die in de app wordt gebruikt.

>[!NOTE]
>Als entiteit A [opzoekvelden](data-platform-entity-lookup.md) voor entiteit B bevat, moet u mogelijk eerst entiteit B verwijderen voordat u entiteit A verwijdert.

