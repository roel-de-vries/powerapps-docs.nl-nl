---
title: Inleiding tot oplossingen | Microsoft Docs
description: Meer informatie over hoe u oplossingen kunt gebruiken om model-apps te maken.
services: ''
suite: powerapps
documentationcenter: na
author: JimDaly
manager: faisalmo
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/19/2018
ms.author: jdaly
ms.openlocfilehash: b9e06888a23426a44eeaf4354bf456dd8b15cfad
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2018
---
# <a name="introduction-to-solutions"></a>Inleiding tot oplossingen

*Oplossingen* geven aan hoe aanpassers en ontwikkelaars de software-eenheden maken, verpakken en onderhouden die een uitbreiding vormen van Common Data Service for Apps. Aanpassers en ontwikkelaars distribueren oplossingen zodat organisaties Common Data Service for Apps kunnen gebruiken om de bedrijfsfunctionaliteit te installeren en te verwijderen die op basis van de oplossing wordt gedefinieerd.

Elke aanpassing die u in Common Data Service for Apps aanbrengt, maakt deel uit van een oplossing. Elke wijziging die u toepast, wordt bijgehouden en eventuele afhankelijkheden kunnen worden berekend. Wanneer u een beheerde oplossing exporteert, worden alle wijzigingen die u voor die oplossing hebt toegepast, in een bestand opgenomen. Dit bestand kunt u vervolgens in een andere Common Data Service for Apps-omgeving importeren.

Als u van plan bent aanpassingen of uitbreidingen tussen verschillende Common Data Service for Apps-omgevingen te transporteren of oplossingen te distribueren met AppSource, is het belangrijk dat u het oplossingsframework begrijpt.

## <a name="unmanaged-and-managed-solutions"></a>Onbeheerde en beheerde oplossingen

Er zijn twee typen oplossingen: *beheerde* en *onbeheerde* oplossingen.

Een **beheerde** oplossing is een voltooide oplossing die bedoeld is om te worden gedistribueerd en geïnstalleerd. 
- U kunt de onderdelen van een beheerde oplossing niet bewerken.
- U kunt een beheerde oplossing niet exporteren.
- U kunt onbeheerde aanpassingen toevoegen aan de onderdelen van een beheerde oplossing. Als u dit doet, maakt u een afhankelijkheid tussen uw onbeheerde aanpassingen en de beheerde oplossing. Als een afhankelijkheid bestaat, kan de beheerde oplossing pas worden verwijderd als u de afhankelijkheid verwijdert.
- Wanneer een beheerde oplossing wordt verwijderd (als de installatie ongedaan wordt gemaakt), worden alle aanpassingen en uitbreidingen van de oplossing verwijderd.

 > [!IMPORTANT]
 > De volgende gegevens gaan verloren wanneer u een beheerde oplossing verwijdert: gegevens die zijn opgeslagen in aangepaste entiteiten die deel uitmaken van de beheerde oplossing en gegevens die zijn opgeslagen in aangepaste kenmerken die deel uitmaken van de beheerde oplossing voor andere entiteiten die geen deel uitmaken van de beheerde oplossing.

Een **onbeheerde** oplossing is een oplossing die nog wordt ontwikkeld en niet is bedoeld om te worden gedistribueerd. 
- Als een oplossing onbeheerd is, kunt u doorgaan met het toevoegen van onderdelen aan de oplossing of het verwijderen van onderdelen uit de oplossing. 
- U kunt een onbeheerde oplossing exporteren om onbeheerde aanpassingen tussen omgevingen te transporteren.
- Wanneer een onbeheerde oplossing wordt verwijderd, wordt alleen de oplossingscontainer met eventuele aanpassingen verwijderd. Alle onbeheerde aanpassingen blijven van kracht en maken deel uit van dezelfde standaardoplossing. 
- Wanneer de onbeheerde oplossing is voltooid en u deze wilt distribueren, exporteert u de oplossing als een beheerde oplossing.

 > [!NOTE]
 > U kunt een beheerde oplossing niet importeren in dezelfde omgeving als die waarin de oorspronkelijke onbeheerde oplossing is opgeslagen. Als u een beheerde oplossing wilt testen, moet u een afzonderlijke omgeving maken en de oplossing hierin importeren.

