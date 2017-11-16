---
title: Een aangepaste entiteit verwijderen en gegevens wissen | Microsoft Docs
description: Een aangepaste entiteit verwijderen en alle gegevens wissen.
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
ms.openlocfilehash: 2c0dbc172ee7354bc94670f9bb6993d33fca8f2c
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="delete-a-custom-entity"></a>Een aangepaste entiteit verwijderen
U kunt aangepaste entiteiten verwijderen, maar u kunt standaardentiteiten niet verwijderen.

1. Ga naar [powerapps.com](https://web.powerapps.com) en vouw de sectie **Common Data Service** uit en klik of tik op **Entiteiten** in het linkernavigatiedeelvenster. U kunt de lijst met entiteiten filteren door een of meer tekens in het zoekvak boven aan de lijst te tikken.
2. Klik of tik in de lijst met entiteiten op de entiteit die u wilt verwijderen en klik of tik vervolgens in de rechterbovenhoek op het prullenbakpictogram.
3. Klik of tik in het dialoogvenster dat verschijnt op **Verwijderen** om de entiteit te verwijderen.

## <a name="notes"></a>Opmerkingen
* Als u een entiteit verwijdert, verwijdert u zowel de definitie van de entiteit als alle gegevens die de entiteit bevat.
* Een app kan mogelijk defect raken als u een entiteit verwijdert die in de app wordt gebruikt.
* Als entiteit A [opzoekvelden](data-platform-entity-lookup.md) voor entiteit B bevat, moet u mogelijk eerst entiteit B verwijderen voordat u entiteit A verwijdert.

