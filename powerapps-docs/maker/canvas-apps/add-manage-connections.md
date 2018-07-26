---
title: Verbindingen met gegevensbronnen toevoegen en beheren in cloudservices | Microsoft Docs
description: Verbindingen met gegevensbronnen, zoals SharePoint, SQL Server, OneDrive voor Bedrijven, Salesforce en Office 365 toevoegen, verwijderen en bijwerken
author: lancedMicrosoft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 03/09/2017
ms.author: lanced
ms.openlocfilehash: c114b803539c2d64695a0bd8c9d976d2604569eb
ms.sourcegitcommit: 0e9af8cace2bdc04750f4c5a70a3c4af8e3d2292
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/22/2018
ms.locfileid: "39195215"
---
# <a name="manage-your-connections-in-powerapps"></a>Uw verbindingen beheren in PowerApps
Via [powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) maakt u een verbinding tussen PowerApps en één of meer gegevensbronnen, verwijdert u een verbinding of werkt u de referenties bij.

U kunt met uw app verbinding maken met SharePoint, SQL Server, Office 365, OneDrive voor Bedrijven, Salesforce, Excel en nog vele andere [gegevensbronnen](connections-list.md).

De volgende stap na het lezen van dit artikel is het bekijken en beheren van de gegevensbron in uw app, zoals in deze voorbeelden:

* Verbinding maken met OneDrive voor Bedrijven en gegevens in een Excel-werkmap beheren in uw app.
* Een lijst bijwerken op een SharePoint-site.
* Verbinding maken met SQL Server en een tabel bijwerken vanuit uw app.
* E-mail verzenden in Office 365.
* Een tweet verzenden.
* Verbinding maken met Twilio en een sms-bericht verzenden vanuit uw app.

## <a name="prerequisites"></a>Vereisten
1. [Meld u aan](../signup-for-powerapps.md) voor PowerApps.
2. Meld u aan bij [powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) met dezelfde referenties die u hebt gebruikt om u te registreren.

## <a name="background-on-data-connections"></a>Achtergrondinformatie over gegevensverbindingen
Voor de meeste PowerApps-apps wordt externe informatie gebruikt (ook wel **gegevensbronnen** genoemd) die is opgeslagen in cloudservices. Een veel voorkomend voorbeeld is bijvoorbeeld een tabel in een Excel-bestand die is opgeslagen in OneDrive voor Bedrijven. Apps kunnen toegang tot deze gegevensbronnen verkrijgen via **verbindingen**.

De meest voorkomende gegevensbron is een tabel, die u kunt gebruiken om informatie op te halen en op te slaan. U kunt verbindingen met gegevensbronnen gebruiken om gegevens te lezen en schrijven in Microsoft Excel-werkmappen, SharePoint-lijsten, SQL-tabellen en nog veel meer. U kunt de gegevens vervolgens opslaan in cloudservices zoals OneDrive voor Bedrijven, DropBox, SQL Server, enzovoort.

Er zijn ook andere soorten gegevensbronnen die geen tabellen zijn, zoals e-mails, agenda's, Twitter en (vanaf binnenkort) meldingen.

Met de besturingselementen **[Galerie](controls/control-gallery.md)**, **[Formulier weergeven](controls/control-form-detail.md)** en **[Formulier bewerken](controls/control-form-detail.md)** kunt u eenvoudig een app maken die gegevens leest uit en schrijft naar een gegevensbron. Lees het artikel [Gegevensformulieren begrijpen](working-with-forms.md) om aan de slag te gaan.

Naast het maken en beheren van verbindingen op [powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), kunt u ook verbindingen maken bij het uitvoeren van de volgende taken:

* Genereer automatisch een [app op basis van gegevens](app-from-sharepoint.md), zoals een aangepaste SharePoint-lijst.
* Een bestaande app bijwerken of een volledig nieuwe app maken zoals beschreven in [Een verbinding toevoegen](add-data-connection.md).
* Een app openen die een andere gebruiker heeft gemaakt en [met u gedeeld](share-app.md).

> [!NOTE]
> Als u in plaats daarvan PowerApps Studio wilt gebruiken, opent u het menu **Bestand** en klikt of tikt u op **Verbindingen**. [powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) wordt dan geopend zodat u hier verbindingen kunt maken en beheren.

## <a name="create-a-new-connection"></a>Een nieuwe verbinding maken
1. Als u dit nog niet hebt gedaan, meld u zich aan op [powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).
2. Klik of tik in de linkernavigatiebalk op **Verbindingen**.
   
    ![Verbindingen beheren](./media/add-manage-connections/open-connections.png)
3. Klik of tik in de rechterbovenhoek op **Nieuwe verbinding**.
   
    ![Verbindingen toevoegen](./media/add-manage-connections/add-connection.png)
4. Klik of tik op een connector in de lijst die wordt weergegeven en volg de instructies.
   
   ![Verbindingen toevoegen](./media/add-manage-connections/choose-connection.png)
5. Klik of tik op de knop **Maken**.
   
   ![Verbindingen toevoegen](./media/add-manage-connections/create-connection.png)
6. Volg de aanwijzingen. Voor sommige connectors moet u referenties of een bepaalde set gegevens opgeven, of andere stappen uitvoeren. Bij andere, zoals **Microsoft Translator** hoeft dat niet.
   
   Voor bijvoorbeeld de volgende connectors zijn aanvullende gegevens vereist voordat u ze kunt gebruiken.
   
   * [SharePoint](connections/connection-sharepoint-online.md)
   * [SQL Server](connections/connection-azure-sqldatabase.md)

De nieuwe connector wordt weergegeven onder **Verbindingen** en u kunt [ deze toevoegen aan een app](add-data-connection.md).

## <a name="update-or-delete-a-connection"></a>Een verbinding bijwerken of verwijderen
Zoek in de lijst met verbindingen de verbinding die u wilt bijwerken of verwijderen en klik of tik daarna op het beletselteken (teken met drie punten) naast de verbinding.

![Verbinding bijwerken](./media/add-manage-connections/auth-or-delete.png)

* Als u de referenties van een verbinding wilt bijwerken, klikt of tikt u op het sleutelpictogram geeft u de referenties voor die verbinding op.
* Als u de verbinding wilt verwijderen, klikt of tikt u op het prullenbakpictogram.