## <a name="solution-publishers"></a>Oplossingsuitgevers
Elke oplossing is gekoppeld aan een oplossingsuitgever. De oplossingsuitgever levert informatie over de manier waarop contact met de uitgever kan worden opgenomen en een waarde voor het aanpassingsvoorvoegsel. De standaardwaarde is `new`.

Wanneer alle schemawijzigingen als onderdeel van een oplossing zijn opgenomen, wordt het aanpassingsvoorvoegsel van de oplossingsuitgever vóór de naam van de schema-items geplaatst. Ook aan aangepaste acties wordt deze waarde toegevoegd. Dit is nuttig omdat u hiermee eenvoudig kunt zien door welke oplossing het schema-item of de aangepaste actie is toegevoegd. Hoewel het niet vereist is voor alle schema-items en aangepaste acties in een oplossing hetzelfde aanpassingsvoorvoegsel te gebruiken, wordt dit wel aangeraden.

> [!IMPORTANT]
> Voordat u een oplossing maakt, moet u een record voor de oplossingsuitgever maken en de nieuwe oplossing aan deze record koppelen. Zorg ervoor dat het aanpassingsvoorvoegsel een betekenisvolle waarde vertegenwoordigt. 

Welke oplossingsuitgever u kiest, is belangrijk als u een update wilt publiceren naar een oplossing die u hebt verzonden. Een update kan alleen worden toegepast op een beheerde oplossing met dezelfde uitgever als de oorspronkelijke beheerde oplossing. 

