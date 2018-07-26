---
title: Een aangepaste entiteit verwijderen | Microsoft Docs
description: Stapsgewijze instructies voor het verwijderen van een aangepaste entiteit en het wissen van alle gegevens in PowerApps
author: clwesene
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: clwesene
ms.openlocfilehash: b17da30916b06b5b76b16cc6bf9758b988549f6f
ms.sourcegitcommit: 0b051bba173353d7ceda3b60921e7e009eb00709
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/24/2018
ms.locfileid: "39218643"
---
# <a name="delete-a-custom-entity"></a>Een aangepaste entiteit verwijderen
U kunt aangepaste entiteiten verwijderen, maar u kunt standaardentiteiten niet verwijderen.

1. Vouw op [powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) de sectie **Gegevens** uit en klik of tik op **Entiteiten** in het linkernavigatiedeelvenster.

    ![Entiteitsgegevens](./media/data-platform-cds-create-entity/entitylist.png "Entiteitslijst")

2. Klik of tik in de lijst met entiteiten op de entiteit die u wilt verwijderen en klik of tik vervolgens op de optie **Entiteit verwijderen** in de opdrachtbalk.

3. Klik of tik in het dialoogvenster dat verschijnt op **Verwijderen** om de entiteit te verwijderen.

>[!NOTE]
>Als u een entiteit verwijdert, verwijdert u zowel de definitie van de entiteit als alle gegevens die de entiteit bevat. Entiteiten en de gegevens daarin kunnen niet worden hersteld als deze zijn verwijderd.

>[!NOTE]
>Een app of stroom kan mogelijk defect raken als u een entiteit verwijdert die in de app wordt gebruikt.

>[!NOTE]
>Als entiteit A [opzoekvelden](data-platform-entity-lookup.md) voor entiteit B bevat, moet u mogelijk eerst entiteit B verwijderen voordat u entiteit A verwijdert.

