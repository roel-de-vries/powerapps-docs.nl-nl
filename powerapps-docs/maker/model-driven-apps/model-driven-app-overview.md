---
title: Overzicht van het maken van een modelgestuurde app met PowerApps | Microsoft Docs
description: Stapsgewijze instructies voor het maken en configureren van een entiteit om een PowerApps-app te gebruiken.
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="what-are-model-driven-apps-in-powerapps"></a>Wat zijn modelgestuurde apps in PowerApps?

Het ontwerp van modelgestuurde apps is een onderdeelgerichte methode voor het ontwikkelen van apps. Voor het ontwerpen van modelgestuurde apps hebt u geen code nodig en u kunt eenvoudige of zeer complexe apps maken.  In tegenstelling tot bij canvasapps, waar de ontwerper volledige controle over de appindeling heeft, is bij modelgestuurde apps veel van de indeling grotendeels voor u gedefinieerd en afhankelijk van de onderdelen die u toevoegt aan de app. 

![Voorbeeld van modelgestuurde app](media/model-driven-app-overview/model-app-sample.png)

Het ontwerp van modelgestuurde apps biedt de volgende voordelen:
- Uitgebreide, op componenten gerichte omgevingen zonder code 
- Complexe responsieve apps met een vergelijkbare UI maken voor een verscheidenheid aan apparaten, zowel desktop- als mobiele apparaten
- Ontwerpmogelijkheden die lijken op wat beschikbaar is in het Dynamics 365 Customer Engagement-platform 
- Uw app kan worden gedistribueerd als oplossing
 
## <a name="the-approach-to-model-driven-app-making"></a>De benadering voor het maken van modelgestuurde apps
Op een fundamenteel niveau omvat het proces voor het maken van modelgestuurde apps drie belangrijke focusgebieden.

- Bedrijfsgegevens modelleren 
- bedrijfsprocessen definiëren 
- De app samenstellen

### <a name="modeling-business-data"></a>Bedrijfsgegevens modelleren
Voor het modelleren van bedrijfsgegevens bepaalt u welke gegevens u in uw app wilt opnemen en hoe deze gegevens samenhangen met andere gegevens. Een modelgestuurd ontwerp maakt gebruik van een architectuur op basis van metagegevens, zodat ontwerpers de app kunnen aanpassen zonder code te schrijven. Metagegevens betekent "gegevens over gegevens" en het definieert de structuur van de gegevens die in het systeem zijn opgeslagen. [Zelfstudie: een aangepaste entiteit maken die onderdelen heeft in PowerApps](../common-data-service/create-custom-entity.md)

### <a name="defining-business-processes"></a>bedrijfsprocessen definiëren
Het definiëren en afdwingen van consistente bedrijfsprocessen is een belangrijk aspect van het ontwerp van modelgestuurde apps. Consistente processen zorgen ervoor dat de gebruikers van uw app zich op hun werk kunnen concentreren en niet op het onthouden van een set handmatige stappen. Processen kunnen eenvoudig of complex zijn en worden in de loop van de tijd regelmatig gewijzigd. Als u een proces wilt maken, selecteert u in het gedeelte Modelgestuurd van PowerApps.com de optie ![Instellingen](media/powerapps-gear.png) > **Geavanceerde aanpassingen** > **Oplossingenverkenner openen**. Selecteer vervolgens in het linkernavigatiedeelvenster van de oplossingenverkenner de optie **Processen** en selecteer tenslotte **Nieuw**. Meer informatie: [Overzicht van bedrijfsprocesstromen](/flow/business-process-flows-overview) en [Bedrijfslogica toepassen met Common Data Service voor Apps](../common-data-service/cds-processes.md). 

### <a name="composing-the-model-driven-app"></a>De modelgestuurde app samenstellen
Na het modelleren van gegevens en het definiëren van processen, kunt u uw app bouwen door met de appontwerper onderdelen te selecteren en te configureren die u nodig hebt.

![Appontwerper](media/model-driven-app-overview/app-designer.png)

## <a name="next-steps"></a>Volgende stappen

[Uw eerste modelgestuurde app maken](build-first-model-driven-app.md)

[Inzicht krijgen in onderdelen van modelgestuurde apps](model-driven-app-components.md)

