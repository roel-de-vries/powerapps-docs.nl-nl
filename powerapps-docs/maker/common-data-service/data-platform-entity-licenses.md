---
title: Licentie-vereisten voor entiteiten | Microsoft Docs
description: Een uitleg van de licentievereisten voor entiteiten binnen Common Data Service (CDS) voor apps.
author: clwesene
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 07/25/2018
ms.author: clwesene
ms.openlocfilehash: 758d5b5ff2c552a4c4ccbf210062f35d4e53209c
ms.sourcegitcommit: efea7ed5ad8e80c87ba423fb094fa94b4e864d75
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/26/2018
ms.locfileid: "39265505"
---
# <a name="license-requirements-for-entities"></a>Licentievereisten voor entiteiten
App-makers kunnen gebruikmaken van de meeste entiteiten die beschikbaar zijn binnen Common Data Service (CDS) voor apps (inclusief aangepaste entiteiten en entiteiten die deel uitmaken van Common Data Service) om apps en stromen te maken voor gebruikers die beschikken over een licentie voor PowerApps-abonnement 1 of Microsoft Flow-abonnement 1. In sommige gevallen bevatten entiteiten complexe bedrijfslogica of zijn ze gekoppeld aan Dynamics 365-toepassingen waarvoor app-gebruikers een specifieke licentie nodig hebben. 


