---
title: Een on-premises gegevensgateway beheren | Microsoft Docs
description: Een on-premises gegevensgateway en de bijbehorende verbindingen beheren
services: 
suite: powerapps
documentationcenter: na
author: archnair
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/30/2016
ms.author: archanan
ms.openlocfilehash: ede3111f322aaff0e29679db2d730684ec18fd44
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="manage-an-on-premises-data-gateway-in-powerapps"></a>Een on-premises gegevensgateway beheren in PowerApps
Installeer een on-premises gegevensgateway om gegevens snel en veilig over te dragen tussen PowerApps en een gegevensbron die zich niet in de cloud bevindt, zoals een on-premises SQL Server-database of een on-premises SharePoint-site. Bekijk alle gateways waarvoor u beheerdersmachtigingen hebt en beheer machtigingen en verbindingen voor deze gateways.

Met een gateway kunt u verbinding maken met on-premises gegevens via deze verbindingen:

* SharePoint
* SQL Server
* Oracle
* Informix
* Bestandssysteem
* DB2

## <a name="prerequisites"></a>Vereisten
* De gebruikersnaam die en het wachtwoord dat u hebt gebruikt om u [aan te melden](signup-for-powerapps.md) voor PowerApps.
* Beheerdersmachtigingen op een gateway. (Deze machtigingen hebt u standaard voor elke gateway die u installeert en een beheerder van een andere gateway kan u deze machtigingen voor die gateway verlenen.)
* Een licentie die ondersteuning biedt voor toegang tot on-premises gegevens via een on-premises gateway. Zie de sectie 'Connectiviteit' van de [pagina met prijzen](https://powerapps.microsoft.com/pricing/) voor meer informatie.
* Gateways en on-premises verbindingen kunnen alleen worden gemaakt en gebruikt in de [standaardomgeving](working-with-environments.md) van de gebruiker.

## <a name="install-a-gateway"></a>Een gateway installeren
1. Klik of tik in de linkernavigatiebalk op [powerapps.com](https://web.powerapps.com) op **Gateways**.
   
    ![Gateways in linkernavigatiebalk](./media/gateway-management/manage-gateway.png)
2. Als u geen beheerdersmachtigingen voor een gateway hebt, klikt of tikt u op [Install a gateway now](http://go.microsoft.com/fwlink/?LinkID=820931) (of op **New Gateway** in de rechterbovenhoek) en volgt u de aanwijzingen in de wizard die wordt weergegeven.
   
    ![Gateways installeren](./media/gateway-management/no-gateway-installed.png)
   
    Zie [Wat zijn on-premises gegevensgateways?](gateway-reference.md) voor meer informatie over het installeren van een gateway.

## <a name="view-and-manage-gateway-permissions"></a>Gatewaymachtigingen weergeven en beheren
1. Klik of tik in de linkernavigatiebalk van [powerapps.com](https://web.powerapps.com) op **Gateways** en klik of tik vervolgens op een gateway.
2. Voeg een gebruiker toe aan een gateway door te klikken of tikken op **Users**, een gebruiker of groep op te geven en vervolgens een machtigingsniveau op te geven:
   
   * **Mag gebruiken**: gebruikers die verbindingen kunnen maken op de gateway om apps en stromen te gebruiken, maar die de gateway niet kunnen delen. Gebruik deze machtiging voor gebruikers die apps moeten uitvoeren, maar niet hoeven delen.
   * **Mag gebruiken + delen**: gebruikers die verbindingen kunnen maken op de gateway om apps en stromen te gebruiken en die de gateway automatisch kunnen delen wanneer ze een app delen. Gebruik deze machtiging voor gebruikers die apps moeten delen met andere gebruikers of met de organisatie.
   * **Beheerder**: beheerders die volledige controle over de gateway hebben, inclusief het toevoegen van gebruikers, het instellen van machtigingen, het maken van verbindingen met alle beschikbare gegevensbronnen en het verwijderen van de gateway.

Voor het machtigingsniveau **Mag gebruiken** en **Mag gebruiken + delen**, selecteert u de gegevensbronnen waarmee de gebruiker via de gateway verbinding kan maken.

## <a name="view-and-manage-gateway-connections"></a>Gatewayverbindingen weergeven en beheren
1. Klik of tik in de linkernavigatiebalk van [powerapps.com](https://web.powerapps.com) op **Gateways** en klik of tik vervolgens op een gateway.
2. Klik of tik op **Verbindingen** en klik of tik op een verbinding om de details ervan weer te geven, de instellingen ervan te wijzigen of de verbinding te verwijderen.
3. Als u een verbinding wilt delen, klikt of tikt u op **Share**, waarna u gebruikers kunt toevoegen of verwijderen.
   
    **Opmerking**: u kunt alleen bepaalde typen verbindingen, zoals SQL Server, delen. Zie [App-resources delen](share-app-resources.md) voor meer informatie.

Zie [Uw verbindingen beheren](add-manage-connections.md) voor meer informatie over het beheren van een verbinding.

## <a name="troubleshooting-and-advanced-configuration"></a>Probleemoplossing en geavanceerde configuratie
Zie [Wat zijn on-premises gegevensgateways?](gateway-reference.md) voor meer informatie over het oplossen van problemen met gateways of het configureren van de gatewayservice voor uw netwerk.

## <a name="next-steps"></a>Volgende stappen
* Maak een app die verbinding maakt met een lokale gegevensbron, zoals [SQL Server](connections/connection-azure-sqldatabase.md) of [SharePoint](connections/connection-sharepoint-online.md).
* [Deel een app](share-app.md) die verbinding maakt met een lokale gegevensbron.

