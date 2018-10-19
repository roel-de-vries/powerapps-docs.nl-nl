---
title: Overzicht van entiteitsrelaties voor Common Data Service voor Apps | MicrosoftDocs
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="entity-relationships-overview"></a>Overzicht van entiteitsrelaties

De entiteitsrelaties bepalen hoe records in de database aan elkaar kunnen worden gerelateerd. Op het meest eenvoudige niveau wordt door het toevoegen van een opzoekveld aan een entiteit een nieuwe 1:N (een-op-veel)-relatie tussen de twee entiteiten gemaakt en kunt u dat opzoekveld in een formulier plaatsen. Met het opzoekveld kunnen gebruikers meerdere *onderliggende* records van die entiteit aan één *bovenliggende* entiteitsrecord koppelen.  
  
De gebruiker kan niet alleen eenvoudig vaststellen hoe records aan andere records kunnen worden gerelateerd, maar met 1:N-entiteitsrelaties ook gegevens bieden om de volgende vragen te beantwoorden:  
  
- Als ik een record verwijder, moeten er dan ook records die zijn gerelateerd aan die record worden verwijderd?  
- Wanneer ik een record heb toegewezen, moet ik dan ook alle records die zijn gerelateerd aan die record aan de nieuwe eigenaar toewijzen?  
- Hoe kan ik het proces van de gegevensinvoer soepeler en sneller laten verlopen wanneer ik een nieuwe verwante record in de context van een bestaande record maak?  
- Hoe kan de persoon die een record bekijkt de verwante records bekijken?  
  
 De entiteiten kunnen ook deel uitmaken van N:N (veel-op-veel)-relaties waarbij een willekeurig aantal records voor twee entiteiten aan elkaar kunnen worden gekoppeld.  

<a name="BKMK_Connections"></a>

## <a name="decide-whether-to-use-entity-relationships-or-connections"></a>Bepalen of u entiteitsrelaties of verbindingen moet gebruiken 
 
Entiteitsrelaties zijn de metagegevens die wijzigingen aan een database aanbrengen. Dankzij deze relaties kunt u via zoekopdrachten heel snel verwante gegevens opzoeken. Gebruik entiteitsrelaties om formele relaties aan te duiden die de entiteit definiëren of waar de meeste records gebruik van kunnen maken. Zo is een verkoopkans zonder potentiële klant bijvoorbeeld niet erg nuttig. De entiteit Verkoopkans staat ook in N:N-relatie met de entiteit Concurrent. Hierdoor kunnen meerdere concurrenten aan de verkoopkans worden toegevoegd. U wilt deze gegevens misschien vastleggen een een rapport maken waarin de concurrenten worden weergegeven.  
  
Er zijn andere minder formele soorten relaties tussen records die *verbindingen* worden genoemd. Het kan bijvoorbeeld handig zijn om te weten of twee contactpersonen getrouwd zijn, of dat ze mogelijk buiten het werk om bevriend zijn, of dat de contactpersoon wordt gebruikt om met een andere account te werken. De meeste bedrijven zullen geen rapporten met dergelijke informatie genereren of vereisen dat die wordt ingevoerd, dus loont het waarschijnlijk niet de moeite entiteitsrelaties te creëren. Meer informatie: [Verbindingsrollen configureren](configure-connection-roles.md)

  
<a name="BKMK_TypesOfRelationships"></a>
 
## <a name="types-of-entity-relationships"></a>Types entiteitsrelaties

Wanneer u de oplossingsverkenner bekijkt, denkt u misschien dat er drie verschillende types entiteitsrelaties bestaan. Het zijn er in feite slechts twee, zoals aangegeven in de volgende tabel.  
  
|Relatietype|Beschrijving|  
|-----------------------|-----------------|  
|**1:N (Een-op-veel)**|Een entiteitsrelatie waarbij de ene entiteit voor de **Primaire entiteit** aan vele andere **Gerelateerde entiteit**-records kan worden gekoppeld dankzij een opzoekveld op de gerelateerde entiteit.<br /><br /> Wanneer u een primair entiteitrecord bekijkt, kunt u een lijst met verwante entiteitsrecords zien die erbij horen.|  
|**N:N (Veel-op-veel)**|Een entiteitsrelatie die afhankelijk van een speciale **Relatie-entiteit** is, ook wel een doorsnedenentiteit genoemd, zodat veel records van de ene entiteit aan veel records van een andere entiteit kunnen worden gerelateerd.<br /><br /> Wanneer u records op van een van deze entiteiten in een N:N-relatie bekijkt, kunt u een lijst zien van records van de andere entiteit die daaraan zijn gerelateerd.|  
  
Het relatietype **N:1 (veel-op-één)** bestaat in de gebruikersinterface aangezien de oplossingenverkenner u een weergave toont die is gegroepeerd op entiteiten. 1:N-relaties bestaan werkelijk *tussen* entiteiten en verwijzen naar elke entiteit als een **Primaire entiteit** of **Gerelateerde entiteit**. De gerelateerde entiteit, ook wel de *onderliggende* entiteit genoemd, heeft een opzoekveld waarin een verwijzing naar een record van de primaire entiteit, ook wel de *bovenliggende* entiteit genoemd, kan worden opgeslagen. Een N:1-relatie is simpelweg een 1:N-relatie gezien vanuit het perspectief van de gerelateerde entiteit.  
 
## <a name="see-also"></a>Zie ook

[Overzicht entiteiten en metagegevens](create-edit-metadata.md)<br />
[1:N- (één-op-veel) of N:1-relaties (veel-op-één) maken en bewerken](create-edit-1n-relationships.md)<br />
[Overzicht van het maken van veel-op-veel-entiteitsrelaties (N:N)](create-edit-nn-relationships.md)

