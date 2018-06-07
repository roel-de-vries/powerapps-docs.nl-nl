---
title: Omgevingsbeveiliging configureren | Microsoft Docs
description: In dit onderwerp wordt uitgelegd hoe u omgevingsbeveiliging kunt configureren.
author: manasmams
manager: kfile
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: manasma
ms.openlocfilehash: d9bd70acaacbbeda98c14337035a233b7c70c181
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34168154"
---
# <a name="configure-environment-security"></a>Omgevingsbeveiliging configureren
Common Data Service (CDS) for Apps gebruikt een op rollen gebaseerd beveiligingsmodel om de toegang tot de database te beveiligen. In dit onderwerp wordt uitgelegd hoe u de beveiligingsartefacten maakt die u nodig hebt om een app te beveiligen. De gebruikersrollen bepalen de runtime-toegang tot gegevens en staan los van de omgevingsrollen voor omgevingsbeheerders en omgevingsmakers. Zie [Environments overview](environments-overview.md) (Overzicht van omgevingen) voor een overzicht van omgevingen.

## <a name="assign-security-roles-to-users"></a>Beveiligingsrollen aan gebruikers toewijzen
Met beveiligingsrollen kunt u de toegang van een gebruiker tot gegevens beheren met een set met toegangsniveaus en -machtigingen. De toegangsniveaus en -machtigingen die zijn opgenomen in een bepaalde beveiligingsrol, zorgen ervoor dat er limieten gelden voor de weergave van gegevens aan de gebruiker en de interactie van de gebruiker met deze gegevens.

Een omgevingsbeheerder kan als volgt via het [PowerApps-beheercentrum][1] een omgevingsrol toewijzen aan een gebruiker of beveiligingsgroep:

1. Selecteer de omgeving in de tabel met omgevingen.

    ![](./media/environment-admin/environment-list-new.png)

2. Selecteer het tabblad **Beveiliging**.

3. Kijk of de gebruiker al in de omgeving bestaat door **view the list of users in the environment** (De lijst met gebruikers in de omgeving weergeven) te selecteren.
    
    ![](./media/database-security/security-viewuser.png)

4. Als de gebruiker niet bestaat, kunt u de gebruiker toevoegen vanuit het PowerApps-beheercentrum. Voeg de gebruiker toe door het e-mailadres van de gebruiker in uw organisatie te vermelden en **Gebruiker toevoegen** te selecteren.

    ![](./media/database-security/security-adduser.png)

    Wacht enkele minuten en controleer dan of de gebruiker beschikbaar is in de lijst met gebruikers in de omgeving.
  
5. Selecteer de gebruiker in de lijst met gebruikers in de omgeving.

    ![](./media/environment-admin/D365-Select-User.png)

6. Wijs de rol aan de gebruiker toe.

    ![](./media/environment-admin/D365-Assign-Role.png)

    > [!NOTE]
    > Op dit moment kunnen rollen alleen worden toegewezen aan de gebruikers. Aan de functie voor het toewijzen van rollen aan beveiligingsgroepen wordt nog gewerkt.

7. Selecteer **OK** om de toewijzingen van de omgevingsrol bij te werken.

## <a name="predefined-security-roles"></a>Vooraf gedefinieerde beveiligingsrollen
De PowerApps-omgeving bevat vooraf gedefinieerde beveiligingsrollen die overeenkomen met algemene gebruikerstaken. Voor deze beveiligingsrollen zijn toegangsniveaus gedefinieerd waarmee toegang wordt geboden tot de minimale hoeveelheid zakelijke gegevens die nodig is om de app te kunnen gebruiken.

|Beveiligingsrol  |* Databasebevoegdheden  |Beschrijving |
|---------|---------|---------|
|Systeembeheerder     |  Maken, Lezen, Schrijven, Verwijderen, Aanpassingen, Beveiligingsrollen       | Personen met deze rol hebben volledige machtiging voor het aanpassen of beheren van de omgeving, inclusief het maken, wijzigen en toewijzen van beveiligingsrollen. Hiermee kunt u alle gegevens in de omgeving weergeven. Zie [Vereiste bevoegdheden voor aanpassen](https://docs.microsoft.com/dynamics365/customer-engagement/customize/privileges-required-customization) voor meer informatie        |
|Systeemaanpasser     | Maken (zelf), Lezen (zelf), Schrijven (zelf), Verwijderen (zelf), Aanpassingen         | Hiermee hebt u volledige machtiging voor het aanpassen van de omgeving. De systeemaanpasser kan echter alleen records weergeven voor de omgevingsentiteiten die de aanpasser maakt. Zie [Vereiste bevoegdheden voor aanpassen](https://docs.microsoft.com/dynamics365/customer-engagement/customize/privileges-required-customization) voor meer informatie.        |
|Omgevingsmaker     |  Geen       | Hiermee kunt u met Microsoft Flow nieuwe aan een omgeving gekoppelde resources maken, waaronder apps, verbindingen, aangepaste API's, gateways en stromen. Hiermee hebt u echter geen toegang tot gegevens in een omgeving. Zie [Overzicht van omgevingen](https://powerapps.microsoft.com/blog/powerapps-environments/) voor meer informatie.        |
|Common Data Service-gebruiker     |  Lezen, Maken (zelf), Schrijven (zelf), Verwijderen (zelf)       | Hiermee kunnen gebruikers een app in de omgeving uitvoeren en veelvoorkomende taken uitvoeren voor de records waarvan ze eigenaar zijn.        |
|Delegeren     | Handelen namens een andere gebruiker        | Hiermee kunt u code uitvoeren als een andere gebruiker of door een andere gebruiker te imiteren.  Deze rol wordt doorgaans gebruikt met een andere beveiligingsrol zodat toegang tot records kan worden verkregen. Zie [Een andere gebruiker imiteren](https://docs.microsoft.com/dynamics365/customer-engagement/developer/org-service/impersonate-another-user) voor meer informatie        |

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
