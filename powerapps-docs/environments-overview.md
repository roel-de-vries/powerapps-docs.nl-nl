---
title: Overzicht van omgevingen | Microsoft Docs
description: Wat zijn omgevingen en hoe ze te gebruiken
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
ms.date: 11/01/2016
ms.author: jamesol
ms.openlocfilehash: 425376f218b01a9edab4dae90555b33cd1d26a80
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="environments-overview"></a>Overzicht van omgevingen
Omgevingen zijn een nieuw concept in PowerApps. Eenvoudig gezegd is een omgeving een ruimte waarin u de zakelijke gegevens, apps en stromen van uw organisatie kunt opslaan, beheren en delen. Een omgeving doet ook dienst als container voor het scheiden van apps met verschillende rollen, beveiligingsvereisten of doelgroepen. Hoe u voordeel haalt uit omgevingen, is afhankelijk van uw organisatie en de apps die u probeert te maken. Bijvoorbeeld:

1. U kunt ervoor kiezen om alleen apps te maken in één omgeving.
2. U kunt afzonderlijke omgevingen maken waarin de test- en productieversies van uw apps worden gegroepeerd.
3. U kunt afzonderlijke omgevingen maken die overeenkomen met de specifieke teams of afdelingen in uw bedrijf, en die elk de relevante gegevens en apps voor elke doelgroep bevatten.
4. U kunt ook afzonderlijke omgevingen maken voor de verschillende algemene vertakkingen van uw bedrijf.  

## <a name="environment-scope"></a>Bereik van omgeving
Elke omgeving wordt gemaakt onder een Azure AD-tenant en alleen gebruikers binnen die tenant hebben toegang tot de bronnen in die omgeving. Een omgeving is ook gebonden aan een geografische locatie, zoals de Verenigde Staten. Wanneer u een app in een omgeving maakt, wordt deze app rondgestuurd naar alleen datacenters in die geografische locatie. De items die u in die omgeving maakt (inclusief verbindingen, gateways, stromen met behulp van Microsoft Flow en nog veel meer) zijn ook gebonden aan de locatie van de omgeving.

Elke omgeving kan één of geen Common Data Service-database hebben, die opslag voor uw apps bieden. De mogelijkheid om een database voor uw omgeving te maken, is afhankelijk van de licentie die u voor PowerApps aankoopt en uw machtiging in deze omgeving. Zie [Prijzen](pricing-billing-skus.md) voor meer informatie.

Wanneer u een app in een omgeving maakt, is deze app alleen gemachtigd om verbinding te maken met de gegevensbronnen die ook in diezelfde omgeving zijn geïmplementeerd, met inbegrip van verbindingen, gateways, stromen en Common Data Service-databases.  Stel dat u twee omgevingen, met de naam 'Test' en 'Ontw', hebt gemaakt met in elk van die omgevingen een Common Data Service-database. Als u in de omgeving 'Test' een app maakt, is deze alleen gemachtigd om verbinding te maken met de database 'Test' en niet met de database 'Ontw'.

Er is ook een proces om resources tussen omgevingen te verplaatsen. Zie [Migrate resources (Resources migreren)](environment-and-tenant-migration.md) voor meer informatie.

![](./media/environments-overview/Environments.png)

## <a name="environment-permissions"></a>Omgevingsmachtigingen
Omgevingen hebben twee ingebouwde rollen die toegang bieden tot machtigingen in een omgeving:

* Personen met de rol Environment Admin (omgevingsbeheerder) kunnen in een omgeving alle beheerderstaken uitvoeren, met inbegrip van:
  
  o    Een gebruiker of groep toevoegen aan of verwijderen uit de rol Environment Admin of Environment Maker
  
  o    Een Common Data Service-database voor de omgeving inrichten
  
  o    Alle resources die in een omgeving zijn gemaakt, weergeven en beheren
  
  o    Beleid instellen ter preventie van gegevensverlies. Zie [Data loss prevention policies (Beleid ter preventie van gegevensverlies)](prevent-data-loss.md) voor meer informatie.
* Personen met de rol Environment Maker kunnen in een omgeving resources maken, met inbegrip van apps, verbindingen, aangepaste connectors, gateways en stromen met behulp van Microsoft Flow.

Environment Makers die apps in een omgeving maken, kunnen deze apps ook distribueren naar andere gebruikers in uw organisatie door de app te delen met individuele gebruikers of beveiligingsgroepen, of naar alle gebruikers in de organisatie. Zie [Een app delen in PowerApps](share-app.md) voor meer informatie.

Gebruikers of groepen die aan deze omgevingsrollen zijn toegewezen, krijgen niet automatisch toegang tot de omgevingsdatabase (indien aanwezig). Zij moeten afzonderlijk toegang krijgen van de eigenaar van een database. Zie [Configure database security (Databasebeveiliging configureren)](database-security.md) voor meer informatie.

