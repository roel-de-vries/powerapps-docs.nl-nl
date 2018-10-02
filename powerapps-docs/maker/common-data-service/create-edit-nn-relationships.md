---
title: Overzicht van het maken van veel-op-veel-entiteitsrelaties maken in Common Data Service voor Apps | MicrosoftDocs
description: Meer informatie over het maken van veel-op-een-entiteitsrelaties
ms.custom: ''
ms.date: 05/29/2018
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
ms.assetid: 248cecfd-c9e8-430b-b4b0-860669866084
caps.latest.revision: 33
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-many-to-many-entity-relationships-overview"></a>Overzicht van het maken van veel-op-veel-entiteitsrelaties

Met één-op-veel-entiteitsrelaties (1:N) wordt een hiërarchie tussen records tot stand gebracht. Met veel-op-veel-relaties (N:N) is er geen expliciete hiërarchie. Er zijn geen opzoekvelden of gedragstypen om te configureren. Records die zijn gemaakt met veel-op-veel-relaties kunnen worden beschouwd als gelijken. De relatie is dan wederzijds.  
  
Met veel-veel-relaties worden in een relatie-entiteit (of overlappende entiteit) de gegevens opgeslagen waarmee de entiteiten worden gekoppeld. Deze entiteit heeft een één-op-veel-relatie met beide gerelateerde entiteiten en slaat alleen de waarden op die nodig zijn om de relatie te definiëren. U kunt geen aangepaste velden aan een relatie-entiteit toevoegen en deze is nooit zichtbaar in de gebruikersinterface. 
  
Voor het maken van een veel-op-veel-relatie moet u de twee entiteiten kiezen die u in de relatie wilt laten deelnemen. Voor modelgestuurde apps kunt u bepalen hoe u de desbetreffende lijsten beschikbaar moeten zijn in de navigatie voor elke entiteit. Dit zijn dezelfde opties als die voor de primaire entiteit in 1:N-entiteitsrelaties. Meer informatie:  [Navigatiedeelvensteritem voor primaire entiteit](create-edit-1n-relationships-solution-explorer.md#navigation-pane-item-for-primary-entity)
  
Niet alle entiteiten kunnen worden gebruikt met veel-op-veel-relaties. Als de entiteit niet kan worden gekozen in de ontwerpfunctie, kunt u geen nieuwe veel-op-veel-relatie maken met deze entiteit. Meer informatie: [Ontwikkelaarsdocumentatie: Entiteitsrelatiegeschiktheid](https://docs.microsoft.com/dynamics365/customer-engagement/developer/entity-relationship-eligibility)

Er zijn twee ontwerpers waarmee u 1:N- (één-op-veel) of N:1-entiteitsrelaties (veel-op-één) kunt maken en bewerken:

|Ontwerper| Beschrijving|
|--|--|
|[PowerApps-portal](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)|Biedt een eenvoudig gestroomlijnde ervaring, maar een aantal speciale instellingen is niet beschikbaar.<br />Meer informatie: [Veel-op-veel-entiteitsrelaties maken in Common Data Service voor Apps met de PowerApps-portal](create-edit-nn-relationships-portal.md)|
|Oplossingenverkenner|Deze ontwerper is niet zo eenvoudig, maar biedt meer flexibiliteit en heeft minder algemene vereisten.<br />Meer informatie: [N:N-entiteitsrelaties (veel-op-veel) maken in Common Data Service voor Apps met de oplossingenverkenner](create-edit-nn-relationships-solution-explorer.md) |

> [!NOTE]
> U kunt ook nieuwe veel-op-veel-entiteitsrelaties (N:N) in uw omgeving maken met het volgende:
> - Importeer een oplossing die de definitie van de relatie bevat. Meer informatie: [Oplossingen importeren, bijwerken en exporteren](import-update-export-solutions.md)
> - Een ontwikkelaar kan [Metagegevensservices](../../developer/common-data-service/use-web-services.md#metadata-services) gebruiken om een programma te schrijven waarmee entiteitsrelaties kunnen worden gemaakt en bijgewerkt. Meer informatie: [Ontwikkelaarsdocumentatie: Metagegevens van entiteitsrelaties aanpassen](https://docs.microsoft.com/dynamics365/customer-engagement/developer/customize-entity-relationship-metadata)

De informatie in dit onderwerp kan u helpen bepalen welke ontwerper u kunt gebruiken. 

U moet de PowerApps-portal gebruiken om veel-op-veel-entiteitsrelaties (N:N) te maken en te bewerken tenzij u aan de volgende vereisten moet voldoen:

- Configureer opties van het navigatiedeelvenster voor modelgestuurde apps.
- Verberg de relatie voor de geavanceerde zoekfunctie in modelgestuurde apps.

## <a name="see-also"></a>Zie ook

[Relaties tussen entiteiten maken en bewerken](create-edit-entity-relationships.md)<br />
[Veel-op-veel-entiteitsrelaties maken in Common Data Service voor Apps met de PowerApps-portal](create-edit-nn-relationships-portal.md)<br />
[N:N-entiteitsrelaties (veel-op-veel) maken in Common Data Service voor Apps met de oplossingenverkenner](create-edit-nn-relationships-solution-explorer.md)<br />
[Ontwikkelaarsdocumentatie: Metagegevens van entiteitsrelaties aanpassen](https://docs.microsoft.com/dynamics365/customer-engagement/developer/customize-entity-relationship-metadata)<br />
[Ontwikkelaarsdocumentatie: Entiteitsrelatiegeschiktheid](https://docs.microsoft.com/dynamics365/customer-engagement/developer/entity-relationship-eligibility)
