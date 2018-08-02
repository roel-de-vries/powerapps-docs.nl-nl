---
title: Reageren op aanvragen van betrokkenen voor PowerApps-gegevens van de klant | Microsoft Docs
description: Overzicht van hoe te reageren op aanvragen van betrokkenen voor het verwijderen van PowerApps-gegevens van de klant
author: jamesol-msft
manager: kvivek
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 05/23/2018
ms.author: jamesol
ms.openlocfilehash: ae73d5df51b2656fc4f33e7258078140a180926d
ms.sourcegitcommit: 2e7b621066cdc3e7be329d5213ecfee0b4223641
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2018
ms.locfileid: "39349197"
---
# <a name="responding-to-data-subject-rights-dsr-requests-for-powerapps-customer-data"></a>Reageren op aanvragen van betrokkenen voor PowerApps-klantgegevens

## <a name="introduction-to-dsr-requests"></a>Inleiding tot DSR-aanvragen
De AVG (algemene verordening gegevensbescherming) van de EU (Europese Unie) verleent rechten aan personen (in de verordening *betrokkenen* genoemd) om de persoonsgegevens te beheren die zijn verzameld door een werkgever of een andere instantie of organisatie (*gegevensverwerker* of *verwerker*). Volgens de AVG zijn persoonsgegevens een breed begrip. Hieronder vallen alle gegevens die verband houden met een geïdentificeerde of identificeerbare natuurlijke persoon. De AVG biedt betrokkenen het recht om het volgende te doen, wanneer dit betrekking heeft op hun persoonsgegevens:

* Kopieën opvragen
* Correcties aanvragen
* Verwerking beperken
* Gegevens verwijderen
* Gegevens in digitale vorm ontvangen, zodat ze aan een andere verwerker kunnen worden overgedragen

Een formele aanvraag van een betrokkene aan een verwerker om actie te ondernemen met betrekking tot zijn of haar persoonsgegevens wordt een aanvraag van de betrokkene genoemd.

In dit artikel wordt beschreven hoe Microsoft zich voorbereidt op de AVG, en het bevat ook voorbeelden van stappen die u kunt uitvoeren om AVG-naleving te ondersteunen bij gebruik van PowerApps, Microsoft Flow en Common Data Service (CDS) for Apps. U leert hoe u producten, services en beheerprogramma's van Microsoft kunt gebruiken om onze klanten te helpen bij het vinden van persoonsgegevens in de Microsoft-cloud als reactie op aanvragen van betrokkenen.

In dit artikel komen de volgende acties aan bod:

* **Detecteren**: zoek- en detectieprogramma's gebruiken om sneller klantgegevens met betrekking tot een DSR-aanvraag te vinden. Zodra mogelijk responsieve documenten zijn verzameld, kunt u een of meer van de volgende acties uitvoeren om op de aanvraag te reageren. U kunt ook besluiten dat de aanvraag niet voldoet aan de richtlijnen van uw organisatie voor reacties op DSR-aanvragen.

* **Toegang verkrijgen**: persoonsgegevens ophalen die zich in de Microsoft-cloud bevinden en, indien aangevraagd, voor de betrokkene een kopie maken van deze gegevens.

* **Herstellen**: wijzigingen aanbrengen of andere aangevraagde acties voor de persoonsgegevens uitvoeren, indien van toepassing.

* **Beperken**: de verwerking van persoonsgegevens beperken door, waar mogelijk, licenties voor verschillende onlineservices te verwijderen of de gewenste services uit te schakelen. U kunt ook gegevens uit de Microsoft-cloud verwijderen en deze on-premises of op een andere locatie bewaren.

* **Verwijderen**: permanent verwijderen van persoonsgegevens die zich bevinden in de Microsoft-cloud.

* **Exporteren**: een elektronisch exemplaar (in een machineleesbare indeling) van persoonsgegevens leveren aan de betrokkene.

