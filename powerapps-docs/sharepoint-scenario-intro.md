---
title: PowerApps, Microsoft Flow en Power BI integreren met SharePoint Online (inleiding) | Microsoft Docs
description: "In deze reeks zelfstudies wordt uitgelegd hoe u een app voor eenvoudig projectbeheer ontwikkelt op basis van SharePoint-lijsten en drie primaire technologieën die integreren met SharePoint Online: PowerApps, Microsoft Flow en Power BI."
services: 
suite: powerapps
documentationcenter: na
author: mgblythe
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/12/2017
ms.author: mblythe
ms.openlocfilehash: 98998b30eb4c407c6c2dcaa61c04c75d5b92e4f9
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="integrate-powerapps-microsoft-flow-and-power-bi-with-sharepoint-online"></a>PowerApps, Microsoft Flow en Power BI integreren met SharePoint Online
Hebt u SharePoint Online en wilt u uw bedrijfsprocessen beter automatiseren en stroomlijnen? Hebt u gewerkt met PowerApps, Microsoft Flow of Power BI, maar u weet niet hoe u deze met SharePoint Online kunt gebruiken? Dan bent u hier op de juiste plaats. In deze reeks zelfstudies wordt uitgelegd hoe u een app voor eenvoudig projectbeheer ontwikkelt op basis van SharePoint-lijsten en drie primaire technologieën die integreren met SharePoint Online: PowerApps, Microsoft Flow en Power BI. Deze technologieën werken met elkaar samen, waardoor u uw bedrijfsresultaten eenvoudig kunt *meten*, op de resultaten *reageren* en uw werkstromen *automatiseren*. Als u deze reeks hebt voltooid, dan beschikt u over een prima scenario. Bijvoorbeeld het volgende:

![Diagram van voltooid scenario](./media/sharepoint-scenario-intro/composite-with-background.png)

## <a name="business-scenario"></a>Bedrijfsscenario
In deze reeks zelfstudies heeft het bedrijf Contoso een SharePoint Online-site waar het de levenscyclus van de processen beheert, van aanvraag, via goedkeuring en ontwikkeling, naar de uiteindelijke beoordeling. Een *projectaanvrager*, bijvoorbeeld een afdelingshoofd, vraagt een IT-project aan door een item toe te voegen aan een SharePoint-lijst. Een *projectfiatteur*, bijvoorbeeld een IT-beheerder, beoordeelt het project, waarna deze het goedkeurt of afkeurt. Indien goedgekeurd, wordt het project toegewezen aan een *projectmanager* en worden via dezelfde app aanvullende details aan een tweede lijst toegevoegd. Een *bedrijfsanalist* beoordeelt de huidige en voltooide projecten met behulp van een Power BI-rapport dat in SharePoint is ingesloten.  Microsoft Flow wordt gebruikt om een goedkeurings-e-mail te verzenden en op de Power BI-waarschuwingen te reageren.

## <a name="getting-started-quickly"></a>Snel aan de slag
Het scenario dat in deze reeks zelfstudies wordt gepresenteerd, is eenvoudig in vergelijking met een app voor een volwaardig projectbeheer en bijbehorende analyse, maar het kost toch nog tijd om alle taken te voltooien. Als u slechts een snelle inleiding zoekt voor het gebruik van PowerApps, Microsoft Flow en Power BI met SharePoint, lees dan de volgende artikelen:

* **PowerApps**: [Een app genereren vanuit SharePoint met behulp van PowerApps](generate-app-from-sharepoint-list-interface.md) en [Een app genereren voor het beheren van gegevens in een SharePoint-lijst](app-from-sharepoint.md)
* **Microsoft Flow**: [Wachten op goedkeuring in Microsoft Flow](https://flow.microsoft.com/documentation/wait-for-approvals)
* **Power BI**: [Embed with report web part in SharePoint Online](https://powerbi.microsoft.com/documentation/powerbi-service-embed-report-spo) (Power BI: insluiten met webonderdeel Rapporteren in SharePoint Online)

Als u daarmee klaar bent, komt u hopelijk terug om het volledige scenario te bekijken.

Zelfs in dit scenario kunt u zich richten op de taken die voor u interessant zijn en ze voltooien als u tijd hebt. Als u SharePoint-lijsten in taak 1 hebt ingesteld, kunt u taak 2 t/m 5 in willekeurige volgorde doorlopen. Vervolgens voert u achtereenvolgens taak 6, 7 en 8 uit. Ten slotte hebben we voor dit scenario twee voltooide apps en een Power BI Desktop-rapport opgenomen als onderdeel van het [downloadpakket](https://aka.ms/o4ia0f). Bekijk deze en leer van de voorbeelden, ook al loopt u niet alle stappen van elke taak door.

## <a name="prerequisites"></a>Vereisten
Als u het scenario wilt voltooien, hebt u de volgende abonnementen en bureaubladprogramma's nodig. Het Office 365 Business Premium-abonnement omvat PowerApps en Microsoft Flow.

| **Abonnement of programma** | **Koppeling** |
| --- | --- |
| Office 365 Business Premium-abonnement |[Proefabonnement](https://signup.microsoft.com/Signup?OfferId=467eab54-127b-42d3-b046-3844b860bebf&dl=O365_BUSINESS_PREMIUM&ali=1) |
| PowerApps Studio |PowerApps Studio voor internet (downloaden niet nodig) of [PowerApps Studio voor Windows](https://aka.ms/powerappswin) gebruiken |
| Power BI Pro-abonnement |[Trial subscription](https://powerbi.microsoft.com/get-started/) (proefabonnement) (klik op **TRY FREE**) |
| Power BI Desktop |[Free download](https://powerbi.microsoft.com/get-started/) (gratis download) (klik op **DOWNLOAD FREE**) |

Het zou mooi zijn als u bekend bent met elke technologie, maar u kunt het scenario ook voltooien als u sommige niet kent. Gebruik de volgende inhoud om u voor te bereiden:

* [Aan de slag met SharePoint](https://support.office.com/article/Get-started-with-SharePoint-909ec2f0-05c8-4e92-8ad3-3f8b0b6cf261)
* [PowerApps: Gestuurd leren](https://powerapps.microsoft.com/guided-learning/)
* [Microsoft Flow: Gestuurd leren](https://flow.microsoft.com/guided-learning/)
* [Power BI Guided Learning](https://powerbi.microsoft.com/guided-learning/) (Power BI: Gestuurd leren)

## <a name="next-steps"></a>Volgende stappen
De volgende stap in deze reeks zelfstudies bestaat uit het [instellen van de SharePoint Online-lijsten](sharepoint-scenario-setup.md) die in de reeks worden gebruikt.

