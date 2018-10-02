---
title: Alternatieve sleutels voor verwijzingen naar records opgeven met Common Data Service voor Apps | MicrosoftDocs
description: Leer hoe u alternatieve sleutels voor verwijzingen naar records opgeeft in Common Data Service voor Apps
ms.custom: ''
ms.date: 06/06/2018
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
ms.assetid: 29e53691-0b18-4fde-a1d0-7490aa227898
caps.latest.revision: 10
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="define-alternate-keys-to-reference-records"></a>Alternatieve sleutels definiëren om te verwijzen naar records

Met *alternatieve sleutels* beschikt u over een efficiënte en nauwkeurige manier om gegevens te integreren met externe systemen. Het is essentieel in gevallen waarin een extern systeem de GUID (Globally Unique Identifier), waarmee records in Common Data Service voor Apps uniek worden geïdentificeerd, niet opslaat. 

Een systeem voor gegevensintegratie gebruikt alternatieve sleutels om records uniek te identificeren op basis van een of meer entiteitsveldwaarden die een unieke combinatie vormen. Elke alternatieve sleutel heeft een unieke naam. 

Wanneer u een accountrecord met een alternatieve sleutel wilt identificeren, kunt u bijvoorbeeld het accountnummer of het accountnummerveld gebruiken in combinatie met enkele andere velden met waarden die niet moeten worden gewijzigd.