|Entiteit  |Beschrijving  |Vereiste  |
|---------|---------|---------|
|Entiteiten met complexe bedrijfslogica  | Dit zijn de entiteiten waarvoor complexe bedrijfslogica wordt gebruikt aan de serverzijde. Een voorbeeld is een entiteit waarvoor in realtime een werkstroom wordt gebruikt of waarvoor een code-invoegtoepassing wordt gebruikt.     | [PowerApps-abonnement 2](https://powerapps.microsoft.com/pricing/) of [Flow-abonnement 2](https://flow.microsoft.com/pricing/)  | 
|Beperkte entiteiten    | Dit zijn entiteiten die niet standaard onderdeel zijn van de Common Data Service voor apps, maar die onderdeel zijn van een Dynamics 365-toepassing voor klantbetrokkenheid of een oplossing van een derde partij. Voorbeelden: de entiteiten voor kennisartikelen, doelstellingen en rechten.    | [Een Dynamics 365-abonnement](https://dynamics.microsoft.com/pricing/)    |


> [!NOTE]
> Voor apps en stromen die gebruikmaken van deze entiteiten heeft de gebruiker van de app of stroom de juiste licenties nodig, niet de maker of ontwikkelaar van de app of stroom.

## <a name="entities-with-complex-business-logic"></a>Entiteiten met complexe bedrijfslogica
Voor entiteiten die de volgende complexe serverlogica bevatten, hebben gebruikers van een app of stroom die gebruikmaakt van deze entiteiten een licentie nodig voor PowerApps-abonnement 2 of Microsoft Flow-abonnement 2:

* Code-invoegtoepassingen (zie [Invoegtoepassingen ontwikkelen](https://docs.microsoft.com/dynamics365/customer-engagement/developer/plugin-development) voor meer informatie)
* Realtimewerkstromen (zie [Werkstroomprocessen](https://docs.microsoft.com/dynamics365/customer-engagement/customize/workflow-processes) voor meer informatie)

    > [!NOTE]
    >  Alleen de werkstromen die worden geconverteerd naar een realtimewerkstroom worden beschouwd als realtime en synchroon. Werkstromen die op de achtergrond worden uitgevoerd, kunnen nog steeds worden gebruikt met het juiste PowerApps-abonnement, zonder dat er aanvullende licenties nodig zijn.

Als u wilt weten of u wel of geen complexe bedrijfslogica aan uw entiteiten hebt toegevoegd, bekijkt u de lijst met invoegtoepassingsassembly's en werkstromen die in uw omgeving zijn geconfigureerd. Zie [Complexe entiteiten waarvoor PowerApps P2-licenties zijn vereist](data-platform-complex-entities.md) voor de lijst entiteiten die mogelijk logica aan de serverzijde bevatten na het installeren van een Dynamics 365-toepassing 

### <a name="impacting-license-requirements-when-adding-complex-business-logic"></a>Licentievereisten met gevolgen tijdens het toevoegen van complexe bedrijfslogica
App-makers kunnen code-invoegtoepassingen en realtimewerkstromen toevoegen aan entiteiten binnen CDS voor Apps, maar hierdoor veranderen wel de licentievereisten voor gebruikers van apps die al zijn geïmplementeerd. App-makers moeten daarom goed opletten wanneer ze complexe bedrijfslogica toevoegen aan een entiteit en controleren van welke apps de entiteit gebruikmaakt en of gebruikers van deze apps over de juiste licenties beschikken.

## <a name="restricted-entities"></a>Beperkte entiteiten
Voor bepaalde entiteiten die aan de functionaliteit van Dynamics 365-toepassingen zijn gekoppeld, hebben app-gebruikers de bijbehorende licentie voor die toepassing nodig als ze records binnen de entiteiten willen maken, bijwerken of verwijderen. Zie [Beperkte entiteiten waarvoor Dynamics 365-licenties vereist zijn](data-platform-restricted-entities.md) voor een volledige lijst met beperkte entiteiten.

## <a name="licensing-examples"></a>Licentievoorbeelden
Barb en Isaac maken apps in PowerApps met behulp van CDS voor apps om hun gegevens op te slaan.

Barb maakt twee canvas-apps:

* App 1 &ndash; maakt gebruik van de entiteit Contact plus een aangepaste entiteit waarin verwante informatie wordt opgeslagen
* App 2 &ndash; maakt gebruik van de entiteit Contact plus de entiteit Incident, een beperkte entiteit

Isaac maakt twee modelgestuurde apps:

* App 3 &ndash; maakt gebruik van de entiteit Contact plus een aangepaste entiteit waarin verwante informatie wordt opgeslagen
* App 4 &ndash; maakt gebruik van de entiteit Contact plus de entiteit Incident, een beperkte entiteit

Barb en Isaac hebben de volgende licenties nodig:
* Barb heeft een licentie voor PowerApps-abonnement 1 nodig om canvas-apps met behulp van CDS voor apps te maken. Als ze een database of een aangepaste entiteit moet maken, heeft ze een licentie voor PowerApps-abonnement 2 nodig.

* Isaac heeft een licentie voor PowerApps-abonnement 2 nodig om modelgestuurde apps te bouwen.

App-gebruikers hebben de volgende licenties nodig:
* Gebruikers van app 1 hebben alleen een licentie voor PowerApps-abonnement 1 of -abonnement 2 nodig omdat de app geen entiteiten met complexe bedrijfslogica of beperkte entiteiten bevat.

* Gebruikers van app 2 hebben een licentie voor Dynamics 365 for Customer Service, Enterprise Edition (of een Dynamics 365- of Dynamics 365 Customer Engagement-abonnement) nodig omdat de app een beperkte entiteit bevat.

* Gebruikers van app 3 hebben een licentie voor PowerApps-abonnement 2 nodig omdat het een modelgestuurde app is.

* Gebruikers van app 4 hebben een licentie voor Dynamics 365 for Customer Service, Enterprise Edition (of een Dynamics 365- of Dynamics 365 Customer Engagement-abonnement) nodig omdat de app een beperkte entiteit bevat.

    Het Dynamics 365 for Customer Service-abonnement bevat een licentie voor PowerApps-abonnement 2, waarmee gebruikers modelgestuurde apps kunnen uitvoeren.

Nu gaan we kijken wat er gebeurt als Isaac een realtimewerkstroom toevoegt aan de aangepaste entiteit die zowel Barb als Isaac in hun apps gebruiken.

Barb en Isaac hebben de volgende licenties nodig:
* Barb heeft nog steeds een licentie voor PowerApps-abonnement 1 nodig om canvas-apps met behulp van CDS voor apps te maken.

* Isaac heeft nog steeds een licentie voor PowerApps-abonnement 2 nodig om modelgestuurde apps te bouwen.

App-gebruikers hebben de volgende licenties nodig:
* Gebruikers van app 1 hebben nu een licentie voor PowerApps-abonnement 2 nodig omdat de app een entiteit met een realtimewerkstroom bevat.

* Gebruikers van app 2 hebben nog steeds een licentie voor Dynamics 365 for Customer Service, Enterprise Edition (of een Dynamics 365- of Dynamics 365 Customer Engagement-abonnement) nodig omdat de app een beperkte entiteit bevat. 

* Gebruikers van app 3 hebben nog steeds een licentie voor PowerApps-abonnement 2 nodig omdat het een modelgestuurde app is.

* Gebruikers van app 4 hebben nog steeds een licentie voor Dynamics 365 for Customer Service, Enterprise Edition (of een Dynamics 365- of Dynamics 365 Customer Engagement-abonnement) nodig omdat de app een beperkte entiteit bevat.

    Het Dynamics 365 for Customer Service-abonnement bevat een licentie voor PowerApps-abonnement 2, waarmee gebruikers modelgestuurde apps kunnen uitvoeren.

De enige app die gevolgen ondervindt door deze wijziging is app 1, waarvoor eerder een licentie voor PowerApps-abonnement 1 nodig was, maar waar nu een licentie voor PowerApps-abonnement 2 nodig is omdat deze een entiteit met complexe bedrijfslogica bevat. 

## <a name="more-about-licensing"></a>Meer informatie over licentieverlening
Zie [Licentieoverzicht](../../administrator/pricing-billing-skus.md) voor meer informatie over PowerApps- en Dynamics 365-licenties.
