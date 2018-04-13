---
title: Common Data Service for Apps-webservices gebruiken| Microsoft Docs
description: Informatie over hoe ontwikkelaars Common Data Service for Apps-webservices kunnen gebruiken.
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
ms.date: 02/26/2018
ms.author: jdaly
ms.openlocfilehash: 7f89a74b37ebf322137d680e165c007cd8fa6d26
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2018
---
# <a name="use-common-data-service-for-apps-web-services"></a>Common Data Service for Apps-webservices gebruiken

De Common Data Service for Apps biedt twee webservices waarmee u gegevens kunt beheren. Kies de service die het beste overeenkomt met de vereisten en uw vaardigheden. Zie [Dynamics 365 Customer Engagement Developer Guide: Choose your development style for Dynamics 365 Customer Engagement](/dynamics365/customer-engagement/developer/choose-development-style) (Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: Uw ontwikkelingsstijl voor Dynamics 365 Customer Engagement kiezen) voor meer informatie.

## <a name="web-api"></a>Web-API
De Web API is een OData v4 RESTful-eindpunt. Dit kunt u gebruiken voor elke programmeertaal die HTTP-aanvragen en -verificatie met behulp van OAuth 2.0 ondersteunt.

Zie [Dynamics 365 Customer Engagement Developer Guide: Use the Dynamics 365 Customer Engagement Web API](/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-web-api) (Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: Uw ontwikkelingsstijl voor Dynamics 365 Customer Engagement kiezen) voor meer informatie.

## <a name="organization-service"></a>Organisatieservice

De organisatieservice is een essentieel onderdeel van het Common Data Service for Apps-platform. Het is een WCF-service (Windows Communication Foundation) die momenteel alleen een SOAP-eindpunt biedt. .NET-ontwikkelaars kunnen de SDK-assembly's gebruiken voor gegevensbewerkingen. Binnen een invoegtoepassing is de organisatieservice via de SDK-assembly's de enige optie.
> [!NOTE]
> Ontwikkelaars kunnen van het SOAP-eindpunt van de organisatieservice gebruikmaken zonder de .NET SDK-assembly's te gebruiken, maar door de RESTful-eigenschap van de web-API is dit nu een veel beter alternatief.

Zie [Dynamics 365 Customer Engagement Developer Guide: Use the Dynamics 365 Organization service](/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-organization-service) (Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: De organisatieservice van Dynamics 365 gebruiken) voor meer informatie.

## <a name="about-the-web-services-and-the-platform"></a>Over de webservices en het platform

Het is nuttig om in te zien dat het platform door de organisatieservice wordt bepaald. De web-API biedt een RESTful-programmeerervaring, maar uiteindelijk verlopen alle gegevensbewerkingen via de onderliggende organisatieservice. 

De organisatieservice definieert de ondersteunde bewerkingen als berichten. Elk bericht heeft een naam. In de SDK-assembly's beschikt elk bericht over een bijbehorende *&lt;berichtnaam&gt;*`Request` en *&lt;berichtnaam&gt;*`Response`klasse. De [IOrganizationService-interface](/dotnet/api/microsoft.xrm.sdk.iorganizationservice) in de `Microsoft.Xrm.Sdk.dll` definieert verschillende hulpmethoden voor algemene CRUD-bewerkingen, evenals een [uitvoermethode](/dotnet/api/microsoft.xrm.sdk.iorganizationservice.execute) waarmee berichten kunnen worden aangeroepen. Voor alle berichten wordt de onderliggende [OrganizationRequest-klasse](/dotnet/api/microsoft.xrm.sdk.organizationrequest) gebruikt.

De web-API biedt dezelfde bewerkingen als de organisatieservice, maar geeft deze weer in een RESTful-stijl met behulp van het OData v4-protocol. OData v4 voorziet in benoemde bewerkingen via *Functies* of *Acties*. Bijna elk bericht dat beschikbaar is in de Organisatieservice wordt bekend gemaakt als functie of actie met een overeenkomstige naam. Deze berichten die met CRUD-bewerkingen overeenkomen zijn niet beschikbaar in de web-API omdat deze als RESTful-service implementaties hebben met behulp van de HTTP-methoden GET, POST, PATCH en DELETE.

