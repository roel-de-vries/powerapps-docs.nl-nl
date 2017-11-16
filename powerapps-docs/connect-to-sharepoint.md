---
title: Een verbinding met SharePoint maken vanuit PowerApps | Microsoft Docs
description: Maak op powerapps.com verbinding met SharePoint om een app automatisch te kunnen genereren of om een volledig nieuwe app te bouwen.
services: 
suite: powerapps
documentationcenter: na
author: skjerland
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/03/2016
ms.author: sharik
ms.openlocfilehash: 8af2017bb77c68316c643dd95a18d051fa5942a7
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="create-a-connection-to-sharepoint-from-powerapps"></a>Een verbinding met SharePoint maken vanuit PowerApps
Maak een verbinding naar SharePoint Online of naar on-premises SharePoint zodat u automatisch een app kunt genereren of om een volledig nieuwe app te bouwen.

Zie [Introduction to PowerApps](getting-started.md) (Inleiding tot PowerApps) als u onbekend bent met PowerApps.

Op het moment van schrijven ondersteunt PowerApps aangepaste lijsten, maar geen bibliotheken. Daarnaast kunt u gegevens weergeven in sommige typen kolommen, bijvoorbeeld **Keuze** en **Afbeelding**. U kunt de gegevens echter niet bijwerken. Zie [Known issues](connections/connection-sharepoint-online.md#known-issues) (Bekende problemen) voor meer informatie.

## <a name="specify-a-sharepoint-connection"></a>Een SharePoint-verbinding opgeven
1. [Registreer u voor PowerApps](signup-for-powerapps.md) als u dat nog niet hebt gedaan.
2. Meld u aan bij [powerapps.com](https://web.powerapps.com) met dezelfde referenties die u hebt gebruikt om u te registreren.
3. Klik of tik in de linker navigatiebalk op **Beheren** en vervolgens op **Verbindingen**.
   
    ![Optie Nieuw in het menu Bestand](./media/connect-to-sharepoint/manage-connections.png)
4. Klik of tik in de rechterbovenhoek op **Nieuwe verbinding**.
   
    ![Knop Nieuwe verbinding](./media/connect-to-sharepoint/new-connection.png)
5. Klik of tik in de lijst met verbindingen op **SharePoint**.
   
    ![SharePoint-verbinding toevoegen](./media/connect-to-sharepoint/add-sp-portal.png)
6. Volg de stappen in een van deze procedures, die later in dit onderwerp aan bod komen:
   
   * [Verbinding maken met een SharePoint Online-site](connect-to-sharepoint.md#connect-to-a-sharepoint-online-site).
   * [Verbinding maken met een on-premises SharePoint-site](connect-to-sharepoint.md#connect-to-an-on-premises-sharepoint-site).

## <a name="connect-to-a-sharepoint-online-site"></a>Verbinding maken met een SharePoint Online-site
1. Klik of tik op **Connect directly (cloud services)** en vervolgens op **Verbinding toevoegen**.
   
    ![SharePoint Online kiezen](./media/connect-to-sharepoint/choose-online.png)
2. Ga naar [Volgende stappen](connect-to-sharepoint.md#next-steps) aan het eind van dit onderwerp.

## <a name="connect-to-an-on-premises-sharepoint-site"></a>Verbinding maken met een on-premises SharePoint-site
1. Klik of tik op **Connect using on-premises data gateway**.
   
    ![SharePoint on-premises kiezen](./media/connect-to-sharepoint/choose-onprem.png)
   
    **Opmerking**: gateways en on-premises verbindingen kunnen alleen worden gemaakt en gebruikt in de [standaardomgeving](working-with-environments.md) van de gebruiker.
2. Geef uw gebruikersnaam en wachtwoord op.
   
    Als er bij uw referenties sprake is van een domeinnaam, geef deze dan op als *Domain\Alias*.
   
    ![Uw referenties opgeven](./media/connect-to-sharepoint/specify-credentials.png)
3. Als er geen on-premises gegevensgateway is geïnstalleerd, [installeert u er een](gateway-reference.md) en klik of tik op het pictogram om de lijst met gateways te vernieuwen.
   
    ![Een gateway installeren](./media/connect-to-sharepoint/install-gateway.png)
4. Klik of tik onder **Choose a gateway** op de gateway die u wilt gebruiken en vervolgens op **Verbinding toevoegen**.
   
    ![Een gateway kiezen](./media/connect-to-sharepoint/choose-gateway.png)

## <a name="next-steps"></a>Volgende stappen
* [Genereer automatisch een app](app-from-sharepoint.md) op basis van een door u opgegeven lijst. De app heeft standaard drie schermen: een voor het bladeren in records, een voor het weergeven van details van één record en een voor het maken of bijwerken van een record.
* [Een volledig nieuwe app bouwen](get-started-create-from-blank.md). Dit onderwerp is geschreven voor Excel, maar voor SharePoint gelden dezelfde principes.

