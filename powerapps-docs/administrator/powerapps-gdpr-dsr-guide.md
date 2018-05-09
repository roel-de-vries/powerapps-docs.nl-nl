---
title: PowerApps DSR-handleiding voor door de klant opgestelde gegevens | Microsoft Docs
description: PowerApps DSR-handleiding voor door de klant opgestelde gegevens
services: powerapps
suite: powerapps
documentationcenter: na
author: jamesol-msft
manager: kfile
editor: ''
tags: ''
ms-topic: article
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/17/2018
ms.author: jamesol
ms.openlocfilehash: 823c14d0677ef96c48a26e2488bac1c91bbea225
ms.sourcegitcommit: e3a2819c14ad67cc4ca6640b9064550d0f553d8f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/20/2018
---
# <a name="responding-to-data-subject-rights-dsr-requests-for-powerapps-customer-data"></a>Reageren op DSR-aanvragen (Data Subject Rights, rechten van de betrokkenen) voor PowerApps-klantgegevens

## <a name="introduction-to-dsr-requests"></a>Inleiding tot DSR-aanvragen
Als bijdrage aan onze inzet om u als partner te helpen bij de implementatie van de AVG (algemene verordening gegevensbescherming) hebben we deze documentatie ontwikkeld om u voor te bereiden. In de documentatie wordt niet alleen beschreven wat we doen ter voorbereiding op de AVG maar worden ook voorbeelden gegeven van stappen die u vandaag nog kunt uitvoeren met Microsoft om AVG-naleving te ondersteunen bij gebruik van PowerApps, Microsoft Flow en Common Data Service for Apps.

De Europese AVG (Algemene verordening gegevensbescherming) verleent rechten aan personen (in de verordening 'betrokkenen' genoemd) om de persoonsgegevens te beheren die zijn verzameld door een werkgever of een andere instantie of organisatie ('gegevensverwerker' of 'verwerker'). Volgens de AVG zijn persoonsgegevens een breed begrip. Hieronder vallen alle gegevens die verband houden met een geïdentificeerde of identificeerbare natuurlijke persoon. De AVG verleent betrokkenen specifieke rechten voor hun persoonsgegevens. Deze rechten omvatten het verkrijgen van kopieën van hun persoonsgegevens, aanvragen voor correcties in de gegevens, beperken van de verwerking van de gegevens, verwijdering van de gegevens of een elektronisch exemplaar van de gegevens, zodat deze naar een andere verwerker kunnen worden verplaatst. Een formele aanvraag van een betrokkene aan een verwerker om actie te ondernemen met betrekking tot zijn of haar persoonsgegevens wordt een DSR-aanvraag (Data Subject Rights, rechten van de betrokkene) genoemd.

In de handleiding wordt beschreven hoe producten, services en beheerprogramma's van Microsoft kunnen worden gebruikt om onze klanten te helpen bij het vinden van persoonsgegevens en om te reageren op DSR-aanvragen. Dit betreft in het bijzonder het vinden, bekijken en reageren op persoonsgegevens in de Microsoft-cloud. Hier volgt een beknopt overzicht van de processen die in deze handleiding worden beschreven:

1. **Detecteren**: zoek- en detectieprogramma's gebruiken om sneller klantgegevens met betrekking tot een DSR-aanvraag te vinden. Zodra mogelijk responsieve documenten zijn verzameld, kunt u op de aanvraag reageren door een of meer DSR-acties uit te voeren die worden beschreven in de volgende stappen. U kunt ook besluiten dat de aanvraag niet voldoet aan de richtlijnen van uw organisatie voor reacties op DSR-aanvragen.

1. **Toegang verkrijgen**: persoonsgegevens ophalen die zich in de Microsoft-cloud bevinden en, indien aangevraagd, voor de betrokkene een kopie van deze gegevens maken.

1. **Herstellen**: wijzigingen aanbrengen of andere aangevraagde acties voor de persoonsgegevens uitvoeren, indien van toepassing.

