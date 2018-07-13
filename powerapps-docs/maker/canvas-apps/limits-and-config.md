---
title: Systeemvereisten, limieten en configuratiewaarden | Microsoft Docs
description: Systeemvereisten, limieten en configuratiewaarden voor PowerApps
author: skjerland
ms.service: PowerApps
ms.topic: conceptual
ms.component: canvas
ms.date: 03/07/2018
ms.author: sharik
ms.openlocfilehash: e76710bc800782624ca1190086cc19dd47d60939
ms.sourcegitcommit: 79b8842fb0f766a0476dae9a537a342c8d81d3b3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2018
ms.locfileid: "37896093"
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

> [!IMPORTANT]
>   Als u bestaande configuraties hebt, moet u deze zo snel mogelijk voor 1 september 2018 bijwerken zodat ze de IP-adressen in deze lijst bevatten en daarmee overeenkomen voor de regio’s waarin uw PowerApps-apps bestaan.

| Regio | Uitgaande IP |
| --- | --- |
| Azië | 13.75.36.64 - 13.75.36.79, 13.67.8.240 - 13.67.8.255, 52.175.23.169, 52.187.68.19, 52.163.91.227, 52.163.89.40, 52.163.89.65, 52.163.95.29, 13.75.89.9, 3.75.91.198, 13.75.92.202, 13.75.92.124  |
| Australië  | 13.70.72.192 - 13.70.72.207, 13.72.243.10, 13.77.50.240 - 13.77.50.255, 13.70.136.174, 13.77.7.172, 13.70.189.7, 13.70.187.251, 13.70.82.210, 13.73.203.158, 13.73.207.42, 13.73.205.35, 13.70.191.49 |
| Canada | 13.71.170.208 - 13.71.170.223, 13.71.170.224 - 13.71.170.239, 52.237.24.126, 40.69.106.240 - 40.69.106.255, 52.242.35.152, 52.233.30.222, 52.233.30.148, 52.233.30.199, 52.233.29.254, 52.232.130.205, 52.229.126.118, 52.229.126.28, 52.229.123.56 |
| Europa | 13.69.227.208 - 13.69.227.223, 52.178.150.68, 13.69.64.208 - 13.69.64.223, 52.174.88.118, 52.166.241.149, 52.166.244.232, 52.166.245.173, 52.166.243.169, 40.69.45.126, 40.69.45.11, 40.69.45.93, 40.69.42.254 |
| India  | 104.211.81.192 - 104.211.81.207, 52.172.211.12, 40.78.194.240 - 40.78.194.255, 13.71.125.22, 104.211.146.224 - 104.211.146.239, 104.211.189.218, 52.172.54.172, 52.172.55.107, 52.172.55.84, 52.172.51.70, 52.172.158.185, 52.172.159.100, 52.172.158.2, 52.172.155.245 |
| Japan | 13.78.108.0 - 13.78.108.15, 13.71.153.19, 40.74.100.224 - 40.74.100.239, 104.215.61.248, 104.214.137.186, 104.214.139.29, 104.214.140.23, 104.214.138.174, 13.78.85.193, 13.78.84.73, 13.78.85.200, 13.78.86.229 |
| Verenigd Koninkrijk | 51.140.148.0 - 51.140.148.15, 51.140.80.51, 51.140.211.0 - 51.140.211.15, 51.141.47.105, 51.140.80.51, 51.141.47.105 |
| Verenigde Staten | 13.89.171.80 - 13.89.171.95, 52.173.245.164, 40.71.11.80 - 40.71.11.95, 40.71.249.205, 40.70.146.208 - 40.70.146.223, 52.232.188.154, 52.162.107.160 - 52.162.107.175, 52.162.242.161, 40.112.243.160 - 40.112.243.175, 104.42.122.49, 104.43.232.28, 104.43.232.242, 104.43.235.249, 104.43.234.211, 52.160.93.247, 52.160.91.66, 52.160.92.131, 52.160.95.100, 40.117.101.91, 40.117.98.246, 40.117.101.120, 40.117.100.191 |
| Verenigde Staten (vroege toegang) | 13.71.195.32 - 13.71.195.47, 52.161.102.22, 13.66.140.128 - 13.66.140.143, 52.183.78.157, 52.161.26.191, 52.161.27.42, 52.161.29.40, 52.161.26.33, 13.66.213.240, 13.66.214.51, 13.66.210.166, 13.66.213.29 |

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
