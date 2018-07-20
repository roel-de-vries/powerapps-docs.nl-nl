---
title: De functie Gebruiker | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis, voor de functie Gebruiker in PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2016
ms.author: gregli
ms.openlocfilehash: 05fcf0e10522bf8f70972ddc5b86d504afb28e4e
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/13/2018
ms.locfileid: "39022281"
---
# <a name="user-function-in-powerapps"></a>De functie Gebruiker in PowerApps
Retourneert informatie over de huidige gebruiker.

## <a name="description"></a>Beschrijving
De functie **Gebruiker** retourneert een [record](../working-with-tables.md#records) met informatie over de huidige gebruiker:

| Eigenschap | Beschrijving |
| --- | --- |
| **User().Email** |E-mailadres van de huidige gebruiker. |
| **User().FullName** |Volledige naam van de huidige gebruiker, met voor- en achternaam. |
| **User().image** |Afbeelding van de huidige gebruiker. Dit is een afbeeldings-URL in de vorm "blob:*id*". Stel de eigenschap **[Afbeelding](../controls/properties-visual.md)** van het besturingselement **[Afbeelding](../controls/control-image.md)** in op deze waarde om de afbeelding in de app weer te geven. |

> [!NOTE]
> De informatie die wordt geretourneerd, is de informatie over de huidige PowerApps-gebruiker.  Dit komt overeen met de 'Account'-informatie die wordt weergegeven in de PowerApps-spelers en -studio, die buiten alle opgestelde apps kan worden gevonden.  Mogelijk komt dit niet overeen met de informatie van de huidige gebruiker in Office 365 of andere services.

## <a name="syntax"></a>Syntaxis
**User**()

## <a name="examples"></a>Voorbeelden
De huidige PowerApps-gebruiker heeft de volgende informatie:

* Volledige naam: **"John Doe"**
* E-mailadres: **"john.doe@contoso.com"**
* Afbeelding: ![](media/function-user/john-doe-picture.png) 

|       Formule       |                                                                    Beschrijving                                                                    |                                                 Resultaat                                                  |
|---------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------|
|     **Gebruiker()**      |                                             Record met alle gegevens van de huidige PowerApps-gebruiker.                                             |    { VolledigeNaam:&nbsp;"John Doe", E-mail:&nbsp;john.doe@contoso.com Afbeelding:&nbsp;"blob:1234...5678"}    |
|  **User().Email**   |                                                 Het e-mailadres van de huidige PowerApps-gebruiker.                                                  |                                         "john.doe@contoso.com"                                          |
| **User().FullName** |                                                   De volledige naam van de huidige PowerApps-gebruiker.                                                    |                                               "John Doe"                                                |
|  **User().image**   | De afbeeldings-URL voor de huidige PowerApps-gebruiker.  Stel de eigenschap **Afbeelding** van het besturingselement **Afbeelding** in op deze waarde om de afbeelding in de app weer te geven. | "blob:1234...5678"<br><br>Met **ImageControl.Image**:<br>![](media/function-user/john-doe-picture.png) |

