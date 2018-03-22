---
title: Een gegevensverbinding toevoegen in een app | Microsoft Docs
description: Een gegevensverbinding toevoegen in een bestaande app of lege app
services: ''
suite: powerapps
documentationcenter: na
author: archnair
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/02/2017
ms.author: archanan
ms.openlocfilehash: 2134aa28f1b842614e1f4b82acaca2f100126120
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2018
---
# <a name="add-a-data-connection-in-powerapps"></a>Een gegevensverbinding toevoegen in PowerApps
In PowerApps voegt u een gegevensverbinding toe met een bestaande app, of met een app die u volledig nieuw bouwt. In dit onderwerp maakt u gebruik van PowerApps Studio, maar u kunt ook [powerapps.com](https://web.powerapps.com) gebruiken, zoals in het onderwerp [Verbindingen beheren](add-manage-connections.md) wordt beschreven.

De gegevensverbinding van uw app kan bestaan met SharePoint, Salesforce, OneDrive of [een van de vele andere gegevensbronnen](connections-list.md).

De [volgende stap](#next-steps) na het lezen van dit artikel is het bekijken en beheren van de gegevensbron in uw app, zoals in deze voorbeelden:

* Verbinding maken met OneDrive en gegevens in een Excel-werkmap beheren in uw app.
* Verbinding maken met Twilio en een sms-bericht verzenden vanuit uw app.
* Verbinding maken met SQL Server en een tabel bijwerken vanuit uw app.

## <a name="prerequisites"></a>Vereisten
[Registreer u](../signup-for-powerapps.md) voor PowerApps, [installeer](http://aka.ms/powerappsinstall) het, open het en meld u aan met dezelfde referenties die u hebt gebruikt om u te registreren.

## <a name="background-on-data-connections"></a>Achtergrondinformatie over gegevensverbindingen
Voor de meeste PowerApps-apps wordt externe informatie gebruikt (ook wel **gegevensbronnen** genoemd) die is opgeslagen in cloudservices. Een veel voorkomend voorbeeld is bijvoorbeeld een tabel in een Excel-bestand die is opgeslagen in OneDrive voor Bedrijven. Apps kunnen toegang tot deze gegevensbronnen verkrijgen via **connectors**.

De meestvoorkomende gegevensbron is een tabel, die u kunt gebruiken om informatie op te halen en op te slaan. U kunt connectors met gegevensbronnen gebruiken om gegevens te lezen en schrijven in Microsoft Excel-werkmappen, SharePoint-lijsten, SQL-tabellen en nog veel meer. U kunt de gegevens vervolgens opslaan in cloudservices zoals OneDrive voor Bedrijven, DropBox, SQL Server, enzovoort.

Er zijn ook andere soorten gegevensbronnen, zoals e-mail, agenda's, Twitter en meldingen.

Met de besturingselementen **[Galerie](controls/control-gallery.md)**, **[Formulier weergeven](controls/control-form-detail.md)** en **[Formulier bewerken](controls/control-form-detail.md)** kunt u eenvoudig een app maken die gegevens leest uit en schrijft naar een gegevensbron. Lees het artikel [Gegevensformulieren begrijpen](working-with-forms.md) om aan de slag te gaan.

## <a name="add-a-connection"></a>Een verbinding toevoegen
1. Selecteer in het menu **File** (aan de linkerkant van het scherm) de optie **New**.

    ![Optie Nieuw in het menu Bestand](./media/add-data-connection/file-new.png)

2. Klik of tik op de tegel **Lege app** op **Telefoonindeling**.

    ![Een volledig nieuwe app maken](./media/add-data-connection/blank-app.png)

3. Klik of tik in het middelste deelvenster op **verbinding maken met gegevens**.

4. Als de verbinding die u wilt gebruiken in het deelvenster **Gegevens** in de lijst wordt weergegeven, klikt of tikt u erop om deze aan de app toe te voegen. Ga anders naar de volgende stap.

    ![Gegevensbron toevoegen](./media/add-data-connection/choose-existing-connections.png)

5. Klik of tik op **Nieuwe verbinding** om een lijst connectors weer te geven.

    ![Verbinding toevoegen](./media/add-data-connection/new-connection.png)

6. Blader door de lijst connectors tot u het type verbinding dat u wilt maken, hebt gevonden (bijvoorbeeld **Office 365 Outlook**). Klik of tik er daarna op.

    ![Verbinding kiezen](./media/add-data-connection/choose-connection.png)

7. Klik of tik op **Maken** om de verbinding te maken en deze toe te voegen aan uw app.

    Voor sommige connectors, zoals **Microsoft Translator**, zijn geen extra stappen nodig, en u kunt de gegevens daarvan direct weergeven. Voor andere connectors moet u referenties of een bepaalde set gegevens opgeven, of andere stappen uitvoeren. Voor bijvoorbeeld [SharePoint](connections/connection-sharepoint-online.md) en [SQL Server](connections/connection-azure-sqldatabase.md) zijn aanvullende gegevens vereist voordat u er gebruik van kunt maken.

## <a name="view-or-change-a-data-source"></a>Weergeven of wijzigen van een gegevensbron
Als u een app bijwerkt, moet u mogelijk de bron van gegevens die wordt weergegeven in een galerie, een formulier of een ander besturingselement met een eigenschap **Item** identificeren of wijzigen. U werkt bijvoorbeeld aan een app die iemand anders heeft gemaakt of u wilt uzelf herinneren aan een gegevensbron die u een tijdje geleden hebt geconfigureerd.

1. Selecteer het besturingselement waarvoor u de gegevensbron wilt identificeren.

    Selecteer bijvoorbeeld een galerie (niet een besturingselement in de galerie) door er in een hiërarchische lijst van schermen en besturingselementen in de buurt van de linkerrand op te klikken of te tikken.

    De naam van de gegevensbron wordt weergegeven op het tabblad **Eigenschappen** van het rechterdeelvenster.

    ![Gegevensbron op het tabblad Eigenschappen](./media/add-data-connection/properties-tab.png)

2. Om meer informatie over de gegevensbron weer te geven of te wijzigen, klikt of tikt u **Gegevens** in het rechterdeelvenster.

    ![Gegevensdeelvenster](./media/add-data-connection/data-pane.png)

3. Als u de gegevensbron wilt wijzigen, klikt of tikt u op de pijl-omlaag naast de gegevensbron en kiest of maakt u vervolgens een andere bron.

## <a name="next-steps"></a>Volgende stappen
* Als u de gegevens in bronnen als Excel, SharePoint Online, SQL Server en Dynamics CRM wilt weergeven en bijwerken, [voegt u een galerie toe](add-gallery.md) en [voegt u een formulier toe](add-form.md).
* Voor de gegevens in andere bronnen kunt u de functies gebruiken die specifiek zijn voor de betreffende connector, zoals die voor [Office 365 Outlook](connections/connection-office365-outlook.md), [Twitter](connections/connection-twitter.md) en [Microsoft Translator](connections/connection-microsoft-translator.md).