De .NET SDK-assembly's voor het SOAP-eindpunt van de organisatieservice zijn zo ontworpen dat ze een nauwgezet model vormen van de onderliggende platformservices op basis van de [IOrganizationService-interface](/dotnet/api/microsoft.xrm.sdk.iorganizationservice). Maar het zijn niet dezelfde onderdelen en ze mogen niet met elkaar worden verward. 

Het SOAP-eindpunt voor de organisatieservice is geïntroduceerd in 2011 en er is aangekondigd dat het wordt afgeschaft. Dit betekent dat het eindpunt blijft werken en wordt ondersteund totdat het door Microsoft wordt verwijderd. Microsoft heeft ook aangekondigd dat de .NET SDK-assembly's worden bijgewerkt, zodat deze blijven werken nadat het SOAP-eindpunt is verwijderd. Dit betekent dat er bijgewerkte SDK-assembly's beschikbaar zijn voordat het SOAP-eindpunt wordt verwijderd. Ontwikkelaars zullen op een bepaald moment in de toekomst hun code moeten bijwerken voor het gebruik van deze nieuwe assembly's.

## <a name="discovery-services"></a>Detectieservices

Elke Common Data Service for Apps-gebruiker kan toegang krijgen tot meerdere Common Data Service for Apps-instanties. Via detectieservices kunt u code schrijven om gebruikers een lijst met instanties aan te bieden waarmee ze verbinding kunnen maken op basis van het Microsoft-account dat ze gebruiken. Elke instantie bevat een URL die u vervolgens kunt gebruiken om verbinding te maken met de instantie van hun keuze. 

U kunt een detectieservice openen via de web-API of de organisatieservice.

- Zie [Dynamics 365 Customer Engagement Developer Guide: Discover the URL for your organization using the Web API](/dynamics365/customer-engagement/developer/webapi/discover-url-organization-web-api) (Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: De URL voor uw organisatie met behulp van de web-API detecteren) voor meer informatie over de Web-API.
- Zie [Dynamics 365 Customer Engagement Developer Guide: Discover the URL for your organization using the Organization Service](/dynamics365/customer-engagement/developer/org-service/discover-url-organization-organization-service) (Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: De URL voor uw organisatie met behulp van de organisatieservice detecteren) voor meer informatie over de organisatieservice.

## <a name="use-custom-actions"></a>Aangepaste acties gebruiken

Een van de declaratieve opties die beschikbaar is voor processen is het maken van een *aangepaste actie*. Een aangepaste actie is in wezen het maken van een nieuw bericht in de Organisatieservice. Met aangepaste acties kunt u een reeks bewerkingen in een benoemde herbruikbare bewerking combineren. U kunt bijvoorbeeld een nieuw bericht maken met de naam *new_Escalate* waarmee u een reeks bewerkingen combineert die te maken hebben met het op de hoogte brengen van de juiste personen wanneer een belangrijke klant een ernstig probleem ondervindt.

Wanneer u een aangepaste actie definieert, kiest u de handtekening van de bewerking door de invoerparameters en eigenschappen te definiëren die in geretourneerde resultaten moeten worden opgenomen. Aangepaste acties kunnen vervolgens met behulp van de ontwerpfunctie of door code worden aangeroepen vanuit een declaratieve proces. 

De unieke waarde van aangepaste acties is dat de specifieke bewerkingen die ze bevatten, kunnen worden gewijzigd door iemand die geen ontwikkelaar is door middel van de ontwerpfunctie, zonder andere processen of de code die wordt aangeroepen te beïnvloeden.  Dit blijft van toepassing als de handtekening van de actie niet worden gewijzigd. Als u andere invoerparameters of uitvoereigenschappen nodig hebt, moet u een nieuwe, andere aangepaste actie maken om te voorkomen dat processen of code worden beschadigd via een bestaande code.

Als een aangepaste actie is gedefinieerd in een omgeving, is een nieuwe OData-v4-actie beschikbaar via de web-API en kan binnen de organisatieservice de aangepaste actie rechtstreeks worden aangeroepen met de [OrganizationRequest-klasse](/dotnet/api/microsoft.xrm.sdk.organizationrequest) of via een sterk getypeerde klasse die wordt gegenereerd met het *hulpprogramma voor het genereren van code (CrmSvcUtil.exe)*.

