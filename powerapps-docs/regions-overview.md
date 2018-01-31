---
title: "Overzicht van regio’s | Microsoft Docs"
description: "Regio's in PowerApps: waar apps zijn geïmplementeerd, beschikbare regio's, functies die specifiek zijn voor een regio"
services: 
suite: powerapps
documentationcenter: na
author: skjerland
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/04/2017
ms.author: sharik
ms.openlocfilehash: 114aa01bd745ed501e209e314e75904751aad3f5
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/23/2018
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

## <a name="what-features-are-specific-to-a-given-region"></a>Welke functies zijn specifiek voor een bepaalde regio?
Omgevingen kunnen in verschillende regio's worden gemaakt en zijn gebonden aan die geografische locatie. Wanneer u een app maakt in een omgeving, wordt deze app geïmplementeerd in datacenters op die geografische locatie. Dit geldt voor alle items die u maakt in deze omgeving, waaronder databases in de Common Data Service, apps, verbindingen, gateways en aangepaste connectors.

Als uw gebruikers zich in Europa bevinden, maakt en gebruikt u de omgeving in de regio Europa om optimale prestaties te waarborgen. Als uw gebruikers zich in de Verenigde Staten bevinden, maakt en gebruikt u de omgeving in de Verenigde Staten.

> [!NOTE]
> On-premises gegevensgateways zijn niet beschikbaar in de regio India of aangepaste omgevingen. In de standaardomgeving moet u gateways maken.

