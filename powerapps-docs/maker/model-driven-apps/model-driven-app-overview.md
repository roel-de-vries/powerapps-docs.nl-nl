---
title: Overzicht van het bouwen van modelgestuurde apps met PowerApps | Microsoft Docs
description: Stapsgewijze instructies voor het maken en configureren van een entiteit voor gebruik met een PowerApps-app.
documentationcenter: na
author: Mattp123
manager: kvivek
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: model
ms.date: 08/09/2018
ms.author: matp
ms.openlocfilehash: f6434e6a9248586c05fa0b56b8934d910af3087a
ms.sourcegitcommit: 2a61989be5880fede31510c5dab1593a6f42a741
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/09/2018
ms.locfileid: "39723841"
---
# <a name="what-are-model-driven-apps-in-powerapps"></a>Wat zijn modelgestuurde apps in PowerApps?

Het ontwerp van modelgestuurde apps is een componentgerichte methode voor het ontwikkelen van apps. Het ontwerp van modelgestuurde apps vereist geen code en de apps die u maakt, kunnen eenvoudig of zeer complex zijn.  In tegenstelling tot ontwikkeling van canvas-apps waar de ontwerper volledige controle over de app-indeling heeft, wordt met modelgestuurde apps een groot deel van de lay-out voor u bepaald en grotendeels bepaald door de onderdelen die u aan de app toevoegt. 

![Voorbeeld van modelgestuurde app](media/model-driven-app-overview/model-app-sample.png)

Het ontwerp van modelgestuurde apps biedt de volgende voordelen:
- Rijke componentgerichte omgevingen voor ontwerpen zonder code 
- Complexe responsieve apps maken met een vergelijkbare UI in een groot aantal apparaten, van pc tot mobiele apparatuur
- Ontwerpfunctionaliteit is vergelijkbaar met wat beschikbaar is in het Dynamics 365 Customer Engagement-platform 
- Uw app kan als oplossing worden gedistribueerd
 
## <a name="the-approach-to-model-driven-app-making"></a>De aanpak voor het maken van modelgestuurde apps
Op een fundamenteel niveau bestaat het maken van modelgestuurde apps uit drie belangrijke focusgebieden.

- Bedrijfsgegevens modelleren 
- Bedrijfsprocessen definiëren 
- De app samenstellen

### <a name="modeling-business-data"></a>Bedrijfsgegevens modelleren
Voor het modelleren van bedrijfsgegevens bepaalt u welke gegevens u in uw app wilt opnemen en hoe deze gegevens samenhangen met andere gegevens. Een modelgestuurd ontwerp maakt gebruik van een architectuur op basis van metagegevens, zodat ontwerpers de app kunnen aanpassen zonder code te schrijven. Metagegevens betekent 'gegevens over gegevens'. Deze gegevens bepalen de structuur van de gegevens die zijn opgeslagen in het systeem. [Zelfstudie: Een aangepaste entiteit met componenten in PowerApps maken](../common-data-service/create-custom-entity.md)

### <a name="defining-business-processes"></a>Bedrijfsprocessen definiëren
Het definiëren en afdwingen van consistente bedrijfsprocessen is een belangrijk aspect van het modelgestuurde app-ontwerp. Consistente processen zorgen ervoor dat de gebruikers van uw app zich op hun werk kunnen concentreren en niet op het onthouden van een set handmatige stappen. Processen kunnen eenvoudig of complex zijn en worden in de loop van de tijd regelmatig gewijzigd. Als u een proces wilt maken, gaat u in het gedeelte Modelgestuurd van PowerApps.com naar ![Instellingen](media/powerapps-gear.png) > **Geavanceerde aanpassingen** > **Solution Explorer openen**. Selecteer vervolgens in het linkernavigatiedeelvenster van Solution Explorer de optie **Processen** en selecteer tenslotte **Nieuw**. Meer informatie: [Overzicht zakelijke processtromen](/flow/business-process-flows-overview) en [Bedrijfslogica toepassen met Common Data Service for Apps](../common-data-service/cds-processes.md). 

### <a name="composing-the-model-driven-app"></a>De modelgestuurde app samenstellen
Na het modelleren van gegevens en het definiëren van processen, kunt u uw app bouwen door met de appontwerper onderdelen te selecteren en te configureren die u nodig hebt.

![Appontwerper](media/model-driven-app-overview/app-designer.png)

## <a name="next-steps"></a>Volgende stappen

[Uw eerste modelgestuurde app bouwen](build-first-model-driven-app.md)

[Componenten van modelgestuurde apps begrijpen](model-driven-app-components.md)

