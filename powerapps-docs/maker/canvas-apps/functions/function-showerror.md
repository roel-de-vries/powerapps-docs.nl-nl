---
title: De functie ShowError | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functie ShowError in PowerApps
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 03/21/2018
ms.author: gregli
ms.openlocfilehash: 1191016f26192f997b8347cdbfecc7701c19cb8c
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
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
