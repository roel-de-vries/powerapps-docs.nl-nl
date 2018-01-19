---
title: Een app delen | Microsoft Docs
description: Deel uw app door anderen toestemming te geven die uit te voeren of te wijzigen
services: 
suite: powerapps
documentationcenter: na
author: linhtranms
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/28/2016
ms.author: litran
ms.openlocfilehash: 1d32873009c337a835a047df38b9ef18d5bf2064
ms.sourcegitcommit: 33099e6197c0139679cd08c42e9e2a5717904c92
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/12/2018
---
# <a name="share-an-app-in-powerapps"></a>Een app delen in PowerApps
Het is fantastisch om apps te ontwikkelen die voldoen aan uw eigen zakelijke behoeften, maar de werkelijke kracht van PowerApps schuilt in het delen van die apps met anderen. In dit onderwerp wordt uitgelegd hoe u apps kunt delen met specifieke gebruikers of beveiligingsgroepen, of zelfs met uw hele organisatie.

## <a name="open-the-share-app-screen"></a>Open het venster App delen
Om een app te delen, moet u powerapps.com openen. We bieden geen ondersteuning meer voor het delen van apps via PowerApps Studio of PowerApps Mobile.

**Vanuit PowerApps Studio**

* Optie 1: klik of tik in het menu **Bestand** op **Delen**.
  
    ![Bestand en Delen](./media/share-app/studio-share.png)
* Optie 2: klik of tik in het menu **Bestand** op **Openen** en klik of tik vervolgens bij een app op het deelpictogram.
  
    ![Beletselteken en Delen](./media/share-app/studio-share-icon.png)