Meer informatie: 
- [Aanpassingshandleiding voor Dynamics 365 Customer Engagement: Overzicht van acties](/dynamics365/customer-engagement/customize/actions)
- [Dynamics 365 Customer Engagement Developer Guide: Create your own actions](/dynamics365/customer-engagement/developer/create-own-actions) (Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: Uw eigen acties maken)
- [Dynamics 365 Customer Engagement Developer Guide: Use Web API actions > Use a custom action](/dynamics365/customer-engagement/developer/webapi/use-web-api-actions#use-a-custom-action) (Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: Acties web-API gebruiken > Een aangepaste actie gebruiken)

## <a name="metadata-services"></a>Metagegevensservices

Zowel de web-API als de organisatieservice bevatten functionaliteit om CRUD-bewerkingen op de entiteit-schema uit te voeren. Hoewel u deze bewerkingen met behulp van code kunt uitvoeren, gebruikt u in het algemeen ontwerpfuncties om aangepaste schema-elementen toe te voegen, bij te werken of te verwijderen. Gebruikers moeten beheerdersrechten hebben om schemawijzigingen toe te passen, maar alle gebruikers kunnen de metagegevens lezen.

De metagegevensservices worden vaker gebruikt voor het ophalen van metagegevens over de omgeving waarin uw uitbreiding wordt uitgevoerd. Omdat elke omgeving kan afwijken en metagegevens van schema’s veel informatie bevatten over hoe de omgeving is geconfigureerd, moet u deze informatie mogelijk ophalen zodat uw uitbreidingen kunnen worden aangepast aan andere aanpassingen die in die omgeving van kracht zijn.

Enkele voorbeelden:
- Het aantal opties dat beschikbaar is in een optieset-kenmerk kan veranderen. In plaats van de waarden in uw omgeving te programmeren, kunt u overwegen of er andere opties beschikbaar zijn. U kunt een query op het systeem uitvoeren om te bepalen of de huidige omgeving over andere opties beschikt.
- De weergavenaam voor een entiteit kan worden gewijzigd. De standaard weergavenaam voor de accountentiteit is *Account*. Dit kan worden gewijzigd in *Bedrijf*. Als u een bericht wilt weergegeven aan een gebruiker en naar de naam van een entiteit wilt verwijzen, moet u deze niet programmeren maar in plaats daarvan de waarde gebruiken die overeenkomt met wat de gebruiker gewend is om te zien, en de weergavenaam gebruiken die in plaats daarvan is opgehaald uit de metagegevens van de entiteit.

Als u een goed praktisch begrip van de metagegevens in het systeem hebt ontwikkeld, begrijpt u beter hoe het Common Data Service for Apps-platform werkt. In de ontwerpfuncties die beschikbaar zijn voor het bewerken van metagegevens kunnen niet alle in de metagegevens gevonden details worden weergegeven. U kunt de modelgestuurde app genaamd *Metadatabrowser* installeren, waarmee u alle verborgen entiteiten en eigenschappen van metagegevens kunt weergeven die in het systeem zijn gevonden. 

Zie [Dynamics 365 Customer Engagement Developer Guide: Browse the metadata for your organization](/dynamics365/customer-engagement/developer/browse-your-metadata) (Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: Blader door de metagegevens voor uw organisatie) voor meer informatie.

Zie voor meer informatie over het programmatisch werken met metagegevens:
- [Dynamics 365 Customer Engagement Developer Guide: Use the Web API with metadata](/dynamics365/customer-engagement/developer/webapi/use-web-api-metadata) (Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: De web-API gebruiken met metagegevens)
- [Dynamics 365 Customer Engagement Developer Guide: Use the Organization service with Dynamics 365 metadata](/dynamics365/customer-engagement/developer/org-service/use-organization-service-metadata) (Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: De organisatieservice gebruiken met metagegevens van Dynamics 365)
 
### <a name="see-also"></a>Zie ook

[Overzicht van Common Data Service for Apps voor ontwikkelaars](overview.md)

