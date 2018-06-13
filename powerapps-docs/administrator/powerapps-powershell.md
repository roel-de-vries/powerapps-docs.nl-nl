---
title: PowerShell-ondersteuning (preview) | Microsoft Docs
description: Beschrijving van de verschillende PowerShell-cmdlets en een overzicht van hoe u ze installeert en uitvoert.
author: jamesol-msft
manager: kfile
ms.service: powerapps
ms.component: pa-admin
ms.topic: reference
ms.date: 05/23/2018
ms.author: jamesol
ms.openlocfilehash: 788f9ec1ce1ac8604606d2d2ad836a0cd12360d4
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34552985"
---
# <a name="powershell-support-for-powerapps-preview"></a>PowerShell-ondersteuning voor PowerApps (preview-versie)
U kunt met de preview-introductie van de PowerShell-cmdlets voor app-ontwerpers en -beheerders een groot deel van de bewakings- en beheertaken automatiseren die nu alleen handmatig kunnen worden uitgevoerd in [PowerApps](https://web.powerapps.com) of het [PowerApps-beheercentrum](https://admin.powerapps.com).

## <a name="installation"></a>Installatie
Ga als volgt te werk om de PowerShell-cmdlets voor app-ontwerpers uit te voeren:

1. Download het [bestand met PowerShell-scripts](https://go.microsoft.com/fwlink/?linkid=872358).

2. Pak het bestand uit in een map.

3. Open in dezelfde map een PowerShell-opdrachtvenster (als beheerder).

4. Voer de volgende eenmalige PowerShell-opdracht uit (ervan uitgaande dat u nog nooit PowerShell-opdrachten hebt uitgevoerd op de huidige computer):

    ```
    Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Force
    ```

5. Importeer de vereiste modules met de volgende opdrachten:

    ```
    Import-Module .\Microsoft.PowerApps.Administration.PowerShell.psm1 -Force
    Import-Module .\Microsoft.PowerApps.PowerShell.psm1 -Force
    ```

6.  Er is momenteel een [bekend probleem](https://powerusers.microsoft.com/t5/Administering-PowerApps/Getting-errors-when-I-try-to-import-the-preview-powerapps/td-p/109036) dat inhoudt dat u mogelijk ook de PowerShell-bestanden handmatig moet deblokkeren met de volgende opdracht:

    ```
    dir . | Unblock-File
    ```
7. Voordat u toegang tot de opdrachten kunt krijgen, moet u uw referenties invoeren met de volgende opdracht. Deze referenties worden vernieuwd voor maximaal ongeveer acht uur voordat u zich opnieuw moet aanmelden om het gebruik van de cmdlets voort te zetten.

    ```
    Add-PowerAppsAccount
    ```


## <a name="powerapps-cmdlets-for-app-creators-preview"></a>PowerApps-cmdlets voor app-ontwerpers (preview)

### <a name="prerequisite"></a>Vereisten
Gebruikers met een geldige PowerApps-licentie kunnen de bewerkingen in deze cmdlets uitvoeren, maar ze hebben alleen toegang tot de bronnen (bijvoorbeeld apps, stromen, enzovoort) die ze zelf hebben gemaakt of met hen zijn gedeeld.

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
> Gebruik de volgende opdrachten om de syntaxis te begrijpen en om voorbeelden voor elk van de cmdlets te bekijken:
>```
>Get-Help Get-PowerAppsEnvironment
>Get-Help Get-PowerAppsEnvironment -Examples
>Get-Help Get-PowerAppsEnvironment -Detailed
>```

## <a name="powerapps-cmdlets-for-administrators-preview"></a>PowerApps-cmdlets voor beheerders (preview-versie)

### <a name="prerequisite"></a>Vereisten
Om de beheerbewerkingen in de beheer-cmdlets uit te voeren, hebt u het volgende nodig:

* Een betaalde PowerApps-abonnement 2-licentie of een PowerApps-abonnement 2-evaluatielicentie. U kunt zich aanmelden voor een 30-daagse evaluatielicentie op [http://web.powerapps.com/trial](http://web.powerapps.com/trial). Evaluatielicenties kunnen worden vernieuwd als ze zijn verlopen.

* [Globale beheerder voor Office 365](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504)- of [globale beheerder Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal)-machtigingen als u in de resources van een andere gebruiker wilt zoeken. (Let op: omgevingsbeheerders hebben alleen toegang tot de omgevingen en omgevingsresources waarvoor ze machtigingen hebben.)

### <a name="cmdlet-list"></a>Lijst met cmdlets
| Doel | Cmdlets
| --- | ---
| Omgevingen lezen en verwijderen | Get-AdminEnvironment <br> Remove-AdminEnvironment
| Machtigingen voor omgevingen lezen, bijwerken en verwijderen <br><br> *Deze cmdlets werken alleen voor omgevingen waarin geen CDS voor apps-database aanwezig is.* | Get-AdminEnvironmentRoleAssignment <br> Set-AdminEnvironmentRoleAssignment <br> Remove-AdminEnvironmentRoleAssignment
| Canvas-apps lezen en verwijderen | Get-AdminApp <br> Remove-AdminApp
| Machtigingen voor canvas-apps lezen, bijwerken en verwijderen | Get-AdminAppRoleAssignment <br> Remove-AdminAppRoleAssignment <br> Set-AdminAppRoleAssignment <br> Set-AdminAppOwner
| Stromen lezen, bijwerken en verwijderen | Get-AdminFlow <br> Enable-AdminFlow <br> Disable-AdminFlow <br> Remove-AdminFlow  <br> Remove-AdminFlowOwnerRole
| Verbindingen lezen en verwijderen | Get-AdminConnection <br> Remove-AdminConnection
| Machtigingen voor verbindingen lezen, bijwerken en verwijderen | Get-AdminConnectionRoleAssignment <br> Set-AdminConnectionRoleAssignment <br> Remove-AdminConnectionRoleAssignment
| Aangepaste connectors lezen en verwijderen | Get-AdminConnector <br> Remove-AdminConnector
| Machtigingen voor connectoren lezen, bijwerken en verwijderen | Get-AdminConnectorRoleAssignment <br> Set-AdminConnectorRoleAssignment <br> Remove-AdminConnectorRoleAssignment
| PowerApps-gebruikersinstellingen, appinstellingen van gebruikers en meldingen van een gebruiker lezen | Get-AdminPowerAppsUserDetails
| De Microsoft Flow-instellingen van een gebruiker lezen en verwijderen die niet zichtbaar zijn voor de gebruiker maar die wel stroomuitvoering ondersteunen | Get-AdminFlowUserDetails <br> Remove-AdminFlowUserDetails
| Beleid met betrekking tot het voorkomen van gegevensverlies voor uw organisatie maken, lezen, bijwerken en verwijderen | Get-AdminApiPolicy <br> Add-AdminApiPolicy <br> Remove-AdminApiPolicy <br> Set-AdminApiPolicy <br> Add-ConnectorToBusinessDataGroup <br>  Remove-ConnectorFromBusinessDataGroup

> [!NOTE]
> Gebruik de volgende opdrachten om de syntaxis te begrijpen en om een voorbeeld voor elk van de cmdlets te bekijken:
>```
>Get-Help Get-AdminEnvironment
>Get-Help Get-AdminEnvironment -Examples
>Get-Help Get-AdminEnvironment -Detailed
>```

## <a name="questions"></a>Vragen?

Eventuele opmerkingen, suggesties of vragen kunt u publiceren op [Administering PowerApps Community Board](https://powerusers.microsoft.com/t5/Administering-PowerApps/bd-p/Admin_PowerApps).
