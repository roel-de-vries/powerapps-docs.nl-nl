---
title: Omgevingen beheren | Microsoft Docs
description: Omgevingen in PowerApps beheren (maken, naam wijzigen, verwijderen en beveiligen)
services: 
suite: powerapps
documentationcenter: na
author: jamesol-msft
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/11/2017
ms.author: jamesol
ms.openlocfilehash: 1eeb79d0c109181ae75b86a78cecdb4babe058ab
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="environments-administration-in-powerapps"></a>Omgevingen beheren in PowerApps
In het [PowerApps-beheercentrum][1] kunt u omgevingen beheren die u hebt gemaakt en waarvoor u bent toegevoegd aan de rol Omgevingsbeheerder. Vanuit het beheercentrum kunt u de volgende beheeracties uitvoeren:

* Omgevingen maken.
* De naam van omgevingen wijzigen.
* Een gebruiker of groep toevoegen aan of verwijderen uit de rol Environment Admin of Environment Maker.
* Een Common Data Service-database voor de omgeving inrichten.
* Beleid instellen ter preventie van gegevensverlies.
* Databasebeveiligingsbeleid instellen (als open of beperkt door databaserollen).
* Leden met de rol Algemeen beheerder van de Azure AD-tenant (inclusief Office 365 algemeen beheerders) kunnen ook alle omgevingen beheren die in hun tenant zijn gemaakt en tenant-brede beleidsregels instellen.

## <a name="access-the-powerapps-admin-center"></a>Toegang tot het PowerApps-beheercentrum
U opent als volgt het PowerApps-beheercentrum:

* Ga rechtstreeks naar [admin.powerapps.com][1] of
* Ga naar [powerapps.com][2] en selecteer het tandwielpictogram in de navigatiebalk.
  
    ![](./media/environment-admin/powerapps-gear-dropdown.png)

Voor het beheren van een omgeving in het PowerApps-beheercentrum, moet u een van deze rollen hebben:

* De rol Omgevingsbeheerder voor de omgeving of
* De rol Algemeen beheerder voor uw Azure AD- of Office 365-tenant.

U hebt ook PowerApps-abonnement 2 of Flow-abonnement 2 nodig voor toegang tot het beheercentrum. Zie voor meer informatie de [PowerApps-pagina met prijzen][3].

**Belangrijk**: alle wijzigingen die u in het PowerApps-beheercentrum aanbrengt, hebben invloed op het [Flow-beheercentrum][4] en vice versa.

## <a name="create-an-environment"></a>Een omgeving maken
Klik eerst op **+ Nieuwe omgeving** om een dialoogvenster te openen en een omgeving te maken.

![](./media/environment-admin/new-environment-button.png)

Voer dan de volgende gegevens in:

