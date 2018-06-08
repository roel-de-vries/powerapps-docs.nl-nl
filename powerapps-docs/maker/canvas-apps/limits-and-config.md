---
title: Systeemvereisten, limieten en configuratiewaarden | Microsoft Docs
description: Systeemvereisten, limieten en configuratiewaarden voor PowerApps
documentationcenter: na
author: skjerland
manager: kfile
editor: ''
tags: ''
ms.service: PowerApps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 03/07/2018
ms.author: sharik
ms.openlocfilehash: 5bf57ec96569751b3db656abdf04cebb1e13133a
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "32329842"
---
# <a name="system-requirements-limits-and-configuration-values"></a>Systeemvereisten, limieten en configuratiewaarden
Dit onderwerp bevat vereisten voor apparaatplatformen en webbrowsers, maar ook limieten en configuratiewaarden voor PowerApps.

## <a name="supported-platforms-for-running-apps-using-the-powerapps-app"></a>Ondersteunde platforms voor het uitvoeren van apps met behulp van de PowerApps-app
| **Minimale vereiste** | **Aanbevolen** |
| --- | --- |
| iOS 9.3 of hoger |iOS 10 of hoger met ten minste 2 GB RAM-geheugen |
| Android 5 of hoger |Android 7 of hoger met ten minste 4 GB RAM-geheugen |
| Windows 8.1 of hoger (alleen pc) |Windows 10 Fall Creators Update met ten minste 8 GB RAM-geheugen)|

## <a name="supported-browsers-for-running-apps"></a>Ondersteunde browsers voor het uitvoeren van apps
| **Browser** | **Besturingssysteem** |
| --- | --- |
| Google Chrome (meest recente versie)<br>(aanbevolen) |Windows 7 SP1, 8.1 en 10 <br>Android 5 of hoger <br>iOS 8 of hoger<br>macOS |
| Microsoft Edge (meest recente versie)<br>(aanbevolen) |Windows 10 |
| Microsoft Internet Explorer 11 (Compatibiliteitsweergave moet uitgeschakeld zijn) |Windows 7 SP1, 8.1 en 10 |
| Mozilla Firefox (meest recente versie) |Windows 7 SP1, 8.1 en 10 <br> Android 5 of hoger <br>iOS 8 of hoger <br>macOS |
| Apple Safari (meest recente versie) |iOS 8 of hoger <br>macOS |

## <a name="supported-browsers-for-powerapps-studio"></a>Ondersteunde browsers voor PowerApps Studio
| **Browser** | **Besturingssysteem** |
| --- | --- |
| Google Chrome (meest recente versie)<br>(aanbevolen) |Windows 7 SP1, 8.1 en 10 <br>macOS |
| Microsoft Edge (meest recente versie)<br>(aanbevolen) |Windows 10 |
| Microsoft Internet Explorer 11 (Compatibiliteitsweergave moet uitgeschakeld zijn) |Windows 7 SP1, 8.1 en 10 |

## <a name="request-limits"></a>Aanvraaglimieten
Deze limieten gelden voor elke uitgaande aanvraag:

| Naam | Limiet |
| --- | --- |
| Time-out |180 seconden |
| Nieuwe pogingen |4 |

> [!NOTE]
> De waarde van nieuwe pogingen kan variëren. Bij bepaalde fouten is het onnodig om het opnieuw te proberen.

## <a name="ip-addresses"></a>IP-adressen
Voor aan vragen van PowerApps wordt gebruikgemaakt van IP-adressen die afhankelijk zijn van de regio van de [omgeving](../../administrator/environments-overview.md) waarin de app zich bevindt. Er worden geen volledig gekwalificeerde domeinnamen gepubliceerd voor PowerApps-scenario's.

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
