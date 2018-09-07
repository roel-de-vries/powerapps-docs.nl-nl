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
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: f3932d21683b83008e95f03ba2aae646d2b8e491
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42836456"
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

