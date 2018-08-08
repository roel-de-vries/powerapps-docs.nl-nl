---
title: Een omgeving maken | Microsoft Docs
description: In deze snelstartgids leert u hoe u een omgeving kunt maken.
author: jimholtz
ms.service: powerapps
ms.component: pa-admin
ms.topic: quickstart
ms.date: 03/21/2018
ms.author: jimholtz
ms.openlocfilehash: eefcd30e4f5e6ec7441147c157cbb46864ebf718
ms.sourcegitcommit: 2e7b621066cdc3e7be329d5213ecfee0b4223641
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2018
ms.locfileid: "39349243"
---
# <a name="create-an-environment"></a>Een omgeving maken
Een omgeving is een ruimte om de bedrijfsgegevens, -apps en -stromen van uw organisatie op te slaan, te beheren en te delen. Een omgeving doet ook dienst als container voor het scheiden van apps met verschillende rollen, beveiligingsvereisten of doelgroepen. PowerApps maakt automatisch één standaardomgeving voor elke tenant, die door alle gebruikers in die tenant wordt gedeeld.

Elke omgeving kan één of geen Common Data Service-database hebben, die opslag voor uw apps biedt. Wanneer gebruikers een app in een omgeving maken, kan die app verbinding maken met een willekeurige gegevensbron, waaronder verbindingen, gateways en stromen. Binnen dezelfde omgeving kan de app echter alleen verbinding maken met de Common Data Service-databases. Hoe u voordeel haalt uit omgevingen, is afhankelijk van uw organisatie en de apps die u probeert te bouwen. Zie voor meer informatie [Overzicht van omgevingen](environments-overview.md).

In dit onderwerp leest u hoe u een omgeving en een database voor die omgeving maakt.

## <a name="prerequisites"></a>Vereisten
 Als u de stappen in dit onderwerp wilt uitvoeren, zijn de volgende items vereist:
 * Een licentie voor PowerApps Plan 2 óf voor Microsoft Flow Plan 2. U kunt zich ook aanmelden voor een [gratis proefversie van een PowerApps-abonnement 2](https://web.powerapps.com/signup?redirect=marketing&email=).
 * Machtigingen voor omgevingsbeheerder van PowerApps, globale beheerder van Office 365 of tenantbeheerder van Azure Active Directory. Zie het Engelstalige artikel [Environments administration in PowerApps](environments-administration.md) (Omgevingen beheren in PowerApps) voor meer informatie.

## <a name="sign-in-to-the-powerapps-admin-center"></a>Aanmelden bij PowerApps-beheercentrum
Meld u aan bij het beheercentrum op [https://admin.powerapps.com](https://admin.powerapps.com).

## <a name="create-an-environment-and-database"></a>Een omgeving en database maken
1. Klik of tik in het navigatiedeelvenster op **Omgevingen** en klik of tik op **Nieuwe omgeving**.

    ![Bestand en Delen](./media/create-environment/new-environment.png)
2. Voer in het dialoogvenster **Nieuwe omgeving** een naam in voor de omgeving en selecteer een regio en omgevingstype in de vervolgkeuzelijsten. De regio wordt standaard ingesteld op de basisregio van de Azure Active Directory-tenant, maar u kunt de gewenste regio in de vervolgkeuzelijst selecteren. Als de omgeving eenmaal is gemaakt, kunt u de regio niet meer wijzigen. Klik of tik op **Omgeving maken** als u klaar bent.

    ![Bestand en Delen](./media/create-environment/new-environment-dialog.png)
3. Zodra de omgeving is gemaakt, verschijnt een bevestigingsbericht in het dialoogvenster en wordt u gevraagd of u een database wilt maken. Klik of tik op **Database maken** om toegang tot Common Data Service in te schakelen.

    **Opmerking:** op dit moment kunt u alleen een database maken in de basisregio van de Azure Active Directory-tenant.

    ![Bestand en Delen](./media/create-environment/create-database-dialog.png)
4. Selecteer de valuta en de taal voor de gegevens die in de database zijn opgeslagen. Als de database eenmaal is gemaakt, kunt u de valuta en de taal niet meer wijzigen. Klik of tik op **Database maken** als u klaar bent.

    ![Bestand en Delen](./media/create-environment/create-database-dialog2.png)

    Het duurt enkele minuten totdat de database is gemaakt in Common Data Service. Zodra de database is gemaakt, wordt de nieuwe omgeving weergegeven in de lijst met omgevingen op de pagina **Omgevingen**.

    ![Bestand en Delen](./media/create-environment/new-environment-created.png)

    Klik of tik op de omgeving om de details van de omgeving weer te geven.

## <a name="next-steps"></a>Volgende stappen
In dit onderwerp hebt u geleerd hoe u een omgeving en een database voor die omgeving maakt. Hierna leert u hoe u de omgevingen in uw organisatie kunt beheren.

> [!div class="nextstepaction"]
> [Omgevingen beheren in PowerApps](environments-administration.md)
