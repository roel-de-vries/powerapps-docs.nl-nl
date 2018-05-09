---
title: PowerShell-ondersteuning | Microsoft Docs
description: PowerShell-ondersteuning voor PowerApps
services: powerapps
suite: powerapps
documentationcenter: na
author: jamesol-msft
manager: kfile
editor: ''
tags: ''
ms-topic: article
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/17/2018
ms.author: jamesol
ms.openlocfilehash: 274d34ca56cc993ec26fa4f4ced77bb2aba9985f
ms.sourcegitcommit: e3a2819c14ad67cc4ca6640b9064550d0f553d8f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/20/2018
---
# <a name="powershell-support-for-powerapps-preview"></a>PowerShell-ondersteuning voor PowerApps (preview-versie)

U kunt met de preview-introductie van de PowerShell-cmdlets voor app-ontwerpers en -beheerders een groot deel van de bewakings- en beheertaken automatiseren die nu alleen handmatig kunnen worden uitgevoerd in de [PowerApps-site](https://web.powerapps.com) of het [PowerApps-beheercentrum](https://admin.powerapps.com).

## <a name="installation"></a>Installatie
Als u de PowerShell-cmdlets voor app-ontwerpers wilt uitvoeren, moet u eerst de volgende stappen uitvoeren:

1. Download het bestand met PowerShell-scripts [hier](https://go.microsoft.com/fwlink/?linkid=872358).

2. Pak het bestand uit in een map.

3. Open als beheerder een PowerShell-opdrachtvenster in dezelfde map.

4. Voer vervolgens de volgende eenmalige PowerShell-opdracht uit (ervan uitgaande dat u nog nooit PowerShell-opdrachten hebt uitgevoerd op de huidige computer):

    ```
    Set-ExecutionPolicy -ExecutionPolicy Unrestricted -Force
    ```

5. Importeer vervolgens de vereiste modules met de volgende opdrachten:

    ```
    Import-Module .\Microsoft.PowerApps.Administration.PowerShell.psm1 -Force
    Import-Module .\Microsoft.PowerApps.PowerShell.psm1 -Force
    ```

6. Ten slotte moet u uw referenties invoeren met de volgende opdracht voordat u toegang tot de opdrachten kunt krijgen. Deze referenties worden vernieuwd voor maximaal ongeveer acht uur voordat u zich opnieuw moet aanmelden om het gebruik van de cmdlets voort te zetten.

    ```
    Add-PowerAppsAccount
    ```

## <a name="powerapps-cmdlets-for-app-makers-preview"></a>PowerApps-cmdlets voor app-ontwerpers (preview)

### <a name="prerequisite"></a>Vereisten
Alle gebruikers met een geldige PowerApps-licentie kunnen de bewerkingen in deze cmdlets uitvoeren. Ze hebben echter alleen toegang tot de resources (bijvoorbeeld apps, stromen enzovoort) die zijn gemaakt of die met hen zijn gedeeld.

### <a name="cmdlet-list"></a>Lijst met cmdlets
| Doel | Cmdlet |
| --- | --- |
| Omgevingen lezen | Get-PowerAppsEnvironment <br> Get-FlowEnvironment
| Een canvas-app lezen, bijwerken en verwijderen | Get-App <br> Remove-App <br> Publish-App <br> Set-AppDisplayName <br> Get-AppVersion <br> Restore-AppVersion
| Machtigingen voor canvas-apps lezen, bijwerken en verwijderen | Get-AppRoleAssignment <br> Set-AppRoleAssignment <br> Remove-AppRoleAssignment
| Een stroom lezen, bijwerken en verwijderen | Get-Flow <br> Get-FlowRun <br> Enable-Flow <br> Disable-Flow <br> Remove-Flow
| Machtigingen voor stromen lezen, bijwerken en verwijderen | Get-FlowOwnerRole <br> Set-FlowOwnerRole <br> Remove-FlowOwnerRole
| Stroomgoedkeuringen lezen en hierop reageren | Get-FlowApprovalRequest <br> Get-FlowApproval <br> RespondTo-FlowApprovalRequest
| Verbindingen lezen en verwijderen | Get-Connection <br> Remove-Connection
| Machtigingen voor verbindingen lezen, bijwerken en verwijderen | Get-ConnectionRoleAssignment <br> Set-ConnectionRoleAssignment <br> Remove-ConnectionRoleAssignment
| Connectoren lezen en verwijderen | Get-Connector <br> Remove-Connector
| Machtigingen voor connectoren lezen, bijwerken en verwijderen | Get-ConnectorRoleAssignment <br> Set-ConnectorRoleAssignment <br> Remove-ConnectorRoleAssignment

> [!NOTE]
> De volgende opdrachten kunnen worden gebruikt om de syntaxis te begrijpen en om voorbeelden voor elk van de cmdlets te bekijken:
>```
>Get-Help Get-PowerAppsEnvironment
>Get-Help Get-PowerAppsEnvironment -Examples
>Get-Help Get-PowerAppsEnvironment -Detailed
>```

## <a name="powerapps-cmdlets-for-administrators-preview"></a>PowerApps-cmdlets voor beheerders (preview-versie)

### <a name="prerequisite"></a>Vereisten
Als u de beheerbewerkingen in de beheer-cmdlets wilt uitvoeren, moet u een account met de volgende machtigingen hebben:

- Een betaalde licentie voor PowerApps-abonnement 2 of een licentie voor de proefversie van PowerApps-abonnement 2. U kunt zich aanmelden voor een 30-daagse licentie voor de proefversie op [http://web.powerapps.com/trial](http://web.powerapps.com/trial). Licenties voor de proefversie kunnen worden verlengd als ze zijn verlopen.

- U moet ook beschikken over de bevoegdheden van een [globale beheerder voor Office 365](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) of een [globale beheerder voor Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal) als u in de resources van een andere gebruiker moet zoeken. Anders hebt u alleen toegang tot omgevingen en omgevingsresources waarvoor u omgevingsbeheerdersbevoegdheden hebt.

### <a name="cmdlet-list"></a>Lijst met cmdlets
| Doel | Cmdlets
| --- | ---
| Omgevingen lezen en verwijderen | Get-AdminEnvironment <br> Remove-AdminEnvironment
| Bevoegdheden voor omgevingen lezen, bijwerken en verwijderen <br><br> *Deze cmdlets werken alleen voor omgevingen waarin geen Common Data Service for Apps-database aanwezig is.* | Get-AdminEnvironmentRoleAssignment <br> Set-AdminEnvironmentRoleAssignment <br> Remove-AdminEnvironmentRoleAssignment
| Canvas-apps lezen en verwijderen | Get-AdminApp <br> Remove-AdminApp
| Machtigingen voor canvas-apps lezen, bijwerken en verwijderen | Get-AdminAppRoleAssignment <br> Remove-AdminAppRoleAssignment <br> Set-AdminAppRoleAssignment <br> Set-AdminAppOwner
| Stromen lezen, bijwerken en verwijderen | Get-AdminFlow <br> Enable-AdminFlow <br> Disable-AdminFlow <br> Remove-AdminFlow  <br> Remove-AdminFlowOwnerRole

> [!NOTE]
> De volgende opdrachten kunnen worden gebruikt om de syntaxis te begrijpen en om een voorbeeld voor elk van de cmdlets te bekijken:
>```
>Get-Help Get-AdminEnvironment
>Get-Help Get-AdminEnvironment -Examples
>Get-Help Get-AdminEnvironment -Detailed
>```

## <a name="questions"></a>Vragen?

Als u eventuele opmerkingen, suggesties of vragen hebt, kunt u ze sturen naar de [Administering PowerApps Community Board](https://powerusers.microsoft.com/t5/Administering-PowerApps/bd-p/Admin_PowerApps).
