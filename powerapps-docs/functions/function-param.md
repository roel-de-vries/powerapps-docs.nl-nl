---
title: Functies Downloaden, Starten en Parameters | Microsoft Docs
description: Referentie-informatie, inclusief syntaxis en voorbeelden, voor de functies Downloaden, Starten en Parameters in PowerApps
services: 
suite: powerapps
documentationcenter: na
author: gregli-msft
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 4ed646431263e96a079483bc514c8154b6d9b653
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="download-launch-and-param-functions-in-powerapps"></a>Functies Download, Launch en Param in PowerApps
Downloadt of start een webpagina of een app met parameters.  

## <a name="description"></a>Beschrijving
De functie **Download** downloadt een bestand van internet naar het lokale apparaat.  De gebruiker wordt om een locatie gevraagd waar het bestand moet worden opgeslagen.  **Download** retourneert de lokale locatie waar het bestand werd opgeslagen als een tekenreeks.  

De functie **Launch** start een webpagina of een app.  Deze functie kan optioneel parameters aan de app doorgeven.  

De functie **Param** ontvangt een parameter die aan de app werd doorgegeven toen hij werd gestart.  Als de genoemde parameter niet werd doorgegeven, retourneert **Param** *blank*.

## <a name="syntax"></a>Syntaxis
**Download**( *Address* )

* *Address* - vereist.  Het adres van een te downloaden webresource.

**Launch**( *Address* [, *ParameterName1*, *ParameterValue1*, ... ] )

* *Address* - vereist.  Het adres van een webpagina of de ID van een app die moet worden geopend.
* *ParameterName(s)* - optioneel.  Parameternaam.
* *ParameterValue(s)* - optioneel.  Bijbehorende parameterwaarden die aan de app of de webpagina moeten worden doorgegeven.

**Param**( *ParameterName* )

* *ParameterName* - vereist.  De naam van de parameter die aan de app wordt doorgegeven.

