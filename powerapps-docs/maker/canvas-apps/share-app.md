---
title: Een app delen | Microsoft Docs
description: Deel uw app door anderen toestemming te geven die uit te voeren of te wijzigen
documentationcenter: na
author: AFTOwen
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 03/18/2018
ms.author: anneta
ms.openlocfilehash: c87f0e644668e9b9804b001560402972fd3d4531
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "32329129"
---
# <a name="share-an-app-in-powerapps"></a>Een app delen in PowerApps
Het is fantastisch om apps te ontwikkelen die voldoen aan uw eigen zakelijke behoeften, maar de werkelijke kracht van PowerApps schuilt in het delen van die apps met anderen. In dit onderwerp wordt uitgelegd hoe u apps kunt delen met specifieke gebruikers of beveiligingsgroepen, of zelfs met uw hele organisatie.

## <a name="specify-an-app"></a>Een app opgeven
1. Meld u aan bij PowerApps en klik of tik vervolgens bij de linkerrand op **Apps**.

    ![Lijst met apps weergeven](./media/share-app/file-apps.png)

1. Klik of tik op het beletselteken (...) voor de app die u wilt delen en klik of tik op **delen**.

    ![Scherm voor delen openen](./media/share-app/ellipsis-share.png)

## <a name="share-an-app"></a>Een app delen
1. Geef aan met welke gebruikers of beveiligingsgroepen in Azure Active Directory u de app wilt delen en of u een e-mail wilt verzenden naar deze personen om ze op de hoogte te brengen.

    U kunt ook de app met uw hele organisatie delen, zodat ze de app kunnen uitvoeren, maar niet kunnen wijzigen of te delen.

    ![Gebruikers opgeven](./media/share-app/share-list.png)

1. Geef het machtigingsniveau op en klik of tik op **Opslaan**.

    * **Can use**: gebruikers of groepen kunnen de app uitvoeren, maar niet delen.
    * **Can edit**: gebruikers of groepen kunnen de app uitvoeren, aanpassen en de aangepaste versie verder delen met andere gebruikers.

        ![Machtigingen opgeven](./media/share-app/edit-use.png)

Als u de machtigingen voor een gebruiker of groep wilt wijzigen, herhaalt u stap 1 van deze procedure en geeft u een andere optie op in de lijst met machtigingen voor die gebruiker of groep. Als u alle machtigingen voor een gebruiker of groep wilt verwijderen, klikt of tikt u op het pictogram **x** voor de gebruiker of groep.

### <a name="send-email-notification"></a>E-mailmelding verzenden
Wanneer u een app deelt, kunt u aangeven of u dit de gebruikers of een beveiligingsgroep via e-mail wilt melden. Als u deze optie kiest, wordt er een e-mailbericht verzonden om de gebruikers of beveiligingsgroepen op de hoogte te brengen. Het e-mailbericht bevat een koppeling die toegang geeft tot de app. Indien van toepassing, worden gebruikers gevraagd om zich aan te melden voor PowerApps.

De melding bevat een ander soort koppeling, afhankelijk van de machtigingen die u toewijst:

- Wanneer u de app deelt met de machtiging **Can use**, bevat het e-mailbericht de koppeling om de app uit te voeren.
- Wanneer u de app deelt met de machtiging **Can edit**, bevat het e-mailbericht de koppeling om de app uit te voeren of te bewerken.

### <a name="how-do-my-users-see-the-app-i-shared"></a>Hoe kunnen mijn gebruikers de gedeelde app zien?
Nadat u een app deelt met een of meer gebruikers of beveiligingsgroepen, is hoe zij de app kunnen zien afhankelijk van de machtiging waarmee u de app hebt gedeeld.

