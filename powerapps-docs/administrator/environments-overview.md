---
title: Overzicht van omgevingen | Microsoft Docs
description: Meer informatie over omgevingen in PowerApps en hoe u ze kunt gebruiken
author: manasmams
manager: kfile
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: manasma
ms.openlocfilehash: 4973265baf701851ac5c2e8bca9da541b246c068
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34167787"
---
# <a name="environments-overview"></a>Overzicht van omgevingen
Een omgeving is een ruimte om de bedrijfsgegevens, -apps en -stromen van uw organisatie op te slaan, te beheren en te delen. Een omgeving doet ook dienst als container voor het scheiden van apps met verschillende rollen, beveiligingsvereisten of doelgroepen. Hoe u voordeel haalt uit omgevingen, is afhankelijk van uw organisatie en de apps die u probeert te maken. Bijvoorbeeld:

* U kunt ervoor kiezen om alleen apps te maken in één omgeving.
* U kunt afzonderlijke omgevingen maken waarin de test- en productieversies van uw apps worden gegroepeerd.
* U kunt afzonderlijke omgevingen maken die overeenkomen met de specifieke teams of afdelingen in uw bedrijf, en die elk de relevante gegevens en apps voor elke doelgroep bevatten.
* U kunt ook afzonderlijke omgevingen maken voor de verschillende algemene vertakkingen van uw bedrijf.  

## <a name="environment-scope"></a>Bereik van omgeving
Elke omgeving wordt gemaakt onder een Azure AD-tenant en alleen gebruikers binnen die tenant hebben toegang tot de bronnen in die omgeving. Een omgeving is ook gebonden aan een geografische locatie, zoals de Verenigde Staten. Wanneer u een app in een omgeving maakt, wordt deze app rondgestuurd naar alleen datacenters in die geografische locatie. De items die u in die omgeving maakt (inclusief verbindingen, gateways, stromen met behulp van Microsoft Flow en nog veel meer) zijn ook gebonden aan de locatie van de omgeving.

Elke omgeving kan één of geen Common Data Service-database hebben, die opslag voor uw apps bieden. De mogelijkheid om een database voor uw omgeving te maken, is afhankelijk van de licentie die u voor PowerApps aankoopt en uw machtiging in deze omgeving. Zie [Prijzen](pricing-billing-skus.md) voor meer informatie.

Wanneer u een app in een omgeving maakt, is deze app alleen gemachtigd om verbinding te maken met de gegevensbronnen die ook in diezelfde omgeving zijn geïmplementeerd, met inbegrip van verbindingen, gateways, stromen en Common Data Service-databases.  Stel dat u twee omgevingen, met de naam 'Test' en 'Ontw', hebt gemaakt met in elk van die omgevingen een Common Data Service-database. Als u in de omgeving 'Test' een app maakt, is deze alleen gemachtigd om verbinding te maken met de database 'Test' en niet met de database 'Ontw'.

Er is ook een proces om resources tussen omgevingen te verplaatsen. Zie [Migrate resources (Resources migreren)](environment-and-tenant-migration.md) voor meer informatie.

![](./media/environments-overview/Environments.png)

## <a name="environment-permissions"></a>Omgevingsmachtigingen
Omgevingen hebben twee ingebouwde rollen die toegang bieden tot machtigingen in een omgeving:

* Personen met de rol Environment Admin (omgevingsbeheerder) kunnen in een omgeving alle beheerderstaken uitvoeren, met inbegrip van:

    * Een gebruiker of groep toevoegen aan of verwijderen uit de rol Environment Admin of Environment Maker

    * Een Common Data Service-database voor de omgeving inrichten

    * Alle resources die in een omgeving zijn gemaakt, weergeven en beheren

    * Beleid instellen ter preventie van gegevensverlies. Zie [Data loss prevention policies (Beleid ter preventie van gegevensverlies)](prevent-data-loss.md) voor meer informatie.

    Nadat de database in de omgeving is gemaakt, kunt u de rol Systeembeheerder gebruiken in plaats van de rol Omgevingsbeheerder.

* Personen met de rol Environment Maker kunnen in een omgeving resources maken, met inbegrip van apps, verbindingen, aangepaste connectors, gateways en stromen met behulp van Microsoft Flow.

Environment Makers die apps in een omgeving maken, kunnen deze apps ook distribueren naar andere gebruikers in uw organisatie door de app te delen met individuele gebruikers of beveiligingsgroepen, of naar alle gebruikers in de organisatie. Zie [Een app delen in PowerApps](../maker/canvas-apps/share-app.md) voor meer informatie.

Gebruikers of groepen die aan deze omgevingsrollen zijn toegewezen, krijgen niet automatisch toegang tot de omgevingsdatabase (indien aanwezig). Zij moeten afzonderlijk toegang krijgen van de eigenaar van een database. Zie [Configure database security (Databasebeveiliging configureren)](database-security.md) voor meer informatie.

Gebruikers of beveiligingsgroepen kunnen aan een van deze twee rollen worden toegewezen door een Environment Admin van het [PowerApps-beheercentrum][1]. Zie [Omgevingen beheren in PowerApps](environments-administration.md) voor meer informatie.

![](./media/environments-overview/EnvironmentRoles.png)