1. **Beperken**: de verwerking van persoonsgegevens beperken door, waar mogelijk, licenties voor verschillende onlineservices te verwijderen of de gewenste services uit te schakelen. U kunt ook gegevens uit de Microsoft-cloud verwijderen en deze on-premises of op een andere locatie bewaren.

5. **Verwijderen**: permanent verwijderen van persoonsgegevens die zich bevinden in de cloud van Microsoft.

6. **Exporteren**: een elektronisch exemplaar (in een machineleesbare indeling) van persoonsgegevens leveren aan de betrokkene.

In elke sectie van deze handleiding worden de technische procedures beschreven die een organisatie voor gegevensverwerking kan uitvoeren om te reageren op een DSR-aanvraag voor persoonsgegevens in de Microsoft-cloud.

## <a name="discover"></a>Ontdekken
De eerste stap bij het reageren op een DSR-aanvraag is het zoeken van de persoonsgegevens waarvoor de aanvraag wordt gedaan. Deze eerste stap (de betreffende persoonsgegevens zoeken en beoordelen) helpt u te bepalen of een DSR-aanvraag voldoet aan de vereisten van uw organisatie voor het accepteren of weigeren van een DSR-aanvraag. Bijvoorbeeld: nadat u de betreffende persoonsgegevens hebt gevonden en beoordeeld, kunt u bepalen dat de aanvraag niet voldoet aan de vereisten van uw organisatie omdat deze negatieve gevolgen kan hebben voor de rechten en vrijheden van anderen.

### <a name="step-1-find-personal-data-for-the-user-in-powerapps"></a>Stap 1: Persoonsgegevens voor de gebruiker zoeken in PowerApps
Hieronder volgt een overzicht van de typen PowerApps-resources die persoonsgegevens voor een specifieke gebruiker bevatten.

