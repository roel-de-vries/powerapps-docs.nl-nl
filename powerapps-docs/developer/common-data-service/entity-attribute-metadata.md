---
title: Kenmerkmetagegevens | Microsoft Docs
description: Informatie over het gebruik van kenmerkmetagegevens in Common Data Service for Apps.
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
ms.openlocfilehash: efe04d9bd9c761f432d16d4c9304c52e55503aeb
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2018
---
# <a name="attribute-metadata"></a>Kenmerkmetagegevens

Entiteiten bevatten een verzameling met kenmerken waarmee wordt aangegeven welke gegevens in een record kunnen worden opgenomen. Ontwikkelaars moeten de verschillende typen kenmerken begrijpen en weten hoe ze ermee kunnen werken. 

Zie [Dynamics 365 Customer Engagement Developer Guide: Introduction to entity attributes](/dynamics365/customer-engagement/developer/introduction-entity-attributes) (Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: Inleiding in entiteitskenmerken) voor meer informatie.

## <a name="attribute-names"></a>Kenmerknamen

Net als een entiteit heeft elk kenmerk een unieke naam die tijdens het maken van het kenmerk wordt gedefinieerd. Deze naam wordt op verschillende manieren weergegeven:


|Naam |Beschrijving  |
|---------|---------|
|`SchemaName`|Doorgaans de logische naam in PascalCase-indeling (bijvoorbeeld `AccountNumber`).|
|`LogicalName`|De naam in uitsluitend kleine letters (bijvoorbeeld `accountnumber`).|

Wanneer u een aangepast kenmerk maakt, wordt de naam die u kiest voorafgegaan door de waarde van het aanpassingsvoorvoegsel van de oplossingsuitgever die is gekoppeld aan de oplossing waarin het kenmerk is gemaakt.

U kunt de naam van een kenmerk niet wijzigen nadat dit is gemaakt.

Elk kenmerk heeft ook twee eigenschappen waarmee gelokaliseerde waarden kunnen worden weergegeven. Dit zijn de waarden die worden gebruikt om in een app naar de kenmerken te verwijzen.

|Naam |Beschrijving  |
|---------|---------|
|`DisplayName`|Doorgaans dezelfde naam als de schemanaam, maar deze naam mag spaties bevatten. (bijvoorbeeld **Nummer account**).|
|`Description`|Een korte zin waarmee het kenmerk wordt beschreven of meer informatie voor de gebruiker wordt geboden (bijvoorbeeld *Typ een id-nummer of code voor het account om het account snel te zoeken in systeemweergaven*).<br />In modelgestuurde apps wordt deze informatie weergegeven wanneer gebruikers met de muisaanwijzer over het veld voor dit kenmerk in een formulier bewegen.|


Dit zijn de lokaliseerbare waarden die worden gebruikt om in een app naar de kenmerken te verwijzen. Deze waarden kunnen op elk gewenst moment worden gewijzigd. Zie [Aanpassingshandleiding voor Dynamics 365 Customer Engagement: Aangepaste entiteit en veldteksten vertalen in andere talen](/dynamics365/customer-engagement/customize/export-customized-entity-field-text-translation) als u gelokaliseerde waarden wilt toevoegen of bewerken.

## <a name="attribute-types"></a>Kenmerktypen

Met de eigenschap `AttributeTypeName` wordt het kenmerktype beschreven. Deze eigenschap bevat een waarde van het type `AttributeTypeDisplayName` waarmee een label wordt geboden voor de verschillende kenmerktypen. 

> [!NOTE]
> Verwar deze eigenschap niet met de eigenschap `AttributeType`. De waarden in deze oudere eigenschap lijken het meest op `AttributeTypeName`, met uitzondering dat `ImageType`-kenmerken worden weergegeven als `Virtual`. U moet een verwijzing opnemen naar de eigenschap `AttributeTypeName` in plaats van naar de eigenschap `AttributeType`.

Voor de onderstaande tabel geldt het volgende:

- De typen zijn gegroepeerd op categorie voor vergelijkingsdoeleinden.
- Voor elke `AttributeTypeDisplayName`-waarde wordt de bijbehorende afgeleide .NET-assemblyklasse [AttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.attributemetadata) opgenomen, indien beschikbaar. Er is geen 1:1-relatie tussen deze typen en het `AttributeTypeDisplayName`-label.
- Voor kenmerktypen die als aangepaste kenmerken kunnen worden gemaakt, wordt het bijbehorende label in de gebruikersinterface weergegeven.


