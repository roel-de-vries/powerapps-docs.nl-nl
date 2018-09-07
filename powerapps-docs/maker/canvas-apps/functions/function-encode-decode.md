---
title: De functies EncodeUrl en PlainText | Microsoft Docs
description: Referentie-informatie, inclusief syntaxis en voorbeelden, voor de functies EncodeUrl en PlainText in PowerApps
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
ms.openlocfilehash: 30d3378f46e587e45314c30be1fce3c36b2bb120
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42832992"
---
# <a name="encodeurl-and-plaintext-functions-in-powerapps"></a>De functies EncodeUrl en PlainText in PowerApps
Hiermee codeert en decodeert u tekenreeksen.

## <a name="description"></a>Beschrijving
De functie **EncodeUrl** codeert een URL-reeks, waarbij niet-alfanumerieke tekens worden vervangen door % en een hexadecimaal nummer.  

De functie **PlainText** verwijdert HTML- en XML-tags en zet ze om in toepasselijk symbolen:

* **&amp;nbsp;**
* **&amp;quot;**

De geretourneerde waarde van deze functies is de gecodeerde of gecodeerde tekenreeks.   

## <a name="syntax"></a>Syntaxis
**EncodeUrl**( *String* )

* *String* - vereist.  URL die moet worden gecodeerd.

**PlainText**( *String* )

* *String* - vereist. Tekenreeks waarin HTML- en XML-tags worden verwijderd.

## <a name="examples"></a>Voorbeelden
Als u een RSS-feed weergeeft in een tekstgalerie en vervolgens de eigenschap **[Text](../controls/properties-core.md)** van een label in die galerie instelt op **ThisItem.description**, kan het label onbewerkte HTML- of XML-code tonen, zoals in dit voorbeeld:

    <p>We have done an unusually&nbsp;&quot;deep&quot; globalization and localization.<p>

Als u de eigenschap **[Text](../controls/properties-core.md)** van dat label instelt op **PlainText(ThisItem.description)**, wordt de tekst zoals in dit voorbeeld weergegeven:

    We have done an unusually "deep" globalization and localization.
