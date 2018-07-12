---
title: Overzicht van het bouwen van modelgestuurde apps met PowerApps | Microsoft Docs
description: Stapsgewijze instructies voor het maken en configureren van een entiteit voor gebruik met een PowerApps-app.
documentationcenter: na
author: Mattp123
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: model
ms.date: 03/21/2018
ms.author: matp
ms.openlocfilehash: eceaf1886bf77b85d6d6b3faae3f32428223cb7e
ms.sourcegitcommit: 79b8842fb0f766a0476dae9a537a342c8d81d3b3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2018
ms.locfileid: "37899497"
---
# <a name="overview-of-building-a-model-driven-app"></a>Overzicht van het bouwen van een modelgestuurde app

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
Het definiëren en afdwingen van consistente bedrijfsprocessen is een belangrijk aspect van het modelgestuurde app-ontwerp. Consistente processen zorgen ervoor dat de gebruikers van uw app zich op hun werk kunnen concentreren en niet op het onthouden van een set handmatige stappen. Processen kunnen eenvoudig of complex zijn en worden in de loop van de tijd regelmatig gewijzigd. Voor het maken van een proces selecteert u **Geavanceerd** om [Solution Explorer](#advanced-model-driven-app-making) te openen. Selecteer vervolgens in het linkernavigatiedeelvenster van Solution Explorer de optie **Processen** en selecteer tenslotte **Nieuw**. Meer informatie: [Werken met bedrijfslogica](#working-with-business-logic)  

### <a name="composing-the-model-driven-app"></a>De modelgestuurde app samenstellen
Na het modelleren van gegevens en het definiëren van processen, kunt u uw app bouwen door met de appontwerper onderdelen te selecteren en te configureren die u nodig hebt.

![Appontwerper](media/model-driven-app-overview/app-designer.png)

## <a name="model-driven-app-components-and-designers"></a>Componenten van modelgestuurde apps en ontwerpers
Een goed ontworpen modelgestuurde app bestaat uit verschillende componenten die de ontwerper selecteert voor het bouwen van de vormgeving en functionaliteit van de voltooide app. De componenten en componenteigenschappen die ontwerpers gebruiken bij de constructie van een app, worden de metagegevens. Om te begrijpen hoe elk van deze onderdelen zich verhoudt tot app-ontwerp, zijn deze hier verdeeld in de categorieën *Gegevens*, *Gebruikersinterface*, *Logica* en *Visualisatie*. 

### <a name="data"></a>Gegevens
Deze componenten bepalen op welke gegevens de app wordt gebaseerd.



|Component  |Beschrijving  |Ontwerper  |
|---------|---------|---------|
|Entiteit     |Een item met eigenschappen die u bijhoudt, zoals een contactpersoon of account. Veel standaardentiteiten zijn beschikbaar. U kunt een standaardentiteit die niet tot het systeem behoort (productie-entiteit) aanpassen of een volledig nieuwe aangepaste entiteit maken.     | [!INCLUDE [powerapps](../../includes/powerapps.md)] entiteitdesigner        |
|Veld     | Een eigenschap die is gekoppeld aan een entiteit. Een veld wordt gedefinieerd door een gegevenstype, waarmee wordt bepaald welk soort gegevens kunnen worden ingevoerd of geselecteerd. Voorbeelden zijn onder meer tekst, getal, datum en tijd, valuta of zoekactie (hiermee maakt u een relatie met een andere entiteit). Velden worden meestal gebruikt voor formulieren, weergaven en zoekopdrachten.        | [!INCLUDE [powerapps](../../includes/powerapps.md)] entiteitdesigner   |
|Relatie     | Entiteitsrelaties definiëren welke relaties entiteiten met elkaar hebben. Dit zijn de soorten relaties: 1:N (een-op-veel), N:1 (veel-op-een) en N:N (veel-op-veel) Wanneer u bijvoorbeeld een zoekveld toevoegt aan een entiteit, zorgt dit voor een nieuwe 1:N-relatie tussen de twee entiteiten en kunt u het opzoekveld op een formulier plaatsen.   | [!INCLUDE [powerapps](../../includes/powerapps.md)] entiteitdesigner        |
|Veld Optieset     | Dit is een speciaal type veld dat de gebruiker een reeks vooraf bepaalde opties biedt. Elke optie heeft een numerieke waarde en een label. Wanneer deze wordt toegevoegd aan een formulier, wordt in dit veld een besturingselement voor de gebruiker weergegeven om een optie te selecteren.  Er zijn twee soorten optiesets; optiesets waarbij de gebruiker slechts één optie kan selecteren en optiesets voor meervoudige selectie, waardoor meer dan één selectie mogelijk is.  | [!INCLUDE [powerapps](../../includes/powerapps.md)] optiesetontwerper     |

### <a name="ui"></a>GEBRUIKERSINTERFACE
Met deze componenten kunt u bepalen hoe gebruikers met de app communiceren. 

|Component  |Beschrijving  |Ontwerper  |
|---------|---------|---------|
|App     | Hiermee bepaalt u de grondbeginselen van de app zoals componenten, eigenschappen, clienttype en URL van uw app.      | Appontwerper   |
|Sitemap     | Hiermee geeft u de navigatie voor uw app aan.        | Sitemapontwerper        |
|Formulier     | Een reeks velden voor gegevensinvoer van een bepaalde entiteit die overeenkomt met de items die binnen uw organisatie voor de entiteit worden bijgehouden. Bijvoorbeeld een reeks velden voor gegevensinvoer waar gebruikers relevante informatie invoeren voor het bijhouden van de vorige bestellingen van een klant, samen met specifiek aangevraagde datums voor nieuwe bestellingen.        | Formulierontwerper        |
|Weergeven     | In Weergaven kunt u bepalen hoe een lijst met records voor een specifieke entiteit wordt weergegeven in uw app. In een weergave definieert u de weer te geven kolommen, de breedte van elke kolom, het sorteergedrag en de standaardfilters.   |  Weergaveontwerper       |

![Appontwerper en formulierontwerper](media/model-driven-app-overview/app-and-form-designers.png)

### <a name="logic"></a>Logica
Hiermee bepaalt u de bedrijfsprocessen, de regels en in hoeverre de app is geautomatiseerd. [!INCLUDE [powerapps](../../includes/powerapps.md)]-makers gebruiken een ontwerper die specifiek is voor het type proces of regel. 


|Type logica  |Beschrijving  |Ontwerper  |
|---------|---------|---------|
|Zakelijke processtroom     | Een online proces waarin gebruikers een standaard bedrijfsproces doorlopen. Gebruik bijvoorbeeld een zakelijke processtroom als u wilt dat iedereen aanvragen voor klantenservice op dezelfde manier afhandelt, of om medewerkers te verplichten om goedkeuring te vragen voor een factuur voordat zij een order verzenden.        | Ontwerper zakelijke processtroom        |
|Werkstroom     |  Via werkstromen kunt u bedrijfsprocessen automatiseren zonder gebruikersinterface. Ontwerpers gebruiken werkstromen om een automatisering in te stellen waarvoor geen interactie met de gebruiker is vereist.       | Workflow Designer        |
|Acties    |  Acties zijn een type proces waarmee u rechtstreeks vanuit een werkstroom acties handmatig kunt aanroepen, met inbegrip van aangepaste acties.       |  Procesontwerper       |
|Bedrijfsregel     | Wordt gebruikt om een logica voor regels of aanbevelingen toe te passen op een formulier, zoals het stellen van vereisten voor velden, het verbergen van velden of het valideren van gegevens. Appontwerpers implementeren en onderhouden via een eenvoudige interface snel veranderende en veelgebruikte regels.         |  Bedrijfsregelontwerper       |
|Stroom     | Flow is een op de cloud gebaseerde service waarmee u geautomatiseerde werkstromen kunt maken tussen apps en services voor het ophalen van meldingen, synchroniseren van bestanden, het verzamelen van gegevens en nog veel meer.        | Microsoft Flow        |

![Ontwerpers van werkstromen, acties en bedrijfsprocessen](media/model-driven-app-overview/designer-mash.png)

### <a name="visualizations"></a>Visualisaties
Hiermee wordt bepaald over welk type gegevensvisualisaties en rapportage de app gaat beschikken.


|Component  |Beschrijving  |Ontwerper  |
|---------|---------|---------|
|Grafiek     | Eén enkele grafische visualisatie die kan worden weergegeven in een weergave of op een formulier, of die kan worden toegevoegd aan een dashboard.        | Grafiekontwerper        |
|Dashboard     | Fungeert als een palet voor een of meer grafische visualisaties die een overzicht van bruikbare bedrijfsgegevens bieden.        | Dashboardontwerper        |
|Ingesloten Power BI     | Ingesloten Power BI-tegels en -dashboards toevoegen aan uw app. Power BI is een cloudservice die u inzicht in business intelligence biedt.        |  Combinatie van grafiekontwerper, dashboardontwerper en Power BI       |

![Voorbeelddashboard](media/model-driven-app-overview/dashboard-designer.png)

### <a name="advanced-model-driven-app-making"></a>Geavanceerde modelgestuurde apps maken
Solution Explorer is een uitgebreid hulpprogramma dat wordt gebruikt voor het bouwen van geavanceerde modelgestuurde apps. In Solution Explorer kunt u met het navigatievenster aan de linkerkant van het hulpprogramma door een hiërarchie navigeren die bestaat uit alle app-componenten.

![Solution Explorer](media/model-driven-app-overview/solutionexplorer-entitiescollapsed.png)

Als u Solution Explorer wilt openen, selecteert u **Modelgestuurd** in het linkerdeelvenster van [!INCLUDE [powerapps](../../includes/powerapps.md)].

  ![Selecteer Modelgestuurd](media/model-driven-app-overview/app-type-picker-mod.png)

Selecteer vervolgens het tabblad **Geavanceerd**. 

## <a name="model-driven-app-development-resources"></a>Resources voor het ontwikkelen van modelgestuurde apps
Zie de volgende onderwerpen voor meer informatie over het ontwikkelen van modelgestuurde apps.
### <a name="modeling-your-data"></a>Uw gegevens modelleren
- [Aangepaste zakelijke apps ontwerpen met de appontwerper](https://docs.microsoft.com/dynamics365/customer-engagement/customize/design-custom-business-apps-using-app-designer)
- [Formulieren maken en ontwerpen](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-design-forms)
- [Weergaven maken of bewerken](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-edit-views)  

### <a name="modeling-and-composing-your-app"></a>Uw app modelleren en samenstellen
- [Entiteiten maken of bewerken](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-edit-entities)
- [Relaties maken en bewerken](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-edit-entity-relationships) 
- [Velden maken en bewerken](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-edit-fields)
- [Algemene optiesets maken en bewerken](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-edit-global-option-sets)

### <a name="working-with-business-logic"></a>Werken met bedrijfslogica
- [Overzicht zakelijke processtromen](https://docs.microsoft.com/dynamics365/customer-engagement/customize/business-process-flows-overview)
- [Werkstroomprocessen gebruiken om processen te automatiseren](https://docs.microsoft.com/dynamics365/customer-engagement/customize/workflow-processes)
- [Overzicht van acties](https://docs.microsoft.com/dynamics365/customer-engagement/customize/actions)
- [Bedrijfsregels maken en aanbevelingen doen voor het toepassen van logica](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-business-rules-recommendations-apply-logic-form)

### <a name="using-visualizations-in-your-app"></a>Visualisaties gebruiken in uw app
- [Een systeemgrafiek maken of bewerken](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-edit-system-chart)
- [Dashboards maken of bewerken](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-edit-dashboards)


### <a name="distributing-your-app"></a>Uw app distribueren
[Een oplossing maken](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-solution)

## <a name="next-steps"></a>Volgende stappen
[Snelstart: Een aangepaste entiteit maken](../common-data-service/data-platform-create-entity.md)

[Zelfstudie: Een aangepaste entiteit met componenten in PowerApps maken](../common-data-service/create-custom-entity.md)

