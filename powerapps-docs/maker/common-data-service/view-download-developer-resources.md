---
title: Resources voor ontwikkelaars weergeven of downloaden | MicrosoftDocs
description: Resources voor ontwikkelaars en URL’s van service-eindpunten zoeken
keywords: ''
ms.date: 06/06/2018
ms.service: crm-online
ms.custom: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: e200d242-ff3f-48e5-af32-aed050e02441
author: Mattp123
ms.author: matp
manager: kvivek
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.openlocfilehash: ae93b57d9ead3a62fb538ae986eb524367259545
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39680007"
---
<!-- TODO: The Developer Resources page have to be updated to match this page -->

# <a name="view-or-download-developer-resources"></a>Resources voor ontwikkelaars weergeven of downloaden

Op deze pagina vindt u resources voor ontwikkelaars en informatie over de specifieke instantie waaraan u werkt. 

## <a name="view-the-developer-resources-page-for-your-environment"></a>De pagina Resources voor ontwikkelaars voor uw omgeving weergeven

1. Vanaf de PowerApps-portal selecteert u de ![knop Instellingen](../../administrator/media/settings-button-nav-bar.png) knop Instellingen en kiest u **Geavanceerde aanpassingen**.

    ![Geavanceerde aanpassingen](media/advanced-customizations-menu.png)

1. In het deelvenster **Geavanceerde aanpassingen** kiest u de koppeling **Resources voor ontwikkelaars**:<br />![Koppeling Resources voor ontwikkelaars](media/developer-resources-link.png)

## <a name="getting-started"></a>Aan de slag 

In deze sectie vindt u koppelingen waar ontwikkelaars resources kunnen vinden. De volgende resources zijn beschikbaar:


|Koppeling |Beschrijving|
|---------|---------|
|[Ontwikkelaarscentrum](https://go.microsoft.com/fwlink/?LinkId=551006)|Het belangrijkste toegangspunt voor documentatie voor ontwikkelaars.|
|[Forums voor ontwikkelaars](https://go.microsoft.com/fwlink/?LinkId=550993)|Vragen stellen en beantwoorden met andere ontwikkelaars.|
|[NuGet-pakketten](https://go.microsoft.com/fwlink/?LinkId=550994)|Ontdek NuGet-pakketten om SDK-assembly's toe te voegen aan uw projecten.|
|[Hulpprogramma's downloaden](https://go.microsoft.com/fwlink/?LinkID=512122)|Hulpprogramma's die u nodig hebt, kunnen worden gedownload van NuGet. Gebruik het PowerShell-script op deze pagina om de meest recente versies op te halen.|
|[Voorbeeldcode](https://go.microsoft.com/fwlink/?LinkId=553007)|Een lijst met beschikbare voorbeelden.|
|[Overzicht voor ontwikkelaars](https://go.microsoft.com/fwlink/?LinkId=550995)|Koppeling naar een onderwerp met een overzicht voor ontwikkelaars.|

<!-- TODO update 512122 to go to https://docs.microsoft.com/dynamics365/customer-engagement/developer/download-tools-nuget -->


## <a name="connect-your-apps-to-this-instance-of-common-data-service-for-apps"></a>Uw apps verbinden met deze instantie van Common Data Service voor Apps

In deze sectie vindt u informatie die u nodig hebt om verbinding te maken met uw Common Data Service voor Apps-instantie.

### <a name="instance-web-api"></a>Instantie van Web-API

Dit is de URL voor de Web-API voor uw instantie. De Web-API is een OData v4 RESTful API. U kunt ook het servicedocument downloaden waarin de metagegevens en de bewerkingen worden beschreven die beschikbaar zijn in uw instantie. Meer informatie: [Documentatie voor ontwikkelaars: de Dynamics 365 Customer Engagement Web API gebruiken](/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-web-api)

### <a name="organization-service"></a>Organisatieservice

Dit is de URL voor het SOAP-eindpunt voor de Organisatieservice voor uw instantie.
U kunt de WSDL voor deze service hier downloaden, maar meestal gebruikt u het hulpprogramma CrmSvcUtil.exe om entiteitsklassen te bouwen voor .NET-projecten. Meer informatie: 
- [Documentatie voor ontwikkelaars: Vroege gebonden entiteitsklassen maken met het hulpprogramma voor het genereren van code (CrmSvcUtil.exe)](/dynamics365/customer-engagement/developer/org-service/create-early-bound-entity-classes-code-generation-tool)
- [Documentatie voor ontwikkelaars: De Organisatieservice gebruiken om gegevens of metagegevens te lezen en schrijven](/dynamics365/customer-engagement/developer/org-service/use-organization-service-read-write-data-metadata)

### <a name="instance-reference-information"></a>Instantieverwijzingsgegevens

Deze informatie beschrijft uw instantie op een unieke manier. Er is een GUID-**id** en een **Unieke naam**.
U hebt deze informatie nodig wanneer u Azure-extensies gebruikt met uw instanties.
Meer informatie: [Documentatie voor ontwikkelaars: Azure-extensies voor Dynamics 365 Customer Engagement](/dynamics365/customer-engagement/developer/azure-extensions)

## <a name="connect-your-apps-to-the-common-data-service-for-apps-discovery-service"></a>Uw apps verbinden met de instantie van Common Data Service voor Apps Discovery-service

Omdat mensen toegang kunnen hebben tot meerdere CDS voor apps-omgevingen, kunnen met de discovery-services de beschikbare omgevingen worden opgehaald waartoe een persoon toegang heeft op basis van zijn gebruikersreferenties.

### <a name="discovery-web-api"></a>Discovery Web-API

Dit is het adres van het eindpunt voor de RESTful OData v4-versie van de discovery-service die moet worden gebruikt voor uw instantie. U kunt het servicedocument ook hier downloaden.
Meer informatie: [Documentatie voor ontwikkelaars: De URL voor uw organisatie met behulp van de Web-API detecteren](/dynamics365/customer-engagement/developer/webapi/discover-url-organization-web-api)


### <a name="discovery-service"></a>Discovery-service

Dit is het adres van het eindpunt voor de SOAP-versie van de discovery-service die moet worden gebruikt voor uw instantie. U kunt het servicedocument ook hier downloaden.
Meer informatie: [Documentatie voor ontwikkelaars: De URL voor uw organisatie met behulp van de Discovery-service](/dynamics365/customer-engagement/developer/org-service/discover-url-organization-organization-service)
  
### <a name="more-information"></a>Meer informatie

[Documentatie voor ontwikkelaars: Pagina met resources voor ontwikkelaars](/dynamics365/customer-engagement/developer/developer-resources-page)<br />
[Documentatie voor ontwikkelaars: de Dynamics 365 Customer Engagement Web-API gebruiken](/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-web-api)<br />
[Documentatie voor ontwikkelaars: De Organisatieservice gebruiken om gegevens of metagegevens te lezen en schrijven](/dynamics365/customer-engagement/developer/org-service/use-organization-service-read-write-data-metadata)<br />
[Documentatie voor ontwikkelaars: Azure-extensies voor Dynamics 365 Customer Engagement](/dynamics365/customer-engagement/developer/azure-extensions)<br />
[Documentatie voor ontwikkelaars: De URL voor uw organisatie met behulp van de Web-API detecteren](/dynamics365/customer-engagement/developer/webapi/discover-url-organization-web-api)<br />
[Documentatie voor ontwikkelaars: De URL voor uw organisatie met behulp van de Discovery-service detecteren](/dynamics365/customer-engagement/developer/org-service/discover-url-organization-organization-service)
  

