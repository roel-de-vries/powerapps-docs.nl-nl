---
title: De functies Enable en Disable | Microsoft Docs
description: Referentie-informatie, inclusief syntaxis en voorbeelden, voor de functies Enable en Disable in PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 1b5395459dd5833d054755dadca37bc9b39785c9
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/13/2018
ms.locfileid: "39019061"
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

