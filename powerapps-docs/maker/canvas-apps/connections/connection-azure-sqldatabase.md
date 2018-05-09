---
title: Overzicht van de SQL Server-verbinding | Microsoft Docs
description: Stapsgewijze instructies om verbinding te maken met Azure SQL of een on-premises SQL Server-database
documentationcenter: ''
author: lancedMicrosoft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 07/12/2016
ms.author: lanced
ms.openlocfilehash: 65fa5cff5d3b9c9595cc3f9338a7e7af43256f86
ms.sourcegitcommit: 45fac73f04aa03b5796ae6833d777f4757e67945
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/03/2018
---
# <a name="connect-to-sql-server-from-powerapps"></a>Verbinding maken met SQL Server vanuit PowerApps
![SQL Server-pictogram](./media/connection-azure-sqldatabase/sqlicon.png)

Maak in Azure of een on-premises database verbinding met SQL Server, zodat u gegevens daaruit kunt weergeven in PowerApps.

## <a name="prerequisites"></a>Vereisten

* [Registreer u](../../signup-for-powerapps.md) voor PowerApps en [meld u vervolgens aan](http://web.powerapps.com) door dezelfde referenties in te voeren die u hebt gebruikt om u te registreren.
* Verzamel de volgende informatie voor een database die ten minste één tabel met een primaire sleutel bevat:
  
  * de naam van de database
  * de naam van de server waarop de database wordt gehost
  * een geldige gebruikersnaam en geldig wachtwoord om verbinding te maken met de database
  * het type verificatie dat nodig is om verbinding te maken met de database
    
    Als u deze informatie niet hebt, vraag er dan naar bij de beheerder van de database die u wilt gebruiken.
* Voor een on-premises database identificeert u een [gegevensgateway](../gateway-management.md) die met u is gedeeld (of maakt u er een).
  
    > [!NOTE]
> Gateways en on-premises verbindingen kunnen alleen worden gemaakt en gebruikt in de [standaardomgeving](../working-with-environments.md) van de gebruiker.

## <a name="generate-an-app-automatically"></a>Automatisch een app genereren
1. Klik of tik in PowerApps Studio op **New** in het menu **File** (aan de linkerkant).
   
    ![Optie Nieuw in het menu Bestand](./media/connection-azure-sqldatabase/file-new.png)
2. Klik of tik onder **Start with your data** op de pijl-rechts aan het einde van de rij met connectors.
3. Als u al een verbinding hebt met de database die u wilt gebruiken, klikt of tikt u erop en gaat u naar stap 7 in deze procedure.
4. Klik of tik op **New connection** en klik of tik vervolgens op **SQL Server**.
   
    ![SQL Server-verbinding toevoegen](./media/connection-azure-sqldatabase/add-sql-connection.png)
5. Voer een van de volgende stappen uit:
   
   * Geef **Connect directly (cloud services)** op en typ of plak de servernaam, de databasenaam, de gebruikersnaam en het wachtwoord voor de database die u wilt gebruiken.
     
       ![Verbinding maken met een database in Azure](./media/connection-azure-sqldatabase/connect-azure.png)
   * Geef **Connect using on-premises data gateway** op, typ of plak de servernaam, de databasenaam, de gebruikersnaam en het wachtwoord voor de database die u wilt gebruiken en geef het verificatietype en de gateway op.
     
       ![Verbinding maken met een on-premises database](./media/connection-azure-sqldatabase/connect-onprem.png)
     
       > [!NOTE]
> Als u geen gateway hebt, [installeert u er een](../gateway-reference.md) en klikt of tikt u op **Gatewaylijst vernieuwen**.
6. Klik of tik op **Verbinden**.
7. Klik of tik op een optie onder **Choose a dataset**, klik op of tik op een optie onder **Choose a table** en klik of tik op **Connect**.
   
    PowerApps maakt een app die gegevens op drie schermen weergeeft. U krijgt een voorstel over het soort gegevens dat wordt weergegeven, maar wellicht moet u de gebruikersinterface aan uw behoeften aanpassen.
8. Pas de app aan met behulp van technieken die vergelijkbaar zijn met de technieken die worden beschreven in [Een app maken vanuit Excel](../get-started-create-from-data.md), te beginnen met het wijzigen van de app-indeling.

## <a name="build-an-app-from-scratch"></a>Een volledig nieuwe app bouwen
1. Meld u aan bij [powerapps.com](https://web.powerapps.com) met hetzelfde account dat u hebt gebruikt om u te registreren voor PowerApps.
2. Klik of tik in de linkernavigatiebalk op **Connections**:  
   
    ![Verbindingen beheren](./media/connection-azure-sqldatabase/manage-connections.png)
3. Klik of tik in de rechterbovenhoek op **New connection** en klik of tik vervolgens op **SQL Server**.
4. Voer een van de volgende stappen uit:
   
   * Geef **Connect directly (cloud services)** op en typ of plak de servernaam, de databasenaam, de gebruikersnaam en het wachtwoord voor de database die u wilt gebruiken.
     
       ![Verbinding maken met een database in Azure](./media/connection-azure-sqldatabase/connect-azure-portal.png)
   * Geef **Connect using on-premises data gateway** op, typ of plak de servernaam, de databasenaam, de gebruikersnaam en het wachtwoord voor de database die u wilt gebruiken en geef het verificatietype en de gateway op.
     
       ![Verbinding maken met een database in Azure](./media/connection-azure-sqldatabase/connect-onprem-portal.png)
     
       > [!NOTE]
> Als u geen gateway hebt, [installeert u er een](../gateway-reference.md) en klikt of tikt u op het pictogram met de pijl die met de klok mee beweegt om de lijst te vernieuwen.
5. Klik of tik op **Maken** om de verbinding te maken.
6. Maak een app met behulp van de technieken die vergelijkbaar zijn met de technieken die worden beschreven in [Een volledig nieuwe app maken](../get-started-create-from-blank.md).

## <a name="update-an-existing-app"></a>Een bestaande app bijwerken
1. Open in PowerApps Studio de app die u wilt bijwerken.
2. Klik of tik op het lint, in het tabblad **Weergeven**, op **Gegevensbronnen**.
3. Klik of tik in het rechterdeelvenster op **Gegevensbron toevoegen**.
   
    ![Gegevensbron toevoegen](./media/connection-azure-sqldatabase/add-data-source.png)
4. Klik of tik op **New connection**, klik of tik op **SharePoint** en klik of tik op **Connect**.
5. Voer een van de volgende stappen uit:
   
   * Geef **Connect directly (cloud services)** op en typ of plak de servernaam, de databasenaam, de gebruikersnaam en het wachtwoord voor de database die u wilt gebruiken.
     
       ![Verbinding maken met een database in Azure](./media/connection-azure-sqldatabase/connect-azure-fromblank.png)
   * Geef **Connect using on-premises data gateway** op, typ of plak de servernaam, de databasenaam, de gebruikersnaam en het wachtwoord voor de database die u wilt gebruiken en geef het verificatietype en de gateway op.
     
       ![Verbinding maken met een database in Azure](./media/connection-azure-sqldatabase/connect-onprem-fromblank.png)
     
       > [!NOTE]
> Als u geen gateway hebt, [installeert u er een](../gateway-reference.md) en klikt of tikt u op het pictogram met de pijl die met de klok mee beweegt om de lijst te vernieuwen.
6. Klik of tik op **Verbinden**.
7. Onder **Choose a dataset** klikt of tikt u op een optie.
8. Schakel onder **Choose a table** een of meer selectievakjes in en klik of tik op **Connect**.

## <a name="next-steps"></a>Volgende stappen
* Lees hoe u [gegevens uit een gegevensbron weergeeft](../add-gallery.md).
* Lees hoe u [gegevens weergeeft en records maakt of bijwerkt](../add-form.md).
* Bekijk andere typen [gegevensbronnen](../connections-list.md) waarmee u verbinding kunt maken.  
* [Tabellen en records begrijpen](../working-with-tables.md) met gegevensbronnen in tabelvorm.

<!--NotAvailableYet
## View the available functions ##
This connection includes the following functions:

| Function Name |  Description |
| --- | --- |
|[GetItems](connection-azure-sqldatabase.md#getitems) | Retrieves rows from a SQL table |
|[PostItem](connection-azure-sqldatabase.md#postitem) | Inserts a new row into a SQL table |
|[GetItem](connection-azure-sqldatabase.md#getitem) | Retrieves a single row from a SQL table |
|[DeleteItem](connection-azure-sqldatabase.md#deleteitem) | Deletes a row from a SQL table |
|[PatchItem](connection-azure-sqldatabase.md#patchitem) | Updates an existing row in a SQL table |
|[GetTables](connection-azure-sqldatabase.md#gettables) | Retrieves tables from a SQL database |

### GetItems
Get rows: Retrieves rows from a SQL table

#### Input properties

| Name| Data Type|Required|Description|
| ---|---|---|---|
|table|string|yes|Name of SQL table|
|$skip|integer|no|Number of entries to skip (default = 0)|
|$top|integer|no|Maximum number of entries to retrieve (default = 256)|
|$filter|string|no|An ODATA filter query to restrict the number of entries|
|$orderby|string|no|An ODATA orderBy query for specifying the order of entries|

### PostItem
Insert row: Inserts a new row into a SQL table

#### Input properties

| Name| Data Type|Required|Description|
| ---|---|---|---|
|table|string|yes|Name of SQL table|
|item| |yes|Row to insert into the specified table in SQL|

#### Output properties

| Property Name | Data Type | Required | Description |
|---|---|---|---|
|value|array|No | |


### GetItem
Get row: Retrieves a single row from a SQL table

#### Input properties

| Name| Data Type|Required|Description|
| ---|---|---|---|
|table|string|yes|Name of SQL table|
|id|string|yes|Unique identifier of the row to retrieve|

#### Output properties

| Property Name | Data Type | Required | Description |
|---|---|---|---|
|ItemInternalId|string|No | |


### DeleteItem
Delete row: Deletes a row from a SQL table

#### Input properties

| Name| Data Type|Required|Description|
| ---|---|---|---|
|table|string|yes|Name of SQL table|
|id|string|yes|Unique identifier of the row to delete|

#### Output properties
None.

### PatchItem
Update row: Updates an existing row in a SQL table

#### Input properties

| Name| Data Type|Required|Description|
| ---|---|---|---|
|table|string|yes|Name of SQL table|
|id|string|yes|Unique identifier of the row to update|
|item| |yes|Row with updated values|

#### Output properties

| Property Name | Data Type | Required | Description |
|---|---|---|---|
|ItemInternalId|string|No | &nbsp; |


### GetTables
Get tables: Retrieves tables from a SQL database

#### Input properties
None.

#### Output properties

| Property Name | Data Type | Required | Description |
|---|---|---|---|
|value|array|No | Can output the Name and DisplayName properties |

### ExecuteProcedure
Execute stored procedure: Executes a stored procedure in SQL

#### Input properties

| Name| Data Type|Required|Description|
| ---|---|---|---|
|procedure|string|yes|Procedure name|
|parameters| |yes|Input parameters|

#### Output properties
Result of the stored procedure execution.

| Property Name | Data Type | Required | Description |
|---|---|---|---|
|OutputParameters|object|No | Output parameter values |
|ReturnCode|integer|No | Return code of a procedure |
|ResultSets|object|No | Result sets|

-->
