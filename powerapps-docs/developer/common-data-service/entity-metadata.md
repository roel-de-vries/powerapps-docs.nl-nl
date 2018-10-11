---
title: Entiteitsmetagegevens | Microsoft Docs
description: Meer informatie over het gebruik van entiteitsmetagegevens in Common Data Service for Apps.
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
ms.openlocfilehash: 60fafa90df656bb6d135a8cf7e2c2f3b4f8457da
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42840741"
---
# <a name="entity-metadata"></a>Entiteitsmetagegevens

Elke entiteit biedt de mogelijkheid voor het opslaan van gestructureerde gegevens. Voor ontwikkelaars komen de entiteiten overeen met de klassen die u wilt gebruiken tijdens het werken met gegevens in Common Data Service for Apps.

## <a name="entity-names"></a>Entiteitsnamen
Elke entiteit heeft een unieke naam die tijdens het maken van de entiteit wordt gedefinieerd. Deze naam wordt op verschillende manieren weergegeven:

|Naameigenschap |Beschrijving|
|---------|---------|
|`SchemaName`|Doorgaans de logische naam in PascalCase-indeling (bijvoorbeeld Account).|
|`CollectionSchemaName`|De meervoudsvorm van de schemanaam (bijvoorbeeld Accounts).|
|`LogicalName`|De naam van het schema in uitsluitend kleine letters (bijvoorbeeld account).|
|`LogicalCollectionName`|De naam van het schema in uitsluitend kleine letters (bijvoorbeeld accounts).|
|`EntitySetName`|Wordt gebruikt voor het identificeren van verzamelingen met de web-API. Standaard is dit dezelfde naam als de naam van de logische verzameling.<br />U kunt de naam van de entiteitsset wijzigen door de metagegevens via een programma bij te werken. U kunt de naam alleen wijzigen voordat de code van de web-API voor de entiteit wordt geschreven. Zie [Dynamics 365 Customer Engagement Developer Guide: Web API types and operations > Change the name of an entity set](/dynamics365/customer-engagement/developer/webapi/web-api-types-operations#change-the-name-of-an-entity-set) (Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: Web-API-typen en -bewerkingen > De naam van een entiteitsset wijzigen) voor meer informatie.|

> [!NOTE]
> Wanneer u een aangepaste entiteit maakt, wordt de naam die u kiest voorafgegaan door de waarde van het aanpassingsvoorvoegsel van de oplossingsuitgever die is gekoppeld aan de oplossing waarin de entiteit is gemaakt. In tegenstelling tot de naam van een entiteitssets kunt u de naam van een entiteit niet meer wijzigingen nadat deze is gemaakt. Als u consistente namen voor metagegevensitems in de oplossing wilt gebruiken, moet u de items maken in de context van de oplossing die u maakt, gekoppeld aan de oplossingsuitgever die het aanpassingsvoorvoegsel bevat dat u wilt gebruiken. Zie [Een oplossingsuitgever en oplossing maken](introduction-solutions.md#create-a-solution-publisher-and-solution) voor meer informatie.

Elke entiteit heeft ook drie eigenschappen waarmee gelokaliseerde waarden kunnen worden weergegeven:


|Naam  |Beschrijving  |
|---------|---------|
|`DisplayName`|Doorgaans dezelfde naam als de schemanaam, maar deze naam mag spaties bevatten. (bijvoorbeeld Account).|
|`DisplayCollectionName`|De meervoudsvorm van de weergavenaam (bijvoorbeeld Accounts).|
|`Description`|Een korte zin waarmee de entiteit wordt beschreven, bijvoorbeeld *Bedrijf dat een klant of potentiële klant vertegenwoordigt. Het bedrijf dat voor zakelijke transacties wordt gefactureerd.*|

Dit zijn de lokaliseerbare waarden die worden gebruikt om in een app naar de entiteiten te verwijzen. Deze waarden kunnen op elk gewenst moment worden gewijzigd. Zie [Dynamics 365 Customer Engagement aanpassen: Aangepaste entiteit en veldteksten vertalen in andere talen](/dynamics365/customer-engagement/customize/export-customized-entity-field-text-translation) als u gelokaliseerde waarden wilt toevoegen of bewerken.


## <a name="primary-key"></a>Primaire sleutel

De waarde van de eigenschap `PrimaryIdAttribute` is de logische naam van het kenmerk dat de primaire sleutel voor de entiteit is.

Standaard hebben alle entiteiten één kenmerk voor de GUID. Meestal is dit *&lt; logische naam van entiteit &gt;*+ `Id`.

## <a name="primary-name"></a>Primaire naam

De waarde van de eigenschap `PrimaryNameAttribute` is de logische naam van het kenmerk waarmee de tekenreekswaarde wordt opgeslagen waarmee de entiteitsrecord wordt aangegeven. Dit is de waarde die wordt weergegeven in een koppeling waarmee u de record in een gebruikersinterface kunt openen.

**Bijvoorbeeld**: de entiteit Contact gebruikt het kenmerk `fullname` als kenmerk voor de primaire naam.

> [!NOTE]
> Niet elke entiteit heeft een primaire naam. Sommige entiteiten zijn niet bedoeld om te worden weergegeven in een gebruikersinterface.

## <a name="entity-images"></a>Entiteitsafbeeldingen

De waarde van de eigenschap `PrimaryImageAttribute` is de logische naam van het kenmerk waarmee de afbeeldingsgegevens voor de entiteitsrecord worden opgeslagen. Elke entiteit kan slechts één afbeeldingskenmerk bevatten en de logische naam van dit kenmerk is altijd `entityimage`.

**Bijvoorbeeld**: in het kenmerk [EntityImage](reference/entities/contact.md#BKMK_EntityImage) van de [entiteit Contact](reference/entities/contact.md) kan een foto van de contactpersoon worden opgeslagen.

Om prestatieredenen worden entiteitsafbeeldingen niet opgenomen in ophaalbewerkingen, tenzij dit expliciet wordt aangevraagd.

Elke entiteit die ondersteuning biedt voor entiteitsafbeeldingen, bevat drie ondersteunende kenmerken.

|SchemaName|Type|Beschrijving|
|--|--|--|
|`EntityImage_Timestamp` |`BigIntType`|De waarde geeft aan wanneer de afbeelding voor het laatst is bijgewerkt en wordt gebruikt om ervoor te zorgen dat de meest recente versie van de afbeelding wordt gedownload en in het cachegeheugen van de client wordt opgeslagen.|
|`EntityImage_URL`|`StringType`|Een absolute URL om de entiteitsafbeelding op een client weer te geven.|
|`EntityImageId`|`UniqueIdentifierType`|De unieke id van de afbeelding.|

Meer informatie: 
- [Dynamics 365 Customer Engagement Developer Guide: Image attributes](/dynamics365/customer-engagement/developer/image-attributes) (Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: Afbeeldingskenmerken)
- [Dynamics 365 Customer Engagement Developer Guide Sample: Set and retrieve entity images](/dynamics365/customer-engagement/developer/sample-set-retrieve-entity-images) (Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: Entiteitsafbeeldingen instellen en ophalen - voorbeeld)

> [!NOTE]
> Dit is niet het pictogram dat in modelgestuurde apps voor een entiteit wordt weergegeven. Het kenmerk `IconVectorName` bevat de naam van de SVG-webresource waarmee de afbeelding wordt ingesteld.

## <a name="types-of-entities"></a>Typen entiteiten

De mogelijkheden en het gedrag van entiteiten zijn afhankelijk van verschillende entiteitseigenschappen. De meeste van deze eigenschappen zijn relatief eenvoudig en hebben beschrijvende namen. Vier eigenschappen waarvoor aanvullende uitleg nodig is, zijn: *Eigendom*, *Activiteitsentiteiten*, de *entiteit Activityparty* en *Onderliggende entiteiten*.

### <a name="entity-ownership"></a>Eigendom van entiteit

Entiteiten kunnen worden ingedeeld op basis van het eigendom van de gegevens in de entiteit. Dit is een belangrijk concept dat betrekking heeft op de manier waarop beveiliging wordt toegepast op entiteiten. Deze informatie is opgeslagen in de eigenschap `OwnershipType`. In de volgende tabel vindt u een beschrijving van de verschillende eigendomstypen.

|Eigendomstype  |Beschrijving  |
|---------|---------|
|Business|De gegevens horen bij het bedrijfsonderdeel. Toegang tot de gegevens kan worden beheerd op het niveau van het bedrijfsonderdeel.|
|Geen|De gegevens zijn geen eigendom van een andere entiteit.|
|Organisatie|De gegevens horen bij de organisatie. Toegang tot de gegevens wordt beheerd op het niveau van de organisatie.|
|Gebruiker of team|De gegevens horen bij een gebruiker of een team. Acties die kunnen worden uitgevoerd voor deze records, kunnen worden beheerd op het niveau van een gebruiker.|

Wanneer u nieuwe entiteiten maakt, zijn alleen de eigendomsopties **Organisatie** of **Gebruiker of team** beschikbaar. Als u eenmaal een keuze voor deze optie hebt gemaakt, kunt u deze niet meer wijzigen. Kies **Gebruiker of team** voor de meest gedetailleerde controle over wie acties voor de records kan bekijken of uitvoeren. Kies **Organisatie** wanneer dit niveau van controle niet nodig is. 

### <a name="activity-entities"></a>Activiteitsentiteiten

Een activiteit is een taak die door een gebruiker is of wordt uitgevoerd. Een activiteit is een actie waarvoor een item in een kalender kan worden gemaakt. 

Activiteiten zijn anders gemodelleerd dan andere soorten entiteiten waarmee bedrijfsgegevens worden opgeslagen. Gegevens over activiteiten worden vaak samen in een lijst weergegeven, maar voor elke soort activiteit zijn unieke eigenschappen nodig. In plaats van één activiteitsentiteit met alle mogelijke eigenschappen zijn er afzonderlijke soorten activiteitsentiteiten aanwezig en voor elk van deze entiteiten worden de eigenschappen overgenomen van een basis-[ActivityPointer-entiteit](reference/entities/activitypointer.md). Voor deze entiteiten is de eigenschap `IsActivity` ingesteld op 'waar'.


|Entiteit |Beschrijving  |
|---------|---------|
|[Appointment](reference/entities/appointment.md)|Verplichting waarmee een tijdsinterval met een begin- en eindtijd en een duur wordt aangegeven.|
|[E-mail](reference/entities/email.md)|Activiteit die wordt geleverd met behulp van e-mailprotocollen.|
|[Fax](reference/entities/fax.md)|Activiteit waarmee het resultaat van gesprekken en het aantal faxpagina's wordt bijgehouden. Optioneel kan een elektronisch exemplaar van het document worden opgeslagen.|
|[Letter](reference/entities/letter.md)|Activiteit waarmee de bezorging van een brief wordt bijgehouden. De activiteit kan het elektronische exemplaar van de brief bevatten.|
|[PhoneCall](reference/entities/phonecall.md)|Activiteit waarmee een telefoongesprek wordt bijgehouden.|
|[RecurringAppointmentMaster](reference/entities/recurringappointmentmaster.md)|De hoofdafspraak van een reeks terugkerende afspraken.|
|[SocialActivity](reference/entities/socialactivity.md)|Alleen voor intern gebruik.|
|[Task](reference/entities/task.md)|Algemene activiteit waarmee het werk wordt aangegeven dat moet worden uitgevoerd.|

Wanneer iemand een van deze soorten activiteitsentiteitsrecords maakt, wordt een bijbehorende `ActivityPointer`-entiteitsrecord met dezelfde kenmerkwaarde voor de unieke id voor `ActivityId` gemaakt. U kunt geen exemplaren van de entiteit `ActivityPointer` maken, bijwerken of verwijderen, maar u kunt ze wel ophalen. Zo kunt u alle soorten activiteiten samen in een lijst weergeven.

U kunt aangepaste activiteitsentiteiten met hetzelfde gedrag maken.
<!-- TODO: Add link to topic about creating an activity entity -->

### <a name="activityparty-entity"></a>ActivityParty-entiteit

Deze entiteit wordt gebruikt om structuur toe te voegen aan de kenmerken van de activiteitsentiteit `PartyListType` die verwijzingen naar andere entiteiten bevatten. U kunt deze entiteit gebruiken bij het instellen van de kenmerken van activiteitsentiteiten, zoals `Email.to` of `PhoneCall.from`. Binnen de [ActivityParty-entiteit](reference/entities/activityparty.md) stelt u het kenmerk [ParticipationTypeMask](reference/entities/activityparty.md#BKMK_ParticipationTypeMask) in om de rol te definiëren die de verwijzing speelt. Voorbeelden van rollen zijn `Sender`, `ToRecipient` en `Organizer`.

U kunt een query uitvoeren op de entiteit `ActivityParty`, maar u kunt geen betrokkene bij een activiteit maken, ophalen, bijwerken of verwijderen buiten de activiteit waaraan de entiteit is gerelateerd.
Meer informatie: 
- [Dynamics 365 Customer Engagement Developer Guide: ActivityParty entity](/dynamics365/customer-engagement/developer/activityparty-entity) (Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: ActivityParty-entiteit).


### <a name="child-entities"></a>Onderliggende entiteiten

Voor entiteiten waarvoor de eigenschap `IsChildEntity` is ingesteld op 'waar', worden nooit bevoegdheden gedefinieerd. Daarnaast zijn deze entiteiten nooit het eigendom van een gebruiker of team. Welke bewerkingen voor een onderliggende entiteit kunnen worden uitgevoerd, is afhankelijk van de entiteit waaraan de onderliggende entiteit via een veel-op-een-relatie is gekoppeld. Gebruikers kunnen alleen bewerkingen voor onderliggende entiteiten uitvoeren als ze dezelfde bewerking voor de gerelateerde entiteit kunnen uitvoeren. Onderliggende entiteiten worden automatisch verwijderd wanneer de entiteitsrecord waarvan ze afhankelijk zijn, wordt verwijderd.

`PostComment`, `PostLike` en `PostRole` zijn bijvoorbeeld onderliggende elementen van de entiteit `Post`.

## <a name="entity-keys"></a>Entiteitssleutels

De definitie van een alternatieve sleutel is een beschrijving van een of meer kenmerken waarmee een entiteitsexemplaar uniek wordt aangeduid. Alternatieve sleutels worden doorgaans alleen toegepast voor de integratie met externe systemen. U kunt alternatieve sleutels definiëren als unieke identificatie van een record. Dit is nuttig als u gegevens integreert met een systeem dat geen ondersteuning biedt voor unieke GUID-sleutels. U kunt één veldwaarde of een combinatie van veldwaarden definiëren om een entiteit uniek aan te duiden. Als u een alternatieve sleutel toevoegt, wordt een uniekheidsbeperking op deze kenmerken afgedwongen. Het is dan niet mogelijk een andere entiteitsrecord met dezelfde waarden te maken of bij te werken.

Meer informatie: 
 - [Aanpassingshandleiding Dynamics 365 Customer Engagement: Alternatieve sleutels definiëren om te verwijzen naar Dynamics 365-records](/dynamics365/customer-engagement/customize/define-alternate-keys-reference-records)
 - [Dynamics 365 Customer Engagement Developer Guide: Define alternate keys for an entity and Developer Guide: Synchronize Dynamics 365 data with external systems](/dynamics365/customer-engagement/developer/synchronize-dynamics-365-data-with-external-systems) (Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: Alternatieve sleutels definiëren voor een entiteit en Ontwikkelaarshandleiding: Dynamics 365-gegevens synchroniseren met externe systemen)

## <a name="entity-states"></a>Entiteitsstatuswaarden

De meeste entiteiten hebben twee eigenschappen waarmee de status van een record kan worden bijgehouden. Dit zijn de eigenschappen `StateCode` (**Status** in modelgestuurde apps) en `StatusCode` (**Statusreden** in modelgestuurde apps). 

Beide kenmerken bevatten een set met opties op basis waarvan de geldige waarden worden weergegeven. De waarden van de kenmerken `StateCode` en `StatusCode` zijn gekoppeld, waardoor slechts bepaalde opties voor `StatusCode` geldig zijn voor een bepaalde `StateCode`.

Dit gedrag kan variëren per entiteit, maar het algemene patroon voor diverse entiteiten en de standaardwaarde voor aangepaste entiteiten is als volgt:

|Opties voor StateCode  |Opties voor StatusCode  |
|---------|---------|
|0: Actief|1: Actief|
|1: Inactief|2: Inactief|

Sommige entiteiten beschikken over andere sets met opties. 

**Bijvoorbeeld**: de opties `StateCode` en `StatusCode` voor de entiteit `PhoneCall`.


|`StateCode`|`StatusCode`|
|---------|---------|
|0: Open|1: Open|
|1: Voltooid|2: Gemaakt <br />4: Ontvangen|
|2: Geannuleerd|3: Geannuleerd|

De set met geldige staatcodes voor een entiteit kan niet worden aangepast, maar de statuscodes kunnen wel worden aangepast. U kunt aanvullende `StatusCode`-opties toevoegen voor een bijbehorende `StateCode`.

Voor aangepaste entiteiten kunt u aanvullende criteria definiëren voor een geldige overgang tussen statuswaarden. Meer informatie: 
- [Dynamics 365 Customer Engagement Developer Guide: Customize entity attribute metadata](/dynamics365/customer-engagement/developer/customize-entity-attribute-metadata) (Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: Metagegevens van entiteitskenmerken aanpassen)
- [Dynamics 365 Customer Engagement Developer Guide: Define custom state model transitions](/dynamics365/customer-engagement/developer/define-custom-state-model-transitions) (Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: modelovergang voor aangepaste staatwaarden definiëren)

### <a name="see-also"></a>Zie ook

[Common Data Service for Apps-entiteiten](entities.md)
