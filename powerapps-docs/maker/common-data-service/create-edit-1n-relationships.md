---
title: 'Overzicht van het maken van 1:N- (één-op-veel) of N:1-entiteitsrelaties (veel-op-één) in PowerApps | MicrosoftDocs'
description: Informatie over het maken van één-op-veel- of veel-op-één-entiteitsrelaties
ms.custom: ''
ms.date: 05/27/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: 52c00707-b2bc-4950-abec-89baefd94f6e
caps.latest.revision: 33
ms.author: matp
manager: kvivek
tags: null
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-one-to-many-or-many-to-one-entity-relationships-overview"></a>Overzicht van het maken van één-op-veel- of veel-op-één-entiteitsrelaties

In Common Data Service voor Apps wordt met 1:N- (één-op-veel) of N:1-entiteitsrelaties (veel-op-één) gedefinieerd hoe twee entiteiten in relatie staan tot elkaar. 
  
Evalueer voordat u een aangepaste entiteitsrelatie maakt of het gebruik van een bestaande entiteitsrelatie aan uw vereisten voldoet. <br />Meer informatie: [Nieuwe metagegevens maken of bestaande metagegevens gebruiken?](create-edit-metadata.md#create-new-metadata-or-use-existing-metadata)

Er zijn twee ontwerpers waarmee u 1:N- (één-op-veel) of N:1-entiteitsrelaties (veel-op-één) kunt maken en bewerken:

|Ontwerper| Beschrijving|
|--|--|
|[PowerApps-portal](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)|Biedt een eenvoudig gestroomlijnde ervaring, maar een aantal speciale instellingen is niet beschikbaar.<br />Meer informatie: [1:N- (één-op-veel) of N:1-entiteitsrelaties (veel-op-één) maken en bewerken in de PowerApps-portal](create-edit-1n-relationships-portal.md)|
|Oplossingenverkenner|Deze ontwerper is niet zo eenvoudig, maar biedt meer flexibiliteit en heeft minder algemene vereisten. <br />Meer informatie: [1:N- (één-op-veel) of N:1-entiteitsrelaties (veel-op-één) maken en bewerken met de oplossingenverkenner](create-edit-1n-relationships-solution-explorer.md) |

> [!NOTE]
> U kunt ook nieuwe entiteitsrelaties in uw omgeving maken met het volgende:
> - Selecteer in modelgestuurde apps **Nieuw veld** in de formuliereneditor en maak een veld *Opzoeken*. <br />Meer informatie: [Een veld toevoegen aan een formulier](../model-driven-apps/add-field-form.md)
> - Maak een nieuw opzoekveld voor de gerelateerde entiteit. <br />Meer informatie: [Velden maken en bewerken](create-edit-fields.md)
> - Importeer een oplossing die de definitie van de entiteitsrelatie bevat. <br />Meer informatie: [Oplossingen importeren, bijwerken en exporteren](import-update-export-solutions.md)
> - Gebruik Power Query om nieuwe entiteiten te maken en deze te vullen met gegevens. <br />Meer informatie: [Gegevens aan een entiteit toevoegen in Common Data Service voor Apps met behulp van Power Query](data-platform-cds-newentity-pq.md).
> - Een ontwikkelaar kan [webservices](../../developer/common-data-service/use-web-services.md#metadata-services) gebruiken om een programma te schrijven waarmee entiteitsrelaties kunnen worden gemaakt en bijgewerkt. <br />Meer informatie: [Metagegevens van entiteitsrelaties aanpassen](https://docs.microsoft.com/dynamics365/customer-engagement/developer/customize-entity-relationship-metadata)

De informatie in dit onderwerp kan u helpen bepalen welke ontwerper u kunt gebruiken. 

U kunt de PowerApps-portal gebruiken om 1:N- (één-op-veel) of N:1-entiteitsrelaties (veel-op-één) te maken en te bewerken tenzij u aan de volgende vereisten moet voldoen:

- Veldtoewijzingen configureren
- Opties van het navigatiedeelvenster voor modelgestuurde apps configureren
- Relatiegedragingen configureren
- Bepaal of de relatie in de geavanceerde zoekfunctie wordt verborgen.
- Een hiërarchische relatie maken


## <a name="community-tools"></a>Community-hulpprogramma's

**[Entity Relation Diagram Creator](https://www.xrmtoolbox.com/plugins/JourneyIntoCRM.XrmToolbox.ERDPlugin/)** is een hulpprogramma dat de XrmToolbox-community voor CDS voor Apps heeft ontwikkeld. Raadpleeg het onderwerp [Ontwikkelaarshulpprogramma´s voor Common Data Service voor Apps](https://docs.microsoft.com/dynamics365/customer-engagement/developer/developer-tools) voor meer hulpprogramma´s die door de community zijn ontwikkeld.

> [!NOTE]
> De community-hulpprogramma's zijn geen product van Microsoft en Microsoft biedt geen ondersteuning voor de community-hulpprogramma's. Als u vragen hebt over het hulpprogramma, raadpleegt u de uitgever hiervan. Meer informatie: [XrmToolBox](https://www.xrmtoolbox.com).

### <a name="see-also"></a>Zie ook

[Relaties tussen entiteiten maken en bewerken](create-edit-entity-relationships.md)<br />
[1:N- (één-op-veel) of N:1-entiteitsrelaties (veel-op-één) maken en bewerken in de PowerApps-portal](create-edit-1n-relationships-portal.md)<br />
[1:N- (één-op-veel) of N:1-entiteitsrelaties (veel-op-één) maken en bewerken met de oplossingenverkenner](create-edit-1n-relationships-solution-explorer.md)<br />
[Ontwikkelaarsdocumentatie: Metagegevens van entiteitsrelaties aanpassen](/dynamics365/customer-engagement/developer/customize-entity-relationship-metadata)<br />
[Ontwikkelaarsdocumentatie: Entiteitsrelatiegeschiktheid](/dynamics365/customer-engagement/developer/entity-relationship-eligibility)


