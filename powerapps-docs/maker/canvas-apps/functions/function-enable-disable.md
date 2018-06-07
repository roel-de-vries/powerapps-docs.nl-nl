---
title: De functies Enable en Disable | Microsoft Docs
description: Referentie-informatie, inclusief syntaxis en voorbeelden, voor de functies Enable en Disable in PowerApps
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
ms.openlocfilehash: b35d819730715917f3092ca803b9a38ea9173edc
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "31825114"
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

