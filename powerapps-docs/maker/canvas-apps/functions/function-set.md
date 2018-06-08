---
title: De functie Set | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functie Set in PowerApps
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 06/29/2017
ms.author: gregli
ms.openlocfilehash: 3615328bf1c272425779998545b0d16ac5626297
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "31832599"
---
# <a name="set-function-in-powerapps"></a>De functie Set in PowerApps
De waarde van een globale variabele instellen.

## <a name="overview"></a>Overzicht
Gebruik de functie **Set** om de waarde van een globale variabele in te stellen die tijdelijk een stukje informatie opslaat, zoals het aantal keren dat de gebruiker een knop heeft geselecteerd of het resultaat van een gegevensbewerking.  

Globale variabelen zijn in uw app beschikbaar op alle schermen.  Dit zijn de meest eenvoudige variabelen en voldoen voor de meeste situaties.  Er zijn ook contextvariabelen die zijn gericht op één scherm en verzameling, die wijzigingen in tabellen op rijniveau mogelijk maken.  Zie voor meer informatie over deze opties [werken met variabelen](../working-with-variables.md).

PowerApps zijn gebaseerd op formules die automatisch opnieuw worden berekend terwijl de gebruiker de app gebruikt.  Globale variabelen bieden dit voordeel niet, waardoor uw app mogelijk moeilijker te ontwikkelen en te begrijpen is.  Raadpleeg [werken met variabelen](../working-with-variables.md) voordat u een variabele gebruikt.

## <a name="description"></a>Beschrijving
Globale variabelen worden impliciet gemaakt met behulp van de functie **Set**.  Er is geen expliciete declaratie vereist.  Als u alle **Set**-functies verwijdert voor een globale variabele, gaat de globale variabele verloren.  Om een variabele te wissen, stelt u de waarde ervan in op het resultaat van de functie [**Blank**](function-isblank-isempty.md).

U ziet de waarden, definities en het gebruik van uw variabelen met de weergave Variabelen onder het menu Bestand in de ontwerpomgeving.

Zoals de voorbeelden verderop in dit onderwerp laten zien, kunnen globale variabelen verschillende soorten informatie bevatten, waaronder de volgende:

* één waarde
* een record
* een tabel
* een verwijzing naar een object
* een resultaat van een formule

Een globale variabele behoudt zijn waarde totdat de app wordt gesloten.  Nadat de app is gesloten, gaat de waarde van de globale variabele verloren en moet die opnieuw worden gemaakt wanneer de app wordt geladen.

Globale variabelen kunnen niet dezelfde naam gebruiken als een bestaande verzameling of bestaand besturingselement.  Ze kunnen wel dezelfde naam gebruiken als een contextvariabele.  Om onderscheid te maken tussen de twee, gebruikt u de [Ondubbelzinnigheidsoperator](operators.md#disambiguation-operator).

**Set** heeft geen retourwaarde en u kunt deze functie alleen gebruiken in een [gedragsformule](../working-with-formulas-in-depth.md).

## <a name="syntax"></a>Syntaxis
**Set**( *VariableName*, *Value* )

* *VariableName*: vereist.  De naam van de globale variabele die moet worden gemaakt of bijgewerkt.
* *Value*: vereist.  De waarde die moet worden toegewezen aan de contextvariabele.

## <a name="examples"></a>Voorbeelden
| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **Set(&nbsp;Teller,&nbsp;1&nbsp;)** |Hiermee maakt of wijzigt u de globale variabele **Teller** en stelt u de waarde in op **1**. |**Teller** heeft de waarde **1**. U kunt verwijzen naar die variabele door de naam **Teller** in een formule te gebruiken. |
| **Set(&nbsp;Teller,&nbsp;2&nbsp;)** |Hiermee stelt u de waarde van de globale variabele **Teller** uit het vorige voorbeeld in op **2**. |**Teller** heeft de waarde **2**. |
| **Set(&nbsp;Teller,&nbsp;Teller + 1&nbsp;)** |Hiermee stelt u de waarde van de globale variabele **Teller** uit het vorige voorbeeld in op **3**. |**Teller** heeft de waarde **3**. |
| **Set(&nbsp;Naam,&nbsp;"Lily" )** |Hiermee maakt of wijzigt u de globale variabele **Naam** en stelt u de waarde in op **Lily**. |**Naam** heeft de waarde **Lily**. |
| **Set(&nbsp;Persoon,&nbsp;{&nbsp;Naam:&nbsp;"Jobse", Adres:&nbsp;"1&nbsp;Grote&nbsp;Markt"&nbsp;} )** |Hiermee maakt of wijzigt u de globale variabele **Persoon** en stelt u de waarde in op een record. De record bevat twee kolommen, genaamd **Naam** en **Adres**. De waarde van de kolom **Naam** is **Jobse** en de waarde van de kolom **Adres** is **Oude Markt 1**. |**Persoon** heeft de waarde van record **{&nbsp;Naam:&nbsp;"Jobse", Adres:&nbsp;"1&nbsp;Grote&nbsp;Markt"&nbsp;}**.<br><br>U kunt verwijzen naar deze record in zijn geheel met de naam **Persoon** of u kunt verwijzen naar een afzonderlijke kolom in deze record met **Persoon.Naam** of **Persoon.Adres**. |
| **Set(&nbsp;Persoon, Patch(&nbsp;Persoon,&nbsp;{Adres:&nbsp;"2&nbsp;Grote&nbsp;Markt"&nbsp;}&nbsp;)&nbsp;)** |Gebruikt de functie **[Patch](function-patch.md)** om de globale variabele **Persoon** bij te werken door de waarde van de kolom **Adres** te wijzigen in **Grote Markt 2**. |**Persoon** heeft nu de waarde van record **{&nbsp;Naam:&nbsp;"Jobse", Adres:&nbsp;"Grote&nbsp;Markt&nbsp;2"&nbsp;}**. |

