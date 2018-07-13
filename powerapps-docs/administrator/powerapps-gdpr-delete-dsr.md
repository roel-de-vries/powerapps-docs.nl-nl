---
title: Reageren op AVG-aanvragen voor het verwijderen van klantgegevens | Microsoft Docs
description: Instructies voor hoe u moet reageren op aanvragen van betrokkenen voor het verwijderen van PowerApps-gegevens van de klant.
author: jamesol-msft
manager: kfile
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 05/23/2018
ms.author: jamesol
ms.openlocfilehash: d518cbf398d0f29b25da9dafcfa6e9026fcee88e
ms.sourcegitcommit: 79b8842fb0f766a0476dae9a537a342c8d81d3b3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2018
ms.locfileid: "37897174"
---
# <a name="responding-to-data-subject-rights-dsr-requests-to-delete-powerapps-customer-data"></a>Reageren op AVG-aanvragen voor het verwijderen van PowerApps-gegevens van de klant

Het ‘recht op wissing’ door het verwijderen van persoonlijke gegevens uit de klantgegevens van een organisatie, is een belangrijke beschermingsmaatregel in de Algemene verordening gegevensbescherming (AVG) van de Europese Unie (EU). Het verwijderen van persoonlijke gegevens omvat het verwijderen van door het systeem gegenereerde logboeken, maar niet gegevens uit auditlogboeken.

Met PowerApps kunnen gebruikers Line-Of-Business-toepassingen ontwikkelen die een belangrijk onderdeel vormen van de dagelijkse bedrijfsvoering van uw organisatie. Wanneer een gebruiker uw organisatie verlaat, moet u handmatig controleren en bepalen of bepaalde gegevens en resources die de gebruiker heeft gemaakt, moeten worden verwijderd. Andere persoonlijke gegevens worden automatisch verwijderd wanneer het account van de gebruiker wordt verwijderd uit Azure Active Directory.

Hieronder is uitgesplitst welke persoonlijke gegevens automatisch worden verwijderd en welke gegevens u handmatig moet controleren en verwijderen:

Moet handmatig worden gecontroleerd en verwijderen |   Wordt automatisch verwijderd wanneer de gebruiker wordt verwijderd uit Azure Active Directory
--- | ---
Omgeving\** | Gateway
Omgevingsmachtigingen\*** | Gateway-machtigingen
Canvas-app\** | PowerApps-meldingen
Machtigingen voor canvas-apps | Gebruikersinstellingen voor PowerApps
Verbinding\** | Gebruikers-app-instellingen voor PowerApps
Verbindingsmachtigingen |
Aangepaste connector\** |
Machtigingen voor aangepaste connector |  

\** Elk van deze resources bevat records Gemaakt door- en Gewijzigd door-records die persoonlijke gegevens bevatten. Uit veiligheidsoverwegingen wordt deze records bewaard totdat de resource wordt verwijderd.

\*** Voor omgevingen met een CDS for Apps-database (Common Data Service), worden omgevingsmachtigingen (dat wil zeggen, welke gebruikers zijn toegewezen aan de rollen Omgevingsmaker en Omgevingsbeheerder) opgeslagen als records in die database. Zie [Responding to Data Subject Rights (DSR) requests for Common Data Service for Apps customer data](common-data-service-gdpr-dsr-guide.md) (Reageren op AVG-aanvragen voor Common Data Service for Apps-gegevens van de klant) voor instructies over het reageren op AVG-aanvragen van gebruikers die CDS for Apps gebruiken.

Voor de gegevens en resources waarvoor handmatige controle vereist is, biedt PowerApps de volgende ervaringen voor het opnieuw toewijzen (indien van toepassing) of verwijderen van persoonlijke gegevens voor een specifieke gebruiker:

