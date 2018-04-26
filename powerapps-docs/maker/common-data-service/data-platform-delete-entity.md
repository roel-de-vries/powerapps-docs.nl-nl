---
title: Snelstartgids voor het verwijderen van een aangepaste entiteit en het wissen van gegevens | Microsoft Docs
description: Snelstartgids om een aangepaste entiteit te verwijderen en alle gegevens te wissen
documentationcenter: na
author: clwesene
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: cds
ms.date: 3/21/2018
ms.author: clwesene
ms.openlocfilehash: 971016233578c4eadf397d662a0ea74187548635
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
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