Gebruikers of beveiligingsgroepen kunnen aan een van deze twee rollen worden toegewezen door een Environment Admin van het [PowerApps-beheercentrum][1]. Zie [Environment Administration (Beheer van omgeving)](environments-administration.md) voor meer informatie.

![](./media/environments-overview/EnvironmentRoles.png)

## <a name="the-default-environment"></a>De standaardomgeving
PowerApps maakt automatisch één standaardomgeving voor elke tenant, die door alle gebruikers in die tenant wordt gedeeld. Wanneer nieuwe gebruikers zich aanmelden voor PowerApps, worden ze automatisch toegevoegd aan de rol Maker van de standaardomgeving. De standaardomgeving wordt in de dichtstbijzijnde regio van de standaardregio van de AAD-tenant gemaakt.

> [!NOTE]
> Aan de rol Admin van de standaardomgeving worden niet automatisch gebruikers toegevoegd. Zie [Environment Administration (Beheer van omgeving)](environments-administration.md) voor meer informatie.
> 
> 

De standaardomgeving heet: "{naam van Azure AD-tenant} (standaard)"

![](./media/environments-overview/DefaultEnvironment.png)

## <a name="choosing-an-environment"></a>Een omgeving kiezen
Door de introductie van omgevingen ziet u een nieuwe ervaring wanneer u naar [https://web.powerapps.com](https://web.powerapps.com) gaat.  De apps, verbindingen en andere items die zichtbaar zijn op de site worden nu gefilterd op basis van de huidige omgeving die is geselecteerd.  Uw huidige omgeving is vermeld in de omgevingskiezer rechts van de kop. Als u een andere omgeving wilt kiezen, klikt of tikt u op de kiezer om een lijst met beschikbare omgevingen weer te geven. Klik of tik op de omgeving waartoe u toegang wenst.

In de kiezer worden omgevingen weergegeven als u aan een van de volgende voorwaarden voldoet:

1. U bent lid van de rol Environment Admin voor de omgeving.
2. U bent lid van de rol Environment Maker voor de omgeving.
3. U bent geen Environment Admin of Environment Maker van de omgeving, maar u hebt tot ten minste één app in de omgeving toegang gekregen als 'Medewerker'. Zie [Een app delen](share-app.md) voor meer informatie. **Opmerking**: in dit geval kunt u geen apps maken in deze omgeving. U kunt alleen de bestaande apps wijzigen die met u zijn gedeeld.

![](./media/environments-overview/EnvironmentPicker.png)

## <a name="creating-an-environment"></a>Een omgeving maken
### <a name="who-can-create-environments"></a>Wie kan omgevingen maken?
Uw licentie bepaalt of u omgevingen kunt maken.

| Licentie | Gemachtigd om omgeving te maken |
| --- | --- |
| PowerApps P2 |√ |
| PowerApps P2-proefversie |√ |
| PowerApps P1 |x |
| PowerApps P1-proefversie |x |
| Dynamics 365-abonnementen |x |
| Office 365-abonnementen |x |
| Dynamics 365-abonnementen voor Apps en Teams |x |

Elke gebruiker kan maximaal twee omgevingen maken.

### <a name="where-can-environments-be-created"></a>Waar kunnen omgevingen worden gemaakt?
U kunt nieuwe omgevingen maken in [PowerApps.com][2] en vanuit het [PowerApps-beheercentrum][1]. Als u een omgeving maakt, wordt u voor die omgeving automatisch toegevoegd aan de rol Environment Admin. Er is geen limiet op het aantal omgevingen waaraan u kunt deelnemen als lid van de rol Environment Admin of Environment Maker. Zie [Environment Administration (Beheer van omgeving)](environments-administration.md) voor meer informatie.

![](./media/environments-overview/CreateEnvironmentDialog.png)

## <a name="what-will-change-for-powerapps-preview-users"></a>Wat verandert er voor PowerApps Preview-gebruikers?
Gebruikers die aan de PowerApps-preview hebben deelgenomen, zullen enkele wijzigingen gewaarworden in hun ervaring met de introductie van omgevingen.  De volgende tabel geeft aan wat gebruikers binnen en buiten de Verenigde Staten kunnen verwachten:

| User | Wat gebeurt er |
| --- | --- |
| Preview-gebruiker die een Common Data Service-database heeft gemaakt |U ziet een omgeving met de naam "Omgeving van {uw eigen naam}" die uw Common Data Service-previewdatabase bevat en alle apps die u ervoor hebt ontwikkeld.  U wordt toegevoegd aan de rollen Environment Maker en Environment Admin van deze omgeving en als een database-eigenaar van de database. Wanneer PowerApps algemeen beschikbaar komt, zullen we de metagegevens van de Common Data Service bijwerken. Deze wijziging heeft als gevolg dat u nog steeds de entiteiten en apps kunt gebruiken die u al hebt gebouwd voor uw Common Data Service-previewdatabase. U zult in die database echter geen velden of entiteiten kunnen maken. Binnenkort zullen wij richtlijnen publiceren voor het maken van een omgeving met een database die de bijgewerkte metagegevens bevat en voor het migreren van uw apps naar die omgeving.<br>**Opmerking**: als uw apps die voor uw Common Data Service-previewdatabase zijn gebouwd, ook een aangepaste connector als gegevensbron gebruiken, zullen ze in deze omgeving tijdelijk niet werken omdat alle aangepaste connectors naar de standaardomgeving worden gemigreerd. U moet de aangepaste connector in deze omgeving opnieuw maken om alle betrokken apps te herstellen. |
| Preview-gebruiker in de Verenigde Staten |De volgende resources die u tijdens de preview-periode van PowerApps hebt gemaakt, komen beschikbaar in de standaardomgeving van uw tenant:<br>- Alle apps die u hebt gemaakt (met uitzondering van apps die verbinding maakten met een Common Data Service-previewdatabase)<br>- Alle verbindingen en aangepaste connectors die u hebt gemaakt<br>- Alle on-premises gegevensgateways die u hebt geïnstalleerd |
| Preview-gebruiker buiten de Verenigde Staten |Naast de standaardomgeving ziet u ook een omgeving met de naam "{Azure AD-tenant} (van preview)" die de volgende resources bevat die u tijdens de preview-periode van PowerApps hebt gemaakt:<br>- Alle apps die u hebt gemaakt (met uitzondering van apps die verbinding maakten met een Common Data Service-previewdatabase)<br>- Alle verbindingen en aangepaste connectors die u hebt gemaakt<br>- Alle on-premises gegevensgateways die u hebt geïnstalleerd.<br>U wordt toegevoegd aan de rol Environment Maker van deze omgeving. |

Een *preview-gebruiker* is iemand die Microsoft PowerApps gebruikt voordat het algemeen beschikbaar (AB) is.

Twee weken nadat PowerApps algemeen beschikbaar (AB) wordt gesteld, zullen omgevingen die preview-inhoud bevatten, als alleen-lezen worden gemarkeerd (met uitzondering van de standaardomgeving); alle bestaande apps en stromen blijven in deze omgevingen werken, maar u kunt geen apps of stromen maken. Het is raadzaam dat gebruikers van deze omgevingen hun inhoud migreren naar de standaardomgeving of een andere aangepaste omgeving. Raadpleeg de volgende blog (die deze week wordt gepost) voor meer informatie over het migratieproces: [Common Data Service features announcement blog (Aankondigingsblog Common Data Service-functies)][3].

### <a name="example-environments-for-a-preview-user-in-us"></a>Voorbeeldomgevingen voor een preview-gebruiker in de Verenigde Staten
![](./media/environments-overview/USuser1.png)

### <a name="example-environments-for-a-preview-user-not-in-us"></a>Voorbeeldomgevingen voor een preview-gebruiker buiten de Verenigde Staten
![](./media/environments-overview/non-USuser1.png)

## <a name="managing-environments-for-your-organization"></a>Omgevingen voor uw organisatie beheren
Bij de introductie van omgevingen introduceren we ook het PowerApps-beheercentrum, waarin u alle omgevingen kunt beheren die u hebt gemaakt of waarvoor u aan de rol Environment Admin bent toegevoegd. In het beheercentrum kunt u alle beheerderstaken uitvoeren op een omgeving, waaronder de volgende:

* Een gebruiker of groep toevoegen aan of verwijderen uit de rol Environment Admin of Environment Maker.  Zie [Environment Administration (Beheer van omgeving)](environments-administration.md) voor meer informatie.
* Een Common Data Service-database voor de omgeving inrichten. Zie [Create a Common Data Service database (Een Common Data Service-database maken)](create-database.md) voor meer informatie.
* Beleid instellen ter preventie van gegevensverlies. Zie [Data loss prevention policies (Beleid ter preventie van gegevensverlies)](prevent-data-loss.md) voor meer informatie.
* Databasebeveiligingsbeleid instellen (als open of beperkt door databaserollen). Zie [Configure database security (Databasebeveiliging configureren)](database-security.md) voor meer informatie.
* Leden met de rol Global Administrator (Hoofdbeheerder) van de Azure AD-tenant (inclusief Office 365-hoofdbeheerders) kunnen ook alle omgevingen beheren die in hun tenant zijn gemaakt en tenant-brede beleidsregels instellen vanuit het PowerApps-beheercentrum.

<!--Reference links in article-->
[1]: https://admin.powerapps.com
[2]: https://web.powerapps.com
[3]: https://aka.ms/cdspreviewtoga
