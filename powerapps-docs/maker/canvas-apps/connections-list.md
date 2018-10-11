---
title: Overzicht van connectors voor canvas-apps | Microsoft Docs
description: Overzicht van alle beschikbare verbindingen die u kunt gebruiken om canvas-apps te bouwen
author: lancedMicrosoft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 08/28/2017
ms.author: lanced
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 20a725ff417ad1a36b83b6a24ca1aaecc667da14
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42834557"
---
# <a name="overview-of-canvas-app-connectors-for-powerapps"></a>Overzicht van canvas-app-connectors voor PowerApps
Gegevens vormen de kern van de meeste apps, inclusief de oplossingen die u zelf in PowerApps bouwt. Gegevens worden opgeslagen in een *gegevensbron* en u brengt die gegevens naar uw app door een *verbinding* te maken. De verbinding maakt gebruikt van een specifieke *connector* om te communiceren met de gegevensbron. PowerApps bevat connectors voor veel populaire services en on-premises gegevensbronnen, waaronder SharePoint, SQL Server, Office 365, Salesforce en Twitter. Als u gegevens wilt toevoegen aan een canvas-app, raadpleegt u [Een gegevensverbinding toevoegen in PowerApps](add-data-connection.md).

Een connector kan **tabellen** bieden van gegevens of **acties**. Sommige connectors bieden alleen tabellen, sommige alleen acties en sommige bieden beide. Uw connector kan ook een standaard of aangepaste connector zijn.

## <a name="tables"></a>Tabellen

Als uw connector tabellen biedt, kunt u uw gegevensbron toevoegen en vervolgens de tabel selecteren in de gegevensbron die u wilt beheren. PowerApps haalt tabelgegevens op in uw app en werkt voor u gegevens bij in uw gegevensbron. U kunt bijvoorbeeld een gegevensbron toevoegen die een tabel bevat met de naam **Lessen** en de eigenschap **Items** van een besturingselement instellen, zoals een galerie of formulier, op deze waarde in de formulebalk:

 ![De gewone gegevensbron met eigenschap Items](./media/connections-list/ItemPropertyPlain.png)

U kunt de gegevens opgeven die door uw app wordt opgehaald door de eigenschap **Items** aan te passen van het besturingselement waarmee uw gegevens worden weergegeven. U kunt, om door te gaan met het vorige voorbeeld, de gegevens in de tabel **Lessen** sorteren en filteren met behulp van deze naam als argument voor de functies **Zoeken** en **SortByColumn**. In deze afbeelding geeft de formule waarmee de eigenschap **Items** is ingesteld aan dat de gegevens worden gesorteerd en gefilterd op basis van de tekst in **TextSearchBox1**. 

 ![De uitgebreide gegevensbron met eigenschap Items](./media/connections-list/ItemPropertyExpanded.png)

Zie voor meer informatie over het aanpassen van de formule met tabellen de volgende onderwerpen:

  [Gegevensbronnen begrijpen in PowerApps](working-with-data-sources.md)<br> 
  [Een app genereren op basis van Excel-gegevens](get-started-create-from-data.md)<br> 
  [Een volledig nieuwe app maken](get-started-create-from-blank.md)<br>
  [Understand tables and records in PowerApps (Over tabellen en records in PowerApps)](working-with-tables.md)

  > [!NOTE]
  > Als u verbinding wilt maken met gegevens in een Excel-werkmap, moet deze worden gehost in een cloudopslagservice, zoals OneDrive. Zie voor meer informatie [Verbinding maken met cloudopslag vanuit PowerApps](connections/cloud-storage-blob-connections.md).

## <a name="actions"></a>Acties

Als uw connector acties biedt, moet u net als voorheen nog steeds uw gegevensbron selecteren. In plaats van een tabel te selecteren als volgende stap, verbindt u echter handmatig een besturingselement met een actie door de eigenschap **Items** te bewerken van het besturingselement dat uw gegevens weergeeft. De formule waarop u de eigenschap **Items** instelt, geeft de actie aan waarmee de gegevens worden opgehaald. De app haalt bijvoorbeeld geen gegevens op als u verbinding maakt met Yammer en vervolgens de eigenschap **Items** instelt op de naam van de gegevensbron. Als u een besturingselement met gegevens invult, geeft u een actie op als **GetMessagesInGroup (5033622).messages**.

