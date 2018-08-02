---
title: Overzicht connectors | Microsoft Docs
description: Overzicht van alle beschikbare verbindingen die u kunt gebruiken om apps te bouwen
author: lancedMicrosoft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 08/28/2017
ms.author: lanced
ms.openlocfilehash: 15da6ed2ce6b44c17645ac11d1b049b95e157703
ms.sourcegitcommit: 47be38a23c96ba7478fd777065f5db41181af40b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/20/2018
ms.locfileid: "39164743"
---
# <a name="overview-of-connectors-for-powerapps"></a>Overzicht van connectors voor PowerApps
Gegevens vormen de kern van de meeste apps, inclusief de oplossingen die u zelf in PowerApps bouwt. Gegevens worden opgeslagen in een *gegevensbron* en u brengt die gegevens naar uw app door een *verbinding* te maken. De verbinding maakt gebruikt van een specifieke *connector* om te communiceren met de gegevensbron. PowerApps bevat connectors voor veel populaire services en on-premises gegevensbronnen, waaronder SharePoint, SQL Server, Office 365, Salesforce, Twitter en meer. Om te gegevens toe te voegen aan een app, raadpleegt u [Een gegevensverbinding toevoegen in PowerApps](add-data-connection.md).

De volgende tabel bevat koppelingen naar meer informatie over onze populairste connectors. Raadpleeg [Alle connectors](#all-connectors) voor een volledig overzicht van connectors.

| &nbsp; | &nbsp; | &nbsp; | &nbsp; | &nbsp; |
| --- | --- | --- | --- | --- |
| ![Common Data Service](./media/connections-list/cdm.png) |[**Common Data Service**](../common-data-service/data-platform-intro.md) |&nbsp; |![Office 365 Outlook](./media/connections-list/office365.png) |[**Office 365 Outlook**](connections/connection-office365-outlook.md) |
| ![SharePoint](./media/connections-list/sharepoint.png) |[**SharePoint**](connections/connection-sharepoint-online.md) |&nbsp; |![Excel](./media/connections-list/excel.png) |[**Excel**](connections/connection-excel.md) |
| ![SQL Server](./media/connections-list/sql.png) |[**SQL Server**](connections/connection-azure-sqldatabase.md) |&nbsp; |![OneDrive voor Bedrijven](./media/connections-list/onedrive.png) |[**OneDrive voor Bedrijven**](connections/cloud-storage-blob-connections.md) |
| ![Dynamics 365](./media/connections-list/dynamics-365.png) |[**Dynamics 365**](connections/connection-dynamics-crmonline.md) |&nbsp; |![OneDrive](./media/connections-list/onedrive.png) |[**OneDrive**](connections/cloud-storage-blob-connections.md) |
| ![Office 365-gebruikers](./media/connections-list/office365.png) |[**Office 365-gebruikers**](connections/connection-office365-users.md) |&nbsp; |![Dropbox](./media/connections-list/dropbox.png) |[**Dropbox**](connections/cloud-storage-blob-connections.md) |

## <a name="types-of-connectors"></a>Types connectors
PowerApps beschikt over twee typen connectors: *standaardconnectors*, zoals hierboven worden genoemd, en *aangepaste connectors*. Als u verbinding maakt met een gegevensbron die door PowerApps wordt ondersteunt door middel van een standaard-connector, gebruikt u die connector. Als u verbinding moet maken met een andere bron, zoals een service die u hebt gemaakt, raadpleegt u [Register and use custom connectors](../canvas-apps/register-custom-api.md) (Aangepaste connectoren registreren en gebruiken).

Standaard-connectors gedragen zich anders, afhankelijk van het type gegevensbron waarmee ze verbinding maken en hoe gegevens door die gegevensbron worden geretourneerd:

* Sommige connectors werken met gegevensbronnen in tabelvorm, zoals SharePoint, SQL Server en Excel. Als u werkt met deze gegevensbronnen, worden resultaatgegevens naar PowerApps geretourneerd als een tabel. PowerApps maakt gebruikt van een eigen functies, zoals [Patch()](functions/function-patch.md), [Collect()](functions/function-clear-collect-clearcollect.md), [Update()](functions/function-update-updateif.md), enzovoort om te communiceren met deze gegevens. Gegevens in tabelvorm zijn ook eenvoudig te gebruiken in formulieren en galerieën, waarbij een veld in een tabel wordt weergegeven als een veld in een galerie of formulier. Raadpleeg voor meer informatie de volgende artikelen:

    [Gegevensbronnen begrijpen in PowerApps](working-with-data-sources.md)

    [Een app genereren op basis van Excel-gegevens](get-started-create-from-data.md)

    [Een volledig nieuwe app maken](get-started-create-from-blank.md)

    > [!NOTE]
  > Als u verbinding wilt maken met gegevens in Excel, moet de werkmap worden gehost in een cloudopslagservice, zoals OneDrive. Zie voor meer informatie [Verbinding maken met cloudopslag vanuit PowerApps](connections/cloud-storage-blob-connections.md).

* Andere connectors werken met gegevensbronnen op basis van functie, zoals Twitter, Facebook en Office 365 Outlook. Als u met deze gegevensbronnen werkt, worden gegevens naar PowerApps geretourneerd door specifieke functies in de onderliggende service aan te roepen. Met de Twitter-connector kunt u bijvoorbeeld `Twitter.MyFollowers()` aanroepen om een lijst met uw volgers te retourneren. U kunt deze gegevens ook in een formulier of galerie gebruiken, maar dat vereist meer werk dan het bij tabelgegevens kost. Zie voor meer informatie [Verbinding maken met Twitter vanuit PowerApps](connections/connection-twitter.md).

## <a name="all-connectors"></a>Alle connectors
Zie de [referentie voor Microsoft-connectors](https://docs.microsoft.com/connectors/) voor een volledige lijst met connectors. Premium-connectors vereisen PowerApps-abonnement 1 of 2. Raadpleeg [PowerApps-abonnementen](https://powerapps.microsoft.com/pricing/) voor meer informatie.


Als u vragen over een specifieke connector hebt, gebruikt u de [PowerApps Forums](https://powerusers.microsoft.com/t5/PowerApps-Community/ct-p/PowerApps1). Als u een idee voor een nieuwe connector of suggesties voor verbeteringen hebt, gebruikt u [PowerApps Ideas](https://powerusers.microsoft.com/t5/PowerApps-Ideas/idb-p/PowerAppsIdeas).