Zie [Dynamics 365 Customer Engagement Developer Guide: Maintain managed solutions > Create managed solution updates](/dynamics365/customer-engagement/developer/maintain-managed-solutions#create-managed-solution-updates) (Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: Beheerde oplossingen onderhouden > Updates aanbrengen in beheerde oplossingen) voor meer informatie.

## <a name="create-a-solution-publisher-and-solution"></a>Een oplossingsuitgever en oplossing maken 

Als u een oplossingsuitgever en een oplossing wilt maken, navigeert u naar het gebied voor het aanpassen van Dynamics 365.

Via [powerapps.com](https://web.powerapps.com)

1. Selecteer het pictogram van de *wafel* in de linkerbovenhoek.
2. Selecteer **Alle apps** in het fly-outmenu.
3. Zoek **Dynamics 365 - aangepaste app**.
 U kunt op het beletselteken (...) klikken en **Deze app vastmaken** kiezen zodat u de volgende keer eenvoudiger naar het item kunt navigeren.
4. Selecteer de app **Dynamics 365 - aangepaste app**.
5. Navigeer naar **Instellingen** > **Aanpassing** > **Aanpassingen**.

Via [home.dynamics.com](http://home.dynamics.com/)

1. Zoek de tegel **Dynamics 365 - aangepast** en klik hierop.
2. Navigeer naar **Instellingen** > **Aanpassing** > **Aanpassingen**.

### <a name="create-a-solution-publisher"></a>Een oplossingsuitgever maken

1. Selecteer **Uitgevers** in het gebied met aanpassingen.
2. Klik op **Nieuw**.
3. Voer een **weergavenaam** in het formulier voor de uitgever in. Op basis van de weergavenaam wordt een waarde voor het veld **Naam** gegenereerd. U kunt de gegenereerde waarde accepteren of een nieuwe waarde opgeven.
4. Geef in het veld **Voorvoegsel** het aanpassingsvoorvoegsel op dat moet worden toegevoegd aan de aangepaste schema-items die u tijdens het ontwikkelen van uw oplossing toevoegt. De standaardwaarde is `new`. Kies een waarde die aansluit bij uw organisatie en waarmee gebruikers duidelijk kunnen zien welke onderdelen in hun systeem afkomstig zijn van uw oplossing.
5. Er wordt een **voorvoegsel voor optiewaarde** gegenereerd op basis van uw keuze voor het aanpassingsvoorvoegsel. Dit is een waarde die wordt toegevoegd aan de waarden voor de opties in de optieset die u aan de kenmerken in uw oplossing toevoegt. Met deze waarde wordt duidelijk welke opties u aan uw oplossing toevoegt.
6. In de sectie **Contactgegevens** van het formulier kunt u contactgegevens toevoegen voor personen die de oplossing installeren.
7. Klik op **Opslaan en sluiten** wanneer u klaar bent.

### <a name="create-a-solution"></a>Een oplossing maken

1. Selecteer **Oplossingen** in het gebied met aanpassingen.
2. Klik op **Nieuw**.
3. Voer een **weergavenaam** in het formulier voor de oplossing in. Op basis van de weergavenaam wordt een waarde voor het veld **Naam** gegenereerd. U kunt de gegenereerde waarde accepteren of een nieuwe waarde opgeven.
4. Zoek in het veld **Uitgever** de uitgever op die u hebt gemaakt in [Een oplossingsuitgever maken](#create-a-solution-publisher).
5. Selecteer in het veld **Versie** de gewenste versie voor uw oplossing (bijvoorbeeld 1.0.0.0).
6. Klik op **Opslaan** wanneer u klaar bent.

> [!IMPORTANT]
> Wanneer u een nieuw oplossingsonderdeel maakt dat u in deze oplossing wilt opnemen, gebruikt u deze oplossing of een andere aan dezelfde oplossingsuitgever gekoppelde oplossing om het onderdeel toe te voegen.
> Oplossingsonderdelen die zijn gemaakt in de context van een oplossing die aan een andere oplossingsuitgever is gekoppeld, kunt u aan deze oplossing toevoegen, maar het kan zijn dat hiervoor inconsistente aanpassingsvoorvoegselwaarden worden ingesteld.

## <a name="solution-layering"></a>Laaggebruik van oplossingen

U kunt twee beheerde oplossingen die met elkaar of met een andere op de omgeving toegepaste aanpassing in strijd zijn installeren om een beheerde oplossing te overschrijven. Hoe werkt dit?

Beheerde oplossingen in Common Data Service for Apps worden geëvalueerd op basis van de volgorde waarin ze zijn geïnstalleerd. Eventuele aanpassingen die niet in de beheerde oplossing zijn opgenomen, worden als laatste geëvalueerd.

In het volgende diagram ziet u hoe beheerde oplossingen en onbeheerde aanpassingen samenwerken om te bepalen wat tijdens de runtime in de toepassing wordt opgenomen.

![Diagram met laaggebruik van oplossing](media/solution-layering.png)

In dit voorbeeld wordt het standaardgedrag dat in de systeemoplossing is gedefinieerd, overschreven of toegevoegd door beheerde oplossingen. Aanpassingen die vervolgens zichtbaar zijn in de toepassing, kunnen worden overschreven of worden toegevoegd door onbeheerde aanpassingen.

Zie [Dynamics 365 Customer Engagement Developer Guide: Introduction to solutions > Unmanaged and managed solutions](/dynamics365/customer-engagement/developer/introduction-solutions#unmanaged-and-managed-solutions) (Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: Inleiding tot oplossingen > Beheerde en onbeheerde oplossingen) voor meer informatie.

## <a name="managed-properties"></a>Beheerde eigenschappen

Wanneer u een beheerde oplossing distribueert, kan iedereen die uw oplossing installeert zijn eigen onbeheerde aanpassingen in de oplossing opnemen. Gebruikers kunnen deze onbeheerde aanpassingen vervolgens toevoegen aan een oplossing die wordt gedistribueerd als beheerde oplossing die afhankelijk is van uw oplossing. Maar wat als u niet wilt dat gebruikers dit doen? Als uitgever van de beheerde oplossing kunt u beheerde eigenschappen gebruiken om specifieke aanpassingen voor de onderdelen van uw beheerde oplossing uit te schakelen.

Zie [Dynamics 365 Customer Engagement Developer Guide: Use managed properties](/dynamics365/customer-engagement/developer/use-managed-properties) (Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: Beheerde eigenschappen gebruiken) voor meer informatie.

## <a name="modular-solutions"></a>Modulaire oplossingen

U kunt het oplossingsframework gebruiken om een aparte set met onderdelen te maken waarmee een set functies wordt geboden. Elke beheerde oplossing kan worden geïnstalleerd of verwijderd om de implementatie van de klant terug te zetten naar de oorspronkelijke staat. Elke beheerde oplossing die u maakt, wordt boven op de systeemoplossing uitgevoerd en kan toegang krijgen tot de mogelijkheden van de onderliggende oplossing.

U kunt ook beheerde oplossingen maken die worden uitgevoerd boven op andere oplossingen om een set functies te maken die door verschillende oplossingen kan worden gedeeld. Op deze manier kunt u een algemene module bouwen en beheren als oplossing voor de ondersteuning van meerdere oplossingen. Als gevolg hiervan hoeven klanten alleen de oplossingen te installeren die ze nodig hebben en hoeft u dezelfde gedeelde functie niet in elke oplossing op te nemen. Als u een update wilt distribueren naar een oplossing die meerdere oplossingen ondersteunt, hoeft u alleen de algemene module bij te werken.

Klanten, systeemimplementeerders en andere ISV's kunnen vervolgens oplossingen boven op uw oplossingen bouwen voor de aanpassingen die ze nodig hebben.

Een set met bedrijfsfuncties die uit meerdere oplossingen bestaat, wordt een pakket genoemd. U kunt *Package Deployer* gebruiken om meerdere oplossingen in één installeerbare eenheid te combineren.

## <a name="deploy-solution-packages"></a>Oplossingspakketten implementeren

Gebruik *Package Deployer* om een aangepast installatieprogramma te maken voor een pakket dat kan bestaan uit: 
- Een of meer oplossingsbestanden.
- Platte bestanden of geëxporteerde configuratiegegevensbestanden. 
- Aangepaste code die kan worden uitgevoerd voor, tijdens of na de implementatie van het pakket.
- HTML-inhoud die specifiek is voor het pakket en kan worden weergegeven aan het begin en het einde van het implementatieproces. Dit kan handig zijn om een beschrijving te bieden van de oplossingen en bestanden die in het pakket zijn geïmplementeerd.

Zie [Dynamics 365 Customer Engagement Developer Guide: Create packages for the Dynamics 365 Package Deployer](/dynamics365/customer-engagement/developer/create-packages-package-deployer) (Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: Pakketten maken voor Dynamics 365 Package Deployer) voor meer informatie.

## <a name="team-development-of-solutions"></a>Teamontwikkeling van oplossingen

Een oplossingsbestand is een enkel binair bestand dat zich niet leent voor broncodebeheer of teamontwikkeling. Het is niet mogelijk om met meerdere ontwikkelaars aan de aangepaste onderdelen in de oplossing te werken.

Het probleem met broncodebeheer en teamontwikkeling van oplossingsbestanden kunt u oplossen met het hulpprogramma *SolutionPackager*. Hiermee worden afzonderlijke onderdelen in het gecomprimeerde oplossingsbestand geïdentificeerd, waarna deze worden uitgepakt naar afzonderlijke bestanden. Met het hulpprogramma kan het oplossingsbestand ook opnieuw worden gemaakt door de bestanden in te pakken die eerder zijn uitgepakt. Hierdoor kunnen meerdere personen onafhankelijk aan een enkele oplossing werken en de wijzigingen uitpakken naar een algemene locatie. Omdat elk onderdeel in het oplossingsbestand is onderverdeeld in meerdere bestanden, kunnen aanpassingen worden samengevoegd zonder hierbij eerdere wijzigingen te overschrijven. Een tweede gebruiksmogelijkheid van het hulpprogramma SolutionPackager is dat het vanuit een geautomatiseerd buildproces kan worden aangeroepen om een gecomprimeerd oplossingsbestand te genereren van eerder uitgepakte onderdeelbestanden, zonder dat hiervoor een actief exemplaar van Dynamics 365 nodig is.

Zie [Dynamics 365 Customer Engagement Developer Guide: Solution tools for team development](/dynamics365/customer-engagement/developer/solution-tools-team-development) (Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: Oplossingshulpprogramma's voor teamontwikkeling) voor meer informatie.

### <a name="see-also"></a>Zie ook

[Overzicht van Common Data Service for Apps voor ontwikkelaars](overview.md)