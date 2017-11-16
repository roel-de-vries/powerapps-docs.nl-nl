---
title: Limieten en configuratie | Microsoft Docs
description: Limieten en configuratiewaarden voor PowerApps
services: 
suite: PowerApps
documentationcenter: na
author: skjerland
manager: anneta
editor: 
tags: 
ms.service: PowerApps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/06/2017
ms.author: sharik
ms.openlocfilehash: 337f3fc00fe52e0008190e2144f21f40d1632f52
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="limits-and-configuration-in-microsoft-powerapps"></a>Limieten en configuratie in Microsoft PowerApps
Dit onderwerp bevat informatie over de huidige limieten en configuratiegegevens voor PowerApps.

## <a name="requests"></a>Aanvragen
Deze limieten gelden voor elke uitgaande aanvraag:

| Naam | Limiet |
| --- | --- |
| Time-out |180 seconden |
| Nieuwe pogingen |4 |

**Opmerking**: de waarde van nieuwe pogingen kan variëren. Bij bepaalde fouten is het niet logisch om het opnieuw te proberen.

## <a name="ip-addresses"></a>IP-adressen
Voor aan vragen van PowerApps wordt gebruikgemaakt van IP-adressen die afhankelijk zijn van de regio van de [omgeving](environments-overview.md) waarin de app zich bevindt. Er worden geen volledig gekwalificeerde domeinnamen gepubliceerd voor PowerApps-scenario's.

Aanroepen die worden gedaan vanaf een API die is verbonden via een app (bijvoorbeeld de SQL-API of de SharePoint-API), zijn afkomstig van het IP-adres dat verderop in dit onderwerp wordt beschreven.

U moet deze adressen gebruiken als u bijvoorbeeld IP-adressen op de goedgekeurde lijst moet plaatsen voor uw Azure SQL-database.

| Regio | Uitgaande IP |
| --- | --- |
| Azië |52.163.91.227, 52.163.89.40, 52.163.89.65, 52.163.95.29, 13.75.89.9, 13.75.91.198, 13.75.92.202, 13.75.92.124 |
| Australië |13.77.7.172, 13.70.191.49, 13.70.189.7, 13.70.187.251, 13.70.82.210, 13.73.203.158, 13.73.207.42, 13.73.205.35 |
| Canada |52.233.30.222, 52.233.30.148, 52.233.30.199, 52.233.29.254, 52.232.130.205, 52.229.126.118, 52.229.126.28, 52.229.123.56 |
| Europa |52.166.241.149, 52.166.244.232, 52.166.245.173, 52.166.243.169, 40.69.45.126, 40.69.45.11, 40.69.45.93, 40.69.42.254 |
| India |52.172.54.172, 52.172.55.107, 52.172.55.84, 52.172.51.70, 52.172.158.185, 52.172.159.100, 52.172.158.2, 52.172.155.245 |
| Japan |104.214.137.186, 104.214.139.29, 104.214.140.23, 104.214.138.174, 13.78.85.193, 13.78.84.73, 13.78.85.200, 13.78.86.229 |
| Verenigde Staten |104.43.232.28, 104.43.232.242, 104.43.235.249, 104.43.234.211, 52.160.93.247, 52.160.91.66, 52.160.92.131, 52.160.95.100, 40.117.101.91, 40.117.98.246, 40.117.101.120, 40.117.100.191 |
| Verenigde Staten (vroege toegang) |52.161.26.191, 52.161.27.42, 52.161.29.40, 52.161.26.33, 13.66.213.240, 13.66.214.51, 13.66.210.166, 13.66.213.29 |

## <a name="required-services"></a>Vereiste services
Deze lijst bevat alle services die PowerApps Studio aanspreekt en hun gebruik. Uw netwerk mag deze services **niet** blokkeren.

| Domein(en) | Protocollen | Gebruikt |
| --- | --- | --- |
| management.azure.com |https |RP |
| msmanaged-na.azure-apim.net |https |Runtime van connectors/API's |
| login.microsoft.com<br>login.windows.net<br>login.microsoftonline.com<br>secure.aadcdn.microsoftonline-p.com |https |ADAL |
| graph.microsoft.com<br>graph.windows.net |https |Azure Graph - Voor het ophalen van gebruikersgegevens (zoals een profielfoto) |
| gallery.azure.com |https |Voorbeeld- en sjabloon-apps |
| *.azure-apim.net |https |API-hubs - Verschillende subdomeinen voor elke landinstelling |
| *.powerapps.com |https |WebAuth + Portal |
| *.azureedge.net |https |WebAuth |
| *.blob.core.windows.net |https |Blob-opslag |
| vortex.data.microsoft.com |https |Telemetrie |

