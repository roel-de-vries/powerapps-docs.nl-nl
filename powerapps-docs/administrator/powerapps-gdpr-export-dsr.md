---
title: Reageren op AVG-aanvragen voor het exporteren van PowerApps-gegevens van de klant | Microsoft Docs
description: Instructies voor het reageren op aanvragen van betrokkenen voor het exporteren van PowerApps-gegevens van de klant.
author: jamesol-msft
manager: kfile
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 05/23/2018
ms.author: jamesol
ms.openlocfilehash: 000f15ea7b1fa4e11cbe49b44e57017daf973a89
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34552962"
---
# <a name="responding-to-data-subject-rights-dsr-requests-to-export-powerapps-customer-data"></a>Reageren op AVG-aanvragen voor het exporteren van PowerApps-gegevens van de klant
Op basis van het ‘recht op overdraagbaarheid van gegevens’ heeft een betrokkene het recht een kopie van zijn of haar persoonlijke gegevens in elektronische vorm (dat wil zeggen een gestructureerde, gangbare en machineleesbare vorm) op te vragen, die kan worden overgedragen aan een andere verwerkingsverantwoordelijke:

* Websitetoegang: [PowerApps-portal](https://web.powerapps.com), [PowerApps-beheercentrum](https://admin.powerapps.com/) en [Office 365 Service Trust Portal](https://servicetrust.microsoft.com/)

* PowerShell-toegang: PowerApps [cmdlets voor app-ontwikkelaars](https://go.microsoft.com/fwlink/?linkid=871448), [Admin-cmdlets](https://go.microsoft.com/fwlink/?linkid=871804) en [On-premises gateway-cmdlets](https://go.microsoft.com/fwlink/?linkid=872238)

Hieronder volgt een samenvatting van de soorten persoonlijke gegevens die via PowerApps kunnen worden opgeslagen voor een specifieke gebruiker en hoe u deze kunt vinden en exporteren.

Resources met persoonlijke gegevens | Website-toegang |   PowerShell-toegang
--- | --- | --
Omgeving | PowerApps-beheercentrum |  PowerApps-cmdlets
Omgevingsmachtigingen**   | PowerApps-beheercentrum    | PowerApps-cmdlets
Canvas-app  | PowerApps-beheercentrum <br> PowerApps-portal |    PowerApps-cmdlets
Machtigingen voor canvas-apps  | PowerApps-beheercentrum <br> PowerApps-portal  | PowerApps-cmdlets
Gateway | PowerApps-portal***   | Cmdlets voor on-premises gateway
Gatewaymachtigingen | PowerApps-portal***   |
Aangepaste connector | |    App-ontwikkelaar: beschikbaar <br> Beheerder: beschikbaar
Machtigingen voor aangepaste connectors | |    App-ontwikkelaar: beschikbaar <br> Beheerder: beschikbaar
Verbinding | | App-ontwikkelaar: beschikbaar <br> Beheerder: beschikbaar
Verbindingsmachtigingen  | | App-ontwikkelaar: beschikbaar <br> Beheerder: beschikbaar
PowerApps-gebruikersinstellingen, gebruikers-app-instellingen en meldingen | | App-ontwikkelaar: beschikbaar <br> Beheerder: beschikbaar

> **Als er, na de introductie van de Common Data Service (CDS) for Apps, een database wordt gemaakt binnen de omgeving, worden omgevingsmachtigingen en machtigingen voor modelgestuurde apps opgeslagen als records in de CDS for Apps-database-instantie. Zie [Responding to Data Subject Rights (DSR) requests for Common Data Service for Apps customer data](common-data-service-gdpr-dsr-guide.md) (Reageren op AVG-aanvragen voor Common Data Service for Apps-gegevens van de klant) voor instructies over het reageren op AVG-aanvragen van gebruikers die CDS for Apps gebruiken.

> *** Een beheerder heeft alleen toegang tot deze resources uit de [PowerApps-portal](https://web.powerapps.com) als de eigenaar van de resource hem of haar expliciet toegang heeft verleend. Als er geen toegang aan de beheerder is verleend, moet hij of zij gebruikmaken van de [PowerApps-cmdlets voor PowerApps-beheerders](https://go.microsoft.com/fwlink/?linkid=871804).

## <a name="prerequisites"></a>Vereisten

### <a name="for-users"></a>Voor gebruikers
Elke gebruiker met een geldige PowerApps-licentie kan de in dit document beschreven gebruikersbewerkingen uitvoeren met de [PowerApps-portal](https://web.powerapps.com) of de [cmdlets voor app-ontwikkelaars](https://go.microsoft.com/fwlink/?linkid=871448).

### <a name="for-admins"></a>Voor beheerders
Als u met het PowerApps-beheercentrum, Microsoft Flow-beheercentrum of [PowerShell-cmdlets voor PowerApps-beheerders](https://go.microsoft.com/fwlink/?linkid=871804) de beheerbewerkingen wilt uitvoeren die in dit document worden beschreven, hebt u het volgende nodig:

* Een betaalde PowerApps-abonnement 2-licentie of een PowerApps-abonnement 2-evaluatielicentie. U kunt zich aanmelden voor een 30-daagse evaluatielicentie op [http://web.powerapps.com/trial](http://web.powerapps.com/trial). Evaluatielicenties kunnen worden vernieuwd als ze zijn verlopen.

* [Globale beheerder voor Office 365](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504)- of [globale beheerder Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal)-machtigingen als u in de resources van een andere gebruiker wilt zoeken. (Let op: omgevingsbeheerders hebben alleen toegang tot de omgevingen en omgevingsresources waarvoor ze machtigingen hebben.)

## <a name="step-1-export-personal-data-contained-within-environments-created-by-the-user"></a>Stap 1: persoonlijke gegevens exporteren uit omgevingen die door de gebruiker zijn gemaakt

### <a name="powerapps-admin-center"></a>PowerApps-beheercentrum
Beheerders kunnen alle omgevingen die zijn gemaakt door een specifieke gebruiker vanuit het [PowerApps-beheercentrum](https://admin.powerapps.com/) exporteren door de volgende stappen te volgen:

1. Selecteer vanuit het [PowerApps-beheercentrum](https://admin.powerapps.com/) elke omgeving in uw organisatie.

    ![Landingspagina van het beheercentrum](./media/powerapps-gdpr-export-dsr/admin-center-landing.png)

2. Als de omgeving is gemaakt door de gebruiker van de AVG-aanvraag, gaat u naar de pagina **Details**, kopieert u de details en plakt u deze in een document-editor, zoals Microsoft Word.

    ![Omgevingsdetails](./media/powerapps-gdpr-export-dsr/environment-details.png)

### <a name="powershell-cmdlets-for-app-creators"></a>PowerShell-cmdlets voor app-ontwikkelaars
Gebruikers kunnen de omgevingen waartoe ze toegang hebben in PowerApps exporteren met de functie **Get-PowerAppsEnvironment** in de [PowerShell-cmdlets voor PowerApps-ontwikkelaars](https://go.microsoft.com/fwlink/?linkid=871448):

~~~~
Add-PowerAppsAccount
Get-PowerAppsEnvironment | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

### <a name="powershell-cmdlets-for-admins"></a>PowerShell-cmdlets voor beheerders
Beheerders kunnen alle omgevingen die zijn gemaakt door een gebruiker exporteren met de functie **Get-AdminEnvironment** in de [PowerShell-cmdlets voor PowerApps-beheerders](https://go.microsoft.com/fwlink/?linkid=871804):

~~~~
Add-PowerAppsAccount
$userId = "7557f390-5f70-4c93-8bc4-8c2faabd2ca0"
Get-AdminEnvironment -CreatedBy $userId | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~
 
## <a name="step-2-export-the-users-environment-permissions"></a>Stap 2: de omgevingsmachtigingen van de gebruiker exporteren
Aan gebruikers kunnen in een omgeving machtigingen worden toegewezen (zoals Omgevingsbeheerder, Omgevingsmaker, enzovoort), die in PowerApps worden opgeslagen als een *roltoewijzing*. Als er, na de introductie van CDS for Apps, een database wordt gemaakt binnen de omgeving, worden de roltoewijzingen opgeslagen als records in de CDS for Apps-database-instantie. Zie [Omgevingen beheren binnen PowerApps](environments-administration.md) voor meer informatie.

### <a name="for-environments-without-a-cds-for-apps-database"></a>Voor omgevingen zonder een CDS for Apps-database

#### <a name="powerapps-admin-center"></a>PowerApps-beheercentrum
Beheerders kunnen de omgevingsmachtigingen van een gebruiker vanuit het [PowerApps-beheercentrum](https://admin.powerapps.com/) exporteren door de volgende stappen te volgen:

1. Selecteer vanuit het [PowerApps-beheercentrum](https://admin.powerapps.com/) elke omgeving in uw organisatie. U moet een [globale beheerder voor Office 365](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) of [globale beheerder van Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal) zijn om alle omgevingen te kunnen controleren die binnen uw organisatie zijn gemaakt.

    ![Landingspagina van het beheercentrum](./media/powerapps-gdpr-export-dsr/admin-center-landing.png)

2. Selecteer **Beveiliging**.

    Als uw omgeving geen CDS for Apps-database heeft, ziet u een sectie voor **Omgevingsrollen.**

3. Selecteer onafhankelijk van elkaar **Omgevingsbeheerder** en **Omgevingsmaker** en zoek de naam van de gebruiker via de zoekbalk.

    ![Pagina Omgevingsrollen](./media/powerapps-gdpr-export-dsr/admin-environment-role-share-page.png)

4. Als de gebruiker toegang tot een van beide rollen heeft, gaat u naar de pagina **Gebruikers**, kopieert u de details en plakt u deze in een document-editor, zoals Microsoft Word.

#### <a name="powershell-cmdlets-for-admins"></a>PowerShell-cmdlets voor beheerders
Beheerders kunnen alle omgevingsroltoewijzingen voor een gebruiker in alle omgevingen zonder een CDS for Apps-database exporteren met de functie **Get-AdminEnvironmentRoleAssignment** in de [PowerShell-cmdlets voor PowerApps-beheerders](https://go.microsoft.com/fwlink/?linkid=871804):

~~~~
Add-PowerAppsAccount
$userId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
Get-AdminEnvironmentRoleAssignment -UserId $userId | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

> [!IMPORTANT]
>  Deze functie werkt alleen voor omgevingen zonder CDS for Apps database-instantie.
>
>

### <a name="for-environments-with-a-cds-for-apps-database"></a>Voor omgevingen met een CDS for Apps-database
Als er, na de introductie van CDS for Apps, een database wordt gemaakt binnen de omgeving, worden roltoewijzingen opgeslagen als records in de CDS for Apps-database-instantie. Zie [Common Data Service User personal data removal](https://go.microsoft.com/fwlink/?linkid=871886) (Verwijderen van persoonlijke gegevens van gebruikers uit Common Data Service) voor meer informatie over het verwijderen van persoonlijke gegevens uit een CDS for Apps-database-instantie.
 
## <a name="step-3-export-personal-data-contained-within-canvas-apps-created-by-the-user"></a>Stap 3: persoonlijke gegevens exporteren uit canvas-apps die door de gebruiker zijn gemaakt

### <a name="powerapps-portal"></a>PowerApps-portal
Een gebruiker kan een app exporteren uit de [PowerApps-portal](https://web.powerapps.com). Zie [Een app exporteren](environment-and-tenant-migration.md#exporting-an-app) voor stapsgewijze instructies voor het exporteren van een app.

### <a name="powerapps-admin-center"></a>PowerApps-beheercentrum
Een beheerder kan alle apps die zijn gemaakt door een gebruiker vanuit het [PowerApps-beheercentrum](https://admin.powerapps.com/) exporteren door de volgende stappen te volgen:

1. Selecteer vanuit het [PowerApps-beheercentrum](https://admin.powerapps.com/) elke omgeving in uw organisatie. U moet een [globale beheerder voor Office 365](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) of [globale beheerder van Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal) zijn om alle omgevingen te kunnen controleren die binnen uw organisatie zijn gemaakt.

    ![Landingspagina van het beheercentrum](./media/powerapps-gdpr-export-dsr/admin-center-landing.png)

2. Selecteer **Resources** en selecteer vervolgens **Apps**.

3. Zoek via de zoekbalk de naam van de gebruiker. Zo vindt u alle apps die door die gebruiker in deze omgeving zijn gemaakt:

    ![Apps zoeken](./media/powerapps-gdpr-export-dsr/search-apps.png)

4. Selecteer **Share** voor elke app die is gemaakt door deze gebruiker en geef uzelf **Kan bewerken**-toegang tot de app:

    ![App delen selecteren](./media/powerapps-gdpr-export-dsr/select-share.png)

    ![Een gebruiker toegang geven](./media/powerapps-gdpr-export-dsr/grant-access.png)

5. Zodra u voor alle apps van de gebruiker toegang hebt, kunt u een app exporteren uit de [PowerApps-portal](https://web.powerapps.com). Zie [Een app exporteren](environment-and-tenant-migration.md#exporting-an-app) voor stapsgewijze instructies voor het exporteren van een app.

### <a name="powershell-cmdlets-for-admins"></a>PowerShell-cmdlets voor beheerders
Beheerders kunnen apps die zijn gemaakt door een gebruiker exporteren met de functie **Get-AdminApp** in de [PowerShell-cmdlets voor PowerApps-beheerders](https://go.microsoft.com/fwlink/?linkid=871804):

~~~~
Add-PowerAppsAccount
$userId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
Get-AdminApp -Owner $userId | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

## <a name="step-4-export-the-users-permissions-to-canvas-apps"></a>Stap 4: de machtigingen van de gebruiker voor canvas-apps exporteren
Wanneer een app met een gebruiker wordt gedeeld, wordt in PowerApps een record opgeslagen dat een *roltoewijzing* wordt genoemd. Deze roltoewijzing beschrijft de machtigingen van de gebruiker (CanEdit of CanUse) voor de toepassing. Zie [Een app delen](../maker/canvas-apps/share-app.md#share-an-app) voor meer informatie.

### <a name="powershell-cmdlets-for-app-creators"></a>PowerShell-cmdlets voor app-ontwikkelaars
Gebruikers kunnen de roltoewijzing van de app voor alle apps waartoe ze toegang hebben exporteren met de functie **Get-RoleAssignment** in de [PowerShell-cmdlets voor PowerApps-ontwikkelaars](https://go.microsoft.com/fwlink/?linkid=871448):

~~~~
Add-PowerAppsAccount
Get-AppRoleAssignment | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

### <a name="powerapps-admin-center"></a>PowerApps-beheercentrum
Beheerders kunnen app-roltoewijzingen voor een gebruiker vanuit het [PowerApps-beheercentrum](https://admin.powerapps.com/) exporteren door de volgende stappen te volgen:

1. Selecteer vanuit het [PowerApps-beheercentrum](https://admin.powerapps.com/) elke omgeving in uw organisatie. U moet een [globale beheerder voor Office 365](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) of [globale beheerder van Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal) zijn om alle omgevingen te kunnen controleren die binnen uw organisatie zijn gemaakt.

    ![Landingspagina van het beheercentrum](./media/powerapps-gdpr-export-dsr/admin-center-landing.png)

2. Selecteer voor elke omgeving **Resources** en selecteer vervolgens **Apps**.

3. Selecteer **Delen** voor elke app in de omgeving.

    ![App delen selecteren](./media/powerapps-gdpr-export-dsr/select-admin-share-nofilter.png)

4. Als de gebruiker toegang heeft tot de app, gaat u naar de pagina **Delen** van de app, kopieert u de details en plakt u deze in een document-editor, zoals Microsoft Word.

    ![Beheerpagina app delen](./media/powerapps-gdpr-export-dsr/admin-share-page.png)

### <a name="powershell-cmdlets-for-admins"></a>PowerShell-cmdlets voor beheerders
Beheerders kunnen alle roltoewijzingen van apps voor een gebruiker voor alle apps in hun tenant exporteren met de functie **Get-AdminAppRoleAssignment** in de [PowerShell-cmdlets voor PowerApps-beheerders](https://go.microsoft.com/fwlink/?linkid=871804):

~~~~
Add-PowerAppsAccount
$userId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
Get-AdminAppRoleAssignment -UserId $userId | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

## <a name="step-5-export-personal-data-contained-within-connections-created-by-the-user"></a>Stap 5: persoonlijke gegevens exporteren uit verbindingen die door de gebruiker zijn gemaakt
Verbindingen worden gebruikt in combinatie met connectors bij het maken van verbinding met andere API's en SaaS-systemen. Verbindingen bevatten verwijzingen naar de gebruiker door wie ze zijn gemaakt en kunnen, als gevolg hiervan, worden verwijderd om alle verwijzingen naar de gebruiker te verwijden.

### <a name="powershell-cmdlets-for-app-creators"></a>PowerShell-cmdlets voor app-ontwikkelaars
Gebruikers kunnen alle verbindingen waartoe ze toegang hebben exporteren met de functie **Get-Connection** in de [PowerShell-cmdlets voor PowerApps-ontwikkelaars](https://go.microsoft.com/fwlink/?linkid=871448):

~~~~
Add-PowerAppsAccount
Get-Connection | ConvertTo-Json | out-file -FilePath "UserDetails.json"
~~~~

### <a name="powershell-cmdlets-for-admins"></a>PowerShell-cmdlets voor beheerders
Beheerders kunnen alle verbindingen die zijn gemaakt door een gebruiker exporteren met de functie **Get-AdminConnection** in de [PowerShell-cmdlets voor PowerApps-beheerders](https://go.microsoft.com/fwlink/?linkid=871804):

~~~~
Add-PowerAppsAccount
$userId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
Get-AdminConnection -CreatedBy $userId | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~
 
## <a name="step-6-export-the-users-permissions-to-shared-connections"></a>Stap 6: de machtigingen van de gebruiker voor gedeelde verbindingen exporteren

### <a name="powershell-cmdlets-for-app-creators"></a>PowerShell-cmdlets voor app-ontwikkelaars
Gebruikers kunnen de roltoewijzing van de verbinding voor alle verbindingen waartoe ze toegang hebben exporteren met de functie **Get-ConnectionRoleAssignment** in de [PowerShell-cmdlets voor PowerApps-ontwikkelaars](https://go.microsoft.com/fwlink/?linkid=871448):

~~~~
Add-PowerAppsAccount
Get-ConnectionRoleAssignment | ConvertTo-Json | Out-file -FilePath "UserDetails.json"
~~~~

### <a name="powershell-cmdlets-for-admins"></a>PowerShell-cmdlets voor beheerders
Beheerders kunnen alle roltoewijzingen van verbindingen voor een gebruiker exporteren met de functie **Get-AdminConnectionRoleAssignment** in de [PowerShell-cmdlets voor PowerApps-beheerders](https://go.microsoft.com/fwlink/?linkid=871804):

~~~~
Add-PowerAppsAccount
$userId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
Get-AdminConnectionRoleAssignment -PrincipalObjectId $userId | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

## <a name="step-7-export-personal-data-contained-within-custom-connectors-created-by-the-user"></a>Stap 7: persoonlijke gegevens exporteren uit aangepaste connectors die door de gebruiker zijn gemaakt
Aangepaste connectors vormen een aanvulling op de bestaande standaard-connectors en maken connectiviteit met andere API's, SaaS en aangepaste systemen mogelijk.

### <a name="powerapps-app-creator-powershell-cmdlets"></a>PowerShell-cmdlets voor PowerApps-ontwikkelaars
Gebruikers kunnen alle aangepaste connectors die ze hebben gemaakt exporteren met de functie **Get-Connector** in de [PowerShell-cmdlets voor PowerApps-ontwikkelaars](https://go.microsoft.com/fwlink/?linkid=871448):

~~~~
Add-PowerAppsAccount  
Get-Connector -FilterNonCustomConnectors | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

### <a name="powershell-cmdlets-for-admins"></a>PowerShell-cmdlets voor beheerders
Beheerders kunnen alle aangepaste connectors die zijn gemaakt door een gebruiker exporteren met de functie **Get-AdminConnector** in de [PowerShell-cmdlets voor PowerApps-beheerders](https://go.microsoft.com/fwlink/?linkid=871804):

~~~~
Add-PowerAppsAccount
$userId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
Get-AdminConnector -CreatedBy $userId | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

## <a name="step-8-export-the-users-permissions-to-custom-connectors"></a>Stap 8: de machtigingen van de gebruiker voor aangepaste connectors exporteren

### <a name="powershell-cmdlets-for-app-creators"></a>PowerShell-cmdlets voor app-ontwikkelaars
Gebruikers kunnen alle roltoewijzingen van de connector voor de aangepaste connectors waartoe ze toegang hebben exporteren met de functie **Get-ConnectorRoleAssignment** in de [PowerShell-cmdlets voor PowerApps-ontwikkelaars](https://go.microsoft.com/fwlink/?linkid=871448):

~~~~
Add-PowerAppsAccount  
Get-ConnectorRoleAssignment | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

### <a name="powershell-cmdlets-for-admins"></a>PowerShell-cmdlets voor beheerders
Beheerders kunnen alle aangepaste connectorroltoewijzingen voor een gebruiker exporteren met de functie **Get-AdminConnectorRoleAssignment** in de [PowerShell-cmdlets voor PowerApps-beheerders](https://go.microsoft.com/fwlink/?linkid=871804):

~~~~
Add-PowerAppsAccount
$userId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
Get-AdminConnectorRoleAssignment -PrincipalObjectId $userId | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~
 
## <a name="step-9-export-powerapps-notifications-user-settings-and-user-app-settings"></a>Stap 9: meldingen van PowerApps, gebruikersinstellingen en gebruikers-app-instellingen exporteren
PowerApps verzendt verschillende typen meldingen aan gebruikers, zoals wanneer een app met hen wordt gedeeld en wanneer een CDS for Apps-exportbewerking is voltooid. De meldingsgeschiedenis van een gebruiker is voor de gebruiker zichtbaar binnen de [PowerApps-portal](https://web.powerapps.com).

In PowerApps worden tevens verschillende gebruikersvoorkeuren en -instellingen opgeslagen die worden gebruikt om de PowerApps-runtime- en portalervaringen te delen, waaronder wanneer een gebruiker voor het laatst een toepassing heeft geopend, een app heeft vastgemaakt, enzovoort.

### <a name="powershell-cmdlets-for-app-creators"></a>PowerShell-cmdlets voor app-ontwikkelaars
Gebruikers kunnen hun eigen PowerApps-meldingen, gebruikersinstellingen en gebruikersapp-instellingen exporteren met de functie **Get-AdminPowerAppsUserDetails** in de [PowerShell-cmdlets voor PowerApps-ontwikkelaars](https://go.microsoft.com/fwlink/?linkid=871448):

~~~~
Add-PowerAppsAccount  
Get-AdminPowerAppsUserDetails -WriteToFile -OutputFilePath "UserDetails.json"
~~~~

### <a name="powershell-cmdlets-for-admins"></a>PowerShell-cmdlets voor beheerders
Beheerders kunnen de PowerApps-meldingen, gebruikersinstellingen en gebruikersapp-instellingen van een gebruiker exporteren met de functie **Get-AdminPowerAppsUserDetails** in de [PowerShell-cmdlets voor PowerApps-beheerders](https://go.microsoft.com/fwlink/?linkid=871804):

~~~~
Add-PowerAppsAccount
$userId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
Get-AdminPowerAppsUserDetails -WriteToFile -OutputFilePath "UserDetails.json" -UserPrincipalName foobar@microsoft.com
~~~~

## <a name="step-10-export-personal-data-contained-for-a-user-stored-gateway-or-in-the-users-gateway-permissions"></a>Stap 10: persoonlijke gegevens exporteren die zijn opgeslagen in door een gebruiker opgeslagen gateway of in de gebruikersmachtigingen voor de gateway

### <a name="powerapps-portal"></a>PowerApps-portal
Gebruikers kunnen uit de [PowerApps-portal](https://web.powerapps.com) persoonsgegevens exporteren die zijn opgeslagen in de gatewayservice door de volgende stappen te volgen:

1. Selecteer uit de [PowerApps-portal](https://web.powerapps.com), binnen de standaardomgeving voor uw tenant, de optie **Gateways** en selecteer vervolgens **Details** voor elke gateway waartoe u toegang hebt.

    ![Landingspagina van de gateway](./media/powerapps-gdpr-export-dsr/gateway-select-details.png)

2. Als de gegevens van de gateway persoonlijke gegevens bevatten, kopieert u op de pagina **Details** deze gegevens en plakt u deze in een document-editor, zoals Microsoft Word.

    ![Gegevens van de gateway](./media/powerapps-gdpr-export-dsr/gateway-details-drillin.png)

3. Selecteer **Delen**, kopieer de inhoud van de pagina en plak dit in een document-editor, zoals Microsoft Word.

    ![Gegevens van de gateway](./media/powerapps-gdpr-export-dsr/gateway-details-share.png)

### <a name="gateway-powershell-cmdlets"></a>PowerShell-cmdlets voor de gateway
Er zijn ook PowerShell-cmdlets waarmee u uw persoonlijke gateways kunt ophalen, beheren en verwijderen. Zie [On-premises gateway-cmdlets](https://go.microsoft.com/fwlink/?linkid=872238) voor meer informatie.

### <a name="administrators"></a>Beheerders
Raadpleeg het gedeelte **Tenantbeheer** in het artikel [On-premises gegevensgateways voor Microsoft PowerApps leren kennen](https://docs.microsoft.com/powerapps/maker/canvas-apps/gateway-reference#tenant-level-administration) voor richtlijnen met betrekking tot het beheren van gateways voor uw organisatie.

## <a name="step-11-export-the-users-personal-data-in-microsoft-flow"></a>Stap 11: de persoonlijke gegevens van de gebruiker in Microsoft Flow exporteren
PowerApps-licenties omvatten altijd Microsoft Flow-mogelijkheden. Behalve dat Microsoft Flow is opgenomen in PowerApps-licenties, is Microsoft Flow ook beschikbaar als een zelfstandige service. Zie [Responding to GDPR Data Subject Requests for Microsoft Flow](https://go.microsoft.com/fwlink/?linkid=872250) (Reageren op AGV-aanvragen voor gegevensonderwerpen voor Microsoft Flow) voor instructies over het reageren op AVG-aanvragen van gebruikers die de Microsoft Flow-service gebruiken.

> [!IMPORTANT]
>  Het is raadzaam deze stap door beheerders te laten uitvoeren voor PowerApps-gebruikers.
>
>

## <a name="step-12-export-the-users-personal-data-in-cds-for-apps-instances"></a>Stap 12: de persoonlijke gegevens van de gebruiker in CDS for Apps-instanties exporteren
Met bepaalde PowerApps-licenties kunnen gebruikers binnen uw organisatie CDS for Apps-instanties maken en apps maken en bouwen op CDS for Apps. Dit kan onder andere met het PowerApps Community-abonnement: dit is een gratis licentie waarmee gebruikers CDS for Apps kunnen proberen in een individuele omgeving. Zie de [pagina met prijzen voor PowerApps](https://powerapps.microsoft.com/pricing) als u wilt zien welke CDS for Apps-mogelijkheden elke PowerApps-licentie bevat.

Zie [Responding to Data Subject Rights (DSR) requests for Common Data Service for Apps customer data](common-data-service-gdpr-dsr-guide.md) (Reageren op AVG-aanvragen voor Common Data Service for Apps-gegevens van de klant) voor instructies over het reageren op AVG-aanvragen van gebruikers die CDS for Apps gebruiken.

> [!IMPORTANT]
>  Het is raadzaam deze stap door beheerders te laten uitvoeren voor PowerApps-gebruikers.
>
>
