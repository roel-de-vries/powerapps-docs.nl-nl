---
title: De functie ShowError | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functie ShowError in PowerApps
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
ms.date: 03/21/2018
ms.author: gregli
ms.openlocfilehash: 7c1d5a8c7b35d316a2720d564977170029e28359
ms.sourcegitcommit: a9d33322228c398d29964429602dc3fe19fa67d2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/28/2018
---
# <a name="showerror-function-in-powerapps"></a>De functie ShowError in PowerApps
Hiermee wordt een fout weergegeven aan de gebruiker.

## <a name="description"></a>Beschrijving
Met de functie **ShowError** wordt een fout weergegeven aan de gebruiker.  Er worden berichten weergegeven bij het schrijven van de app en wanneer eindgebruikers gebruikmaken van de app.

**ShowError** kan alleen worden gebruikt in [gedragsformules](../working-with-formulas-in-depth.md).

Met **ShowError** wordt altijd *true* geretourneerd.

**ShowError** kan worden gekoppeld aan de functie [**IfError**](function-iferror.md) om fouten met een aangepast foutbericht te detecteren en rapporteren.

## <a name="syntax"></a>Syntaxis
**ShowError**( *Message* )

* *Message*: vereist.  Bericht dat wordt weergegeven aan de gebruiker. 

## <a name="examples"></a>Voorbeelden

### <a name="step-by-step"></a>Stap voor stap

1. Voeg een **knop**besturingselement toe aan het scherm.

2. Stel de eigenschap **OnSelect** van de **knop** in op:

    **ShowError( "Hello, World" )**

3. Klik of druk op de knop.  

    Telkens wanneer op de knop wordt geklikt, wordt het bericht **Hello, World** aan de gebruiker weergegeven.

    ![In de ontwerpomgeving Button.OnSelect weergeven, ShowError aanroepen en het bericht 'Hello, World' in een rode banner weergegeven aan de gebruiker](media/function-showerror/hello-world.png)
