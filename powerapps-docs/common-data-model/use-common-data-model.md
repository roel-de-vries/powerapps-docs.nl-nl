---
title: Ontwikkelen met het Common Data Model | Microsoft Docs
description: In dit artikel wordt beschreven hoe u met het Common Data Model apps en oplossingen kunt ontwikkelen.
author: RobertBruckner
ms.service: powerapps
ms.topic: article
ms.date: 07/24/2018
ms.author: robruc
ms.openlocfilehash: 6e99fbe13d9b6e3acdd0cfdd08662676a321471c
ms.sourcegitcommit: abe4d4728db7f56088f618af5b820af78e7099c9
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/28/2018
ms.locfileid: "39332073"
---
# <a name="how-to-use-the-common-data-model"></a>Instructies voor het gebruik van Common Data Model

Met het **Common Data Model (CDM)** kunt u de gegevens notaties meegeven, die staan voor algemeen gebruikte concepten en activiteiten, die veel worden gebruikt en als zodanig worden herkend. Op die manier kunt u query's uitvoeren op die gegevens, deze opnieuw gebruiken en gegevens uitwisselen met andere ondernemingen en toepassingen die ook gebruikmaken van deze notatie. Net zoals u de grootte en de vorm van een AA-batterij kent zodat u weet dat alle afstandsbedieningen deze kunnen gebruiken, definieert CDM de grootte en de vorm van (bijvoorbeeld) een *Contactpersoon*. Op die manier weten uw toepassingsontwikkelaars en zakelijke partners hoe ze die gegevens moeten interpreteren en kunnen ze met vertrouwen en gemak uw apps ontwikkelen (of gegevens uitwisselen). En omdat CDM een open source definitie is van standaardentiteiten, kunnen geïnteresseerde ontwikkelaars dit snel begrijpen en deelnemen aan schemadefinities.

Momenteel wordt CDM gebruikt in Common Data Service (CDS) for Apps die ondersteuning biedt voor Dynamics en PowerApps, en de mogelijkheden voor gegevensvoorbereiding in Power BI om geschematiseerde bestanden te maken in Azure Data Lake.

![Common Data Model met CDS for Apps](media/cdm-with-cds.png)

U kunt het CDM en CDS for Apps op de volgende manieren gebruiken:

-   **Uw gegevens veilig opslaan en beheren in de CDM-notatie**: u kunt met CDS for Apps uw gegevens veilig opslaan en beheren in de gestandaardiseerde CDM-notatie. Op die manier kunt u vervolgens toegang krijgen tot die gegevens en deze gebruiken in Microsoft-apps en -services als Dynamics, PowerApps, Flow of Power BI, of uw eigen aangepaste toepassingen.

-   **Aangepaste CDM-entiteiten maken**: het CDM kan worden uitgebreid, zodat u entiteiten kunt maken die niet in het CDM voorkomen en die specifiek zijn voor uw organisatie. U kunt deze entiteiten vervolgens vullen met uw bestaande gegevens met behulp van **Power Query**. U kunt zo gebruikmaken van het CDM en dit ook afstemmen op uw bedrijf.

-   **Uw eigen opslagplaatsen van gegevens maken**: u kunt opslagplaatsen van gegevens maken die voldoen aan het schema van het **Common Data Model (CDM)** en met die gegevensbronnen verbinding maken met behulp van Microsoft-gegevensconnectors. Op deze manier kunt u aangepaste Line-Of-Business-app-toepassingen maken die gebruikmaken van uw CDM-gegevens of deze delen, ongeacht de locatie waar de gegevens vandaan komen of zijn opgeslagen.

-   **Snel inzichten afleiden en distribueren met behulp van Power BI**: u kunt geavanceerde services voor gegevensvoorbereiding in Power BI gebruiken. U hebt hiermee toegang tot uw CDM-gegevensarchieven (zoals de gegevens die u in CDS for Apps hebt opgenomen) zodat u rapporten en dashboards kunt maken. U kunt vervolgens apps maken die rapporten genereren en die aangepaste inzichten voor personen en groepen in uw organisatie automatisch vullen met uw CDM-gegevens.

-   **Aangepaste rapporten voor de gehele organisatie genereren in Power BI**: u kunt apps gebruiken die automatisch aangepaste rapporten genereren die u in Power BI-werkruimten voor gebruikers in uw organisatie en daarbuiten kunt plaatsen.

Microsoft blijft, samen met veel partners en specialisten, het CDM uitbreiden en nieuwe bedrijfstakken, zoals de gezondheidszorg, kunnen profijt trekken van het CDM en de platformen die dit ondersteunen.

## <a name="data-integration-and-power-query-online"></a>Gegevensintegratie en Power Query Online

Beide platformen die momenteel ondersteuning bieden voor het CDM bieden ook gegevensintegratie via Power Query Online. Gebruikers kunnen hiermee gegevens ophalen uit een groot aantal bronnen, deze zo nodig transformeren en ze vervolgens toewijzen aan standaardentiteiten in het CDM of aangepaste entiteiten maken. Power Query Online maakt gebruik van dezelfde visuele weergave en selfservice voor gegevensvoorbereiding als Power Query in Excel en Power BI Desktop, zodat gebruikers snel aan de slag kunnen gaan.

![Gegevens toewijzen aan entiteiten in CDM](media/cdm-map-entities.png)

## <a name="common-data-service-for-apps"></a>Common Data Service for Apps

Met CDS for Apps kunt u snel aan de slag met apps die gebruikmaken van het CDM met ingebouwde bedrijfslogica, beveiliging en integratie. Met het platform kunt u:

-   **Gebruikmaken van bedrijfstoepassingspakketten**: veel Microsoft Dynamics-oplossingen en veel toepassingen van derden zijn gebouwd op CDS for Apps (of maken hier minstens gebruik van). Wanneer uw gegevens in het CDM zijn opgenomen, kunt u gebruikmaken van deze toepassingspakketten.

-   **Toegang krijgen tot aangepaste oplossingen**: er bestaat een ecosysteem van uitbreidingen en volledige toepassingen die zijn gemaakt door ontwikkelaars die kennis hebben van gegevens in de CDM-notatie en hiermee werken. Zie [Inleiding tot oplossingen](https://docs.microsoft.com/powerapps/developer/common-data-service/introduction-solutions) voor meer informatie.

Wat uw doeleinden ook zijn, met het CDM worden uw gegevens in een gemeenschappelijke notatie omgezet zodat u de gegevens gemakkelijker kunt gebruiken, delen en analyseren.

**Resources voor CDS for Apps**

-   [Wat is CDS for Apps?](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)

-   [Gegevens toevoegen aan een entiteit in CDS for Apps met behulp van Power Query](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-cds-newentity-pq)

-   [Inleiding tot oplossingen](https://docs.microsoft.com/powerapps/developer/common-data-service/introduction-solutions)

-   [Build a model-driven app](https://docs.microsoft.com/powerapps/maker/model-driven-apps/model-driven-app-overview) (Een modelgestuurde app bouwen)

-   [Build a canvas app](https://docs.microsoft.com/powerapps/maker/canvas-apps/getting-started) (Een canvas-app bouwen)

-   [Een stroom maken die gebruikmaakt van CDS voor Apps](https://docs.microsoft.com/flow/common-data-model-intro)

