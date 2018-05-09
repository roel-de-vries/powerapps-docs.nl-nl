---
title: Licentie-vereisten voor entiteiten | Microsoft Docs
description: Een uitleg van de licentievereisten voor entiteiten binnen Common Data Service (CDS) voor apps.
documentationcenter: na
author: clwesene
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: cds
ms.date: 05/01/2018
ms.author: clwesene
ms.openlocfilehash: 7fc98e359b5daf1a170b63990005121fc2520d53
ms.sourcegitcommit: 45fac73f04aa03b5796ae6833d777f4757e67945
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/03/2018
---
# <a name="license-requirements-for-entities"></a>Licentie-vereisten voor entiteiten
App-makers kunnen gebruikmaken van de meeste entiteiten die beschikbaar zijn binnen Common Data Service (CDS) voor apps (inclusief aangepaste entiteiten en entiteiten die deel uitmaken van Common Data Service) om apps en stromen te maken voor gebruikers die alleen beschikken over een licentie voor PowerApps-abonnement 1 of Microsoft Flow-abonnement 1. In sommige gevallen bevatten entiteiten complexe bedrijfslogica of zijn ze gekoppeld aan Dynamics 365-producten waarvoor app-gebruikers een specifieke licentie nodig hebben. Meer informatie over beschikbare abonnementen vindt u op de [PowerApps-pagina met prijzen](https://powerapps.microsoft.com/pricing).

> [!NOTE]
> Voor apps en stromen die gebruikmaken van deze entiteiten heeft de gebruiker van de app of stroom de juiste licenties nodig,&mdash;niet de maker of ontwikkelaar van de app of stroom.

## <a name="entities-with-complex-business-logic"></a>Entiteiten met complexe bedrijfslogica
Voor entiteiten die de volgende complexe serverlogica bevatten, hebben gebruikers van een app of stroom die gebruikmaakt van deze entiteiten een licentie nodig voor PowerApps-abonnement 2 of Microsoft Flow-abonnement 2:

* Code-invoegtoepassingen (zie [Invoegtoepassingen ontwikkelen](https://docs.microsoft.com/dynamics365/customer-engagement/developer/plugin-development) voor meer informatie)
* Realtimewerkstromen (zie [Werkstroomprocessen](https://docs.microsoft.com/dynamics365/customer-engagement/customize/workflow-processes) voor meer informatie)

    > [!NOTE]
    >  Alleen de werkstromen die worden geconverteerd naar een realtimewerkstroom worden beschouwd als realtime en synchroon. Werkstromen die op de achtergrond worden uitgevoerd, kunnen nog steeds worden gebruikt met het juiste PowerApps-abonnement, zonder dat er aanvullende licenties nodig zijn.

Als u wilt weten of u wel of geen complexe bedrijfslogica aan uw entiteiten hebt toegevoegd, bekijkt u de lijst met invoegtoepassingsassembly's en werkstromen die in uw omgeving zijn geconfigureerd.

## <a name="impacting-license-requirements-when-adding-complex-business-logic"></a>Licentievereisten met gevolgen tijdens het toevoegen van complexe bedrijfslogica
App-makers kunnen code-invoegtoepassingen en realtimewerkstromen toevoegen aan entiteiten binnen CDS voor Apps, maar hierdoor veranderen wel de licentievereisten voor gebruikers van apps die al zijn geïmplementeerd. App-makers moeten daarom goed opletten wanneer ze complexe bedrijfslogica toevoegen aan een entiteit en controleren van welke apps de entiteit gebruikmaakt en of gebruikers van deze apps over de juiste licenties beschikken.

## <a name="entities-restricted-to-dynamics-365-licenses"></a>Entiteiten die beperkt zijn tot Dynamics 365-licenties
Voor bepaalde entiteiten die aan de functionaliteit van Dynamics 365-producten zijn gekoppeld, hebben app-gebruikers de bijbehorende licentie voor dat product nodig als ze records binnen de entiteiten willen maken, bijwerken of verwijderen. Zie [Beperkte entiteiten waarvoor Dynamics 365-licenties vereist zijn](data-platform-restricted-entities.md) voor een volledige lijst met beperkte entiteiten.

## <a name="licensing-example"></a>Licentievoorbeelden
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

## <a name="licensing"></a>Licentieverlening
Zie [Licentieoverzicht](../../administrator/pricing-billing-skus.md) voor meer informatie over PowerApps- en Dynamics 365-licenties.
