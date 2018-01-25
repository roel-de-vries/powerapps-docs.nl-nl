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
ms.openlocfilehash: d3e83ad17fcafcfd65aab47b065413c5b72b4f35
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/23/2018
---
# <a name="delete-a-custom-entity"></a>Een aangepaste entiteit verwijderen
U kunt aangepaste entiteiten verwijderen, maar u kunt standaardentiteiten niet verwijderen.

1. Vouw op [powerapps.com](https://web.powerapps.com) de sectie **Common Data Service** uit en klik of tik op **Entiteiten** in het linkernavigatiedeelvenster. U kunt de lijst met entiteiten filteren door een of meer tekens in het zoekvak boven aan de lijst te tikken.
2. Klik of tik in de lijst met entiteiten op de entiteit die u wilt verwijderen en klik of tik vervolgens in de rechterbovenhoek op het prullenbakpictogram.
3. Klik of tik in het dialoogvenster dat verschijnt op **Verwijderen** om de entiteit te verwijderen.

>[!NOTE]
>Als u een entiteit verwijdert, verwijdert u zowel de definitie van de entiteit als alle gegevens die de entiteit bevat.

>[!NOTE]
>Een app kan mogelijk defect raken als u een entiteit verwijdert die in de app wordt gebruikt.

>[!NOTE]
>Als entiteit A [opzoekvelden](data-platform-entity-lookup.md) voor entiteit B bevat, moet u mogelijk eerst entiteit B verwijderen voordat u entiteit A verwijdert.

