---
title: Overzicht van regio's | Microsoft Docs
description: Meer informatie over regio's in PowerApps
author: manasmams
manager: kvivek
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: manasma
search.audienceType:
- admin
search.app:
- D365CE
- PowerApps
- Powerplatform
ms.openlocfilehash: 2d36fcc9b09f157da4da6b6293c34fad4320acbb
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42832766"
---
# <a name="regions-overview-in-powerapps"></a>Overzicht van regio's in PowerApps
## <a name="how-do-i-find-out-where-my-app-is-deployed"></a>Hoe kan ik nagaan waar mijn app wordt geïmplementeerd?
Uw app wordt geïmplementeerd in de regio die als host fungeert voor de omgeving. Als uw omgeving bijvoorbeeld is gemaakt in de regio Europa, wordt uw app geïmplementeerd in Europese datacenters.

Als u een beheerder bent, kunt u in het PowerApps-beheercentrum nagaan wat de regio is van elke omgeving.

* Ga naar het [beheercentrum](https://admin.powerapps.com) en meld u aan met uw werkaccount.
  
    In het beheercentrum worden alle bestaande omgevingen weergegeven op het tabblad **Omgevingen**. In deze lijst wordt de **Regio** weergegeven waarin uw app wordt geïmplementeerd:
  
   ![Tabblad Omgevingen](./media/regions-overview/environment-list.png)

## <a name="what-regions-are-available"></a>Welke regio's zijn er beschikbaar?
* Verenigde Staten
* Canada
* Europa
* Azië
* Australië
* India
* Japan
* Verenigd Koninkrijk

## <a name="what-features-are-specific-to-a-given-region"></a>Welke functies zijn specifiek voor een bepaalde regio?
Omgevingen kunnen in verschillende regio's worden gemaakt en zijn gebonden aan die geografische locatie. Wanneer u een app maakt in een omgeving, wordt deze app geïmplementeerd in datacenters op die geografische locatie. Dit geldt voor alle items die u maakt in deze omgeving, waaronder databases in de Common Data Service, apps, verbindingen, gateways en aangepaste connectors.

Als uw gebruikers zich in Europa bevinden, maakt en gebruikt u de omgeving in de regio Europa om optimale prestaties te waarborgen. Als uw gebruikers zich in de Verenigde Staten bevinden, maakt en gebruikt u de omgeving in de Verenigde Staten.

> [!NOTE]
> U kunt op dit moment alleen een database maken in een productie- of proefversieomgeving die zich in dezelfde regio bevindt als de basisregio van uw Azure AD- of Office 365-tenant. We werken aan de functie voor het maken van databases in omgevingen die in een andere regio zijn gemaakt dan de basislocatie van uw tenant. Daarnaast is het momenteel niet mogelijk een database in de standaardomgeving en een afzonderlijke omgeving te maken (gemaakt met PowerApps Community-abonnement).

> [!NOTE]
> On-premises gegevensgateways zijn niet beschikbaar in de regio India of aangepaste omgevingen. In de standaardomgeving moet u gateways maken.