| Eigenschap | Beschrijving |
| --- | --- |
| Naam van omgeving |Voer de naam van uw omgeving in. |
| Regio |Kies de locatie waar u uw omgeving wilt hosten. We raden een locatie aan die zich het dichtst bij uw gebruikers bevindt. Als uw appgebruikers bijvoorbeeld in Londen zitten, kiest u een locatie in Europa. Als uw appgebruikers zich in New York bevinden, kiest u de Verenigde Staten. Zie [Ondersteunde regio's](regions-overview.md) voor een lijst van ondersteunde omgevingsregio's. |
| Een database voor deze omgeving maken |Schakel dit selectievakje in om een Common Data Service-database te maken voor deze omgeving. Een database kan worden opengesteld voor alle gebruikers in de omgeving of worden beperkt tot databaserollen. Zie [Configure database security (Databasebeveiliging configureren)](database-security.md) voor meer informatie. |

![](./media/environment-admin/new-environment-updated.png)

Selecteer ten slotte **Een omgeving maken**.

De nieuwe omgeving verschijnt in de tabel met omgevingen.

> [!NOTE]
> Wanneer u een omgeving maakt, krijgt u voor die omgeving automatisch de rol Omgevingsbeheerder.
> 
> 

## <a name="view-your-environments"></a>Uw omgevingen weergeven
Wanneer u het beheercentrum opent, wordt standaard het tabblad Omgevingen weergegeven met een lijst van alle omgevingen waarvoor u omgevingsbeheerder bent (zoals hieronder weergegeven):

![](./media/environment-admin/environment-list-updated.png)

Als u lid bent van de rol Algemeen beheerder van uw Azure AD- of Office 365-tenant, worden alle omgevingen weergegeven die zijn gemaakt door gebruikers in uw tenant, omdat u automatisch omgevingsbeheerder bent voor al deze omgevingen.

## <a name="rename-your-environment"></a>De naam van uw omgeving wijzigen
1. Open het [PowerApps-beheercentrum][1], zoek de omgeving waarvan u de naam wilt wijzigen in de lijst en klik of tik erop.
   
    ![](./media/environment-admin/environment-list-updated3.png)
2. Klik of tik op **Details**.
   
    ![](./media/environment-admin/environment-rename-details-2.png)
3. Typ de nieuwe naam in het tekstvak **Naam** en klik vervolgens op **Opslaan**.
   
    ![](./media/environment-admin/environment-rename-2.png)

## <a name="delete-your-environment"></a>Uw omgeving verwijderen
1. Klik of tik in het [PowerApps-beheercentrum][1] op de omgeving die u wilt verwijderen.
   
    ![](./media/environment-admin/environment-list-updated3.png)
2. Klik of tik op **Details**.
   
    ![](./media/environment-admin/environment-rename-details-2.png)
3. Klik of tik op **Omgeving verwijderen** om uw omgeving te verwijderen.
   
    ![](./media/environment-admin/delete-environment-2.png)

## <a name="create-a-common-data-service-database-for-an-environment"></a>Een Common Data Service-database voor een omgeving maken
Als een omgeving nog geen database heeft, kan een omgevingsbeheerder er een maken in het [PowerApps-beheercentrum][1] met de volgende stappen. Alleen gebruikers met PowerApps-abonnement 2 kunnen Common Data Service-databases maken.

1. Selecteer een omgeving in de tabel met omgevingen.
   
    ![](./media/environment-admin/choose-environment-updated.png)
2. Selecteer het tabblad **Database**.
3. Selecteer **Een database maken**.
   
    ![](./media/environment-admin/database-tab.png)
   
    Wanneer de database is ingericht, wordt dit bevestigingsbericht weergegeven:
   
    ![](./media/environment-admin/database-tab-success.png)

Nadat u een database hebt gemaakt, kiest u een beveiligingsmodel. Zie [Configure database security (Databasebeveiliging configureren)](database-security.md) voor meer informatie.

## <a name="manage-security-for-your-environments"></a>Beveiliging van uw omgevingen beheren
### <a name="environment-permissions"></a>Omgevingsmachtigingen
Alle gebruikers in de Azure AD-tenant van een omgeving zijn ook gebruikers van deze omgeving. Maar als ze meer bevoegdheden willen, moet hun een specifieke omgevingsrol worden toegewezen. Omgevingen hebben twee ingebouwde rollen die toegang bieden tot machtigingen in een omgeving:

* Personen met de rol **Omgevingsbeheerder** kunnen in een omgeving alle beheerderstaken uitvoeren, met inbegrip van:
  
  o    Een gebruiker of groep toevoegen aan of verwijderen uit de rol Omgevingsbeheerder of Omgevingsmaker
  
  o    Een Common Data Service-database voor de omgeving inrichten
  
  o    Alle resources die in een omgeving zijn gemaakt, weergeven en beheren
  
  o    Beleid instellen ter preventie van gegevensverlies. Zie [Data loss prevention policies (Beleid ter preventie van gegevensverlies)](prevent-data-loss.md) voor meer informatie.
* Personen met de rol **Environment Maker** kunnen in een omgeving resources maken, met inbegrip van apps, verbindingen, aangepaste connectors, gateways en stromen met behulp van Microsoft Flow. Omgevingsmakers kunnen ook de apps die ze in een omgeving hebben gemaakt, distribueren naar andere gebruikers in uw organisatie. Ze kunnen de app delen met individuele gebruikers, beveiligingsgroepen of alle gebruikers in de organisatie. Zie [Een app delen in PowerApps](share-app.md) voor meer informatie.

Een omgevingsbeheerder kan als volgt via het [PowerApps-beheercentrum][1] een omgevingsrol toewijzen aan een gebruiker of beveiligingsgroep:

1. Selecteer de omgeving in de tabel met omgevingen.
   
    ![](./media/environment-admin/choose-environment-updated.png)
2. Selecteer **Rollen van de omgeving** op het tabblad **Beveiliging**.
3. Selecteer de rol **Omgevingsbeheerder** of **Omgevingsmaker**.
   
    ![](./media/environment-admin/choose-environment-role.png)
4. Geef de naam op van een of meer gebruikers of beveiligingsgroepen in Azure Active Directory of geef aan dat u uw hele organisatie wilt toevoegen.
   
    ![](./media/environment-admin/enter-name.png)
5. Selecteer **Opslaan** om de toewijzingen van de omgevingsrol bij te werken.

Als u alle machtigingen voor een gebruiker of groep wilt verwijderen, klikt of tikt u op het pictogram **x** bij de betreffende gebruiker of groep.

> [!NOTE]
> Gebruikers of groepen die aan deze omgevingsrollen zijn toegewezen, krijgen niet automatisch toegang tot de omgevingsdatabase (indien aanwezig). Zij moeten afzonderlijk toegang krijgen van de eigenaar van een database. Zie [Configure database security (Databasebeveiliging configureren)](database-security.md) voor meer informatie.  
> 
> 

### <a name="database-security"></a>Databasebeveiliging
De gebruikersrollen en machtigingensets van de database bepalen of u de mogelijkheid hebt om een databaseschema te maken en aan te passen en om verbinding maken met de gegevens in een database die in uw omgeving is ingericht. U kunt de gebruikersrollen en machtigingensets voor de database van uw omgeving beheren in de sectie **Gebruikersrollen** en **Machtigingensets** van het tabblad **Beveiliging**. Zie [Configure database security (Databasebeveiliging configureren)](database-security.md) voor meer informatie.

![](./media/environment-admin/database-security.png)

> [!NOTE]
> Omgevingsbeheerders kunnen geen gebruikersrollen en machtigingensets maken en beheren voor de database van een omgeving. Deze mogelijkheid is beperkt tot leden van de gebruikersrol **Database-eigenaar**.  
> 
> 

## <a name="data-policies"></a>Gegevensbeleid
Gegevens van een organisatie moeten worden beveiligd en mogen niet worden gedeeld met mensen die hier geen toegang toe horen te hebben. U kunt hiertoe een beleid instellen dat bepaalt met welke consumentenservices en connectorspecifieke bedrijven gegevens mogen worden gedeeld. Een beleid dat definieert hoe gegevens mogen worden gedeeld, wordt aangeduid als beleid ter preventie van gegevensverlies (DLP). U kunt het DLP-beleid voor uw omgevingen beheren in de sectie **Gegevensbeleid** van het [PowerApps-beheercentrum][1].  Zie [Data loss prevention policies (Beleid ter preventie van gegevensverlies)](prevent-data-loss.md) voor meer informatie.

![](./media/environment-admin/data-policies.png)

## <a name="frequently-asked-questions"></a>Veelgestelde vragen
### <a name="how-many-environments-can-i-create"></a>Hoeveel omgevingen kan ik maken?
Elke gebruiker kan maximaal twee omgevingen maken.

### <a name="how-many-databases-can-i-provision"></a>Hoeveel databases kan ik inrichten?
Elke gebruiker kan tot twee omgevingen inrichten.

### <a name="can-i-rename-an-environment"></a>Kan ik de naam van een omgeving wijzigen?
Ja, deze functionaliteit is beschikbaar vanuit het PowerApps-beheercentrum. Zie [Environment Administration](environments-administration.md#rename-your-environment) (Beheer van omgeving) voor meer informatie.

### <a name="can-i-delete-an-environment"></a>Kan ik een omgeving verwijderen?
Ja, deze functionaliteit is beschikbaar vanuit het PowerApps-beheercentrum. Zie [Environment Administration](environments-administration.md#delete-your-environment) (Beheer van omgeving) voor meer informatie.

### <a name="as-an-environment-admin-can-i-view-and-manage-all-resources-apps-flows-apis-etc-for-an-environment"></a>Kan ik als omgevingsbeheerder alle resources (apps, stromen, API's enz.) voor een omgeving weergeven en beheren?
Ja, de mogelijkheid om de apps en stromen voor een omgeving te bekijken, is beschikbaar via het PowerApps-beheercentrum. Raadpleeg [Apps weergeven](admin-view-apps.md) voor meer informatie.

### <a name="which-license-includes-common-data-service"></a>Welke licentie bevat Common Data Service?
PowerApps-abonnement 2.  Zie de [PowerApps-pagina met prijzen][3] voor meer informatie over de abonnementen met deze licentie.

### <a name="can-the-common-data-service-be-used-outside-of-an-environment"></a>Kan Common Data Service worden gebruikt buiten een omgeving?
Nee. Voor Common Data Service is een omgeving vereist.

<!--Reference links in article-->
[1]: https://admin.powerapps.com
[2]: https://web.powerapps.com
[3]: https://powerapps.microsoft.com/pricing/
[4]: https://admin.flow.microsoft.com