## <a name="the-default-environment"></a>De standaardomgeving
PowerApps maakt automatisch één standaardomgeving voor elke tenant, die door alle gebruikers in die tenant wordt gedeeld. Wanneer nieuwe gebruikers zich aanmelden voor PowerApps, worden ze automatisch toegevoegd aan de rol Maker van de standaardomgeving. De standaardomgeving wordt in de dichtstbijzijnde regio van de standaardregio van de AAD-tenant gemaakt.

> [!NOTE]
> Aan de rol Admin van de standaardomgeving worden niet automatisch gebruikers toegevoegd. Zie [Omgevingen beheren in PowerApps](environments-administration.md) voor meer informatie.
>
>

De standaardomgeving heet: "{naam van Azure AD-tenant} (standaard)"

![](./media/environments-overview/DefaultEnvironment.png)

## <a name="production-and-trial-environments"></a>Productie- en evaluatieomgevingen
U kunt voor verschillende doeleinden omgevingen maken. Een evaluatieomgeving is bedoeld voor het proberen van de omgeving en de database met Common Data Service-ervaring. Deze omgeving verloopt na een bepaalde periode. Zie [Omgevingen beheren in PowerApps](environments-administration.md) voor meer informatie.

## <a name="choosing-an-environment"></a>Een omgeving kiezen
Door de introductie van omgevingen ziet u een nieuwe ervaring wanneer u naar [https://web.powerapps.com](https://web.powerapps.com) gaat.  De apps, verbindingen en andere items die zichtbaar zijn op de site worden nu gefilterd op basis van de huidige omgeving die is geselecteerd.  Uw huidige omgeving is vermeld in de omgevingskiezer rechts van de kop. Als u een andere omgeving wilt kiezen, klikt of tikt u op de kiezer om een lijst met beschikbare omgevingen weer te geven. Klik of tik op de omgeving waartoe u toegang wenst.

In de kiezer worden omgevingen weergegeven als u aan een van de volgende voorwaarden voldoet:

* U bent lid van de rol Environment Admin voor de omgeving.
* U bent lid van de rol Environment Maker voor de omgeving.
* U bent geen Environment Admin of Environment Maker van de omgeving, maar u hebt tot ten minste één app in de omgeving toegang gekregen als 'Medewerker'. Zie [Een app delen](../maker/canvas-apps/share-app.md) voor meer informatie. In dit geval kunt u geen apps maken in deze omgeving. U kunt alleen de bestaande apps wijzigen die met u zijn gedeeld.

![](./media/environments-overview/EnvironmentPicker.png)

## <a name="creating-an-environment"></a>Een omgeving maken
### <a name="who-can-create-environments"></a>Wie kan omgevingen maken?
Uw licentie bepaalt of u omgevingen kunt maken.

| Licentie | Gemachtigd om omgeving te maken |
| --- | --- |
| PowerApps P2 |√ (Twee productie- en twee eveluatieomgevingen)|
| PowerApps P2-proefversie |√ (Twee evaluatieomgevingen)|
| PowerApps P1 |x |
| PowerApps P1-proefversie |x |
| Dynamics 365-abonnementen |x |
| Office 365-abonnementen |x |
| Dynamics 365-abonnementen voor Apps en Teams |x |


### <a name="where-can-environments-be-created"></a>Waar kunnen omgevingen worden gemaakt?
U kunt nieuwe omgevingen maken in [PowerApps.com][2] en vanuit het [PowerApps-beheercentrum][1]. Als u een omgeving maakt, wordt u voor die omgeving automatisch toegevoegd aan de rol Omgevingsbeheerder. Er is geen limiet op het aantal omgevingen waaraan u kunt deelnemen als lid van de rol Omgevingsbeheerder of Omgevingsmaker. Zie [Omgevingen beheren in PowerApps](environments-administration.md) voor meer informatie over omgevingen. Zie [Een omgeving maken](create-environment.md) voor instructies over het maken van een omgeving.

![](./media/environments-overview/CreateEnvironmentDialog-New.png)


## <a name="managing-environments-for-your-organization"></a>Omgevingen voor uw organisatie beheren
In het PowerApps-beheercentrum kunt u alle omgevingen beheren die u hebt gemaakt of waarvoor u bent toegevoegd aan de rol Omgevingsbeheerder. In het beheercentrum kunt u alle beheerderstaken uitvoeren op een omgeving, waaronder de volgende:

* Een gebruiker of groep toevoegen aan of verwijderen uit de rol Environment Admin of Environment Maker.  Zie [Omgevingen beheren in PowerApps](environments-administration.md) voor meer informatie.
* Een Common Data Service-database voor de omgeving inrichten. Zie [Create a Common Data Service database (Een Common Data Service-database maken)](create-database.md) voor meer informatie.
* Beleid instellen ter preventie van gegevensverlies. Zie [Data loss prevention policies (Beleid ter preventie van gegevensverlies)](prevent-data-loss.md) voor meer informatie.
* Databasebeveiligingsbeleid instellen (als open of beperkt door databaserollen). Zie [Configure database security (Databasebeveiliging configureren)](database-security.md) voor meer informatie.
* Leden met de rol Global Administrator (Hoofdbeheerder) van de Azure AD-tenant (inclusief Office 365-hoofdbeheerders) kunnen ook alle omgevingen beheren die in hun tenant zijn gemaakt en tenant-brede beleidsregels instellen vanuit het PowerApps-beheercentrum.

<!--Reference links in article-->
[1]: https://admin.powerapps.com
[2]: https://web.powerapps.com
[3]: https://aka.ms/cdspreviewtoga
