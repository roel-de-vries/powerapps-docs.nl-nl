---
title: Overzicht van Common Data Model | Microsoft Docs
description: Informatie over hoe Common Data Service for Apps met Common Data Service for Analytics is verbonden via Common Data Model.
author: RobertBruckner
ms.service: powerapps
ms.topic: article
ms.date: 03/14/2018
ms.author: jdaly
ms.openlocfilehash: 4e9b929558de0b2451bb2df4add4b300d7115848
ms.sourcegitcommit: 7354a0c61578fcc0b9965bf557b9d7c553c73e96
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2018
ms.locfileid: "34803232"
---
# <a name="common-data-model-overview"></a>Overzicht van Common Data Model

**Common Data Model** (CDM) is een open-sourcedefinitie van standaardentiteiten waarmee veelgebruikte concepten en activiteiten voor verschillende zakelijke en toepassingsdomeinen worden aangeduid. Common Data Model biedt *goed gedefinieerde, modulaire en uitbreidbare* zakelijke entiteiten (zoals Account, Bedrijfsonderdeel, Case, Contact, Potentiële klant, Verkoopkans en Product) en interacties en relaties tussen leveranciers, medewerkers en klanten (zoals activiteiten en serviceovereenkomsten). 

Op basis van [Common Data Service for Apps](../maker/common-data-service/data-platform-intro.md) en Common Data Service for Analytics<!-- TODO add link when available  --> van Microsoft wordt Common Data Model geïmplementeerd. Deze services bevatten gegevens die voldoen aan de definitie van Common Data Model. Omdat deze services de basis vormen voor standaardtoepassingen en analytische oplossingen, kunt u hierin gebruikmaken van goed gedefinieerde entiteitsvormen en kunnen gegevens worden gedeeld, ongeacht de locatie waarvan de gegevens afkomstig zijn of worden beheerd. Aangepaste Line-Of-Business-apps en analytische oplossingen kunnen gebruikmaken van dezelfde entiteiten voor het delen van gegevens, waardoor tegemoet kan worden gekomen aan uw specifieke behoeften en zakelijke vereisten. 

Microsoft en de partners van Microsoft streven ernaar toepassingen te baseren op Common Data Service en zakelijke gegevens in CDM-indeling op te slaan. Er zijn steeds *meer oplossingen die efficiënt samenwerken wanneer gegevens worden opgeslagen in de CDM-indeling*, wat betekent dat u snel en eenvoudig nieuwe bedrijfsprocessen kunt implementeren en inzicht kunt krijgen in uw zakelijke activiteiten. In het volgende diagram ziet u toepassingen die zijn gebaseerd op Common Data Services en waarin gebruik wordt gemaakt van Common Data Model-entiteiten.

![Toepassingen die zijn gebaseerd op Common Data Services en waarin gebruik wordt gemaakt van Common Data Model-entiteiten](media/cdm-overview.png)

Met Common Data Model wordt gegevensbeheer vereenvoudigd doordat gegevens worden samengevoegd in een bekende indeling met *structurele en semantische consistentie in alle toepassingen en implementaties*. Gegevens die zijn verzameld uit onder meer bedrijfsprocessen, digitale interacties, producttelemetrie en interactie tussen personen, kunt u met CDM *ondubbelzinnig* maken en integreren. 

Gegevens die zijn opgeslagen in Common Data Service for Apps kunnen *eenvoudig en automatisch worden geïntegreerd* met Common Data Service for Analytics (als klanten beide services gebruiken). Als basis kunt u de zakelijke en transactiegegevens gebruiken die u al in uw bezit hebt (zoals potentiële klanten, campagnegegevens, eerdere aankopen van klanten) en deze combineren met gegevens uit andere bronnen (zoals weblogs of producttelemetrie).

Common Data Model is ook *uitbreidbaar*. Dit betekent dat u velden kunt toevoegen aan de aanpasbare entiteiten die worden meegeleverd met CDM. Daarnaast hebt u de mogelijkheid uw eigen aangepaste entiteiten te maken. Op basis van de CDM-standaard wordt een standaardtaal gedefinieerd voor bedrijfsentiteiten die betrekking heeft op alle bedrijfsprocessen op het gebied van verkoop, services, marketing, bedrijfsactiviteiten, financiën, talent en handel, en van toepassing is op de klanten, personen en productentiteiten die de kern van de bedrijfsprocessen van een organisatie vormen. Common Data Model vereenvoudigt gegevensinteroperabiliteit doordat meerdere kanalen, service-implementaties en leveranciers worden bereikt.

Common Data Model en Common Data Service bieden een uitgebreid en productief ontwikkelplatform via de volgende functies:

