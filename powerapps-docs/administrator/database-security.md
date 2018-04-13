---
title: Omgevingsbeveiliging configureren | Microsoft Docs
description: In dit onderwerp wordt uitgelegd hoe u omgevingsbeveiliging kunt configureren.
services: powerapps
suite: powerapps
documentationcenter: na
author: manasmams
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/21/2018
ms.author: manasma
ms.openlocfilehash: 425600830a64652df7084a0222c02273a1607818
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2018
---
# <a name="configure-environment-security"></a>Omgevingsbeveiliging configureren
Common Data Service gebruikt een op rollen gebaseerd beveiligingsmodel om de toegang tot de database te beveiligen. In dit onderwerp wordt uitgelegd hoe u de beveiligingsartefacten maakt die u nodig hebt om een app te beveiligen. De gebruikersrollen bepalen de runtime-toegang tot gegevens en staan los van de omgevingsrollen voor omgevingsbeheerders en omgevingsmakers. Zie [Environments overview](environments-overview.md) (Overzicht van omgevingen) voor een overzicht van omgevingen.

## <a name="assign-security-roles-to-users"></a>Beveiligingsrollen aan gebruikers toewijzen
Met beveiligingsrollen kunt u de toegang van een gebruiker tot gegevens beheren met een set met toegangsniveaus en -machtigingen. De toegangsniveaus en -machtigingen die zijn opgenomen in een bepaalde beveiligingsrol, zorgen ervoor dat er limieten gelden voor de weergave van gegevens aan de gebruiker en de interactie van de gebruiker met deze gegevens.

Een omgevingsbeheerder kan als volgt via het [PowerApps-beheercentrum][1] een omgevingsrol toewijzen aan een gebruiker of beveiligingsgroep:

1. Selecteer de omgeving in de tabel met omgevingen.

    ![](./media/environment-admin/environment-list-new.png)

2. Selecteer het tabblad **Beveiliging**.

3. Klik op de koppeling voor het beheren van de omgevingsrollen in Dynamics 365.

    ![](./media/environment-admin/Security-Link-D365.png)

4. Selecteer de gebruiker in de lijst met gebruikers in de omgeving.

    ![](./media/environment-admin/D365-Select-User.png)

5. Wijs de rol aan de gebruiker toe.

    ![](./media/environment-admin/D365-Assign-Role.png)

    > [!NOTE]
    > Op dit moment kunnen rollen alleen worden toegewezen aan de gebruikers. Aan de functie voor het toewijzen van rollen aan beveiligingsgroepen wordt nog gewerkt.

6. Selecteer **OK** om de toewijzingen van de omgevingsrol bij te werken.


## <a name="predefined-security-roles"></a>Vooraf gedefinieerde beveiligingsrollen
De PowerApps-omgeving bevat vooraf gedefinieerde beveiligingsrollen die overeenkomen met algemene gebruikerstaken. Voor deze beveiligingsrollen zijn toegangsniveaus gedefinieerd waarmee toegang wordt geboden tot de minimale hoeveelheid zakelijke gegevens die nodig is om de app te kunnen gebruiken.