![De actie-gegevensbron met eigenschap Items](./media/connections-list/ItemPropertyAction.png)

Als u updates van aangepaste gegevens moet afhandelen voor de actie-connectors, ontwikkelt u een formule waarin de functie **Patch** is opgenomen. Identificeer de actie en de velden die u aan de actie gaat binden in de formule.  

Zie de volgende onderwerpen voor meer informatie over het aanpassen van de formule voor aangepaste updates:

[Patch](functions/function-patch.md)<br>[Verzamelen](functions/function-clear-collect-clearcollect.md)<br>[Bijwerken](functions/function-update-updateif.md)

## <a name="popular-connectors"></a>Populaire connectors

Deze tabel bevat koppelingen naar meer informatie over onze populairste connectors. Raadpleeg [Alle connectors](#all-connectors) voor een volledig overzicht van connectors.

| &nbsp; | &nbsp; | &nbsp; | &nbsp; | &nbsp; |
| --- | --- | --- | --- | --- |
| ![Common Data Service](./media/connections-list/cdm.png) |[**Common Data Service**](../common-data-service/data-platform-intro.md) |&nbsp; |![Office 365 Outlook](./media/connections-list/office365.png) |[**Office 365 Outlook**](connections/connection-office365-outlook.md) |
| ![SharePoint](./media/connections-list/sharepoint.png) |[**SharePoint**](connections/connection-sharepoint-online.md) |&nbsp; |![Excel](./media/connections-list/excel.png) |[**Excel**](connections/connection-excel.md) |
| ![SQL Server](./media/connections-list/sql.png) |[**SQL Server**](connections/connection-azure-sqldatabase.md) |&nbsp; |![OneDrive voor Bedrijven](./media/connections-list/onedrive.png) |[**OneDrive voor Bedrijven**](connections/cloud-storage-blob-connections.md) |
| ![Dynamics 365](./media/connections-list/dynamics-365.png) |[**Dynamics 365**](connections/connection-dynamics-crmonline.md) |&nbsp; |![OneDrive](./media/connections-list/onedrive.png) |[**OneDrive**](connections/cloud-storage-blob-connections.md) |
| ![Office 365-gebruikers](./media/connections-list/office365.png) |[**Office 365-gebruikers**](connections/connection-office365-users.md) |&nbsp; |![Dropbox](./media/connections-list/dropbox.png) |[**Dropbox**](connections/cloud-storage-blob-connections.md) |

## <a name="standard-and-custom-connectors"></a>Standaard en aangepaste connectors
PowerApps biedt *standard* connectors voor veel gangbare gegevensbronnen, zoals die hierboven zijn vermeld. Als PowerApps een standaardconnector bevat voor het type gegevensbron dat u wilt gebruiken, moet u die connector gebruiken. Als u verbinding wilt maken met andere typen gegevensbronnen zoals een service die u hebt gemaakt, raadpleegt u [Register and use custom connectors](../canvas-apps/register-custom-api.md) (Aangepaste connectoren registreren en gebruiken).

## <a name="all-standard-connectors"></a>Alle standaardconnectors
Zie de [referentie voor Microsoft-connectors](https://docs.microsoft.com/connectors/) voor een volledige lijst met standaardconnectors. Premium-connectors vereisen PowerApps-abonnement 1 of 2. Raadpleeg [PowerApps-abonnementen](https://powerapps.microsoft.com/pricing/) voor meer informatie.

U kunt vragen stellen over een specifieke connector op de [PowerApps-forums](https://powerusers.microsoft.com/t5/PowerApps-Community/ct-p/PowerApps1) en u kunt connectors voorstellen om toe te voegen of andere verbeteringen aanbrengen in [PowerApps Ideas](https://powerusers.microsoft.com/t5/PowerApps-Ideas/idb-p/PowerAppsIdeas).
