---
title: Entiteitsrelaties maken en bewerken voor Common Data Service for Apps | MicrosoftDocs
ms.custom: ''
ms.date: 05/26/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- PowerApps
ms.assetid: c765b6d9-4d87-4c2d-aae2-5b1c3b664a71
caps.latest.revision: 28
ms.author: matp
manager: brycho
ms.openlocfilehash: 896b026bc72022e66e548db95f78d785e14fdf23
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39674591"
---
# <a name="create-and-edit-relationships-between-entities"></a>Relaties tussen entiteiten maken en bewerken 

Entiteitsrelaties definiëren welke relaties records met elkaar hebben in de database. Op het eenvoudigste niveau betekent dit dat wanneer u een zoekveld toevoegt aan een entiteit, dit voor een nieuwe 1:N-relatie (een-op-veel) tussen de twee entiteiten zorgt en u het opzoekveld in een formulier kunt plaatsen. Met het zoekveld kunnen gebruikers meerdere *onderliggende* records van die entiteit koppelen aan één *bovenliggende* entiteitsrecord.  
  
Behalve eenvoudigweg definiëren welke relaties records met elkaar hebben, leveren 1:N-entiteitsrelaties ook gegevens om de volgende vragen te beantwoorden:  
  
- Wanneer ik een record verwijder, moet ik dan ook records verwijderen die zijn gerelateerd aan die record?  
- Wanneer ik een record aan een nieuwe eigenaar toewijs, moet ik dan ook alle records toewijzen die zijn gerelateerd aan die record?  
- Hoe kan ik het gegevensinvoerproces stroomlijnen wanneer ik een nieuwe gerelateerde record maak in de context van een bestaande record?  
- Hoe moeten gebruikers die een record bekijken de bijbehorende records kunnen bekijken?  
  
 Entiteiten kunnen ook deelnemen aan een N:N-relatie (veel-op-veel) waarbij een willekeurig aantal records voor twee entiteiten aan elkaar kan worden gekoppeld.  

<a name="BKMK_Connections"></a>

## <a name="decide-whether-to-use-entity-relationships-or-connections"></a>Beslissen of u entiteitsrelaties of -verbindingen wilt gebruiken 
 
Entiteitsrelaties zijn metagegevens die wijzigingen aanbrengen in de database. Dankzij deze relaties kunnen query’s zeer efficiënt gerelateerde gegevens ophalen. Gebruik entiteitsrelaties om formele relaties te definiëren die de entiteit definiëren of die de meeste records kunnen gebruiken. Een verkoopkans zonder potentiële klant zou bijvoorbeeld niet echt nut hebben. De entiteit Verkoopkans heeft ook een N:N-relatie met de entiteit Concurrent. Zo kunnen er meerdere concurrenten worden toegevoegd aan de verkoopkans. U wilt deze gegevens mogelijk vastleggen en een rapport maken dat de concurrenten weergeeft.  
  
Er zijn andere, minder formele soorten relaties tussen records die *verbindingen* worden genoemd. Het kan bijvoorbeeld handig zijn te weten dat twee contactpersonen getrouwd zijn of buiten het werk vrienden zijn, of dat een contactpersoon voorheen voor een account werkte. De meeste bedrijven genereren geen rapporten van dit soort informatie en vereisen niet dat deze wordt ingevoerd, dus het is waarschijnlijk niet de moeite waard entiteitsrelaties te maken. Meer informatie: [Verbindingsrollen configureren](configure-connection-roles.md)

  
<a name="BKMK_TypesOfRelationships"></a>
 
## <a name="types-of-entity-relationships"></a>Typen entiteitsrelaties

Wanneer u de oplossingsverkenner bekijkt, denkt u misschien dat er drie typen entiteitsrelaties zijn. Er zijn in werkelijkheid slechts twee typen entiteitsrelaties, zoals u in de volgende tabel kunt zien.  
  
|Relatietype|Beschrijving|  
|-----------------------|-----------------|  
|**1:N (een-op-veel)**|Een entiteitsrelatie waarbij één entiteitsrecord voor de **primaire entiteit** aan verschillende andere records voor de **gerelateerde entiteit** kan worden gekoppeld vanwege een opzoekveld in de gerelateerde entiteit.<br /><br /> Wanneer u een record voor de primaire entiteit bekijkt, kunt u een lijst met de gerelateerde entiteitsrecords weergeven die aan de primaire entiteit zijn gekoppeld.|  
|**N:N (veel-op-veel)**|Een entiteitsrelatie die afhankelijk is van een speciale **relatie-entiteit**, ook wel een Intersect-entiteit genoemd, zodat verschillende records van één entiteit aan verschillende records van een andere entiteit kunnen worden gekoppeld.<br /><br /> Wanneer u records van een van de entiteiten in een N:N-relatie bekijkt, kunt u een lijst weergeven met de records van de andere entiteit die aan deze records zijn gerelateerd.|  
  
Het relatietype **N:1 (veel-op-een)** bestaat in de gebruikersinterface omdat de ontwerper u een weergave toont die is gegroepeerd op entiteiten. *Tussen* de entiteiten bestaan in feite 1:N-relaties en in deze relaties wordt een entiteit een **primaire entiteit** of **gerelateerde entiteit** genoemd. De gerelateerde entiteit (of de *onderliggende* entiteit) heeft een zoekveld waarmee een verwijzing naar een record uit de primaire entiteit (de *bovenliggende* entiteit) kan worden opgeslagen. Een N:1-relatie is in feite een 1:N-relatie gezien vanuit de gerelateerde entiteit.  
 
## <a name="see-also"></a>Zie ook

[Overzicht van entiteiten en metagegevens](create-edit-metadata.md)<br />
[1:N (een-op-veel)- of N:1 (veel-op-een)-relaties maken of bewerken](create-edit-1n-relationships.md)<br />
[N:N (veel-op-veel)-relaties maken](create-edit-nn-relationships.md)