|Categorie|AttributeTypeDisplayName/<br />AttributeMetadata-type|Maken mogelijk/<br />Label|Beschrijving  |
|---------|---------|---------|---------|
|Categorisering|`BooleanType`<br />[BooleanAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.booleanattributemetadata)|Ja<br />**Twee opties**|Bevat de waarde van de geselecteerde optie van twee opties waarmee meestal de waarde 'waar' of 'onwaar' wordt aangegeven.<br />Zie [Optiesets](#option-sets) voor meer informatie.|
|Categorisering|`EntityNameType`<br />[EntityNameAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.entitynameattributemetadata)|Nee|Bevat een optiewaarde die overeenkomt met een entiteit in het systeem. Alleen voor intern gebruik.|
|Categorisering|`MultiSelectPicklistType`<br />[MultiSelectPicklistAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.multiselectpicklistattributemetadata)|Ja<br />**MultiSelect-optieset**|Bevat waarden van meerdere geselecteerde opties wanneer meerdere opties kunnen worden geselecteerd.<br />Meer informatie: <br />[Optiesets](#option-sets)<br />[Dynamics 365 Customer Engagement Developer Guide: Multi-Select Picklist attributes](/dynamics365/customer-engagement/developer/multi-select-picklist) (Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: Kenmerken van multiselect-keuzelijsten)|
|Categorisering|`PicklistType`<br />[PicklistAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.picklistattributemetadata)|Ja<br />**Optieset**|Bevat de waarde van de geselecteerde optie wanneer één optie kan worden geselecteerd.<br />Zie [Optiesets](#option-sets) voor meer informatie.|
|Categorisering|`StateType`<br />[StateAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.stateattributemetadata)|Nee|Bevat de optiewaarde waarmee de status van een entiteitsrecord wordt beschreven.<br />Zie [Optiesets](#option-sets) voor meer informatie.|
|Categorisering|`StatusType`<br />[StatusAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.statusattributemetadata)|Nee|Bevat de optiewaarde waarmee de reden voor de status van een entiteitsrecord wordt beschreven.<br />Zie [Optiesets](#option-sets) voor meer informatie.|
|Verzameling|`CalendarRulesType`|Nee|Bevat een verzameling met `CalendarRules`-entiteitsrecords.<br />Er zijn geen kenmerken die gebruikmaken van dit type. Bij het genereren van een proxy worden met het hulpprogramma voor het genereren van code twee gesimuleerde kenmerken gemaakt die niet aanwezig zijn in de metagegevens. Deze kenmerken vertegenwoordigen een weergave van de kalenderregelrecords die via een een-op-veel-relatie aan de entiteitsrecord zijn gekoppeld.|
|Verzameling|`PartyListType`|Nee|Bevat een verzameling met `ActivityParty`-entiteitsrecords.<br />Zie [ActivityParty-entiteit](#activityparty-entity) voor meer informatie.|
|Datum en tijd|`DateTimeType`<br />[DateTimeAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.datetimeattributemetadata)|Ja<br />**Datum en tijd**|Bevat een waarde voor de datum en tijd.<br />Alle datum- en tijdkenmerken bieden ondersteuning voor waarden vanaf 1-1-1753 00:00 uur.|
|Afbeelding|`ImageType`<br />[ImageAttributeMetadata]()|Ja<br />**Afbeelding**|Bevat gegevens voor ondersteuning bij het ophalen van afbeeldingsgegevens voor een entiteitsrecord.<br />Zie [Entiteitsafbeeldingen](entity-metadata.md#entity-images) voor meer informatie.|
|Beheerde eigenschap|`ManagedPropertyType`<br />[ManagedPropertyAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.imageattributemetadata)|Nee|Bevat gegevens waarmee wordt beschreven of het in de entiteitsrecord opgeslagen oplossingsonderdeel kan worden aangepast wanneer dit in een beheerde oplossing wordt opgenomen.<br />Zie [Beheerde eigenschappen](introduction-solutions.md#managed-properties) voor meer informatie.|
|Hoeveelheid|`BigIntType`<br />[BigIntAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.bigintattributemetadata)|Nee|Bevat een `BigInt`-waarde. Alleen voor intern gebruik.|
|Hoeveelheid|`DecimalType`<br />[DecimalAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.decimalattributemetadata)|Ja<br />**Decimaal getal**|Bevat een `Decimal`-waarde. Met de eigenschap `Precision` wordt het precisieniveau ingesteld.|
|Hoeveelheid|`DoubleType`<br />[DoubleAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.doubleattributemetadata)|Ja<br />**Drijvendekommagetal**|Bevat een `Double`-waarde. Met de eigenschap `Precision` wordt het precisieniveau ingesteld.|
|Hoeveelheid|`IntegerType`<br />[IntegerAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.integerattributemetadata)|Ja<br />**Geheel getal**|Bevat een `Int`-waarde.|
|Hoeveelheid|`MoneyType`<br />[MoneyAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.moneyattributemetadata)|Ja<br />**Valuta**|Bevat een `Decimal`-waarde. Met de eigenschap `PrecisionSource` wordt bepaald waar het precisieniveau wordt ingesteld.<br />0: de eigenschap `Precision`<br />1: het kenmerk `Organization.PricingDecimalPrecision`<br />2: het kenmerk `TransactionCurrency.CurrencyPrecision` in de entiteitsrecord|
|Referentie|`CustomerType`<br />[LookupAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.lookupattributemetadata)|Ja<br />**Klant**|Bevat een verwijzing naar de record van een account- of contactentiteit.|
|Referentie|`LookupType`<br />[LookupAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.lookupattributemetadata)|Ja<br />**Lookup**|Bevat een verwijzing naar een entiteitsrecord. De logische namen van de geldige records worden meestal opgeslagen in de eigenschap `Targets` van het kenmerk.|
|Referentie|`OwnerType`<br />[LookupAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.lookupattributemetadata)|Nee|Bevat een verwijzing naar de record van een gebruikers- en teamentiteit.|
|Tekenreeks|`MemoType`<br />[MemoAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.memoattributemetadata)|Ja<br />**Meerdere tekstregels**|Bevat een tekenreekswaarde die is bedoeld om te worden weergegeven in een tekstvak met meerdere regels.|
|Tekenreeks|`StringType`<br />[StringAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.stringattributemetadata)|Ja<br />**Eén tekstregel**|Bevat een tekenreekswaarde die is bedoeld om te worden weergegeven in een tekstvak met één regel.|
|Unieke id|`UniqueidentifierType`<br />[UniqueIdentifierAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.uniqueidentifierattributemetadata)|Nee|Bevat een unieke id-waarde (GUID).|
|Virtueel|`VirtualType`|Nee|Deze kenmerken kunnen niet worden gebruikt in de code en kunnen meestal worden genegeerd.|


## <a name="supported-operations-and-form-usage-for-attributes"></a>Ondersteunde bewerkingen en formuliergebruik voor kenmerken

Elk kenmerk bevat booleaanse eigenschappen waarmee wordt beschreven aan welke soorten bewerkingen het kenmerk kan deelnemen en hoe een kenmerk in een formulier kan worden gebruikt.

|Eigenschap|Beschrijving|
|--|--|
|`IsRequiredForForm`|Hiermee wordt aangegeven of het kenmerk als een veld in een formulier moet worden opgenomen.|
|`IsValidForCreate`|Hiermee wordt aangegeven of de kenmerkwaarde kan worden ingesteld in een bewerking voor maken.|
|`IsValidForForm`|Hiermee wordt aangegeven of het kenmerk als een veld in een formulier kan worden opgenomen.|
|`IsValidForRead`|Hiermee wordt aangegeven of de kenmerkwaarde kan worden opgehaald.|
|`IsValidForUpdate`|Hiermee wordt aangegeven of de kenmerkwaarde kan worden ingesteld in een bewerking voor bijwerken.|

Als u een waarde wilt instellen in een bewerking voor maken of bijwerken voor een kenmerk dat niet geldig is voor de desbetreffende bewerking, wordt de waarde genegeerd.
Als u een kenmerk wilt ophalen dat niet kan worden gelezen, wordt een null-waarde geretourneerd.


## <a name="attribute-requirement-level"></a>Vereistenniveau voor kenmerk

De eigenschap `RequiredLevel` is een beheerde booleaanse eigenschap waarmee wordt beschreven of een kenmerkwaarde is vereist.

Voor deze eigenschap kunnen de volgende waarden worden ingesteld:

|Naam|Waarde|UI-label|Beschrijving|
|--|--|--|--|
|`None`|0|**Optioneel**|Er zijn geen vereisten opgegeven.|
|`SystemRequired`|1|**Voor het systeem vereist**|Een waarde is vereist voor het kenmerk.|
|`ApplicationRequired`|2|**Onderneming vereist**|Het bedrijf heeft aangegeven dat een waarde is vereist voor het kenmerk.|
|`Recommended`|3|**Onderneming aangeraden**|Een waarde voor het kenmerk wordt aangeraden.|

In Common Data Service wordt de optie `SystemRequired` alleen afgedwongen voor kenmerken die door het systeem zijn gemaakt. Aangepaste kenmerken kunnen niet worden ingesteld voor het gebruik van de optie `SystemRequired`. 

In modelgestuurde apps wordt de optie `ApplicationRequired` afgedwongen en een andere weergave voor de optie `Recommended` gebruikt. Makers van aangepaste clients kunnen deze informatie gebruiken om soortgelijke validatie- of weergaveopties te vereisen.

Omdat dit een beheerde eigenschap is, kunt u als uitgever van een beheerde oplossing bepalen of gebruikers van uw oplossing de instellingen voor de kenmerken in uw oplossing kunnen wijzigen.

Zie [Beheerde eigenschappen](introduction-solutions.md#managed-properties) voor meer informatie.


## <a name="rollup-and-calculated-attributes"></a>Samengetelde en berekende kenmerken

Door gebruik te maken van berekende en samengetelde kenmerken hoeven gebruikers niet meer handmatig berekeningen uit te voeren en kunnen zij zich volledig op hun werk richten. Systeembeheerders kunnen aangeven dat een veld de waarde van een van de veelgebruikte berekeningen moet bevatten zonder dat hiervoor de hulp van een ontwikkelaar nodig is. Ontwikkelaars kunnen in plaats van eigen code ook gebruikmaken van de platformmogelijkheden om deze berekeningen uit te voeren.

Meer informatie: 
- [Aanpassingshandleiding voor Dynamics 365 Customer Engagement: Samengetelde velden definiëren voor het samenvoegen van waarden](/dynamics365/customer-engagement/customize/define-rollup-fields)
- [Aanpassingshandleiding voor Dynamics 365 Customer Engagement: Berekende en samengetelde velden](/dynamics365/customer-engagement/customize/define-calculated-fields)
- [Dynamics 365 Customer Engagement Developer Guide: Calculated and rollup attributes](/dynamics365/customer-engagement/developer/calculated-rollup-attributes) (Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: Berekende en samengetelde velden)

## <a name="attribute-format"></a>Indeling van het kenmerk

Op basis van de indelingswaarden voor kenmerken wordt bepaald hoe kenmerken in modelgestuurde apps worden weergegeven. Ontwikkelaars van aangepaste apps kunnen deze informatie gebruiken om vergelijkbare ervaringen te maken.

### <a name="integer-formats"></a>Notatie met gehele getallen

Gebruik de eigenschap `Format` met kenmerken voor gehele getallen om alternatieve gebruikerservaringen voor dit type weer te geven.

|Optie|Beschrijving|
|--|--|
|`None`|Hiermee wordt een tekstvak weergegeven waarin een numerieke waarde kan worden bewerkt.|
|`Duration`|Hiermee wordt een vervolgkeuzelijst met tijdsintervallen weergegeven. Een gebruiker kan een waarde in de lijst selecteren of een geheel getal typen om het aantal minuten aan te geven.|
|`TimeZone`|Hiermee wordt een vervolgkeuzelijst met tijdzones weergegeven.|
|`Language`|Hiermee wordt een vervolgkeuzelijst weergegeven met de talen die voor de organisatie zijn ingeschakeld. Als er geen andere talen zijn ingeschakeld, is de standaardtaal de enige optie. De opgeslagen waarde is de LCID-waarde voor de taal.|

### <a name="string-formats"></a>Tekenreeksindelingen

Gebruik de eigenschap `FormatName` met tekenreekskenmerken om waarden in te stellen uit de [StringFormatName-klasse](/dotnet/api/microsoft.xrm.sdk.metadata.stringformatname) om te bepalen hoe het tekenreekskenmerk wordt ingedeeld.

|Naam|Beschrijving|
|--|--|
|`Email`|In het formulierveld wordt de tekstwaarde gevalideerd als een e-mailadres, waarna de koppeling mailto in het veld wordt gemaakt.|
|`PhoneNumber`|Het formulierveld bevat een koppeling voor het starten van een telefoongesprek via Skype.|
|`PhoneticGuide`|Alleen voor intern gebruik.|
|`Text`|In het formulier wordt een tekstvak weergegeven.|
|`TextArea`|In het formulier wordt een tekstgebied weergegeven.|
|`TickerSymbol`|In het formulier wordt een koppeling weergegeven waarmee de notering voor het beurssymbool wordt geopend.|
|`URL`|In het formulier wordt een koppeling weergegeven waarmee de URL wordt geopend.|
|`VersionNumber`|Alleen voor intern gebruik.|

### <a name="date-and-time-formats"></a>Datum- en tijdnotatie

Met de eigenschap `DateTimeBehavior` wordt het gedrag voor de datum- en tijdkenmerken bepaald.
Er zijn drie opties:

|Optie|Korte beschrijving|
|--|--|
|`UserLocal`|Hiermee worden de datum- en tijdwaarden als UTC-waarde in het systeem opgeslagen.|
|`DateOnly`|Hiermee wordt de werkelijke datum met de tijdwaarde in het systeem opgeslagen als 12:00 (00: 00:00).|
|`TimeZoneIndependent`|Hiermee worden de werkelijke datum- en tijdwaarden in het systeem opgeslagen, ongeacht de tijdzone van de gebruiker.|

Gebruik de eigenschap `Format` om te bepalen hoe de waarde in een modelgestuurde app moet worden weergegeven, ongeacht de waarde voor `DateTimeBehavior`.

|Optie|Beschrijving|
|--|--|
|DateAndTime|Hiermee worden de volledige datum en tijd weergegeven.|
|DateOnly|Hiermee wordt alleen de datum weergegeven.|

Zie [Dynamics 365 Customer Engagement Developer Guide: Behavior and format of the date and time attribute](/dynamics365/customer-engagement/developer/behavior-format-date-time-attribute) (Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: Gedrag en indeling van het datum- en tijdkenmerk) voor meer informatie.

## <a name="auto-number-attributes"></a>Kenmerken voor automatische nummering

Voor elke entiteit kun u een kenmerk voor automatische nummering toevoegen. Op dit moment kunt u het kenmerk via een programma toevoegen. Er is geen gebruikersinterface beschikbaar waarmee u dit type kenmerk kunt toevoegen.
Zie [Dynamics 365 Customer Engagement Developer Guide: Create auto-number attributes](/dynamics365/customer-engagement/developer/create-auto-number-attributes) (Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: Kenmerken voor automatische nummering maken) voor meer informatie.

## <a name="option-sets"></a>Optiesets

De kenmerken waarmee een set met opties wordt weergegeven, kunnen verwijzen naar een set met opties die op basis van het kenmerk is gedefinieerd of kunnen verwijzen naar een afzonderlijke set met opties die door meerdere kenmerken kan worden gedeeld. Dit is met name nuttig wanneer de waarden in een kenmerk ook van toepassing zijn op andere kenmerken. Als u een verwijzing naar een algemene set met opties opneemt, kunt u de opties op één plek onderhouden. De optiesets die kunnen worden gedeeld, worden *algemene* optiesets genoemd. De optiesets die binnen het kenmerk zijn gedefinieerd, worden *lokale* optiesets genoemd.

### <a name="retrieve-options-data"></a>Gegevens over opties ophalen
In de organisatieservice zijn aanvraagklassen aanwezig die u kunt gebruiken om de opties op te halen die door een kenmerk worden gebruikt.

#### <a name="use-the-organization-service-to-retrieve-options"></a>Opties ophalen met de organisatieservice

Alle kenmerken met opties nemen waarden over van [EnumAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.enumattributemetadata) en bevatten een [OptionSet-eigenschap](/dotnet/api/microsoft.xrm.sdk.metadata.enumattributemetadata.optionset). Deze eigenschap bevat de [OptionSetMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.optionsetmetadata) die de opties binnen de [Options-eigenschap](/dotnet/api/microsoft.xrm.sdk.metadata.optionsetmetadata.options) bevatten. 

In de organisatieservice kunt u de volgende berichten gebruiken om informatie over optiesets op te halen:
|Aanvraagklasse|Beschrijving|
|--|--|
|[RetrieveAllOptionSetsRequest](/dotnet/api/microsoft.xrm.sdk.messages.retrievealloptionsetsrequest) |Hiermee worden gegevens opgehaald over alle *algemene* optiesets.|
|[RetrieveAttributeRequest](/dotnet/api/microsoft.xrm.sdk.messages.retrieveattributerequest) |Hiermee worden gegevens opgehaald over een kenmerk, inclusief *lokale* optiesets.|
|[RetrieveMetadataChangesRequest](/dotnet/api/microsoft.xrm.sdk.messages.retrievemetadatachangesrequest) |Hiermee worden metagegevens opgehaald op basis van een query die *lokale* optiesets kan bevatten.<br />Zie het Engelstalige artikel [Retrieve and detect changes to metadata](/dynamics365/customer-engagement/developer/retrieve-detect-changes-metadata) (Wijzigingen in metagegevens ophalen en detecteren) voor meer informatie.|
|[RetrieveOptionSetRequest](/dotnet/api/microsoft.xrm.sdk.messages.retrieveoptionsetrequest) |Hiermee worden gegevens opgehaald over een *algemene* optieset.|

Meer informatie: 
- [Sample: Dump attribute picklist metadata to a file](/dynamics365/customer-engagement/developer/org-service/sample-dump-attribute-picklist-metadata-file) (Voorbeeld: Metagegevens voor keuzelijsten met metagegevens in een bestand dumpen)
- [Dynamics 365 Customer Engagement Developer Guide : Customize global option sets](/dynamics365/customer-engagement/developer/org-service/customize-global-option-sets) (Ontwikkelaarshandleiding voor Dynamics Customer Engagement: Algemene optiesets aanpassen)

#### <a name="use-the-web-api-to-retrieve-options"></a>Opties ophalen met de web-API

Via de web-API kunt u een query op de optiewaarden uitvoeren via de RESTful-methode. U kunt lokale of algemene opties ophalen door de kenmerken in een entiteit op te halen. Met het volgende voorbeeld worden the [OptionSetMetadata](/dynamics365/customer-engagement/web-api/optionsetmetadata) geretourneerd voor de opties in de eigenschap [Account](reference/entities/account.md).[AccountCategoryCode](reference/entities/account.md#BKMK_AccountCategoryCode).

`GET <organization url>/api/data/v9.0/EntityDefinitions(LogicalName='account')/Attributes(LogicalName='accountcategorycode')/Microsoft.Dynamics.CRM.PicklistAttributeMetadata?$select=LogicalName&$expand=OptionSet`

Met de web-API kunt u ook de [functie RetrieveMetadataChanges](/dynamics365/customer-engagement/web-api/retrievemetadatachanges) gebruiken.

Zie [Dynamics 365 Customer Engagement Developer Guide: Query metadata using the Web API > Querying EntityMetadata attributes](/dynamics365/customer-engagement/developer/webapi/query-metadata-web-api#querying-entitymetadata-attributes) (Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: Query's uitvoeren op metagegevens via de web-API > Query's uitvoeren op het entiteitstype EntityMetadata) voor meer informatie.



## <a name="attribute-mapping"></a>Kenmerktoewijzing

Wanneer u een nieuwe entiteitsrecord in de context van een bestaande entiteitsrecord maakt, kunt u automatisch bepaalde waarden van de bestaande entiteitsrecord als standaardwaarden overdragen voor de nieuwe entiteitsrecord. Hiermee kunt u de gegevensinvoer stroomlijnen voor personen die modelgestuurde apps gebruiken. Gebruikers van de toepassing zien de toegewezen waarden en kunnen ze bewerken voordat de entiteit wordt opgeslagen.

Voor ontwikkelaars die aangepaste clients maken, kan hetzelfde gedrag worden verkregen door gebruik te maken van het bericht `InitializeFrom` ([InitializeFromRequest-klasse](/dotnet/api/microsoft.crm.sdk.messages.initializefromrequest) in de organisatieservice of [InitializeFrom-functie](/dynamics365/customer-engagement/web-api/initializefrom) in de web-API) om de entiteitsgegevens op te halen met de geconfigureerde standaardwaardenset.

Meer informatie 
- [Aanpassingshandleiding voor Dynamics 365 Customer Engagement: Entiteitsvelden toewijzen](/dynamics365/customer-engagement/customize/map-entity-fields#BKMK_mappingEntityFields)
- [Dynamics 365 Customer Engagement Developer Guide Customize entity and attribute mappings](/dynamics365/customer-engagement/developer/customize-entity-attribute-mappings) (Ontwikkelaarshandleiding voor Dynamics Customer Engagement: Entiteit en kenmerktoewijzingen aanpassen)

### <a name="see-also"></a>Zie ook

[Common Data Service for Apps-entiteiten](entities.md)