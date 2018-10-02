---
title: Resources voor ontwikkelaars weergeven of downloaden | MicrosoftDocs
description: Resources voor ontwikkelaars en endpoint-URL's voor services zoeken
keywords: ''
ms.date: 06/06/2018
ms.service: crm-online
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.assetid: e200d242-ff3f-48e5-af32-aed050e02441
author: Mattp123
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
<!-- TODO: The Developer Resources page have to be updated to match this page -->

# <a name="view-or-download-developer-resources"></a>Resources voor ontwikkelaars weergeven of downloaden

Deze pagina biedt informatie over resources voor ontwikkelaars en het specifieke exemplaar waaraan u werkt. 

## <a name="view-the-developer-resources-page-for-your-environment"></a>De pagina Resources voor ontwikkelaars voor uw omgeving weergeven

1. Selecteer in de PowerApps-portal de knop Instellingen ![Knop Instellingen](../../administrator/media/settings-button-nav-bar.png) en kies **Geavanceerde aanpassingen**

    ![Geavanceerde aanpassingen](media/advanced-customizations-menu.png)

1. Kies in het paneel **Geavanceerde aanpassingen** de koppeling **Resources voor ontwikkelaars**:<br />![Koppelingen naar resources voor ontwikkelaars](media/developer-resources-link.png)

## <a name="getting-started"></a>Aan de slag 

Deze sectie biedt koppelingen voor ontwikkelaars om resources te vinden. De volgende resources zijn beschikbaar:


|Koppeling |Beschrijving|
|---------|---------|
|[Ontwikkelaarscentrum](https://go.microsoft.com/fwlink/?LinkId=551006)|De belangrijkste bron voor documentatie voor ontwikkelaars.|
|[Ontwikkelaarsforums](https://go.microsoft.com/fwlink/?LinkId=550993)|Stel en beantwoord vragen met andere ontwikkelaars.|
|[NuGet-pakketten](https://go.microsoft.com/fwlink/?LinkId=550994)|Ontdek NuGet-pakketten om SDK-assembly's aan uw projecten toe te voegen.|
|[Hulpprogramma's downloaden](https://go.microsoft.com/fwlink/?LinkID=512122)|U kunt de hulpprogramma's die u nodig hebt, downloaden van NuGet. Gebruik het PowerShell-script op deze pagina om de nieuwste versies te downloaden.|
|[Voorbeeldcode](https://go.microsoft.com/fwlink/?LinkId=553007)|Een lijst met beschikbare voorbeelden.|
|[Ontwikkelaaroverzicht](https://go.microsoft.com/fwlink/?LinkId=550995)|Koppeling naar een onderwerp met een overzicht voor ontwikkelaars.|

<!-- TODO update 512122 to go to https://docs.microsoft.com/dynamics365/customer-engagement/developer/download-tools-nuget -->


## <a name="connect-your-apps-to-this-instance-of-common-data-service-for-apps"></a>Uw apps verbinden met dit exemplaar van Common Data Service voor Apps

Deze sectie biedt informatie die u nodig hebt om verbinding te maken met uw exemplaar van Common Data Service voor Apps.

### <a name="instance-web-api"></a>Web-API van exemplaar

Dit is de URL voor de web-API voor uw exemplaar. De web-API is een OData v4 RESTful-API. U kunt ook het servicedocument downloaden waarin de beschikbare metagegevens en bewerkingen in uw exemplaar worden beschreven. Meer informatie: [Documentatie voor ontwikkelaars: De web-API voor Dynamics 365 Customer Engagement gebruiken](/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-web-api)

### <a name="organization-service"></a>Organisatieservice

Dit is de URL voor het SOAP-eindpunt voor de organisatieservice voor uw exemplaar.
U kunt de WSDL voor deze service hier downloaden, maar doorgaans gebruikt u het hulpmiddel CrmSvcUtil.exe voor codegeneratie om entiteitsklassen voor .NET-projecten te bouwen. Zie voor meer informatie: 
- [Documentatie voor ontwikkelaars: Eerder gebonden entiteitklassen maken met het hulpmiddel voor het genereren van code (CrmSvcUtil.exe)](/dynamics365/customer-engagement/developer/org-service/create-early-bound-entity-classes-code-generation-tool)
- [Documentatie voor ontwikkelaars: Organisatieservice gebruiken om gegevens of metagegevens te lezen en te schrijven](/dynamics365/customer-engagement/developer/org-service/use-organization-service-read-write-data-metadata)

### <a name="instance-reference-information"></a>Referentie-informatie voor exemplaar

Met deze informatie wordt uw exemplaar uniek beschreven. De informatie bestaat uit uw **id** en **unieke naam** voor de GUID.
Deze informatie is noodzakelijk wanneer u Azure-extensies gebruikt met uw exemplaar.
Meer informatie: [Documentatie voor ontwikkelaars: Azure-extensies voor Dynamics 365 Customer Engagement](/dynamics365/customer-engagement/developer/azure-extensions)

## <a name="connect-your-apps-to-the-common-data-service-for-apps-discovery-service"></a>Uw apps verbinden met de Discovery-service Common Data Service voor Apps

Aangezien gebruikers mogelijk toegang tot meerdere Common Data Service voor Apps-omgevingen hebben, bieden de Discovery-services gebruikers de mogelijkheid om de beschikbare omgevingen op te halen op basis van hun gebruikersreferenties.

### <a name="discovery-web-api"></a>Discovery Web-API

Dit is het eindpuntadres voor de RESTful OData v4-versie van de Discovery-service voor uw exemplaar. U kunt het servicedocument ook hier downloaden.
Meer informatie: [Documentatie voor ontwikkelaars: De URL voor uw organisatie bepalen met de Web-API](/dynamics365/customer-engagement/developer/webapi/discover-url-organization-web-api)


### <a name="discovery-service"></a>Discovery-service

Dit is het eindpuntadres voor de SOAP-versie van de Discovery-service voor uw exemplaar. U kunt het servicedocument ook hier downloaden.
Meer informatie: [Documentatie voor ontwikkelaars: De URL voor uw organisatie bepalen met de Discovery-service](/dynamics365/customer-engagement/developer/org-service/discover-url-organization-organization-service)
  
### <a name="more-information"></a>Meer informatie

[Documentatie voor ontwikkelaars: Pagina Resources voor ontwikkelaars](/dynamics365/customer-engagement/developer/developer-resources-page)<br />
[Documentatie voor ontwikkelaars: De web-API voor Dynamics 365 Customer Engagement gebruiken](/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-web-api)<br />
[Documentatie voor ontwikkelaars: Organisatieservice gebruiken om gegevens of metagegevens te lezen en te schrijven](/dynamics365/customer-engagement/developer/org-service/use-organization-service-read-write-data-metadata)<br />
[Documentatie voor ontwikkelaars: Azure-extensies voor Dynamics 365 Customer Engagement](/dynamics365/customer-engagement/developer/azure-extensions)<br />
[Documentatie voor ontwikkelaars: De URL voor uw organisatie bepalen met de Web-API](/dynamics365/customer-engagement/developer/webapi/discover-url-organization-web-api)<br />
[Documentatie voor ontwikkelaars: De URL voor uw organisatie bepalen met de Discovery-service](/dynamics365/customer-engagement/developer/org-service/discover-url-organization-organization-service)
  

