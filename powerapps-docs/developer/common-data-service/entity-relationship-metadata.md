---
title: Metagegevens van entiteitsrelaties | Microsoft Docs
description: Meer informatie over de metagegevens van entiteitsrelaties die in Common Data Service for Apps worden gebruikt.
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
ms.date: 03/12/2018
ms.author: jdaly
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: ea59e1eea1c0a85c2de1f2d654c10ed687ffe858
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42863512"
---
# <a name="entity-relationship-metadata"></a>Metagegevens van entiteitsrelaties

Wanneer u de oplossingsverkenner of de drie relatieverzamelingen in `EntityMetadata` bekijkt, denkt u misschien dat er drie typen entiteitsrelaties zijn. Er zijn in werkelijkheid slechts twee typen entiteitsrelaties, zoals u in de volgende tabel kunt zien.

|Relatietype|Beschrijving|
|--|--|
|Een-op-veel<br />[OneToManyRelationshipMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.onetomanyrelationshipmetadata)|Een entiteitsrelatie waarbij één entiteitsrecord voor de **primaire entiteit** aan verschillende andere records voor de **gerelateerde entiteit** kan worden gekoppeld vanwege een opzoekveld in de gerelateerde entiteit.<br />Wanneer u een record voor de primaire entiteit bekijkt, kunt u een lijst met de gerelateerde entiteitsrecords weergeven die aan de primaire entiteit zijn gekoppeld.|
|Veel-op-veel<br />[ManyToManyRelationshipMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.manytomanyrelationshipmetadata)|Een entiteitsrelatie die afhankelijk is van een speciale *relatie-entiteit*, ook wel een *Intersect*-entiteit genoemd, zodat verschillende records van één entiteit aan verschillende records van een andere entiteit kunnen worden gekoppeld.<br />Wanneer u records van een van de entiteiten in een veel-op-veel-relatie bekijkt, kunt u een lijst weergeven met de records van de andere entiteit die aan deze records zijn gerelateerd.|

De verzameling `ManyToOneRelationships` van `EntityMetadata` bevat [OneToManyRelationshipMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.onetomanyrelationshipmetadata)-typen. Tussen de entiteiten bestaan een-op-veel-relaties en in deze relaties wordt een entiteit een *primaire entiteit* of *gerelateerde entiteit* genoemd. De gerelateerde entiteit (of de *onderliggende entiteit*) heeft een opzoekkenmerk waarmee een verwijzing naar een record uit de primaire entiteit (de *bovenliggende entiteit*) kan worden opgeslagen. Een veel-op-een-relatie is in feite een een-op-veel-relatie gezien vanuit de gerelateerde entiteit.

> [!NOTE]
> Hoewel gerelateerde entiteiten soms *onderliggende entiteiten* worden genoemd, moeten ze niet worden verward met [onderliggende entiteiten](entity-metadata.md#child-entities). Met onderliggende entiteiten wordt verwezen naar de manier waarop de beveiliging is toegepast op de gerelateerde entiteiten.

Meer informatie:
- [Aanpassingshandleiding voor Dynamics 365 Customer Engagement: Relaties tussen entiteiten maken en bewerken](/dynamics365/customer-engagement/customize/create-edit-entity-relationships)
- [Dynamics 365 Customer Engagement Developer Guide: Customize entity relationship metadata](/dynamics365/customer-engagement/developer/customize-entity-relationship-metadata) (Ontwikkelaarshandleiding voor Dynamics Customer Engagement: Aanpassen metagegevens van entiteitsrelaties)

## <a name="cascade-configuration"></a>Trapsgewijze configuratie

Bij een een-op-veel-relatie tussen entiteiten zijn er trapsgewijze kenmerken die u kunt configureren om de integriteit van gegevens te behouden en bedrijfsprocessen te automatiseren.

Meer informatie:

- [Aanpassingshandleiding voor Dynamics 365 Customer Engagement: 1:N (een-op-veel) of N:1 (veel-op-een) relaties maken > Relatiegedrag](/dynamics365/customer-engagement/customize/create-and-edit-1n-relationships#relationship-behavior)
- [Dynamics 365 Customer Engagement Developer Guide: Entity relationship behavior](/dynamics365/customer-engagement/developer/entity-relationship-behavior) (Ontwikkelaarshandleiding voor Dynamics Customer Engagement: Gedrag van entiteitsrelaties)


## <a name="create-a-hierarchy-of-entities"></a>Een hiërarchie met entiteiten maken

Binnen een naar zichzelf verwijzende een-op-veel-relatie kunt u een hiërarchie maken door de eigenschap `IsHierarchical` in te stellen op `true`.

Op deze manier kunt u in modelgestuurde apps een ervaring inschakelen waarmee u de hiërarchie kunt weergeven en er interactief mee kunt werken. 

Voor ontwikkelaars kunt u op basis van de hiërarchie nieuwe typen query's inschakelen met behulp van de operators `Under` en `Not Under`.

Zie [Dynamics 365 Customer Engagement Developer Guide : Query and visualize hierarchically related data](/dynamics365/customer-engagement/customize/query-visualize-hierarchical-data) (Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: Hiërarchisch gerelateerde gegevens zoeken en visualiseren) voor meer informatie.

### <a name="see-also"></a>Zie ook

[Common Data Service for Apps-entiteiten](entities.md)