|Beveiligingsrol  |* Databasebevoegdheden  |Beschrijving |
|---------|---------|---------|
|Systeembeheerder     |  Maken, Lezen, Schrijven, Verwijderen, Aanpassingen, Beveiligingsrollen       | Personen met deze rol hebben volledige machtiging voor het aanpassen of beheren van de omgeving, inclusief het maken, wijzigen en toewijzen van beveiligingsrollen. De systeembeheerder kan alle gegevens in de omgeving weergeven. Zie [Vereiste bevoegdheden voor aanpassen](https://docs.microsoft.com/dynamics365/customer-engagement/customize/privileges-required-customization) voor meer informatie.        |
|Systeemaanpasser     | Maken (zelf), Lezen (zelf), Schrijven (zelf), Verwijderen (zelf), Aanpassingen         | Personen met deze rol hebben volledige machtiging voor het aanpassen van de omgeving. De systeemaanpasser kan echter alleen records weergeven voor de omgevingsentiteiten die de aanpasser maakt. Zie [Vereiste bevoegdheden voor aanpassen](https://docs.microsoft.com/dynamics365/customer-engagement/customize/privileges-required-customization) voor meer informatie.        |
|Omgevingsmaker     |  Geen       | Personen met deze rol kunnen nieuwe resources voor een omgeving maken, waaronder apps, verbindingen, aangepaste API's, gateways en stromen met behulp van Microsoft Flow. De omgevingsmaker heeft echter geen toegang tot gegevens in een omgeving. Zie [Overzicht van omgevingen](https://powerapps.microsoft.com/blog/powerapps-environments/) voor meer informatie.        |
|Common Data Service-gebruiker     |  Lezen, Maken (zelf), Schrijven (zelf), Verwijderen (zelf)       | Personen met deze rol kunnen een app in de omgeving uitvoeren en veelvoorkomende taken uitvoeren voor de records waarvan ze eigenaar zijn.        |
|Delegeren     | Handelen namens een andere gebruiker        | Hiermee kunt u code uitvoeren als een andere gebruiker of door een andere gebruiker te imiteren.  Deze rol wordt doorgaans gebruikt met een andere beveiligingsrol zodat toegang tot records kan worden verkregen. Zie het Engelstalige artikel [Impersonate another user](https://docs.microsoft.com/dynamics365/customer-engagement/developer/org-service/impersonate-another-user) (Een andere gebruiker imiteren) voor meer informatie.        |

* Bevoegdheid heeft globaal bereik, tenzij anders aangegeven.

- Personen met de rol Omgevingsmaker kunnen niet alleen resources in een omgeving maken, ze kunnen ook de apps die ze in een omgeving bouwen naar andere gebruikers in uw organisatie distribueren. Ze kunnen de app delen met afzonderlijke gebruikers. Zie [Een app delen in PowerApps](../maker/canvas-apps/share-app.md) voor meer informatie.

- Aan gebruikers die apps maken waarmee verbinding met de database wordt gemaakt en aan gebruikers die entiteiten en beveiligingsrollen moeten maken en bijwerken, moet ook de rol Systeemaanpasser worden toegewezen, samen met de rol Omgevingsmaker, omdat de rol Omgevingsmaker geen bevoegdheden voor de database heeft.


## <a name="create-or-configure-a-custom-security-role"></a>Een aangepaste beveiligingsrol maken of configureren
Als uw app is gebaseerd op een aangepaste entiteit, moeten de bevoegdheden expliciet worden opgegeven voordat gebruikers met de app kunnen werken. Dit kunt u op een van de volgende manieren doen.
- U kunt een bestaande vooraf gedefinieerde beveiligingsrol uitbreiden, zodat deze de bevoegdheden voor records bevat op basis van de aangepaste entiteit.
- U kunt een aangepaste beveiligingsrol maken voor het beheren van de bevoegdheden voor de gebruikers van de app.

Als de omgeving records bevat die door meerdere apps kunnen worden gebruikt, hebt u misschien meerdere beveiligingsrollen nodig voor toegang tot de gegevens met verschillende bevoegdheden. Bijvoorbeeld:
- Sommige gebruikers (type A) hebben alleen bevoegdheden nodig voor het lezen, bijwerken en koppelen van andere records. Voor deze gebruikers is een beveiligingsrol nodig met bevoegdheden voor lezen, schrijven en toevoegen.
- Andere gebruikers hebben misschien alle bevoegdheden van gebruikers van type A nodig, plus de mogelijkheid voor maken, toevoegen aan, verwijderen en delen. Aan hun beveiligingsrol moeten dus bevoegdheden worden toegevoegd voor maken, lezen, schrijven, toevoegen, verwijderen, toewijzen, toevoegen aan en delen.

Zie [Beveiligingsrollen](https://docs.microsoft.com/dynamics365/customer-engagement/admin/security-roles-privileges#security-roles) voor meer informatie over bevoegdheden voor toegang en bereik.

1. Selecteer in het [PowerApps-beheercentrum][1] de omgeving waarvoor u een beveiligingsrol wilt bijwerken.

    ![](./media/environment-admin/choose-environment-updated.png)

2. Klik op de koppeling op het tabblad **Details** om de omgeving in het Dynamics 365-beheercentrum te beheren.

3. Selecteer het exemplaar (met dezelfde naam van de omgeving) en klik op Openen.

    ![](./media/database-security/glados-instance-list.png)

4. Klik in de koptekst op **Instellingen** en selecteer **Beveiliging**.

    ![](./media/database-security/dyn365-settings-security.png)

5. Selecteer **Beveiligingsrollen**.

    ![](./media/database-security/dyn365-securityroles.png)

6. Klik op **Nieuw**.

7. In de ontwerpfunctie voor beveiligingsrollen selecteert u de acties (zoals lezen, schrijven of verwijderen) en het bereik voor deze acties.

8. Selecteer het tabblad en zoek uw entiteit (bijvoorbeeld **Aangepaste entiteiten**) om de machtigingen voor een aangepaste entiteit in te stellen.

9. Selecteer de bevoegdheden **Lezen, Schrijven, Toevoegen**.

10. Selecteer **Opslaan en sluiten**.



<!--Reference links in article-->
[1]: https://admin.powerapps.com
