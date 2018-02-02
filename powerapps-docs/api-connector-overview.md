---
title: Overzicht API-connectors | Microsoft Docs
description: Onafhankelijke softwareontwikkelaars en eigenaren van een SaaS-service kunnen connectors ontwikkelen en ze door Microsoft laten certificeren.
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
ms.openlocfilehash: 74bac3b0f5bad2b95ab9b6b312fc5209bf5da3a2
ms.sourcegitcommit: 68eee592c351688e5d0bd458f33a70be507fa53f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/30/2018
---
# <a name="api-connector-overview-powerapps"></a>Overzicht API-connectors (PowerApps)
Een **API-connector** is een op OpenAPI (Swagger) gebaseerde wrapper rond een REST API, waardoor de onderliggende service kan communiceren met [Microsoft Flow](https://flow.microsoft.com), [PowerApps](https://powerapps.microsoft.com) en [Logic Apps](https://docs.microsoft.com/azure/logic-apps/). Deze stelt gebruikers in staat hun accounts te verbinden en gebruik te maken van een reeks vooraf gebouwde **triggers** en **acties**, waarmee ze hun apps en werkstromen kunnen ontwikkelen.

Als **onafhankelijke softwareontwikkelaar** of **eigenaar van een SaaS-service** kunt u connectors bouwen en beschikken over een uitgebreide reeks bedrijfs- en productiviteitsscenario's voor uw gebruikers. Dankzij een connector bent u in het bezit van meer dan alleen een vastgesteld aantal integraties en kunt u het bereik, de zichtbaarheid en het gebruik van uw service vergroten.

## <a name="requirements"></a>Vereisten
Als u een connector wilt bouwen en indienen, moet uw service aan de volgende vereisten voldoen:

* Een scenario voor zakelijke gebruikers dat goed aansluit bij Microsoft Flow, PowerApps en Logic Apps
* Openbaar beschikbare service met stabiele REST API's

## <a name="build-your-connector"></a>De connector bouwen
De eerste stap bij het bouwen van een API-connector bestaat uit het ontwikkelen van een volledig functionele, aangepaste connector. Een aangepaste connector werkt net zo als een API-connector, maar de maker en bepaalde gebruikers binnen de tenant van de maker kunnen er slechts in beperkte mate over beschikken.

De procedure voor het bouwen van een connector bestaat uit meerdere stappen:

![Stappen voor het bouwen van een API-connector](./media/api-connectors-overview/authoring-steps.png)

[Meer informatie](api-connector-dev.md) over het ontwikkelen van een API-connector.

## <a name="submit-for-certification"></a>Indienen voor certificering
Nadat u een connector hebt gebouwd, dient u deze in te dienen voor certificering. Als onderdeel van ons externe certificeringsproces controleert Microsoft de connector voordat deze wordt gepubliceerd.

Het proces valideert de functionaliteit van de connector in Microsoft Flow en PowerApps, en controleert op technische en inhoudsmatige naleving.

[Meer informatie](api-connector-submission.md) over het proces voor het indienen van uw connector voor certificering en publicatie.

## <a name="get-support"></a>Krijg ondersteuning
Voor hulp bij het voorbereiden en ontwikkelen, kunt u een e-mail sturen naar [condevhelp@microsoft.com](mailto:condevhelp@microsoft.com). Dit account wordt actief bewaakt en beheerd. Query's en incidenten van ontwikkelaars worden zo snel mogelijk naar de desbetreffende teams doorgestuurd.

