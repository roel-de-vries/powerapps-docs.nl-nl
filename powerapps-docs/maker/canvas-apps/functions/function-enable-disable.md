---
title: De functies Enable en Disable | Microsoft Docs
description: Referentie-informatie, inclusief syntaxis en voorbeelden, voor de functies Enable en Disable in PowerApps
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
ms.openlocfilehash: 3b9801e804284cb52d389aa0c57d1247a008dd0d
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2018
---
# <a name="enable-and-disable-functions-in-powerapps"></a>De functies Enable en Disable in PowerApps
Hiermee schakelt u een [signaal](signals.md) in of uit.

## <a name="overview"></a>Overzicht
Sommige signalen kunnen vaak wijzigen, waardoor de app opnieuw moet berekenen.  Snelle wijzigingen gedurende een lange periode kunnen de accu van het apparaat snel leeg maken. Met deze functies kunt u handmatig een signaal in- of uitschakelen.

Wanneer een signaal niet wordt gebruikt, wordt het automatisch uitgeschakeld.

## <a name="description"></a>Beschrijving
De functies **Enable** en **Disable** schakelen een signaal respectievelijk in en uit.

Deze functies werken op dit moment alleen voor het signaal **[Location](signals.md)**.

Deze functies retourneren geen waarde. U kunt de functies alleen gebruiken in [gedragsformules](../working-with-formulas-in-depth.md).

## <a name="syntax"></a>Syntaxis
**Enable**( *Signal* )<br>**Disable**( *Signal* )

* *Signal* - vereist.  Het signaal om in of uit te schakelen.