##### <a name="if-you-shared-an-app-with-can-use-permission"></a>Als u een app hebt gedeeld met de machtiging *Mag gebruiken*
De mensen waarmee u de app hebt gedeeld ontvangen een e-mailmelding als u bij het delen van de app dit selectievakje hebt ingeschakeld. Ze kunnen in deze e-mail klikken of tikken op een koppeling om de app uit te voeren via [Dynamics 365](http://home.dynamics.com). Binnenkort wordt ook ondersteuning voor universele links geïmplementeerd, zodat de app in PowerApps Studio of PowerApps Mobile wordt geopend, indien PowerApps Studio of PowerApps Mobile is geïnstalleerd.

Gebruikers kunnen de app ook vinden via [Dynamics 365](http://home.dynamics.com), in AppSource (als u bijvoorbeeld geen e-mail heeft verzonden). [Meer informatie](../../user/app-source.md) over hoe gebruikers apps kunnen verkrijgen via AppSource.

##### <a name="if-you-shared-an-app-with-can-edit-permission"></a>Als u een app hebt gedeeld met de machtiging *Mag bewerken*
De mensen waarmee u de app hebt gedeeld ontvangen een e-mailmelding als u bij het delen van de app dit selectievakje hebt ingeschakeld. Ze kunnen in deze e-mail klikken of tikken op een koppeling om de app direct voor bewerking te openen in PowerApps Studio. De e-mail bevat ook een koppeling om de app uit te voeren via [Dynamics 365](http://home.dynamics.com). Binnenkort wordt ook ondersteuning voor universele koppelingen geïmplementeerd, zodat de app in PowerApps Studio of PowerApps Mobile wordt geopend indien PowerApps Studio of PowerApps Mobile is geïnstalleerd.

Gebruikers kunnen de app ook vinden op [powerapps.com](http://web.powerapps.com) (als u bijvoorbeeld geen e-mail hebt verzonden). Dit is de thuisbasis waar app-makers kunnen bladeren door alle apps die ze hebben gemaakt of die anderen met hen hebben gedeeld met de machtiging **Inzender**. [Dynamics 365](http://home.dynamics.com) biedt gebruikers dan weer de mogelijkheid snel apps van PowerApps en andere zakelijke apps uit te voeren.

## <a name="other-things-to-know"></a>Andere dingen die u moet weten
* Als u een app wilt delen, moet u deze op de cloud opslaan, niet lokaal.
* Bedenk, voordat u een app deelt, met welke gebruikers en beveiligingsgroepen u deze wilt delen en welke rol u ze wilt toekennen: **Can edit** of **Can use**. Wanneer u een app deelt met een groep, hebben alle aanwezige leden van die groep en iedereen die eraan wordt toegevoegd de machtigingen die u opgeeft. Personen die de groep verlaten verliezen deze machtigingen, tenzij ze lid zijn van een andere groep die toegang heeft, of u expliciete machtigingen voor hen opgeeft.
* Ieder lid van een groep heeft dezelfde machtigingen voor een app als de hele groep. U kunt echter meer machtigingen opgeven voor een of meer leden van die groep om ze meer mogelijkheden te bieden. U kunt bijvoorbeeld beveiligingsgroep A de machtiging **Can use** geven, maar u kunt ook gebruiker B, die deel uitmaakt van deze groep, de machtiging **Can edit** geven. Elk lid van de beveiligingsgroep kan de app uitvoeren, maar alleen gebruiker B kan deze bewerken. Als u de beveiligingsgroep A de machtiging **Can edit** geeft en gebruiker B de machtiging **Can use**, kan die gebruiker de app alsnog bewerken.
* U kunt een app delen met uw hele organisatie, maar overweeg zorgvuldig of het nodig is dat iedereen toegang heeft tot uw app.
* Houd er rekening mee dat alle wijzigingen die u in een gedeelde app aanbrengt, ook worden doorgevoerd bij degenen met wie u de app hebt gedeeld zodra u de wijzigingen opslaat. Als u de app verbetert, profiteert iedereen daarvan. Als u de app verbreekt, is dit van invloed op iedereen.
* Geef de app voordat u deze deelt een duidelijke naam en beschrijving, zodat iedereen weet wat uw app doet en de app gemakkelijk uit een lijst is te kiezen. Open in PowerApps Studio het menu **Bestand**, tik of klik op **App-instellingen** en voer vervolgens een beschrijving in.

### <a name="app-sharing-and-the-resources-the-app-uses"></a>Het delen van apps en de resources die apps gebruiken
De meeste apps hebben ten minste een van de volgende typen resources nodig:

* Een verbinding met een gegevensbron
* Een on-premises gegevensgateway
* Een aangepaste connector
* Een Excel-werkmap of andere service
* Een stroom

Gebruikers en medewerkers hebben machtigingen nodig voor alle gegevensverbindingen en gateways die een app gebruikt. Sommige machtigingen zijn impliciet aan de app gekoppeld, maar andere moeten expliciet worden verleend. Zie [App-resources delen](share-app-resources.md) voor meer informatie.

Wanneer u een app deelt die gebruikmaakt van een oudere versie van Common Data Service, moet u de runtime-machtiging afzonderlijk delen voor Common Data Service. Als u niet gemachtigd bent om dit te doen, neemt u contact op met de beheerder van uw omgeving. Wanneer u een app deelt die gebruikmaakt van de meest recente versie van Common Data Service, moet u een aangepaste rol maken en gebruikers daaraan toewijzen. [Meer informatie](../../administrator/database-security.md) over de beveiliging van de Common Data Service.

### <a name="what-isnt-supported"></a>Wat wordt niet ondersteund?
* U kunt apps delen met een beveiligingsgroep, maar niet met een distributiegroep.
* U kunt apps delen met gebruikers in uw organisatie, maar niet met gebruikers in een andere tenant.
* U kunt een app opnieuw delen als u voor die app de machtiging **Can edit** (niet **Can use**) hebt.