## <a name="discover"></a>Ontdekken
De eerste stap bij een reactie op een aanvraag van een betrokkene is het zoeken van de persoonsgegevens waarvoor de aanvraag wordt gedaan. Door deze eerste stap, &mdash;de betreffende persoonsgegevens zoeken en beoordelen&mdash;, kunt u beter bepalen of een aanvraag van een betrokkene voldoet aan de vereisten van uw organisatie voor het accepteren of weigeren van de aanvraag. Bijvoorbeeld: nadat u de betreffende persoonsgegevens hebt gevonden en beoordeeld, kunt u bepalen dat de aanvraag niet voldoet aan de vereisten van uw organisatie omdat deze negatieve gevolgen kan hebben voor de rechten en vrijheden van anderen.

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
Machtigingen voor aangepaste connector    | Aangepaste connectoren kunnen worden gedeeld met gebruikers binnen een organisatie. [Meer informatie](https://go.microsoft.com/fwlink/?linkid=872246)
PowerApps-gebruiker en instellingen van gebruikers-apps    | In PowerApps worden verschillende gebruikersvoorkeuren en instellingen opgeslagen die worden gebruikt voor het leveren van de PowerApps-runtime en portalervaringen.
PowerApps-meldingen | PowerApps verzendt verschillende typen meldingen aan gebruikers, zoals wanneer een app met hen wordt gedeeld en wanneer een CDS voor apps-exportbewerking is voltooid.
Gateway | Gateways zijn on-premises gegevensgateways die kunnen worden geïnstalleerd door een gebruiker om gegevens snel en veilig over te brengen tussen PowerApps en een gegevensbron die zich niet in de cloud bevindt. [Meer informatie](https://go.microsoft.com/fwlink/?linkid=872247)
Gatewaymachtigingen | Gateways kunnen worden gedeeld met gebruikers binnen een organisatie. [Meer informatie](https://go.microsoft.com/fwlink/?linkid=872249)
Modelgestuurde apps en modelgestuurde app-machtigingen  | Het ontwerp van modelgestuurde apps is een componentgerichte methode voor het ontwikkelen van apps. Modelgestuurde apps en hun machtigingen voor gebruikerstoegang worden opgeslagen als gegevens in de CDS voor apps-database.  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=872248)

PowerApps biedt de volgende ervaringen om persoonsgegevens voor een specifieke gebruiker te zoeken:

- **Website-toegang**: [PowerApps-site](https://web.powerapps.com), [PowerApps-beheercentrum](https://admin.powerapps.com/) en [Office 365 Trust Portal](https://servicetrust.microsoft.com/)
- **PowerShell-toegang**: PowerApps-cmdlets (voor [app-ontwerpers](https://go.microsoft.com/fwlink/?linkid=871448) en [beheerders](https://go.microsoft.com/fwlink/?linkid=871804)) en [cmdlets voor on-premises gateways](https://go.microsoft.com/fwlink/?linkid=872238)

Zie [Reageren op aanvragen van betrokkenen om PowerApps-klantgegevens te exporteren](powerapps-gdpr-export-dsr.md) voor gedetailleerde stappen over het gebruik van deze ervaringen om persoonsgegevens voor een specifieke gebruiker te zoeken voor elk van deze typen resources.

Nadat u de gegevens hebt gevonden, kunt u de specifieke actie uitvoeren om te voldoen aan de aanvraag van de betrokkene.

### <a name="step-2-find-personal-data-for-the-user-in-microsoft-flow"></a>Stap 2: Persoonsgegevens voor de gebruiker zoeken in Microsoft Flow
PowerApps-licenties omvatten altijd Microsoft Flow-mogelijkheden. Behalve dat Microsoft Flow is opgenomen in PowerApps-licenties, is Microsoft Flow ook beschikbaar als een zelfstandige service.

Zie [Reageren op inzageverzoeken van betrokkenen in het kader van de AVG met Microsoft Flow](https://go.microsoft.com/fwlink/?linkid=872250) voor instructies over het reageren op AVG-aanvragen van gebruikers die de Microsoft Flow-service gebruiken.

> [!IMPORTANT]
> Het is raadzaam deze stap door beheerders te laten uitvoeren voor PowerApps-gebruikers

### <a name="step-3-find-personal-data-for-the-user-in-instances-of-cds-for-apps"></a>Stap 3: Persoonsgegevens voor de gebruiker zoeken in instanties van CDS voor apps
Bepaalde PowerApps-licenties, waaronder het PowerApps Community-abonnement, bieden gebruikers binnen uw organisatie de mogelijkheid instanties van CDS for Apps te maken en apps te bouwen op CDS for Apps. Het PowerApps Community-abonnement is een gratis licentie waarmee gebruikers CDS for Apps kunnen proberen in een individuele omgeving. Zie de pagina met [prijzen voor PowerApps](https://powerapps.microsoft.com/pricing/) voor informatie over welke mogelijkheden elke PowerApps-licentie bevat.

Zie [Reageren op aanvragen van betrokkenen voor klantgegevens in Common Data Service for Apps](common-data-service-gdpr-dsr-guide.md) voor instructies over hoe u persoonsgegevens detecteert die zijn opgeslagen door CDS for Apps.

> [!IMPORTANT]
> Het is raadzaam deze stap door beheerders te laten uitvoeren voor PowerApps-gebruikers.

## <a name="rectify"></a>Corrigeren
Als een betrokkene u vraagt de persoonsgegevens te corrigeren die zich in de gegevens van uw organisatie bevinden, moeten u en uw organisatie bepalen of de aanvraag moet worden ingewilligd. Het corrigeren van gegevens kan het bewerken of redigeren van persoonsgegevens omvatten of het verwijderen van persoonsgegevens uit een document of een ander type item.

U kunt Azure Active Directory gebruiken om de identiteiten (persoonsgegevens) van uw gebruikers in PowerApps te beheren. Zakelijke klanten kunnen correctieaanvragen van betrokkenen beheren met de beperkte bewerkingsfuncties binnen een bepaalde Microsoft-service. Als gegevensverwerker kan Microsoft door het systeem gegenereerde logboeken niet corrigeren, omdat deze feitelijke activiteiten weerspiegelen en een historisch overzicht vormen van gebeurtenissen in Microsoft-services. Zie [AVG: aanvragen van betrokkenen](https://servicetrust.microsoft.com/ViewPage/GDPRDSR) voor meer informatie.

## <a name="restrict"></a>Beperken
Betrokkenen kunnen u vragen de verwerking van hun persoonsgegevens te beperken.  We bieden zowel bestaande API's (application programming interfaces) als gebruikersinterfaces.  Deze ervaringen bieden de tenantbeheerder van de zakelijke klant de mogelijkheid dergelijke DSR-aanvragen te beheren via een combinatie van het exporteren van gegevens en het verwijderen van gegevens. Een klant kan een aanvraag voor het volgende doen:

* Een elektronisch exemplaar van de persoonsgegevens van de gebruiker exporteren, met inbegrip van:

    - account(s)
    - door het systeem gegenereerde logboeken
    - bijbehorende logboeken

* Het account en de bijbehorende gegevens verwijderen die zich in de Microsoft-systemen bevinden.

## <a name="export"></a>Exporteren
Op basis van het 'recht op overdraagbaarheid van gegevens' heeft een betrokkene het recht een kopie van zijn of haar persoonsgegevens in digitale vorm (dat wil zeggen een gestructureerde, gangbare en door een machine leesbare vorm) op te vragen, die kan worden overgedragen aan een andere verwerkingsverantwoordelijke.

Zie [Reageren op AVG-aanvragen voor het exporteren van PowerApps-gegevens van de klant](powerapps-gdpr-export-dsr.md) voor meer informatie.

## <a name="delete"></a>Verwijderen
Het 'recht op wissing' door het verwijderen van persoonsgegevens uit de klantgegevens van een organisatie is een belangrijke beschermingsmaatregel in de AVG. Het verwijderen van persoonsgegevens omvat het verwijderen van door het systeem gegenereerde logboeken, maar niet gegevens uit auditlogboeken.

Met PowerApps kunnen gebruikers Line-Of-Business-toepassingen ontwikkelen die een belangrijk onderdeel vormen van de dagelijkse bedrijfsvoering van uw organisatie. Wanneer een gebruiker uw organisatie verlaat, moet u handmatig controleren en bepalen of bepaalde gegevens en resources die de gebruiker heeft gemaakt, moeten worden verwijderd. Andere klantgegevens worden automatisch verwijderd wanneer het account van de gebruiker uit Azure Active Directory wordt verwijderd.

Zie [Reageren op AVG-aanvragen voor het verwijderen van PowerApps-gegevens van de klant](powerapps-gdpr-delete-dsr.md) voor meer informatie.