Resources met persoonsgegevens |    Doel
--- | ---
Omgeving |   Een omgeving is een ruimte om de bedrijfsgegevens, -apps en -stromen van uw organisatie op te slaan, te beheren en te delen. [Meer informatie](https://go.microsoft.com/fwlink/?linkid=872239)
Omgevingsmachtigingen | Gebruikers worden toegewezen aan omgevingsrollen om bevoegdheden voor makers en beheerders in een omgeving te krijgen. [Meer informatie](https://go.microsoft.com/fwlink/?linkid=872240)
Canvas-app  | Zakelijke apps voor verschillende platformen die met een leeg canvas kunnen worden gebouwd en met meer dan 200 gegevensbronnen kunnen worden verbonden. [Meer informatie](https://go.microsoft.com/fwlink/?linkid=872241)
Machtigingen voor canvas-apps  | Canvas-apps kunnen worden gedeeld met gebruikers binnen een organisatie. [Meer informatie](https://go.microsoft.com/fwlink/?linkid=872242)
Verbinding  | Worden gebruikt door connectoren en maken connectiviteit met API's, systemen, databases enzovoort mogelijk [Meer informatie](https://go.microsoft.com/fwlink/?linkid=872243)
Verbindingsmachtigingen  | Bepaalde typen verbindingen kunnen worden gedeeld met gebruikers binnen een organisatie. [Meer informatie](https://go.microsoft.com/fwlink/?linkid=872244)
Aangepaste connector    | Aangepaste connectoren die een gebruiker heeft gemaakt voor toegang tot een gegevensbron waarin niet wordt voorzien door een van de standaard-PowerApps-connectoren. [Meer informatie](https://go.microsoft.com/fwlink/?linkid=872245)
Machtigingen voor aangepaste connectoren    | Aangepaste connectoren kunnen worden gedeeld met gebruikers binnen een organisatie. [Meer informatie](https://go.microsoft.com/fwlink/?linkid=872246)
PowerApps-gebruiker en instellingen van gebruikers-apps    | In PowerApps worden verschillende gebruikersvoorkeuren en instellingen opgeslagen die worden gebruikt voor het leveren van de PowerApps-runtime en portalervaringen.
PowerApps-meldingen | PowerApps verzendt verschillende typen meldingen naar gebruikers, zoals wanneer een app met hen wordt gedeeld en wanneer een Common Data Service for Apps-exportbewerking is voltooid.
Gateway | Gateways zijn on-premises gegevensgateways die kunnen worden geïnstalleerd door een gebruiker om gegevens snel en veilig over te brengen tussen PowerApps en een gegevensbron die zich niet in de cloud bevindt. [Meer informatie](https://go.microsoft.com/fwlink/?linkid=872247)
Gatewaymachtigingen | Gateways kunnen worden gedeeld met gebruikers binnen een organisatie. [Meer informatie](https://go.microsoft.com/fwlink/?linkid=872249)
Modelgestuurde apps en modelgestuurde app-machtigingen  | Het ontwerp van modelgestuurde apps is een componentgerichte methode voor het ontwikkelen van apps. Modelgestuurde apps en hun machtigingen voor gebruikerstoegang worden opgeslagen als gegevens in de Common Data Service for App-database.  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=872248)

PowerApps biedt de volgende ervaringen om persoonsgegevens voor een specifieke gebruiker te zoeken:

- **Websitetoegang**: [PowerApps-site](https://web.powerapps.com), [PowerApps-beheercentrum](https://admin.powerapps.com/) en [Office 365 Service Trust Portal](https://servicetrust.microsoft.com/)
- **PowerShell-toegang**: PowerApps-cmdlets (voor [app-ontwerpers](https://go.microsoft.com/fwlink/?linkid=871448) en [beheerders](https://go.microsoft.com/fwlink/?linkid=871804)) en [cmdlets voor on-premises gateways](https://go.microsoft.com/fwlink/?linkid=872238)

Zie [Export Customer Data in PowerApps]( https://go.microsoft.com/fwlink/?linkid=871888) (Klantgegevens in PowerApps exporteren) voor gedetailleerde stappen over het gebruik van deze ervaringen om persoonsgegevens voor een specifieke gebruiker te zoeken voor elk van deze typen resources.

Nadat u de gegevens hebt gevonden, kunt u de specifieke actie uitvoeren om te voldoen aan de aanvraag van de betrokkene.

### <a name="step-2-find-personal-data-for-the-user-in-microsoft-flow"></a>Stap 2: Persoonsgegevens voor de gebruiker zoeken in Microsoft Flow
PowerApps-licenties omvatten altijd Microsoft Flow-mogelijkheden. Behalve dat Microsoft Flow is opgenomen in PowerApps-licenties, is Microsoft Flow ook beschikbaar als een zelfstandige service.
Zie Executing DSRs against Microsoft Flow Customer Data (DSR-aanvragen uitvoeren voor gegevens van Microsoft Flow-klanten) voor instructies over het detecteren van persoonsgegevens die door de Microsoft Flow-service zijn opgeslagen.

> [!IMPORTANT]
> Het is raadzaam deze stap door beheerders te laten uitvoeren voor PowerApps-gebruikers

### <a name="step-3-find-personal-data-for-the-user-in-instances-of-common-data-service-cds-for-apps"></a>Stap 3: Persoonsgegevens voor de gebruiker zoeken in instanties van Common Data Service (CDS) for Apps
Bepaalde PowerApps-licenties, waaronder het PowerApps Community-abonnement, bieden gebruikers binnen uw organisatie de mogelijkheid instanties van CDS for Apps te maken en apps te bouwen op CDS for Apps. Het PowerApps Community-abonnement is een gratis licentie waarmee gebruikers CDS for Apps kunnen proberen in een individuele omgeving. Zie de pagina met [prijzen voor PowerApps](https://powerapps.microsoft.com/pricing/) voor informatie over welke mogelijkheden elke PowerApps-licentie bevat.

Zie Executing DSRs against Common Data Service Customer Data (DSR-aanvragen uitvoeren voor gegevens van Common Data Service-klanten) voor instructies over het detecteren van persoonsgegevens die door CDS for Apps zijn opgeslagen.

> [!IMPORTANT]
> Het is raadzaam deze stap door beheerders te laten uitvoeren voor PowerApps-gebruikers

## <a name="rectify"></a>Corrigeren
Als een betrokkene u heeft gevraagd de persoonsgegevens te corrigeren die zich in de gegevens van uw organisatie bevinden, moeten u en uw organisatie bepalen of de aanvraag moet worden ingewilligd. Het corrigeren van de gegevens kan acties omvatten zoals persoonsgegevens bewerken, redigeren of verwijderen uit een document of een ander type item.

PowerApps heeft afhankelijkheden voor Azure Active Directory om de identiteit te bepalen. Identiteiten bevatten persoonsgegevens en kunnen als zodanig worden bewerkt in Azure Active Directory. Zakelijke klanten kunnen DSR-correctieaanvragen beheren, inclusief het beperkt bewerken van functies volgens de aard van een bepaalde Microsoft-service.  Als gegevensverwerker kan Microsoft door het systeem gegenereerde logboeken niet corrigeren, omdat deze feitelijke activiteiten weerspiegelen en een historisch overzicht vormen van gebeurtenissen in Microsoft-services. Zie de AVG-documentatie over aanvragen van de betrokkenen voor Azure-gegevens in [Office 365 Service Trust Portal](https://servicetrust.microsoft.com/ViewPage/GDPRDSR) voor meer informatie.

## <a name="restrict"></a>Beperken
Betrokkenen kunnen u vragen de verwerking van hun persoonsgegevens te beperken.  We bieden zowel bestaande API's (application programming interfaces) als gebruikersinterfaces.  Deze ervaringen bieden de tenantbeheerder van de zakelijke klant de mogelijkheid dergelijke DSR-aanvragen te beheren via een combinatie van het exporteren van gegevens en het verwijderen van gegevens. Een klant kan een aanvraag voor het volgende doen:

- Een elektronisch exemplaar van de persoonsgegevens van de gebruiker exporteren, met inbegrip van:

    - account(s)
    - door het systeem gegenereerde logboeken
    - bijbehorende logboeken
- Het account en de bijbehorende gegevens verwijderen die zich in de Microsoft-systemen bevinden.

## <a name="export"></a>Exporteren
Op basis van het 'recht op overdraagbaarheid van gegevens' heeft een betrokkene het recht een kopie van zijn of haar persoonsgegevens in elektronische vorm (dat wil zeggen een 'gestructureerde, gangbare en machineleesbare vorm') op te vragen die kan worden overgedragen aan een andere gegevensverwerker.

Zie [Executing Export Data Subject Rights (DSR) Requests against PowerApps Customer Data](https://go.microsoft.com/fwlink/?linkid=871888) (DSR-aanvragen (Data Subject Rights) voor exporteren uitvoeren voor PowerApps-klantgegevens).

## <a name="delete"></a>Verwijderen
Het 'recht op wissing' door het verwijderen van persoonsgegevens uit de klantgegevens van een organisatie is een belangrijke beschermingsmaatregel in de AVG. Het verwijderen van persoonsgegevens omvat het verwijderen van door het systeem gegenereerde logboeken, maar niet gegevens uit auditlogboeken.

Met PowerApps kunnen gebruikers Line-Of-Business-toepassingen ontwikkelen die een belangrijk onderdeel vormen van de dagelijkse bedrijfsvoering van uw organisatie. Wanneer een gebruiker uw organisatie verlaat, moet u handmatig controleren en bepalen of bepaalde gegevens en resources die de gebruiker heeft gemaakt, moeten worden verwijderd. Andere klantgegevens worden automatisch verwijderd wanneer het account van de gebruiker uit Azure Active Directory wordt verwijderd.

Zie [Executing Delete Data Subject Rights (DSR) Requests against PowerApps Customer Data](https://go.microsoft.com/fwlink/?linkid=871883) (DSR-aanvragen (Data Subject Rights) voor verwijderen uitvoeren voor PowerApps-klantgegevens) voor meer informatie.