**Vanuit [powerapps.com](http://web.powerapps.com)**

* Klik of tik in de linkernavigatiebalk op **Apps**, klik of tik op het beletselteken (...) en klik of tik vervolgens op **Delen**.
  
   ![Beletselteken op de portal](./media/share-app/portal-share.png)

## <a name="share-an-app"></a>Een app delen
Hier kunt u een app delen aan de hand van de volgende stappen.

1. Geef de naam op van een of meer gebruikers of beveiligingsgroepen in Azure Active Directory, of geef aan dat u de app wilt delen met uw hele organisatie. Houd er rekening mee dat, indien u de app deelt met uw hele organisatie, u alleen met de machtiging **Gebruiker** kunt delen.
   
    ![Gebruikers opgeven in powerapps.com](./media/share-app/portal-users.png)
2. Geef het machtigingsniveau op:
   
   * **Gebruiker**: gebruikers of groepen kunnen de app uitvoeren, maar niet delen.
   * **Inzender**: gebruikers of groepen kunnen de app uitvoeren, aanpassen en de aangepaste versie delen.
     
       ![App delen - portal](./media/share-app/portal-permissions.png)
3. Klik of tik op **Opslaan**.

Als u de machtigingen voor een gebruiker of groep wilt wijzigen, herhaalt u stap 1 van deze procedure en geeft u een andere optie op in de lijst met machtigingen voor die gebruiker of groep. Als u alle machtigingen voor een gebruiker of groep wilt verwijderen, klikt of tikt u op het pictogram **x** voor de gebruiker of groep.

### <a name="send-email-notification"></a>E-mailmelding verzenden
Wanneer u een app deelt, kunt u aangeven of u dit de gebruikers of een beveiligingsgroep via e-mail wilt melden. Als u deze optie kiest, wordt er een e-mailbericht verzonden om de gebruikers of beveiligingsgroepen op de hoogte te brengen. Het e-mailbericht bevat een koppeling die toegang geeft tot de app. Indien van toepassing worden ze gevraagd om zich aan te melden voor PowerApps en dat te installeren.

Houd er rekening mee dat er verschillende e-mailsjablonen worden verzonden, afhankelijk van de machtiging waarmee u de app wilt delen. Wanneer u de app deelt met de machtiging **Gebruiker**, bevat het e-mailbericht een koppeling om de app uit te voeren. Wanneer u de app deelt met de machtiging **Inzender**, bevat het e-mailbericht een koppeling om de app te bewerken in PowerApps Studio of de app uit te voeren.

### <a name="how-do-my-users-see-the-app-i-shared"></a>Hoe kunnen mijn gebruikers de gedeelde app zien?
Nadat u een app deelt met een of meer gebruikers of beveiligingsgroepen, is hoe zij de app kunnen zien afhankelijk van de machtiging waarmee u de app hebt gedeeld.

##### <a name="if-you-shared-app-with-user-permission"></a>Als u een app hebt gedeeld met de machtiging *Gebruiker*
De mensen waarmee u de app hebt gedeeld ontvangen een e-mailmelding als u bij het delen van de app dit selectievakje hebt ingeschakeld. Ze kunnen in deze e-mail klikken of tikken op een koppeling om de app uit te voeren via [Dynamics 365](http://home.dynamics.com). Binnenkort wordt ook ondersteuning voor universele links geïmplementeerd, zodat de app in PowerApps Studio of PowerApps Mobile wordt geopend, indien PowerApps Studio of PowerApps Mobile is geïnstalleerd.

Gebruikers kunnen de app ook vinden via [Dynamics 365](http://home.dynamics.com), in AppSource (als u bijvoorbeeld geen e-mail heeft verzonden). [Meer informatie](app-source.md) over hoe gebruikers apps kunnen verkrijgen via AppSource.

##### <a name="if-you-shared-an-app-with-contributor-permission"></a>Als u een app hebt gedeeld met de machtiging *Inzender*
De mensen waarmee u de app hebt gedeeld ontvangen een e-mailmelding als u bij het delen van de app dit selectievakje hebt ingeschakeld. Ze kunnen in deze e-mail klikken of tikken op een koppeling om de app direct te openen in de webversie van PowerApps Studio, waar ze deze kunnen bewerken. De e-mail bevat ook een koppeling om de app uit te voeren via [Dynamics 365](http://home.dynamics.com). Binnenkort wordt ook ondersteuning voor universele links geïmplementeerd, zodat de app in PowerApps Studio of PowerApps Mobile wordt geopend, indien PowerApps Studio of PowerApps Mobile is geïnstalleerd.

Gebruikers kunnen de app ook vinden op [powerapps.com](http://web.powerapps.com)  (als u bijvoorbeeld geen e-mail heeft verzonden). Dit is de thuisbasis waar app-makers kunnen bladeren door alle apps die ze hebben gemaakt of die anderen met hen hebben gedeeld met de machtiging **Inzender**. [Dynamics 365](http://home.dynamics.com) biedt gebruikers dan weer de mogelijkheid snel apps van PowerApps en andere zakelijke apps uit te voeren.

## <a name="other-things-to-know"></a>Andere dingen die u moet weten
* Als u een app wilt delen, moet u deze op de cloud opslaan, niet lokaal.
* Bedenk voordat u een app deelt met welke gebruikers en beveiligingsgroepen u deze wilt delen en welke rol u ze wilt toekennen: gebruiker of inzender. Wanneer u een app deelt met een groep, hebben alle leden van die groep en iedereen die eraan wordt toegevoegd de machtigingen die u opgeeft. Personen die de groep verlaten verliezen deze machtigingen, tenzij ze lid zijn van een andere groep die toegang heeft, of u expliciete machtigingen voor hen opgeeft.
* Ieder lid van een groep heeft dezelfde machtigingen voor een app als de hele groep. U kunt echter meer machtigingen opgeven voor een of meer leden van die groep om ze meer mogelijkheden te bieden. U kunt bijvoorbeeld een app delen met beveiligingsgroep A met de machtiging Gebruiker. Elk lid van beveiligingsgroep A kan de app nu uitvoeren. Vervolgens deelt u de app met gebruiker B, die lid is van beveiligingsgroep A, met de machtiging Inzender. Gebruiker B kan de app nu bewerken, terwijl alle andere leden van beveiligingsgroep A de app alleen kunnen gebruiken. Als u minder machtigingen opgeeft voor een of meer leden van een groep, hebben zij nog steeds de machtigingen die u hebt opgegeven voor de groep als geheel.
* U kunt een app delen met uw hele organisatie, maar overweeg zorgvuldig of het nodig is dat iedereen toegang heeft tot uw app.
* Houd er rekening mee dat alle wijzigingen die u in een gedeelde app aanbrengt, ook worden doorgevoerd bij degenen met wie u de app hebt gedeeld zodra u de wijzigingen opslaat. Dat kan prima zijn als u de app verbetert, maar kan ook van invloed zijn op anderen als u functies verwijdert of daar aanzienlijke wijzigingen in aanbrengt.
* Geef de app voordat u deze deelt een duidelijke naam en beschrijving, zodat iedereen weet wat uw app doet en de app gemakkelijk uit een lijst is te kiezen. Open in PowerApps Studio het menu **Bestand**, tik of klik op **App-instellingen** en voer vervolgens een beschrijving in.
  
  ![App-beschrijving](./media/share-app/description.png)

### <a name="app-sharing-and-the-resources-the-app-uses"></a>Het delen van apps en de resources die apps gebruiken
De meeste apps hebben ten minste een van de volgende typen resources nodig:

* een verbinding met een gegevensbron
* een on-premises gegevensgateway
* een aangepaste connector
* een Excel-werkmap of andere service
* een stroom

Gebruikers en medewerkers hebben machtigingen nodig voor alle gegevensverbindingen en gateways die een app gebruikt. Sommige machtigingen zijn impliciet aan de app gekoppeld, maar andere moeten expliciet worden verleend. Zie [App-resources delen](share-app-resources.md) voor meer informatie.

Wanneer u een app deelt die gebruikmaakt van de Common Data Service, wordt een melding getoond dat u een aparte runtime-machtiging moet verlenen voor de Common Data Service. Als u niet gemachtigd bent om dit te doen, neemt u contact op met de beheerder van uw omgeving. [Meer informatie](database-security.md) over de beveiliging van de Common Data Service.

![App-resources bij het delen](./media/share-app/app-sharing-resources.png)

### <a name="what-isnt-supported"></a>Wat wordt niet ondersteund?
* U kunt apps delen met een beveiligingsgroep, maar niet met een distributiegroep.
* U kunt apps delen met gebruikers in uw organisatie, maar niet met gebruikers in een andere tenant.
* U kunt een app delen via [powerapps.com](http://web.powerapps.com), maar niet via PowerApps Studio. (Klik of tik in PowerApps Studio op het pictogram voor delen om [powerapps.com](http://web.powerapps.com) te openen.)
* U kunt een app opnieuw delen als u voor die app de machtiging Inzender hebt (niet als Gebruiker).

