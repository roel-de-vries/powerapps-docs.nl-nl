---
title: Een app delen | Microsoft Docs
description: Deel uw app door anderen toestemming te geven die uit te voeren of te wijzigen
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 07/11/2018
ms.author: anneta
ms.openlocfilehash: 197eb5223c0945a7cb80d8b187aaf44c871e798c
ms.sourcegitcommit: 79a58f1b6880cbc512b64cde71a4d532cebe5bed
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/18/2018
ms.locfileid: "39137017"
---
# <a name="share-an-app-in-powerapps"></a>Een app delen in PowerApps

Nadat u een app hebt ontwikkeld die aansluit op een bedrijfsbehoefte, geeft u op welke gebruikers in uw organisatie de app kunnen uitvoeren en welke gebruikers de app kunnen wijzigen en zelfs opnieuw kunnen delen. U kunt elke gebruiker op naam opgeven of een beveiligingsgroep in Azure Active Directory opgeven. Als iedereen gebruikmaakt van uw app, geeft u op dat uw hele organisatie de app kan uitvoeren.

> [!IMPORTANT]
> U moet ook de machtigingen voor de gegevensbron of -bronnen beheren waarop de app is gebaseerd, zoals [Common Data Service for Apps](#common-data-service-for-apps) of [Excel](share-app-data.md), zodat een gedeelde app naar behoren werkt. Mogelijk moet u ook [andere resources](share-app-resources.md) delen waarvan de app afhankelijk is, zoals stromen, gateways of verbindingen.

## <a name="prerequisites"></a>Vereisten

Voordat u een app deelt, moet u deze in de cloud (niet lokaal) opslaan en vervolgens de app publiceren.

- Geef uw app een betekenisvolle naam en een duidelijke beschrijving, zodat gebruikers weten wat uw app doet en ze deze gemakkelijk in een lijst kunnen vinden. Selecteer in het menu **Bestand** in PowerApps Studio de optie **App-instellingen**, geef een naam op en typ of plak een beschrijving.

- Wanneer u wijzigingen aanbrengt, moet u de app opnieuw opslaan en publiceren als u wilt dat anderen deze wijzigingen kunnen zien.

## <a name="share-an-app"></a>Een app delen

1. [Meld u aan](https://web.powerapps.com) bij PowerApps en selecteer vervolgens bij de linkerrand **Apps**.

    ![Lijst met apps weergeven](./media/share-app/file-apps.png)

1. Selecteer het beletselteken (...) voor de app die u wilt delen en selecteer vervolgens **Delen**.

    ![Scherm voor delen openen](./media/share-app/ellipsis-share.png)

1. Geef op met welke gebruikers of beveiligingsgroepen in Azure Active Directory u de app wilt delen.

    > [!NOTE]
    > U kunt apps niet delen met een distributiegroep in uw organisatie of met gebruikers of groepen buiten uw organisatie.

    ![Gebruikers opgeven](./media/share-app/share-list.png)

    U kunt ook de app met uw hele organisatie delen, zodat ze de app kunnen uitvoeren, maar niet kunnen wijzigen of te delen.

1. (optioneel) Schakel het selectievakje in voor het verzenden van een uitnodiging via e-mail naar gebruikers, zodat ze uw app kunnen vinden.

    De uitnodiging bevat een koppeling die gebruikers kunnen selecteren om de app uit te voeren.

    - Als een gebruiker de koppeling op een desktopcomputer selecteert, wordt de app geopend in [Dynamics 365](http://home.dynamics.com).
    - Als de gebruiker de koppeling op een mobiel apparaat selecteert, wordt de app in PowerApps Mobile geopend.

    Als u gebruikers machtigt om de app te wijzigen, bevat het bericht ook een aparte koppeling om de app in PowerApps Studio te openen en te bewerken.

    Gebruikers kunnen de app vanuit AppSource in [Dynamics 365](http://home.dynamics.com) uitvoeren, ongeacht of u een uitnodiging verzendt. Gebruikers die over de machtiging **Kan bewerken** beschikken, kunnen de app ook in [PowerApps](http://web.powerapps.com) zelf bewerken.

1. Geef de machtiging voor elke gebruiker of beveiligingsgroep op en selecteer vervolgens **Opslaan**.

    - **Kan gebruiken**: de gebruikers kunnen de app uitvoeren, maar niet delen.
    - **Kan bewerken**: gebruikers kunnen de app uitvoeren, aanpassen en de aangepaste versie met andere gebruikers delen.

        ![Machtigingen opgeven](./media/share-app/edit-use.png)

    Als u machtigingen voor een gebruiker of beveiligingsgroep wilt wijzigen, selecteert u de pijl-omlaag naast de machtiging die de gebruiker of groep al heeft en geeft u vervolgens een andere machtiging op.

    Als u alle machtigingen voor een gebruiker of groep wilt verwijderen, selecteert u het **x**-pictogram voor de betreffende gebruiker of groep.

## <a name="security-group-considerations"></a>Overwegingen voor beveiligingsgroepen

- Wanneer u een app deelt met een beveiligingsgroep, beschikken alle bestaande leden van die groep en iedereen die eraan wordt toegevoegd over de machtigingen die u opgeeft voor die groep. Iedereen die de groep verlaat, raakt die machtiging kwijt, tenzij ze deel uitmaken van een andere groep die toegang heeft of u ze als afzonderlijke gebruiker machtigt.
- Ieder lid van een beveiligingsgroep heeft dezelfde machtiging voor een app als de hele groep. U kunt echter meer machtigingen opgeven voor een of meer leden van die groep om ze meer mogelijkheden te bieden. U kunt bijvoorbeeld beveiligingsgroep A de machtiging **Can use** geven, maar u kunt ook gebruiker B, die deel uitmaakt van deze groep, de machtiging **Can edit** geven. Elk lid van de beveiligingsgroep kan de app uitvoeren, maar alleen gebruiker B kan deze bewerken. Als u de beveiligingsgroep A de machtiging **Can edit** geeft en gebruiker B de machtiging **Can use**, kan die gebruiker de app alsnog bewerken.

## <a name="manage-entity-permissions"></a>Machtigingen voor entiteiten beheren

### <a name="common-data-service-for-apps"></a>Common Data Service for Apps

Als u een app maakt op basis van Common Data Service for Apps, moet u er ook voor zorgen dat de gebruikers die de app uitvoeren over de juiste machtigingen beschikken voor de entiteit of entiteiten waarop de app is gebaseerd. Die gebruikers moeten met name behoren tot een beveiligingsrol, waarmee taken kunnen worden gevoerd als het maken, lezen, schrijven en/of verwijderen van de betreffende records. Als u over machtigingen voor **Systeembeheerder** of **Systeemaanpasser** beschikt voor de database in deze omgeving, kunt u een aangepaste rol maken en hieraan vervolgens gebruikers toevoegen.

#### <a name="create-a-security-role"></a>Een beveiligingsrol maken

1. [Meld u aan bij PowerApps](https://web.powerapps.com) en zorg ervoor dat u zich in dezelfde omgeving bevindt als de app die u wilt delen.

1. Selecteer in de rechterbovenhoek het tandwielpictogram en selecteer vervolgens **Geavanceerde aanpassingen**.

    ![Het deelvenster Geavanceerde aanpassingen openen](media/share-app/advanced-customizations.png)

1. Selecteer de koppeling **Beveiligingsrollen**.

    ![Beveiligingsrollen openen](media/share-app/security-roles.png)

1. Selecteer onder **Alle rollen** de optie **Nieuw** en typ of plak vervolgens een naam voor de rol die u maakt.

    ![Beveiligingsrol maken](media/share-app/new-role.png)

1. Selecteer een of meer tabbladen om de entiteit of entiteiten te vinden die door uw app worden gebruikt en selecteer vervolgens de machtigingen die u aan de beveiligingsrol wilt toekennen.

    In deze afbeelding ziet u bijvoorbeeld dat met een beveiligingsrol records kunnen worden gemaakt, gelezen, geschreven en verwijderd in de entiteit Account, die op het tabblad **Basisrecords** wordt weergegeven.

    ![Machtigingen opgeven](media/share-app/grant-access.png)

1. Selecteer **Opslaan en sluiten**.

#### <a name="assign-a-user-to-a-role"></a>Een gebruiker toewijzen aan een rol

1. Open het deelvenster **Geavanceerde aanpassingen**, zoals in de vorige procedure wordt beschreven, en selecteer vervolgens de koppeling **Gebruikers**.

    ![De koppeling Gebruikers](media/share-app/open-users.png)

1. Typ of plak in de rechterbovenhoek de naam van de gebruiker die u aan de rol wilt toewijzen en selecteer vervolgens het zoekpictogram.

    ![Gebruikers zoeken](media/share-app/search-users.png)

1. In de lijst met zoekresultaten wijst u het gewenste resultaat aan en schakelt u vervolgens het selectievakje in dat wordt weergegeven.

1. Selecteer in de bovenste banner **Rollen beheren**.

1. Schakel in het dialoogvenster dat wordt weergegeven de selectievakjes voor **Common Data Service-gebruiker** en de rol die gebruikers nodig hebben voor uw app in en selecteer vervolgens **OK**.

    ![Een gebruiker toewijzen aan een rol](media/share-app/assign-users.png)

### <a name="common-data-service-previous-version"></a>Common Data Service (vorige versie)

Wanneer u een app deelt die is gebaseerd op een oudere versie van Common Data Service, moet u de runtime-machtiging voor de service afzonderlijk delen. Als u niet gemachtigd bent om dit te doen, neemt u contact op met de beheerder van uw omgeving.