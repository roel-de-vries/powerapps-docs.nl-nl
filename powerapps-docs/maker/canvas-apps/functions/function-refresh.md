---
title: FunctieFunctie Vernieuwen | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functie Refresh in PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/21/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 2999665e5882245b594468b6babe67be575c5c1e
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42843592"
---
# <a name="refresh-function-in-powerapps"></a>De functie Refresh in PowerApps
Hiermee vernieuwt u de [records](../working-with-tables.md#records) van een [gegevensbron](../working-with-data-sources.md).

## <a name="description"></a>Beschrijving
De functie **Refresh** haalt een nieuwe kopie van een gegevensbron op.  U ziet dan wijzigingen die andere gebruikers hebben aangebracht.

**Refresh** heeft geen retourwaarde en u kunt deze functie alleen gebruiken in [gedragsformules](../working-with-formulas-in-depth.md).

## <a name="syntax"></a>Syntaxis
**Refresh**( *DataSource* )

* *DataSource* - vereist. De gegevensbron die u wilt vernieuwen.

## <a name="example"></a>Voorbeeld
In dit voorbeeld vernieuwt u de gegevensbron met de naam **IJs** die begint met deze gegevens:

![](media/function-refresh/icecream.png)

Een gebruiker op een ander apparaat wijzigt **Aantal** in de record **Aardbeien** in **400**.  U ziet deze wijziging pas nadat u deze formule hebt uitgevoerd:

**Refresh( IJs )**

Nadat de formule is uitgevoerd, wordt in galerieën die zijn gebonden aan de gegevensbron **IJs** de bijgewerkte waarde voor **Aardbeien** weergegeven:

![](media/function-refresh/icecream-after.png)

