---
title: Licentievereisten voor entiteiten | Microsoft Docs
description: Een uitleg van licentievereisten voor entiteiten in Common Data Service (CDS) voor Apps.
author: clwesene
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 05/01/2018
ms.author: clwesene
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="license-requirements-for-entities"></a>Licentievereisten voor entiteiten
Makers van apps kunnen de meeste entiteiten gebruiken die beschikbaar zijn in Common Data Service (CDS) voor Apps (inclusief aangepaste entiteiten en entiteiten die deel uitmaken van het Common Data Model) om apps en stromen te maken voor gebruikers met een PowerApps Plan 1- of Microsoft Flow Plan 1-licentie. In bepaalde gevallen bevatten entiteiten complexe bedrijfslogica of zijn ze gebonden aan Dynamics 365-toepassingen die vereisen dat appgebruikers een specifieke licentie hebben. 


|Entiteit    |Beschrijving    |Vereiste    |
|---------|---------|---------|
|Entiteiten met complexe bedrijfslogica   | Dit zijn entiteiten die complexe serverbedrijfslogica gebruiken. Bijvoorbeeld elke entiteit die een realtime-werkstroom of codeplug-in gebruikt.       |  [PowerApps Plan 2](https://powerapps.microsoft.com/pricing/) of [Flow Plan 2](https://flow.microsoft.com/pricing/)        |
|Beperkte entiteiten  |  Dit zijn entiteiten die niet standaard bij Common Data Service voor Apps worden geleverd, maar zijn opgenomen in een Dynamics 365 Customer Engagement-toepassing of een oplossing van derden. Bijvoorbeeld entiteiten voor kennisartikelen, doelstellingen en rechten.     |  [Een Dynamics 365-plan](https://dynamics.microsoft.com/pricing/)      | 


> [!NOTE]
> Apps en stromen die deze entiteiten gebruiken, vereisen dat de app- en stroomgebruiker over de juiste licenties beschikt, niet de maker of de ontwikkelaar van de app of de stroom.

## <a name="entities-with-complex-business-logic"></a>Entiteiten met complexe bedrijfslogica
Entiteiten die de volgende complexe serverlogica bevatten, vereisen dat gebruikers van een app of een stroom die deze entiteiten gebruiken, om een PowerApps Plan 2- of Microsoft Flow Plan 2-licentie hebben:

* Codeplug-ins (zie voor meer informatie [Ontwikkeling van plug-ins](https://docs.microsoft.com/dynamics365/customer-engagement/developer/plugin-development))
* Realtime-werkstromen (zie voor meer informatie [Werkstroomprocessen](https://docs.microsoft.com/dynamics365/customer-engagement/customize/workflow-processes))

    > [!NOTE]
    >  Alleen werkstromen die naar een realtime-werkstroom worden geconverteerd, worden beschouwd als realtime en synchroon. Werkstromen die op de achtergrond worden uitgevoerd, kunnen nog steeds worden gebruikt met het juiste PowerApps-plan en vereisen geen aanvullende licenties.

Als u wilt weten of u complexe bedrijfslogica op uw entiteiten hebt toegevoegd of niet, controleert u de lijst met plug-inassembly´s en werkstromen die in uw omgeving zijn geconfigureerd. Zie voor de lijst met entiteiten die serverlogica kunnen bevatten na de installatie van een Dynamics 365-toepassing [Complexe entiteiten die PowerApps Plan 2-licenties vereisen](data-platform-complex-entities.md)  

### <a name="impacting-license-requirements-when-adding-complex-business-logic"></a>Licentievereisten die van invloed zijn bij het toevoegen van complexe bedrijfslogica
Makers van apps kunnen codeplug-ins en realtime-werkstromen toevoegen aan entiteiten in CDS voor Apps, maar als dit gebeurt kunnen de licentievereisten veranderen voor gebruikers van apps die al zijn geïmplementeerd. Makers van apps moeten goed opletten bij het toevoegen van complexe bedrijfslogica aan een entiteit en moeten eerst controleren welke apps de entiteit gebruikt en of gebruikers van deze apps de juiste licenties hebben.

## <a name="restricted-entities"></a>Beperkte entiteiten
Voor bepaalde entiteiten die zijn gebonden met de functionaliteit van Dynamics 365-toepassingen, is het vereist dat gebruikers van apps de bijbehorende licentie voor die toepassing hebben als ze records willen maken, bijwerken of verwijderen in de entiteiten. Zie voor een volledige lijst met beperkte entiteiten [Beperkte entiteiten die Dynamics 365-licenties vereisen](data-platform-restricted-entities.md).

## <a name="licensing-examples"></a>Voorbeelden van licenties
Barbara en Jan maken apps in PowerApps met CDS voor Apps om hun gegevens op te slaan.

Barbara maakt twee canvasapps:

* App 1 &ndash; gebruikt de contactpersoonentiteit samen met een aangepaste entiteit waarin gerelateerde gegevens worden opgeslagen
* App 2 &ndash; gebruikt de contactpersoonentiteit samen met de entiteit Incident. Dit is een beperkte entiteit

Jan maakt twee modelgestuurde apps:

* App 3 &ndash; gebruikt de contactpersoonentiteit samen met een aangepaste entiteit waarin gerelateerde gegevens worden opgeslagen
* App 4 &ndash; gebruikt de contactpersoonentiteit samen met de entiteit Incident. Dit is een beperkte entiteit

Barbara en Jan hebben de volgende licenties nodig:
* Barbara heeft een PowerApps Plan 1-licentie nodig om canvasapps te maken met CDS voor Apps. Als ze een database of een aangepaste entiteit moet maken, heeft ze een PowerApps Plan 2-licentie nodig.

* Jan heeft een PowerApps Plan 2-licentie nodig om modelgestuurde apps te bouwen.

Appgebruikers hebben de volgende licenties nodig:
* Gebruikers van app 1 hebben alleen een PowerApps Plan 1- of Plan 2-licentie nodig, aangezien de app geen entiteiten met complexe bedrijfslogica of beperkte entiteiten bevat.

* Gebruikers van app 2 hebben een licentie voor Dynamics 365 for Customer Service, Enterprise edition (of een abonnement voor Dynamics 365 of Dynamics 365 Customer Engagement) nodig, omdat de app een beperkte entiteit bevat.

* Gebruikers van app 3 hebben een licentie voor PowerApps Plan 2 nodig, omdat het een modelgestuurde app is.

* Gebruikers van app 4 hebben een licentie voor Dynamics 365 for Customer Service, Enterprise edition (of een abonnement voor Dynamics 365 of Dynamics 365 Customer Engagement) nodig, omdat de app een beperkte entiteit bevat.

    Het Dynamics 365 for Customer Service-plan bevat een PowerApps Plan 2-licentie, waarmee gebruikers modelgestuurde apps kunnen uitvoeren.

Laten we kijken wat er gebeurt als Jan een realtime-werkstroom toevoegt aan de aangepaste entiteit die Barbara en Jan alletwee in hun apps gebruiken.

Barbara en Jan hebben de volgende licenties nodig:
* Barbara heeft nog steeds een PowerApps Plan 1-licentie nodig om canvasapps te maken met CDS voor Apps.

* Jan heeft nog steeds een PowerApps Plan 2-licentie nodig om modelgestuurde apps te bouwen.

Appgebruikers hebben de volgende licenties nodig:
* Gebruikers van App 1 hebben nu een PowerApps Plan 2-licentie nodig, omdat de app een entiteit met een realtime-werkstroom bevat.

* Gebruikers van app 2 hebben nog steeds een licentie voor Dynamics 365 for Customer Service, Enterprise edition (of een abonnement voor Dynamics 365 of Dynamics 365 Customer Engagement) nodig, omdat de app een beperkte entiteit bevat. 

* Gebruikers van app 3 hebben nog steeds een licentie voor PowerApps Plan 2 nodig, omdat het een modelgestuurde app is.

* Gebruikers van app 4 hebben nog steeds een licentie voor Dynamics 365 for Customer Service, Enterprise edition (of een abonnement voor Dynamics 365 of Dynamics 365 Customer Engagement) nodig, omdat de app een beperkte entiteit bevat.

    Het Dynamics 365 for Customer Service-plan bevat een PowerApps Plan 2-licentie, waarmee gebruikers modelgestuurde apps kunnen uitvoeren.

De enige app waarop deze wijziging van invloed is, is App 1, waarvoor eerder een PowerApps Plan 1-licentie was vereist. Nu echter is een PowerApps Plan 2-licentie vereist, omdat het een entiteit met complexe bedrijfslogica bevat. 

## <a name="more-about-licensing"></a>Meer informatie over licenties
Zie [Licentieoverzicht](../../administrator/pricing-billing-skus.md) voor meer informatie over PowerApps- en Dynamics 365-licenties.
