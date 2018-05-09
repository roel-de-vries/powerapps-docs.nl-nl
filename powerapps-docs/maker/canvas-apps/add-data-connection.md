---
title: Een gegevensverbinding toevoegen in een app | Microsoft Docs
description: Een gegevensverbinding toevoegen in een bestaande app of lege app
services: ''
suite: powerapps
documentationcenter: na
author: archnair
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/06/2018
ms.author: archanan
ms.openlocfilehash: e4d2e881a058ea8f265a858f54af81674d8c1296
ms.sourcegitcommit: 4710a56d308efe67fe60a7688143e61f5e5f2b44
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="add-a-data-connection-in-powerapps"></a>Een gegevensverbinding toevoegen in PowerApps
In PowerApps voegt u een gegevensverbinding toe met een bestaande app, of met een app die u volledig nieuw bouwt. Uw app kan verbinding maken met SharePoint, Salesforce, OneDrive of [een van de vele andere gegevensbronnen](connections-list.md).

De [volgende stap](#next-steps) na het lezen van dit artikel is het bekijken en beheren van de gegevensbron in uw app, zoals in deze voorbeelden:

* Verbinding maken met OneDrive en gegevens in een Excel-werkmap beheren in uw app.
* Verbinding maken met Twilio en een sms-bericht verzenden vanuit uw app.
* Verbinding maken met SQL Server en een tabel bijwerken vanuit uw app.

## <a name="prerequisites"></a>Vereisten
[Registreer u](../signup-for-powerapps.md) voor PowerApps en [meld u vervolgens aan](http://web.powerapps.com) met dezelfde referenties die u hebt gebruikt om u te registreren.

## <a name="add-a-data-source"></a>Een gegevensbron toevoegen
1. Beweeg de muisaanwijzer op het tabblad **Start** over de tegel **Beginnen met een lege app** en selecteer vervolgens **Deze app maken**.

    ![Een volledig nieuwe app maken](./media/add-data-connection/blank-app-tile.png)

1. Selecteer **Overslaan** in het dialoogvenster **Welkom bij PowerApps Studio**.

3. Klik of tik in het middelste deelvenster op **verbinding maken met gegevens**.

4. Als de verbinding die u wilt gebruiken in het deelvenster **Gegevens** in de lijst wordt weergegeven, selecteert u de verbinding om deze aan de app toe te voegen. Ga anders naar de volgende stap.

    ![Gegevensbron toevoegen](./media/add-data-connection/choose-existing-connections.png)

5. Selecteer **Nieuwe verbinding** om een lijst met connectors weer te geven.

    ![Verbinding toevoegen](./media/add-data-connection/new-connection.png)

6. Blader door de lijst met connectors tot u het type verbinding dat u wilt maken, hebt gevonden (bijvoorbeeld **Office 365 Outlook**). Selecteer vervolgens de verbinding.

    ![Verbinding kiezen](./media/add-data-connection/choose-connection.png)

7. Selecteer **Maken** om de verbinding te maken en deze toe te voegen aan uw app.

    Voor sommige connectors, zoals **Office 365 Outlook**, zijn geen extra stappen nodig; u kunt de gegevens daarvan direct weergeven. Voor andere connectors moet u referenties of een bepaalde set gegevens opgeven, of andere stappen uitvoeren. Voor bijvoorbeeld [SharePoint](connections/connection-sharepoint-online.md) en [SQL Server](connections/connection-azure-sqldatabase.md) zijn aanvullende gegevens vereist voordat u er gebruik van kunt maken.

## <a name="add-another-data-source"></a>Een gegevensbron toevoegen
1. Voeg een besturingselement toe waaraan u een gegevensbron wilt toevoegen.

    Het besturingselement moet de eigenschap **Items** hebben, zoals galerieën en keuzelijsten, of een eigenschap **Item**, zoals formulieren.

1. Open in het paneel **Gegevens** (dit wordt automatisch geopend) de lijst onder **Gegevensbron** en selecteer vervolgens **Een gegevensbron toevoegen**.

1. Volg de vorige procedure vanaf stap 4.

## <a name="identify-or-change-a-data-source"></a>Een gegevensbron identificeren of wijzigen
Als u een app bijwerkt, moet u mogelijk de gegevensbron identificeren of wijzigen die wordt weergegeven in een galerie, een formulier of een ander besturingselement. U moet bijvoorbeeld een gegevensbron identificeren wanneer u een app bijwerkt die iemand anders heeft gemaakt of een app die u al lang geleden hebt gemaakt.

1. Selecteer het besturingselement waarvoor u de gegevensbron wilt identificeren of wijzigen.

    Selecteer bijvoorbeeld een galerie (niet een besturingselement in de galerie) door er in een hiërarchische lijst van schermen en besturingselementen in de buurt van de linkerrand op te klikken of te tikken.

    De naam van de gegevensbron wordt weergegeven op het tabblad **Eigenschappen** van het rechterdeelvenster.

2. Selecteer de gegevensbron om deze te wijzigen of om meer informatie weer te geven.

    ![Gegevensdeelvenster](./media/add-data-connection/data-pane.png)

3. Als u de gegevensbron wilt wijzigen, opent u de lijst met gegevensbronnen en selecteert u een bron of maakt u een bron.

     ![Gegevensdeelvenster](./media/add-data-connection/datasource-list.png)

## <a name="next-steps"></a>Volgende stappen
* Als u de gegevens in bronnen als Excel, SharePoint Online, SQL Server en Dynamics CRM wilt weergeven en bijwerken, [voegt u een galerie toe](add-gallery.md) en [voegt u een formulier toe](add-form.md).
* Voor de gegevens in andere bronnen kunt u de functies gebruiken die specifiek zijn voor de betreffende connector, zoals die voor [Office 365 Outlook](connections/connection-office365-outlook.md), [Twitter](connections/connection-twitter.md) en [Microsoft Translator](connections/connection-microsoft-translator.md).
