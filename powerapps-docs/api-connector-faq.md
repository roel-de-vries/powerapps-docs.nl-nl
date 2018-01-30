---
title: Veelgestelde vragen over API-connectors | Microsoft Docs
description: Vind antwoorden op vragen over vereisten, triggers en andere zaken.
services: 
suite: powerapps
documentationcenter: na
author: asavaritayal
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/06/2017
ms.author: astay
ms.openlocfilehash: b945f2775e26327557255a75f18e87a638a9fe66
ms.sourcegitcommit: 33099e6197c0139679cd08c42e9e2a5717904c92
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/12/2018
---
# <a name="api-connector-faq-powerapps"></a>Veelgestelde vragen over API-connectors (PowerApps)
## <a name="requirements"></a>Vereisten
**V:** Als ik geen ISV ben, kan ik dan toch een connector bouwen?

**A:** Als u een connector openbaar beschikbaar wilt stellen, moet u eigenaar van de onderliggende service zijn of expliciete rechten hebben om de API te gebruiken.

**V:** Kan ik een connector bouwen zonder REST API's?

**A:** Nee. Als u een API-connector wilt bouwen, moet u stabiele HTTP REST API's ondersteunen voor uw service.

**V:** Welke verificatietypen worden ondersteund?

**A:** Wij ondersteunen de volgende verificatiestandaarden:

* OAuth 2.0 (inclusief Azure Active Directory)
* API-sleutel
* Basisverificatie

## <a name="triggers"></a>Triggers
**V:** Kan ik triggers bouwen zonder webhooks? 

**A:** Met API-connectors voor Microsoft Flow en Logic Apps kunt u alleen webhook-gebaseerde triggers bouwen. Als u een verzoek wilt indienen voor andere implementatievormen, neemt u contact op met [condevhelp@microsoft.com](mailto:condevhelp@microsoft.com) en geeft u meer informatie over uw API.

## <a name="miscellaneous"></a>Diversen
**V:** Mijn API's maken gebruik van een dynamische host. Hoe implementeer ik deze in de OpenAPI?

**A:** De API-connectorfunctie biedt geen ondersteuning voor dynamische hosts. Gebruik een statische host voor ontwikkelings- en testdoeleinden. Praat tijdens het indienen van uw verzoek met uw Microsoft-contactpersoon over de dynamische implementatie.

**V:** Wordt Postman Collection V2 ondersteund?

**A:** Nee, Postman V2 wordt momenteel niet ondersteund.

**V:** Wordt OpenAPI 3.0 ondersteund?

**A:** Nee, OpenAPI 2.0 is momenteel de enige ondersteunde versie.

