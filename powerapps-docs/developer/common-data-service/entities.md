---
title: Common Data Service for Apps-entiteiten | Microsoft Docs
description: Meer informatie over de entiteiten die beschikbaar zijn in Common Data Service for Apps.
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
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: f40c05c3bdab521cb1230be15cefc5dbb58eac18
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42844221"
---
# <a name="common-data-service-for-apps-entities"></a>Common Data Service for Apps-entiteiten

Het bieden van opslag voor gegevens is de belangrijkste functie van Common Data Service for Apps. Common Data Service bevat een basisset met entiteiten die structuur biedt voor gegevens die door zakelijke toepassingen worden gebruikt. 

Zie het Engelstalige artikel [Common Data Service for Apps entity reference](reference/about-entity-reference.md) (Naslagwerk voor Common Data Service for Apps-entiteiten) voor een overzicht van de basisset met entiteiten.

## <a name="modify-entities"></a>Entiteiten wijzigen

U kunt de entiteitsmetagegevens op verschillende manieren wijzigen.

### <a name="use-designers"></a>Ontwerpfuncties gebruiken

Er zijn verschillende manieren waarop u de entiteitsmetagegevens kunt wijzigen met behulp van ontwerpfuncties.


|Ontwerper  |Beschrijving  |
|---------|---------|
|powerapps.com|De eenvoudigste en meest gebruikte manier om het schema te wijzigen is door de site [powerapps.com](https://web.powerapps.com/) te gebruiken om Common Data Service te bewerken die aan een omgeving is gekoppeld. Wijzigingen die hier worden toegepast, worden uitgevoerd in de context van een onbeheerde Common Data Service-oplossing. <!-- TODO: Add link to topic that describes this -->|
|Common Data Service-standaardoplossingsverkenner|Er is een andere ontwerpfunctie die tijdens het bewerken van Common Data Service beschikbaar is via de site [powerapps.com](https://web.powerapps.com/). Als u in de linkerbenedenhoek op de knop **Geavanceerd** klikt, wordt de oplossingsverkenner voor de Common Data Service-standaardoplossing geopend. |
|Oplossingsverkenner voor uw oplossing |Als u een oplossing wilt distribueren, moet u nieuwe entiteiten, kenmerken of relaties maken in de context van de onbeheerde oplossing waarmee u uw oplossing wilt ontwikkelen. <br /> Zie [Een oplossingsuitgever en oplossing maken](introduction-solutions.md#create-a-solution-publisher-and-solution) voor meer informatie.|
|De formuliereneditor gebruiken|Tijdens het bewerken van een modelgestuurde app voor een entiteit kunt u op de knop **Nieuw veld** in **Veldverkenner** klikken. Als u een opzoekveld maakt, maakt u een nieuwe entiteitsrelatie ter ondersteuning van het veld.|

### <a name="import-a-solution"></a>Een oplossing importeren

Een oplossing kan entiteitsmetagegevens en andere aangepaste onderdelen bevatten. Als u een beheerde of onbeheerde oplossing in de tenant van Common Data Service for Apps importeert, worden deze entiteiten opgenomen of worden bestaande entiteiten uitgebreid met nieuwe entiteitsmetagegevens die de oplossing bevat.

### <a name="from-a-data-source-using-power-query"></a>Een gegevensbron met Power Query gebruiken

U kunt nieuwe entiteiten maken en deze vullen met gegevens met Power Query. Zie het Engelstalige artikel [Add data to an entity in Common Data Service by using Power Query](../../maker/common-data-service/data-platform-cds-newentity-pq.md) (Gegevens aan een entiteit in Common Data Service toevoegen met Power Query) voor meer informatie

### <a name="use-metadata-services"></a>Metagegevensservices gebruiken

De webservices die in Common Data Service worden weergegeven, omvatten mogelijkheden voor het maken, lezen, schrijven en verwijderen van entiteitsmetagegevens. Deze services worden het meest gebruikt om de metagegevens te lezen, omdat deze gegevens uw code tijdens runtime kunnen informeren over hoe de omgeving is aangepast.

Zie het Engelstalige artikel [Metadata Services](use-web-services.md#metadata-services) (Metagegevensservices) voor meer informatie.

## <a name="entity-metadata"></a>Entiteitsmetagegevens

Het gegevensmodel is gedefinieerd op basis van metagegevens die zijn opgeslagen in Common Data Service. Deze gegevens over het schema worden ook wel de *entiteitsmetagegevens* genoemd. 

- Deze gegevens worden via de [EntityMetadata-klasse](/dotnet/api/microsoft.xrm.sdk.metadata.entitymetadata) bij de organisatieservice gedefinieerd. 
- Met [EntityMetadata EntityType](/dynamics365/customer-engagement/web-api/entitymetadata) worden deze gegevens voor de web-API gedefinieerd. 

De entiteitsmetagegevens bevatten de volgende informatie:


|Gegevens  |Beschrijving  |
|---------|---------|
|Entiteitseigenschappen|Elke entiteit heeft bijna 100 eigenschappen die beschrijven hoe de entiteit wordt aangeduid en wat met de entiteit kan worden gedaan.  Zie het Engelstalige artikel [Entity Metadata](entity-metadata.md) (Metagegevens van entiteiten) voor meer informatie.|
|Kenmerken|De eigenschap `Attributes` van de entiteit bestaat uit een verzameling van kenmerken. Elk kenmerk heeft ongeveer 50 eigenschappen waarmee wordt beschreven hoe de entiteit wordt aangeduid, welk type gegevens de entiteit bevat, hoe de entiteit is ingedeeld en wat met de entiteit kan worden gedaan. Zie het Engelstalige artikel [Attribute Metadata](entity-attribute-metadata.md) (Kenmerkmetagegevens) voor meer informatie.|
|Relaties|Drie van de entiteitseigenschappen zijn verzamelingen van relaties tussen entiteiten. Deze verzamelingen bevatten verschillende typen relaties: veel-op-veel-, veel-op-een- en een-op-veel-relaties. Zie [Metagegevens van entiteitsrelaties](entity-relationship-metadata.md) voor meer informatie.|
|Bevoegdheden|Een van de entiteitseigenschappen is een verzameling van tussen de nul en acht bevoegdheden waarmee de soorten gegevensbewerkingen worden aangeduid die voor die entiteit kunnen worden uitgevoerd. Aan elke bewerking is een unieke id gekoppeld. Voorbeelden van deze bewerkingen zijn *Toevoegen*, *Toevoegen aan*, *Toewijzen*, *Maken*, *Verwijderen*, *Lezen*, *Delen* en *Schrijven*.|
|Sleutels|Standaard beschikt elke entiteit over één GUID-kenmerk (Globally Unique Identifier). De eigenschap `Keys` is een lege verzameling. U kunt alternatieve sleutels aan een entiteit toevoegen. Zie het Engelstalige artikel [Entity Keys](entity-metadata.md#entity-keys) (Entiteitssleutels) voor meer informatie.|

> [!TIP]
> Als u vertrouwd raakt met de entiteitsmetagegevens in het systeem, begrijpt u hoe Common Data Service werkt. Veel van de eigenschappen bepalen ook wat entiteiten kunnen doen in modelgestuurde apps. In de ontwerpfuncties die beschikbaar zijn voor het bewerken van metagegevens kunnen niet alle details worden weergegeven die in de metagegevens zijn gevonden. U kunt de modelgestuurde app Browser voor metagegevens installeren, waarmee u alle verborgen entiteiten en eigenschappen van metagegevens kunt weergeven die in het systeem zijn gevonden. Zie [Dynamics 365 Customer Engagement Developer Guide: Browse the metadata for your organization](/dynamics365/customer-engagement/developer/browse-your-metadata) (Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: Blader door de metagegevens voor uw organisatie) voor meer informatie.

### <a name="see-also"></a>Zie ook

[Overzicht van Common Data Service for Apps voor ontwikkelaars](overview.md)