* Website-toegang: [PowerApps-site](https://web.powerapps.com), [PowerApps-beheercentrum](https://admin.powerapps.com/) en [Office 365 Trust Portal](https://servicetrust.microsoft.com/)

* PowerShell-toegang: PowerApps-cmdlets voor [app-ontwikkelaars](https://go.microsoft.com/fwlink/?linkid=871448) en [beheerders](https://go.microsoft.com/fwlink/?linkid=871804) en cmdlets voor [on-premises gateways](https://go.microsoft.com/fwlink/?linkid=872238).

Hieronder is uitgesplitst welke ervaringen beschikbaar zijn voor het verwijderen van elk type resource dat persoonlijke gegevens bevat:

Resources met persoonsgegevens | Website-toegang | PowerShell-toegang
--- | --- | ---
Omgeving | PowerApps-beheercentrum |  PowerApps-cmdlets
Omgevingsmachtigingen**   | PowerApps-beheercentrum | PowerApps-cmdlets
Canvas-app  | PowerApps-beheercentrum <br> PowerApps| PowerApps-cmdlets
Machtigingen voor canvas-apps  | PowerApps-beheercentrum | PowerApps-cmdlets
Verbinding | | App-ontwikkelaar: beschikbaar <br> Beheerder: beschikbaar
Verbindingsmachtigingen | | App-ontwikkelaar: beschikbaar <br> Beheerder: beschikbaar
Aangepaste connector | | App-ontwikkelaar: beschikbaar <br> Beheerder: beschikbaar
Machtigingen voor aangepaste connector | | App-ontwikkelaar: beschikbaar <br> Beheerder: beschikbaar

\***Als er, na de introductie van de CDS for Apps, een database wordt gemaakt binnen de omgeving, worden omgevingsmachtigingen en machtigingen voor modelgestuurde apps opgeslagen als records in de instantie van die database. Zie [Responding to Data Subject Rights (DSR) requests for Common Data Service for Apps customer data](common-data-service-gdpr-dsr-guide.md) (Reageren op AVG-aanvragen voor Common Data Service for Apps-gegevens van de klant) voor instructies over het reageren op AVG-aanvragen van gebruikers die CDS for Apps gebruiken.

## <a name="prerequisites"></a>Vereisten

### <a name="for-users"></a>Voor gebruikers
Elke gebruiker met een geldige PowerApps-licentie kan de in dit document beschreven gebruikersbewerkingen uitvoeren met [PowerApps](https://web.powerapps.com) of de [PowerShell-cmdlets voor app-ontwikkelaars](https://go.microsoft.com/fwlink/?linkid=871448).

#### <a name="unmanaged-tenant"></a>Onbeheerde tenant
Als u lid bent van een [onbeheerde tenant](https://docs.microsoft.com/azure/active-directory/domains-admin-takeover), wat betekent dat uw Azure AD-tenant geen algemene beheerder heeft, kunt u nog steeds de in dit artikel beschreven stappen volgen voor het verwijderen van uw eigen persoonsgegevens.  Omdat er echter geen algemene beheerder voor uw tenant is, moet u de instructies volgen die in [Stap 11: de gebruiker uit Azure Active Directory verwijderen](#step-11-delete-the-user-from-azure-active-directory) hieronder zijn beschreven om uw eigen account uit de tenant te verwijderen.

Bepaal aan de hand van de volgende stappen of u lid bent van een onbeheerde tenant:

1. Open de volgende URL in een browser en let daarbij op dat u uw e-mailadres in de URL vervangt: https://login.windows.net/common/userrealm/foobar@contoso.com?api-version=2.1

2. Als u lid bent van een **onbeheerde tenant**, ziet u een `"IsViral": true` in het antwoord.
   ```
   {
   ...
   "Login": "foobar@unmanagedcontoso.com",
   "DomainName": "unmanagedcontoso.com",
   "IsViral": true,
   ...
   }
   ```

3. Anders behoort u toe aan een **beheerde tenant**.

### <a name="for-administrators"></a>Voor beheerders
Als u met het [PowerApps-beheercentrum](https://admin.powerapps.com/), het Microsoft Flow-beheercentrum of [PowerShell-cmdlets voor PowerApps-beheerders](https://go.microsoft.com/fwlink/?linkid=871804) de beheerbewerkingen wilt uitvoeren die in dit document worden beschreven, hebt u het volgende nodig:

* Een betaalde PowerApps-abonnement 2-licentie of een PowerApps-abonnement 2-evaluatielicentie. U kunt zich aanmelden voor een 30-daagse evaluatielicentie op [http://web.powerapps.com/trial](http://web.powerapps.com/trial). Evaluatielicenties kunnen worden vernieuwd als ze zijn verlopen.

* [Globale beheerder voor Office 365](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504)- of [globale beheerder Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal)-machtigingen als u in de resources van een andere gebruiker wilt zoeken. (Let op: omgevingsbeheerders hebben alleen toegang tot de omgevingen en omgevingsresources waarvoor ze machtigingen hebben.)

## <a name="step-1-delete-or-reassign-all-environments-created-by-the-user"></a>Stap 1: alle door de gebruiker gemaakte omgevingen verwijderen of opnieuw toewijzen
Als beheerder moet u twee beslissingen nemen bij het verwerken van een AVG-aanvraag voor het verwijderen van gegevens voor elke omgeving die de gebruiker heeft gemaakt:

1. Als u vaststelt dat de omgeving niet wordt gebruikt door iemand anders in uw organisatie, kunt u besluiten de omgeving te verwijderen.

2. Als u vaststelt dat de omgeving nog vereist is, kunt u besluiten de omgeving niet te verwijderen en uzelf (of een andere gebruiker in uw organisatie) toe te voegen als een Omgevingsbeheerder.

> [!IMPORTANT]
> Als u een omgeving verwijdert, worden alle resources in de omgeving definitief verwijderd, inclusief alle apps, flows, verbindingen, enzovoort. Controleer daarom de inhoud van de omgeving voordat u deze verwijdert.

### <a name="give-access-to-a-users-environments-from-the-powerapps-admin-center"></a>Toegang verlenen tot de omgevingen van een gebruiker vanuit het PowerApps-beheercentrum
Een beheerder kan beheerderstoegang verlenen tot een omgeving die door een specifieke gebruiker is gemaakt vanuit het [PowerApps-beheercentrum](https://admin.powerapps.com/) door de volgende stappen te volgen:

1. Selecteer vanuit het [PowerApps-beheercentrum](https://admin.powerapps.com/) elke omgeving in uw organisatie.

    ![Landingspagina van het beheercentrum](./media/powerapps-gdpr-delete-dsr/admin-center-landing.png)

2. Als de omgeving is gemaakt door de gebruiker die de AVG-aanvraag heeft ingediend, selecteert u **Beveiliging** en volgt u de stappen in [Beheerdersomgevingen](environments-administration.md) om uzelf of een andere gebruiker in uw organisatie beheerdersbevoegdheden te geven.

    ![Omgevingsbeveiliging](./media/powerapps-gdpr-delete-dsr/share-environment.png)

### <a name="delete-environments-created-by-a-user-from-the-powerapps-admin-center"></a>Omgevingen verwijderen die zijn gemaakt door een gebruiker vanuit het PowerApps-beheercentrum
Een beheerder kan omgevingen bekijken en verwijderen die door een specifieke gebruiker zijn gemaakt vanuit het [PowerApps-beheercentrum](https://admin.powerapps.com/) door de volgende stappen te volgen:

1. Selecteer vanuit het [PowerApps-beheercentrum](https://admin.powerapps.com/) elke omgeving in uw organisatie.

    ![Landingspagina van het beheercentrum](./media/powerapps-gdpr-delete-dsr/admin-center-landing.png)

2. Als de omgeving is gemaakt door de gebruiker die de AVG-aanvraag heeft ingediend, selecteert u **Verwijderen** en volgt u de stappen voor het verwijderen van de omgeving:

    ![Omgeving verwijderen](./media/powerapps-gdpr-delete-dsr/delete-environment.png)

### <a name="give-access-to-a-users-environments-using-powershell"></a>Toegang verlenen tot de omgevingen van een gebruiker met PowerShell
Een beheerder kan zichzelf (of een andere gebruiker binnen de organisatie) toegang verlenen tot alle omgevingen die door de gebruiker zijn gemaakt via de functie **Set-AdminEnvironmentRoleAssignment** in de [PowerShell-cmdlets voor PowerApps-beheerders](https://go.microsoft.com/fwlink/?linkid=871804):

```
Add-PowerAppsAccount
$deleteDsrUserId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
$myUserId = $global:currentSession.UserId

#Assign yourself as an admin to each environment created by the user
Get-AdminEnvironment -CreatedBy $deleteDsrUserId | Set-AdminEnvironmentRoleAssignment -RoleName EnvironmentAdmin -PrincipalType User -PrincipalObjectId $myUserId

#Retrieve the environment role assignments to confirm
Get-AdminEnvironment -CreatedBy $deleteDsrUserId | Get-AdminEnvironmentRoleAssignment
```

> [!IMPORTANT]
> Deze functie werkt alleen in omgevingen zonder database-instantie in CDS for Apps.

### <a name="delete-environments-created-by-a-user-using-powershell"></a>Omgevingen verwijderen die door een gebruiker zijn gemaakt met PowerShell
 Een beheerder kan alle omgevingen die door een gebruiker zijn gemaakt verwijderen met de functie **Remove-AdminEnvironment** in de [PowerShell-cmdlets voor PowerApps-beheerders](https://go.microsoft.com/fwlink/?linkid=871804):

```
Add-PowerAppsAccount
$deleteDsrUserId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"

# Retrieve all environments created by the user and then delete them
Get-AdminEnvironment -CreatedBy $deleteDsrUserId | Remove-AdminEnvironment
```

## <a name="step-2-delete-the-users-permissions-to-all-other-environments"></a>Stap 2: de machtigingen voor de gebruiker voor alle omgevingen verwijderen
Aan gebruikers kunnen in een omgeving machtigingen worden toegewezen (zoals Omgevingsbeheerder en Omgevingsmaker), die in de PowerApps-service worden opgeslagen als een roltoewijzing.
Als er, na de introductie van CDS for Apps, een database wordt gemaakt binnen de omgeving, worden deze roltoewijzingen opgeslagen als records in de instantie van die database.
Zie [Omgevingen beheren](environments-administration.md) voor meer informatie.

### <a name="for-environments-without-a-cds-for-apps-database"></a>Voor omgevingen zonder een CDS for Apps-database

#### <a name="powerapps-admin-center"></a>PowerApps-beheercentrum
Een beheerder kan de omgevingsmachtigingen voor een omgeving verwijderen vanuit het [PowerApps-beheercentrum](https://admin.powerapps.com/) door de volgende stappen te volgen:

1. Selecteer vanuit het [PowerApps-beheercentrum](https://admin.powerapps.com/) elke omgeving in uw organisatie.

    U moet een [globale beheerder voor Office 365](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) of [globale beheerder van Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal) zijn om alle omgevingen te kunnen controleren die binnen uw organisatie zijn gemaakt.

    ![Landingspagina van het beheercentrum](./media/powerapps-gdpr-delete-dsr/admin-center-landing.png)

2. Selecteer **Beveiliging**.

    Als uw omgeving geen CDS for Apps-database heeft, ziet u een sectie voor **Omgevingsrollen.**

3. Selecteer binnen **Omgevingsrollen** onafhankelijk van elkaar **Omgevingsbeheerder** en **Omgevingsmaker** en zoek de naam van de gebruiker via de zoekbalk.

    ![Pagina Omgevingsrollen](./media/powerapps-gdpr-delete-dsr/admin-environment-role-share-page.png)

5.  Als de gebruiker toegang heeft tot een van beide rollen, verwijdert u vanuit het scherm **Gebruikers** de machtiging en selecteert u **Opslaan**.

#### <a name="powershell"></a>PowerShell
Beheerders kunnen alle omgevingsroltoewijzingen voor een gebruiker in alle omgevingen zonder een CDS for Apps-database verwijderen met de functie **Remove-AdminEnvironmentRoleAssignment** in de [PowerShell-cmdlets voor PowerApps-beheerders](https://go.microsoft.com/fwlink/?linkid=871804):

```
Add-PowerAppsAccount
$deleteDsrUserId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"

#find all environment role assignments for the user for environments without a CDS for Apps instance and delete them
Get-AdminEnvironmentRoleAssignment -UserId $deleteDsrUserId | Remove-AdminEnvironmentRoleAssignment
```

> [!IMPORTANT]
> Deze functie werkt alleen voor omgevingen zonder instantie van een CDS for Apps-database.

### <a name="for-environments-with-a-cds-for-apps-database"></a>Voor omgevingen met een CDS for Apps-database
Als er, na de introductie van CDS for Apps, een database wordt gemaakt binnen de omgeving, worden deze roltoewijzingen opgeslagen als records in de instantie van die database. Raadpleeg de volgende documentatie over het verwijderen van persoonlijke gegevens van een instantie van een database in CDS for Apps: Common Data Service User personal data removal (Verwijderen van persoonlijke gegevens van gebruikers uit Common Data Service)

## <a name="step-3-delete-or-reassign-all-canvas-apps-owned-by-a-user"></a>Stap 3: alle canvas-apps in bezit van een gebruiker verwijderen of opnieuw toewijzen

### <a name="reassign-a-users-canvas-apps-using-the-powerapps-admin-powershell-cmdlets"></a>De canvas-apps van een gebruiker opnieuw toewijzen met de PowerShell-cmdlets voor PowerApps-beheerders
Als een beheerder besluit de canvas-apps van een gebruiker niet te verwijderen, kunnen de apps van een gebruiker via de functie **Set-AdminAppOwner** in de [PowerShell-cmdlets voor PowerApps-beheerders](https://go.microsoft.com/fwlink/?linkid=871804) opnieuw worden toegewezen:

```
Add-PowerAppsAccount
$deleteDsrUserId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
$newAppOwnerUserId = "72c272b8-14c3-4f7a-95f7-a76f65c9ccd8"

#find all apps owned by the DSR user and assigns them a new owner
Get-AdminApp -Owner $deleteDsrUserId | Set-AdminAppOwner -AppOwner $newAppOwnerUserId
```

### <a name="delete-a-users-canvas-app-using-the-powerapps-site"></a>De canvas-app van een gebruiker verwijderen via de PowerApps-site
Een gebruiker kan een app van verwijderen van de [PowerApps-site](https://web.powerapps.com). Zie Een app verwijderen voor instructies voor het verwijderen van een app.

### <a name="delete-a-users-canvas-app-using-the-powerapps-admin-center"></a>De canvas-app van een gebruiker verwijderen via het PowerApps-beheercentrum
Een beheerder kan apps die zijn gemaakt door een gebruiker vanuit het [PowerApps-beheercentrum](https://admin.powerapps.com/) verwijderen door de volgende stappen te volgen:

1. Selecteer vanuit het [PowerApps-beheercentrum](https://admin.powerapps.com/) elke omgeving in uw organisatie.

    U moet een [globale beheerder voor Office 365](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) of [globale beheerder van Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal) zijn om alle omgevingen te kunnen controleren die binnen uw organisatie zijn gemaakt.

    ![Landingspagina van het beheercentrum](./media/powerapps-gdpr-delete-dsr/admin-center-landing.png)

2. Selecteer **Resources** > **Apps**.

3. Zoek via de zoekbalk de naam van de gebruiker. Zo vindt u alle apps die door die gebruiker in deze omgeving zijn gemaakt:

    ![Apps zoeken](./media/powerapps-gdpr-delete-dsr/search-apps.png)

4. Selecteer **Details** voor elke app van de gebruiker:

    ![App details selecteren](./media/powerapps-gdpr-delete-dsr/select-app-details.png)

5. Selecteer **Verwijderen** om elke app te verwijderen:

### <a name="delete-a-users-canvas-app-using-the-powerapps-admin-powershell-cmdlets"></a>De canvas-apps van een gebruiker verwijderen met de PowerShell-cmdlets voor PowerApps-beheerders
Als een beheerder besluit alle canvas-apps van een gebruiker te verwijderen, kan dit met de functie **Remove-AdminApp** in de [PowerShell-cmdlets voor PowerApps-beheerders](https://go.microsoft.com/fwlink/?linkid=871804):

```
Add-PowerAppsAccount
$deleteDsrUserId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"

#find all apps owned by the DSR user and deletes them
Get-AdminApp -Owner "0ecb1fcc-6782-4e46-a4c4-738c1d3accea" | Remove-AdminApp
```

## <a name="step-4-delete-the-users-permissions-to-canvas-apps"></a>Stap 4: de machtigingen van de gebruiker voor canvas-apps verwijderen
Wanneer een app met een gebruiker wordt gedeeld, wordt in PowerApps een record opgeslagen dat een roltoewijzing wordt genoemd. Deze roltoewijzing beschrijft de machtigingen van de gebruiker (CanEdit of CanUse) voor de toepassing. Zie het artikel Een app delen voor meer informatie.

> [!NOTE]
> De roltoewijzingen van een app worden verwijderd als de app wordt verwijderd.

> [!NOTE]
> De roltoewijzingen van de app-eigenaar kunnen alleen worden verwijderd door een nieuwe eigenaar voor de app toe te wijzen.

### <a name="powerapps-admin-center"></a>PowerApps-beheercentrum
Een beheerder kan roltoewijzingen voor apps voor een gebruiker vanuit het [PowerApps-beheercentrum](https://admin.powerapps.com/) verwijderen door de volgende stappen te volgen:

1. Selecteer vanuit het [PowerApps-beheercentrum](https://admin.powerapps.com/) elke omgeving in uw organisatie.

    U moet een [globale beheerder voor Office 365](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) of [globale beheerder van Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal) zijn om alle omgevingen te kunnen controleren die binnen uw organisatie zijn gemaakt.

    ![Landingspagina van het beheercentrum](./media/powerapps-gdpr-delete-dsr/admin-center-landing.png)

2. Selecteer voor elke omgeving **Resources** > **Apps**.

3. Selecteer **Delen** voor elke app in de omgeving:

    ![App delen selecteren](./media/powerapps-gdpr-delete-dsr/select-admin-share-nofilter.png)

4. Als de gebruiker toegang heeft tot de app, verwijdert u vanuit het scherm **Delen** van de app de machtiging en selecteert u **Opslaan**.

    ![Beheerpagina app delen](./media/powerapps-gdpr-delete-dsr/admin-share-page.png)

### <a name="powershell-cmdlets-for-admins"></a>PowerShell-cmdlets voor beheerders
Een beheerder kan alle roltoewijzingen van een gebruiker voor een canvas-app verwijderen met de functie **Remove-AdminAppRoleAssignmnet** in de [PowerShell-cmdlets voor PowerApps-beheerders](https://go.microsoft.com/fwlink/?linkid=871804):

```
Add-PowerAppsAccount
$deleteDsrUserId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"

#find all app role assignments for the DSR user and deletes them
Get-AdminAppRoleAssignment -UserId $deleteDsrUserId | Remove-AdminAppRoleAssignment
```

## <a name="step-5-delete-connections-created-by-a-user"></a>Stap 5: verbindingen verwijderen die door een gebruiker zijn gemaakt
Verbindingen worden gebruikt in combinatie met connectors bij het maken van verbinding met andere API's en SaaS-systemen.  Verbindingen bevatten verwijzingen naar de gebruiker door wie ze zijn gemaakt en kunnen, als gevolg hiervan, worden verwijderd om alle verwijzingen naar de gebruiker te verwijden.

### <a name="powershell-cmdlets-for-app-creators"></a>PowerShell-cmdlets voor app-ontwikkelaars
Een gebruiker kan al zijn of haar verbindingen verwijderen met de functie Remove-Connection in de [PowerShell-cmdlets voor app-ontwikkelaars](https://go.microsoft.com/fwlink/?linkid=871448):

```
Add-PowerAppsAccount

#Retrieves all connections for the calling user and deletes them
Get-Connection | Remove-Connection
```

### <a name="powershell-cmdlets-for-powerapps-administrators"></a>PowerShell-cmdlets voor PowerApps-beheerders
Een beheerder kan alle verbindingen van een gebruiker verwijderen met de functie **Remove-AdminConnection** in de [PowerShell-cmdlets voor PowerApps-beheerders](https://go.microsoft.com/fwlink/?linkid=871804):

```
Add-PowerAppsAccount
$deleteDsrUserId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"

#Retrieves all connections for the DSR user and deletes them
Get-AdminConnection -CreatedBy $deleteDsrUserId | Remove-AdminConnection
```

## <a name="step-6-delete-the-users-permissions-to-shared-connections"></a>Stap 6: de machtigingen van de gebruiker voor gedeelde verbindingen verwijderen

### <a name="powershell-cmdlets-for-app-creators"></a>PowerShell-cmdlets voor app-ontwikkelaars
Een gebruiker kan al zijn of haar verbindingsroltoewijzingen voor gedeelde verbindingen verwijderen met de functie Remove-ConnectionRoleAssignment in de [PowerShell-cmdlets voor app-ontwikkelaars](https://go.microsoft.com/fwlink/?linkid=871448):

```
Add-PowerAppsAccount

#Retrieves all connection role assignments for the calling users and deletes them
Get-ConnectionRoleAssignment | Remove-ConnectionRoleAssignment
```
> [!NOTE]
> Roltoewijzingen voor eigenaren kunnen niet worden verwijderd zonder de verbindingsresource te verwijderen.

### <a name="powershell-cmdlets-for-admins"></a>PowerShell-cmdlets voor beheerders
Een beheerder kan alle roltoewijzingen voor een verbinding van een gebruiker verwijderen met de functie **Remove-AdminConnectionRoleAssignment** in de [PowerShell-cmdlets voor PowerApps-beheerders](https://go.microsoft.com/fwlink/?linkid=871804):

```
Add-PowerAppsAccount
$deleteDsrUserId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"

#Retrieves all connection role assignments for the DSR user and deletes them
Get-AdminConnectionRoleAssignment -PrincipalObjectId $deleteDsrUserId | Remove-AdminConnectionRoleAssignment
```

## <a name="step-7-delete-custom-connectors-created-by-the-user"></a>Stap 7: door de gebruiker gemaakte aangepaste connectors verwijderen
Aangepaste connectors vormen een aanvulling op de bestaande standaard-connectors en maken connectiviteit met andere API's, SaaS en aangepaste systemen mogelijk. Het is raadzaam het eigendom van Aangepaste connectors over te dragen aan andere gebruikers in de organisatie of de Aangepaste connector te verwijderen.

### <a name="powershell-cmdlets-for-app-creators"></a>PowerShell-cmdlets voor app-ontwikkelaars
Een gebruiker kan al zijn of haar aangepaste connectors verwijderen met de functie Remove-Connector in de [PowerShell-cmdlets voor app-ontwikkelaars](https://go.microsoft.com/fwlink/?linkid=871448):

```
Add-PowerAppsAccount

#Retrieves all custom connectors for the calling user and deletes them
Get-Connector -FilterNonCustomConnectors | Remove-Connector
```

### <a name="powershell-cmdlets-for-admins"></a>PowerShell-cmdlets voor beheerders
Een beheerder kan alle aangepaste connectors die door een gebruiker zijn gemaakt verwijderen met de functie **Remove-AdminConnector** in de [PowerShell-cmdlets voor PowerApps-beheerder](https://go.microsoft.com/fwlink/?linkid=871804):

```
Add-PowerAppsAccount
$deleteDsrUserId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"

#Retrieves all custom connectors created by the DSR user and deletes them
Get-AdminConnector -CreatedBy $deleteDsrUserId | Remove-AdminConnector
```

## <a name="step-8-delete-the-users-permissions-to-shared-custom-connectors"></a>Stap 8: de machtigingen van de gebruiker voor gedeelde aangepaste connectors verwijderen

### <a name="powershell-cmdlets-for-app-creators"></a>PowerShell-cmdlets voor app-ontwikkelaars
Een gebruiker kan al zijn of haar connectorroltoewijzingen voor gedeelde aangepaste connectors verwijderen met de functie Remove-ConnectorRoleAssignment in de [PowerShell-cmdlets voor app-ontwikkelaars](https://go.microsoft.com/fwlink/?linkid=871448):

```
Add-PowerAppsAccount

#Retrieves all connector role assignments for the calling users and deletes them
Get-ConnectorRoleAssignment | Remove-ConnectorRoleAssignment
```

> [!NOTE]
> Roltoewijzingen voor eigenaren kunnen niet worden verwijderd zonder de verbindingsresource te verwijderen.

### <a name="powershell-cmdlets-for-admins"></a>PowerShell-cmdlets voor beheerders
Een beheerder kan alle aangepaste roltoewijzingen voor een verbinding van een gebruiker verwijderen met de functie **Remove-AdminConnectorRoleAssignment** in de [PowerShell-cmdlets voor PowerApps-beheerders](https://go.microsoft.com/fwlink/?linkid=871804):

```
Add-PowerAppsAccount
$deleteDsrUserId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"

#Retrieves all custom connector role assignments for the DSR user and deletes them
Get-AdminConnectorRoleAssignment -PrincipalObjectId $deleteDsrUserId | Remove-AdminConnectorRoleAssignment
```

## <a name="step-9-delete-the-users-personal-data-in-microsoft-flow"></a>Stap 9: de persoonlijke gegevens van de gebruiker in Microsoft Flow verwijderen
PowerApps-licenties omvatten altijd Microsoft Flow-mogelijkheden. Behalve dat Microsoft Flow is opgenomen in PowerApps-licenties, is Microsoft Flow ook beschikbaar als een zelfstandige service. Zie [Responding to GDPR Data Subject Requests for Microsoft Flow](https://go.microsoft.com/fwlink/?linkid=872250) (Reageren op AGV-aanvragen voor gegevensonderwerpen voor Microsoft Flow) voor instructies over het reageren op AVG-aanvragen van gebruikers die de Microsoft Flow-service gebruiken.

> [!IMPORTANT]
> Het is raadzaam deze stap door beheerders te laten uitvoeren voor PowerApps-gebruikers.

## <a name="step-10-delete-the-users-personal-data-in-instances-of-cds-for-apps"></a>Stap 10: de persoonlijke gegevens van de gebruiker in instanties van CDS for Apps verwijderen
Bepaalde PowerApps-licenties, waaronder het PowerApps Community-abonnement, bieden gebruikers binnen uw organisatie de mogelijkheid instanties van CDS for Apps te maken en apps te bouwen op CDS for Apps. Het PowerApps Community-abonnement is een gratis licentie waarmee gebruikers CDS for Apps kunnen proberen in een individuele omgeving. Zie de pagina met prijzen voor PowerApps voor informatie over welke mogelijkheden elke PowerApps-licentie bevat.

Zie [Responding to Data Subject Rights (DSR) requests for Common Data Service for Apps customer data](common-data-service-gdpr-dsr-guide.md) (Reageren op AVG-aanvragen voor Common Data Service for Apps-gegevens van de klant) voor instructies over het reageren op AVG-aanvragen van gebruikers die CDS for Apps gebruiken.

> [!IMPORTANT]
> Het is raadzaam deze stap door beheerders te laten uitvoeren voor PowerApps-gebruikers.

## <a name="step-11-delete-the-user-from-azure-active-directory"></a>Stap 11: de gebruiker verwijderen uit Azure Active Directory
Zodra de bovenstaande stappen zijn voltooid, bestaat de laatste stap uit het verwijderen van het account voor Azure Active Directory van de gebruiker.

### <a name="managed-tenant"></a>Beheerde tenant
Als beheerder van een beheerde Azure AD-tenant kunt u het account van de gebruiker verwijderen. Volg hiervoor de stappen in de AVG-documentatie over AVG-verzoeken in de [Office 365 Service Trust-portal](https://servicetrust.microsoft.com/ViewPage/GDPRDSR).

### <a name="unmanaged-tenant"></a>Onbeheerde tenant
Als u lid bent van een onbeheerde tenant, moet u deze stappen uitvoeren voor het verwijderen van uw account uit uw Azure AD-tenant:

> [!NOTE]
> Raadpleeg het bovenstaande [gedeelte over onbeheerde tenants](#unmanaged-tenant) als u wilt weten hoe u achterhaalt of u lid bent van een onbeheerde of beheerde tenant.

1. Navigeer naar de [pagina voor privacy op het werk en op school](https://go.microsoft.com/fwlink/?linkid=87312) en meld u aan met uw Azure AD-account.

2. Selecteer **Account sluiten** en volg de instructies voor het verwijderen van uw account uit uw Azure AD-tenant.

    ![App delen selecteren](./media/powerapps-gdpr-delete-dsr/close-account.png)