- **Definitie van standaardentiteiten**: Common Data Model biedt een definitie van entiteiten die de meest gebruikte entiteiten in zakelijke en productiviteitstoepassingen vertegenwoordigen. De openbare GitHub-opslagplaats voor CDM [ (https://github.com/Microsoft/CDM)](https://github.com/Microsoft/CDM) wordt continu uitgebreid met kernentiteiten die ondersteuning bieden voor alle bedrijfsprocessen in de organisatie, aanvullende verticale gegevensmodellen voor de branche en bronnen die in verschillende gebieden kunnen worden gebruikt, zoals enquêtes, zoekmachines en producttelemetrie.
- **Gegevensintegratie**: u kunt Power Query als geïntegreerde webervaring gebruiken om gegevens uit uw bestaande systemen te importeren en visueel te transformeren, en gegevens samen te voegen uit online- en on-premises bronnen zonder code of code van laag niveau. Uw Excel- en Power BI-vaardigheden voor het transformeren van gegevens sluiten hier naadloos op aan. Zie het Engelstalige artikel [Add data to an entity in the Common Data Service by using Power Query](../maker/common-data-service/data-platform-cds-newentity-pq.md) (Gegevens aan een entiteit in Common Data Service toevoegen met Power Query) voor meer informatie.
    
    Wanneer u gegevens in Common Data Service importeert, kunt u deze toewijzen aan standaardentiteiten in Common Data Model. U kunt ook gegevens maken en deze toewijzen aan nieuwe entiteiten. Dankzij gebruiksklare sjablonen voor gegevensintegratie en -toewijzing kunt u eenvoudig verbinding maken met algemene gegevensbronnen zoals Salesforce. Deze toewijzingssjablonen kunt u volledig aanpassen en uitbreiden. In de volgende schermafbeelding ziet u het proces voor het importeren van externe gegevens en het toewijzen van deze gegevens aan standaardentiteiten in Power Query. 
    
    ![Externe gegevens importeren en deze toewijzen aan standaardentiteiten in Power Query ](media/cdm-mapping-entities.png)<br />

- **Uitbreidbaarheid**: u kunt de entiteiten uitbreiden, zonder dat hierbij de mogelijkheid tot het delen van gegevens met andere apps verloren gaat.
- **Betrouwbaarheid**: omdat u kunt vertrouwen op algemene entiteiten, kunt u herbruikbare onderdelen maken die aan de entiteiten zijn gebonden. Common Data Model biedt ondersteuning voor uitbreidbaarheid en versiebeheer voor onderdelen waardoor de waarde van uw ontwikkelinvestering behouden blijft.
- **Consistentie van entiteiten binnen implementaties**: in uw oplossingen kan verbinding worden gemaakt tussen gegevens uit productiviteitsplatformen en gegevens uit zakelijke toepassingen. U kunt bijvoorbeeld een agenda-afspraak of een taak in Microsoft Outlook verbinden met een verkoopkans. 

Op basis van [Common Data Service for Apps](../maker/common-data-service/data-platform-intro.md) wordt Common Data Model geïmplementeerd, waardoor het volgende mogelijk wordt als het gaat om de ontwikkeling van zakelijke toepassingen:

- **Gebruikmaken van een pakket met zakelijke toepassingen**: de toepassingen Dynamics 365 for Marketing, Sales, Service, Talent, Finance and Operations, en toepassingen van derden gebruiken en/of zijn gebaseerd op Common Data Service for Apps.
- **Toepassingen aanpassen en systeemeigen uitbreidingen bouwen**: aanpassers en ontwikkelaars distribueren oplossingen voor toepassingen met een goed gedefinieerde levenscyclus van toepassingen. Oplossingen hebben betrekking op de manier waarop toepassingen en uitbreidingen worden gedistribueerd. Zie [Inleiding tot oplossingen](../developer/common-data-service/introduction-solutions.md) voor meer informatie.
- **Apps zonder code of met code van laag niveau, modelgestuurde apps en WYSIWYG-canvas-apps bouwen met PowerApps**: u kunt gebruikmaken van dezelfde gedeelde entiteiten als de entiteiten die met de pakkettoepassingen of toepassingen van derden zijn gemaakt of worden gebruikt, en u kunt aanvullende zelfstandige apps maken. Zie voor meer informatie: 
    - [Build a model-driven app](../maker/model-driven-apps/model-driven-app-overview.md) (Een modelgestuurde app bouwen)
    - [Build a canvas app](../maker/canvas-apps/getting-started.md) (Een canvas-app bouwen) 
- **Bedrijfsprocessen automatiseren met Flow**: u kunt een bedrijfsprocesstroom gebruiken om een aantal fasen en stappen te definiëren om het gewenste resultaat te bereiken. Zie [Een stroom maken die gebruikmaakt van de Common Data Service](/flow/common-data-model-intro) voor meer informatie.
 
Met de geplande openbare preview van **Common Data Service for Analytics** <!-- TODO add link when available  --> wordt ook Common Data Model geïmplementeerd, waarmee in een gestandaardiseerde vorm ondersteuning kan worden geboden voor gegevensanalyses van zakelijke gegevens:

- **Analytische pakketoplossingen en aangepaste analytische oplossingen zijn gebaseerd op standaardgegevensentiteiten**: analytische toepassingen zoals Sales Insights, waarmee historische verkoopprestaties worden bijgehouden, bieden consistente inzichten, ongeacht de plek waar de gegevens oorspronkelijk worden beheerd. Dit komt doordat gegevens uit andere bronnen (zoals Salesforce.com) dankzij de gegevensintegratie-ervaring zijn toegewezen aan Common Data Model-entiteitsvormen. Hiermee kan de nadruk in uw analytische oplossingen eenvoudiger worden gelegd op de semantiek van gegevens van goed gedefinieerde entiteiten zoals Potentiële klanten en Verkoopkansen.
- **Power Query-gegevensintegratie zonder code of met code van laag niveau**: u kunt de geïntegreerde ervaring gebruiken om entiteiten te maken, in te vullen, te transformeren en te verrijken. 
- **Gebruikmaken van uw eigen Azure-opslag**: u kunt profiteren van de Azure-gegevensstack om gegevens beschikbaar te maken voor Common Data Service for Analytics. De entiteiten worden opgeslagen in dezelfde Common Data Model-indeling, die door de analytische oplossingen wordt herkend.

