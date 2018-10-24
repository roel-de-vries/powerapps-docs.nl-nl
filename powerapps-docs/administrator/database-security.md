---
title: Omgevingsbeveiliging configureren | Microsoft Docs
description: In dit onderwerp wordt uitgelegd hoe u omgevingsbeveiliging kunt configureren.
author: manasmams
manager: kvivek
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 10/10/2018
ms.author: manasma
search.audienceType:
- admin
search.app:
- D365CE
- PowerApps
- Powerplatform
ms.openlocfilehash: 3c8bdcb855b1e15cbebeb2a51fedf8aea7684286
ms.sourcegitcommit: c4369e5f31bb08716f1af1416f3f7510a4b926d5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/10/2018
ms.locfileid: "49072514"
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
|Common Data Service-gebruiker     |  Lezen (zelf), Maken (zelf), Schrijven (zelf), Verwijderen (zelf)       | Hiermee kunnen gebruikers een app in de omgeving uitvoeren en veelvoorkomende taken uitvoeren voor de records waarvan ze eigenaar zijn.        |
|Delegeren     | Handelen namens een andere gebruiker        | Hiermee kunt u code uitvoeren als een andere gebruiker of door een andere gebruiker te imiteren.  Deze rol wordt doorgaans gebruikt met een andere beveiligingsrol zodat toegang tot records kan worden verkregen. Zie [Een andere gebruiker imiteren](https://docs.microsoft.com/dynamics365/customer-engagement/developer/org-service/impersonate-another-user) voor meer informatie        |

* Bevoegdheid heeft globaal bereik, tenzij anders aangegeven.

- Personen met de rol Omgevingsmaker kunnen niet alleen resources in een omgeving maken, ze kunnen ook de apps die ze in een omgeving bouwen naar andere gebruikers in uw organisatie distribueren. Ze kunnen de app delen met afzonderlijke gebruikers. Zie [Een app delen in PowerApps](../maker/canvas-apps/share-app.md) voor meer informatie.

- Aan gebruikers die apps maken waarmee verbinding met de database wordt gemaakt en aan gebruikers die entiteiten en beveiligingsrollen moeten maken en bijwerken, moet ook de rol Systeemaanpasser worden toegewezen, samen met de rol Omgevingsmaker, omdat de rol Omgevingsmaker geen bevoegdheden voor de database heeft.

## <a name="create-or-configure-a-custom-security-role"></a>Een aangepaste beveiligingsrol maken of configureren
Als uw app gebruikmaakt van een aangepaste entiteit, moeten de bevoegdheden ervan expliciet worden toegewezen in een veiligheidsrol voordat uw app kan worden gebruikt.  U kunt deze bevoegdheden toevoegen aan een bestaande beveiligingsrol of een aangepaste beveiligingsrol maken. Er is een set minimale bevoegdheden die nodig zijn om de nieuwe beveiligingsrol te gebruiken. Raadpleeg [Minimale bevoegdheden om app uit te voeren](#minimum-privileges-to-run-app).

> [!TIP]
> Als u een aangepaste beveiligingsrol wilt maken met de minimaal vereiste bevoegdheden om een app uit te voeren, raadpleegt u de onderstaande sectie: [Minimale bevoegdheden om een app uit te voeren](#minimum-privileges-to-run-app).

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

## <a name="minimum-privileges-to-run-app"></a>Minimale bevoegdheden om een app uit te voeren
Wanneer u een aangepaste beveiligingsrol maakt, moet u een set minimaal vereiste bevoegdheden opnemen in de beveiligingsrol voordat een gebruiker een app kan uitvoeren. We hebben een oplossing gemaakt die u kunt importeren en waarin een beveiligingsrol is opgenomen met de minimaal vereiste bevoegdheden.  

Begin door de oplossing te downloaden uit het Downloadcentrum: [CDS for Apps minimum privilege security role](http://download.microsoft.com/download/6/5/5/6552A30E-05F4-45F0-AEE3-9BB01E13118A/MinprivilegeSecRole_1_0_0_0.zip).

Volg vervolgens de aanwijzingen om de oplossing te importeren: [Oplossingen importeren, bijwerken en exporteren](../maker/common-data-service/import-update-export-solutions.md).

Wanneer u de oplossing importeert, wordt de rol **min prv apps use** gemaakt die u kunt kopiëren (raadpleeg [Een beveiligingsrol maken door Rol kopiëren](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/admin/create-edit-security-role#create-a-security-role-by-copy-role)). Wanneer Rol kopiëren is voltooid, navigeert u naar elk tabblad (Kernrecords, Business Management, Aanpassing, enz.) en stelt u de juiste bevoegdheden in. 

> [!IMPORTANT]
> U moet de oplossing in een ontwikkelingsomgeving uitproberen voordat u deze importeert in een productieomgeving. 

<!--Reference links in article-->
[1]: https://admin.powerapps.com