> [!NOTE]
> Hoewel u alternatieve sleutels kunt definiëren met PowerApps, kunnen deze alleen programmatisch worden gebruikt in code. Zie de volgende onderwerpen voor meer informatie over het programmatisch gebruik van alternatieve sleutels:   
> - [Documentatie voor ontwikkelaars: Een alternatieve sleutel gebruiken voor het maken van een record](/dynamics365/customer-engagement/developer/use-alternate-key-create-record) 
> - [Documentatie voor ontwikkelaars: Een record met een alternatieve sleutel ophalen in de web-API](/dynamics365/customer-engagement/developer/webapi/retrieve-entity-using-web-api#retrieve-using-an-alternate-key)

Tot de voordelen van de functie voor alternatieve sleutels behoren:  
  
- Sneller opzoeken van de records.  
- Robuustere bulksgewijze gegevensbewerkingen.  
- Eenvoudigere programmering van gegevens geïmporteerd vanuit externe systemen zonder record-id's.  
  

## <a name="creating-an-alternate-key"></a>Een alternatieve sleutel maken

Er zijn twee ontwerpers die u kunt gebruiken om alternatieve sleutels te maken:

|Ontwerper| Beschrijving|
|--|--|
|[PowerApps-portal](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)|Biedt een eenvoudig gestroomlijnde ervaring, maar een aantal opties is niet beschikbaar.<br />Meer informatie: [Alternatieve sleutels definiëren via PowerApps-portal](define-alternate-keys-portal.md)|
|Oplossingenverkenner|Deze ontwerper is niet zo eenvoudig, maar biedt meer flexibiliteit en heeft minder algemene vereisten.<br />Meer informatie: [Alternatieve sleutels definiëren via oplossingenverkenner](define-alternate-keys-solution-explorer.md) |

> [!NOTE]
> U kunt ook als volgt een alternatieve sleutel in uw omgeving maken:
> - Importeer een oplossing die de definitie van de alternatieve sleutel bevat.
> - Een ontwikkelaar kan ook code schrijven om deze te maken. Meer informatie: [Documentatie voor ontwikkelaars: Alternatieve sleutels voor een entiteit definiëren](/dynamics365/customer-engagement/developer/define-alternate-keys-entity)

De informatie in dit onderwerp kan u helpen bepalen welke ontwerper u kunt gebruiken. 

U moet de [PowerApps-portal](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) gebruiken om alternatieve sleutels te maken, tenzij u moet voldoen aan de volgende vereisten:

- U wilt een alternatieve sleutel in een andere oplossing dan de standaardoplossing Common Data Service voor Apps maken
- U wilt eenvoudig de systeemtaak kunnen volgen waarmee de voortgang van het maken van de ondersteunende indexen wordt bijgehouden


## <a name="limits-in-creating-alternate-keys"></a>Beperkingen bij het maken van alternatieve sleutels

Er gelden enkele beperkingen bij het maken van alternatieve sleutels.

### <a name="fields-that-can-be-used-for-alternate-keys"></a>Velden die voor alternatieve sleutels kunnen worden gebruikt

Alleen deze typen velden kunnen worden gebruikt om alternatieve sleutels te maken:
 - Decimaal
 - Geheel getal
 - Eén tekstregel (tekenreeks)

### <a name="number-of-keys"></a>Aantal sleutels

U kunt maximaal 5 verschillende sleutels definiëren voor een entiteit.
 
### <a name="valid-key-size"></a>Geldige sleutelgrootte

Bij het maken van een sleutel valideert het systeem of de sleutel kan worden ondersteund door het platform, inclusief of de totale sleutelgrootte niet de beperkingen voor de SQL-index, zoals 900 bytes per sleutel en 16 kolommen per sleutel, overschrijdt. Als de sleutelgrootte niet aan de beperkingen voldoet, wordt een foutmelding weergegeven.

### <a name="unicode-characters-in-key-value"></a>Unicode-tekens in sleutelwaarde

Als de gegevens in een veld dat in een alternatieve sleutel wordt gebruikt een van de tekens `<`,`>`,`*`,`%`,`&`,`:`,`\\` bevat, werken de patch- of upsert-acties niet. 

Als u alleen uniciteit nodig hebt, werkt deze benadering wel, maar als u deze sleutels als onderdeel van een gegevensintegratie moet gebruiken, kunt u de sleutel het beste maken voor velden die geen gegevens met deze tekens bevatten.

## <a name="track-the-status-of-the-creation-of-the-alternate-key"></a>De status van het maken van de alternatieve sleutel bijhouden

Wanneer een alternatieve sleutel wordt gemaakt, wordt er een systeemtaak geïnitieerd om indexen voor de databasetabellen te maken en unieke beperkingen af te dwingen voor de velden die worden gebruikt door de alternatieve sleutel. De alternatieve sleutel wordt pas van kracht als deze indexen zijn gemaakt. Het maken van deze indexen kan enige tijd in beslag nemen, afhankelijk van de hoeveelheid gegevens in het systeem. 

De status van de systeemtaak definieert de status van de alternatieve sleutel. De alternatieve sleutel kan de volgende statussen hebben:
- **In behandeling**
- **Wordt uitgevoerd**
- **Actief**
- **Mislukt**

Als de systeemtaak is voltooid, wordt de status van de alternatieve sleutel **Actief** en is deze beschikbaar voor gebruik.

Als de systeemtaak mislukt, controleert u deze op eventuele fouten. Een systeemtaak heeft een naam met het patroon `Create index for {0} for entity {1}`, waarbij `0` de **weergavenaam** van de alternatieve sleutel is en `1` de naam van de entiteit.


> [!NOTE]
> Als u de status van de systeemtaak wilt controleren, moet u oplossingenverkenner gebruiken om de index te maken. Hierin is een koppeling naar de systeemtaak opgenomen zodat u deze kunt bekijken. Meer informatie: [(Optioneel) De systeemtaak voor het bijhouden van het maken van indexen weergeven](define-alternate-keys-solution-explorer.md#optional-view-the-system-job-tracking-creation-of-indexes)
  
  
### <a name="see-also"></a>Zie ook  

[Alternatieve sleutels definiëren via PowerApps-portal](define-alternate-keys-portal.md)<br />
[Alternatieve sleutels definiëren via oplossingenverkenner](define-alternate-keys-solution-explorer.md)<br />
[Documentatie voor ontwikkelaars: Alternatieve sleutels voor een entiteit definiëren](/dynamics365/customer-engagement/developer/define-alternate-keys-entity)<br />
[Documentatie voor ontwikkelaars: Een alternatieve sleutel gebruiken voor het maken van een record](/dynamics365/customer-engagement/developer/use-alternate-key-create-record)
