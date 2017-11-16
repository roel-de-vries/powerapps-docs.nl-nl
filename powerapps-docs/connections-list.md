---
title: Overzicht connectors | Microsoft Docs
description: Overzicht van alle beschikbare verbindingen die u kunt gebruiken om apps te bouwen
services: 
suite: powerapps
documentationcenter: 
author: archnair
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.workload: na
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: article
ms.date: 08/28/2017
ms.author: archanan
ms.openlocfilehash: e78cf64217d65ee90e9e463452ea62d7ee63df88
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="overview-of-connectors-for-powerapps"></a>Overzicht van connectors voor PowerApps
Gegevens vormen de kern van de meeste apps, inclusief de oplossingen die u zelf in PowerApps bouwt. Gegevens worden opgeslagen in een *gegevensbron* en u brengt die gegevens naar uw app door een *verbinding* te maken. De verbinding maakt gebruikt van een specifieke *connector* om te communiceren met de gegevensbron. PowerApps bevat connectors voor veel populaire services en on-premises gegevensbronnen, waaronder SharePoint, SQL Server, Office 365, Salesforce, Twitter en meer. Om te gegevens toe te voegen aan een app, raadpleegt u [Een gegevensverbinding toevoegen in PowerApps](add-data-connection.md).

De volgende tabel bevat koppelingen naar meer informatie over onze populairste connectors. Raadpleeg [Alle connectors](#all-connectors) voor een volledig overzicht van connectors.

| &nbsp; | &nbsp; | &nbsp; | &nbsp; | &nbsp; |
| --- | --- | --- | --- | --- |
| ![Common Data Service](./media/connections-list/cdm.png) |[**Common Data Service**](data-platform-intro.md) |&nbsp; |![Office 365 Outlook](./media/connections-list/office365.png) |[**Office 365 Outlook**](connections/connection-office365-outlook.md) |
| ![SharePoint](./media/connections-list/sharepoint.png) |[**SharePoint**](connections/connection-sharepoint-online.md) |&nbsp; |![Excel](./media/connections-list/excel.png) |[**Excel**](connections/connection-excel.md) |
| ![SQL Server](./media/connections-list/sql.png) |[**SQL Server**](connections/connection-azure-sqldatabase.md) |&nbsp; |![OneDrive voor Bedrijven](./media/connections-list/onedrive.png) |[**OneDrive voor Bedrijven**](connections/cloud-storage-blob-connections.md) |
| ![Dynamics 365](./media/connections-list/dynamics-365.png) |[**Dynamics 365**](connections/connection-dynamics-crmonline.md) |&nbsp; |![OneDrive](./media/connections-list/onedrive.png) |[**OneDrive**](connections/cloud-storage-blob-connections.md) |
| ![Office 365-gebruikers](./media/connections-list/office365.png) |[**Office 365-gebruikers**](connections/connection-office365-users.md) |&nbsp; |![Dropbox](./media/connections-list/dropbox.png) |[**Dropbox**](connections/cloud-storage-blob-connections.md) |

## <a name="types-of-connectors"></a>Types connectors
PowerApps beschikt over twee typen connectors: *standaardconnectors*, zoals hierboven worden genoemd, en *aangepaste connectors*. Als u verbinding maakt met een gegevensbron die door PowerApps wordt ondersteunt door middel van een standaard-connector, gebruikt u die connector. Als u verbinding moet maken met een andere bron, zoals een service die u hebt gemaakt, raadpleegt u [Register and use custom connectors](register-custom-api.md) (Aangepaste connectoren registreren en gebruiken).

Standaard-connectors gedragen zich anders, afhankelijk van het type gegevensbron waarmee ze verbinding maken en hoe gegevens door die gegevensbron worden geretourneerd:

* Sommige connectors werken met gegevensbronnen in tabelvorm, zoals SharePoint, SQL Server en Excel. Als u werkt met deze gegevensbronnen, worden resultaatgegevens naar PowerApps geretourneerd als een tabel. PowerApps maakt gebruikt van een eigen functies, zoals [Patch()](functions/function-patch.md), [Collect()](functions/function-clear-collect-clearcollect.md), [Update()](functions/function-update-updateif.md), enzovoort om te communiceren met deze gegevens. Gegevens in tabelvorm zijn ook eenvoudig te gebruiken in formulieren en galerieën, waarbij een veld in een tabel wordt weergegeven als een veld in een galerie of formulier. Raadpleeg voor meer informatie de volgende artikelen:
  
    [Gegevensbronnen begrijpen in PowerApps](working-with-data-sources.md)
  
    [Een app genereren op basis van Excel-gegevens](get-started-create-from-data.md)
  
    [Een volledig nieuwe app maken](get-started-create-from-blank.md)
  
    **Opmerking:** om verbinding te maken met gegevens in Excel, moet de werkmap worden gehost in een cloudopslagservice, zoals OneDrive. Zie voor meer informatie [Verbinding maken met cloudopslag vanuit PowerApps](connections/cloud-storage-blob-connections.md).
* Andere connectors werken met gegevensbronnen op basis van functie, zoals Twitter, Facebook en Office 365 Outlook. Als u met deze gegevensbronnen werkt, worden gegevens naar PowerApps geretourneerd door specifieke functies in de onderliggende service aan te roepen. Met de Twitter-connector kunt u bijvoorbeeld `Twitter.MyFollowers()` aanroepen om een lijst met uw volgers te retourneren. U kunt deze gegevens ook in een formulier of galerie gebruiken, maar dat vereist meer werk dan het bij tabelgegevens kost. Zie voor meer informatie [Verbinding maken met Twitter vanuit PowerApps](connections/connection-twitter.md).

## <a name="all-connectors"></a>Alle connectors
De volgende tabel bevat alle onze connectors. Raadpleeg de [naslaggids van Microsoft voor connectors](https://docs.microsoft.com/connectors/) voor meer informatie over elke connector. Premium-connectors vereisen PowerApps-abonnement 1 of 2. Raadpleeg [PowerApps-abonnementen](https://powerapps.microsoft.com/pricing/) voor meer informatie.

| &nbsp; | &nbsp; |
| --- | --- |
| 10to8 Appointment Scheduling<br>Act!<br>Adobe Creative Cloud ![Premium-connector](./media/connections-list/premium.png)<br>Adobe Sign<br>Amazon Redshift ![Premium-connector](./media/connections-list/premium.png)<br>Apache Impala ![Premium-connector](./media/connections-list/premium.png)<br>AppFigures<br>Goedkeuringen<br>Asana<br>AWeber ![Premium-connector](./media/connections-list/premium.png)<br>Microsoft Azure Active Directory<br>Azure Application Insights<br>Azure Automation<br>Azure Blob Storage<br>Azure Cosmos DB<br>Azure Data Lake<br>Azure Event Grid<br>Azure Event Grid Publish<br>Azure File Storage<br>Azure Log Analytics<br>Azure Log Analytics Data Collector<br>Azure-wachtrijen<br>Azure Resource Manager<br>Azure Table Storage<br>Basecamp 2<br>Basecamp 3<br>Benchmark Email ![Premium-connector](./media/connections-list/premium.png)<br>Bing Kaarten<br>Bing Zoeken<br>Bitbucket ![Premium-connector](./media/connections-list/premium.png)<br>Bitly<br>Bizzy (H3 Solutions, Inc.)<br>Blogger<br>Box<br>bttn<br>Buffer<br>Calendly ![Premium-connector](./media/connections-list/premium.png)<br>Campfire<br>Capsule CRM ![Premium-connector](./media/connections-list/premium.png)<br>Chatter ![Premium-connector](./media/connections-list/premium.png)<br>Cognito Forms<br>Common Data Service ![Premium-connector](./media/connections-list/premium.png)<br>Computer Vision-API<br>Inhoudsconversie<br>Content Moderator<br>DB2 ![Premium-connector](./media/connections-list/premium.png)<br>Disqus<br>DocFusion365 – SP ![Premium-connector](./media/connections-list/premium.png)<br>DocuSign ![Premium-connector](./media/connections-list/premium.png)<br>Dropbox<br>Dynamics 365<br>Dynamics 365 for Financials<br>Dynamics voor bewerkingen<br>Dynamics NAV<br>Easy Redmine ![Premium-connector](./media/connections-list/premium.png)<br>Elastic Forms<br>Event Hubs<br>Eventbrite ![Premium-connector](./media/connections-list/premium.png)<br>Excel<br>Face API<br>Facebook<br>Bestandssysteem<br>Flic<br>FlowForma ![Premium-connector](./media/connections-list/premium.png)<br>FreshBooks ![Premium-connector](./media/connections-list/premium.png)<br>Freshdesk<br>Freshservice ![Premium-connector](./media/connections-list/premium.png)<br>FTP<br>GitHub<br>Gmail<br>Google Agenda<br>Google Contactpersonen<br>Google Drive<br>Google Spreadsheets<br>Google Taken<br>GoToMeeting ![Premium-connector](./media/connections-list/premium.png)<br>GoToTraining ![Premium-connector](./media/connections-list/premium.png)<br>GoToWebinar ![Premium-connector](./media/connections-list/premium.png)<br>Harvest ![Premium-connector](./media/connections-list/premium.png)<br>HelloSign ![Premium-connector](./media/connections-list/premium.png)<br>HipChat<br>HTTP met Microsoft Azure Active Directory ![Premium-connector](./media/connections-list/premium.png)<br>Informix ![Premium-connector](./media/connections-list/premium.png)<br>Infusionsoft ![Premium-connector](./media/connections-list/premium.png) |Inoreader<br>Insightly<br>Instagram<br>Instapaper<br>Intercom<br>JIRA ![Premium-connector](./media/connections-list/premium.png)<br>JotForm ![Premium-connector](./media/connections-list/premium.png)<br>LeanKit ![Premium-connector](./media/connections-list/premium.png)<br>LinkedIn<br>LiveChat ![Premium-connector](./media/connections-list/premium.png)<br>LUIS<br>Mail<br>MailChimp ![Premium-connector](./media/connections-list/premium.png)<br>Mandrill ![Premium-connector](./media/connections-list/premium.png)<br>Middelgroot<br>Microsoft Forms<br>Microsoft StaffHub<br>Microsoft Teams<br>Microsoft Translator<br>MSN Weer<br>Muhimbi PDF<br>MySQL ![Premium-connector](./media/connections-list/premium.png)<br>Nexmo ![Premium-connector](./media/connections-list/premium.png)<br>Meldingen<br>Office 365-reserveringen<br>Office 365-groepen<br>Office 365 Outlook<br>Office 365-gebruikers<br>Office 365 Video<br>OneDrive<br>OneDrive voor Bedrijven<br>OneNote (Business)<br>Oracle Database ![Premium-connector](./media/connections-list/premium.png)<br>Outlook Customer Manager<br>Outlook-taken<br>Outlook.com<br>PagerDuty<br>Parserr<br>Paylocity ![Premium-connector](./media/connections-list/premium.png)<br>Pinterest<br>Pipedrive ![Premium-connector](./media/connections-list/premium.png)<br>Pitney Bowes Data Validation ![Premium-connector](./media/connections-list/premium.png)<br>Pivotal Tracker<br>Planner<br>Plivo ![Premium-connector](./media/connections-list/premium.png)<br>PostgreSQL ![Premium-connector](./media/connections-list/premium.png)<br>Power BI<br>PowerApps-melding ![Premium-connector](./media/connections-list/premium.png)<br>Project Online<br>Redmine<br>RSS<br>Salesforce ![Premium-connector](./media/connections-list/premium.png)<br>SendGrid<br>Service Bus<br>SFTP<br>SharePoint<br>Skype voor Bedrijven<br>Slack<br>SmartSheet<br>SMTP<br>SparkPost<br>SQL Server<br>Stripe ![Premium-connector](./media/connections-list/premium.png)<br>SurveyMonkey ![Premium-connector](./media/connections-list/premium.png)<br>Teamwork Projects ![Premium-connector](./media/connections-list/premium.png)<br>Teradata ![Premium-connector](./media/connections-list/premium.png)<br>Tekstanalyse<br>Todoist<br>Toodledo<br>Trello<br>Twilio<br>Twitter<br>TypeForm<br>UserVoice ![Premium-connector](./media/connections-list/premium.png)<br>Video Indexer<br>Vimeo<br>Visual Studio Team Services<br>WebMerge<br>WordPress<br>Wunderlist<br>Yammer<br>YouTube<br>Zendesk ![Premium-connector](./media/connections-list/premium.png) |

Als u vragen over een specifieke connector hebt, gebruikt u de [PowerApps Forums](https://powerusers.microsoft.com/t5/PowerApps-Community/ct-p/PowerApps1). Als u een idee voor een nieuwe connector of suggesties voor verbeteringen hebt, gebruikt u [PowerApps Ideas](https://powerusers.microsoft.com/t5/PowerApps-Ideas/idb-p/PowerAppsIdeas).

