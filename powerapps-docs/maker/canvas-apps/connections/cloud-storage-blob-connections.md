---
title: Overzicht van de verbinding met cloudopslag | Microsoft Docs
description: Kijk hoe u verbinding maakt met een account voor cloudopslag en Excel-gegevens weergeeft in uw app
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
ms.openlocfilehash: 7c3d88498c92d8e1d0e8490bfafc0654b044e98b
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
---
# <a name="connect-to-cloud-storage-from-powerapps"></a>Verbinding maken met cloudopslag vanuit PowerApps
PowerApps biedt diverse verbindingen met cloudopslag. Bij elk van deze verbindingen kunt u een Excel-bestand opslaan en de gegevens erin overal in uw app gebruiken. Deze verbindingen zijn onder andere:  

| **Azure Blob** | **Box** | **Dropbox** | **Google Drive** | **OneDrive** | **OneDrive<br> voor Bedrijven** |
| --- | --- | --- | --- | --- | --- |
| ![Pictogram](./media/cloud-storage-blob-connections/blobicon.png) |![API-pictogram][boxicon] |![API-pictogram][dropboxicon] |![API-pictogram][googledriveicon] |![API-pictogram][onedriveicon] |![API-pictogram][onedriveforbusinessicon] |

[!INCLUDE [connection-requirements](../../../includes/connection-requirements.md)]

* Een Excel-bestand met gegevens die zijn [opgemaakt als een tabel](https://support.office.com/article/Create-an-Excel-table-in-a-worksheet-E81AA349-B006-4F8A-9806-5AF9DF0AC664):
  
  1. Open het Excel-bestand en selecteer vervolgens een cel in de gegevens die u wilt gebruiken.
  2. Selecteer **Tabel** op het tabblad **Invoegen**.
  3. Schakel in het dialoogvenster **Opslaan als tabel** het selectievakje **De tabel bevat kopteksten** in en selecteer vervolgens **OK**.
  4. Sla uw wijzigingen op.

## <a name="connect-to-the-cloud-storage-connection"></a>Verbinding maken met de cloudopslagverbinding
1. Ga naar [powerapps.com](https://web.powerapps.com), vouw **Beheren** uit en selecteer **Verbindingen**:  
   
    ![Verbindingen selecteren](./media/cloud-storage-blob-connections/connections.png)
2. Selecteer **Nieuwe verbinding** en selecteer uw verbinding met cloudopslag. Selecteer bijvoorbeeld **OneDrive**.
3. U wordt gevraagd om de gebruikersnaam en het wachtwoord van uw cloudopslagaccount. Voer deze gegevens in en selecteer **Aanmelden**:  
    ![Gebruikersnaam en wachtwoord invoeren](./media/cloud-storage-blob-connections/signin.png)
   
    Nadat u bent aangemeld, is deze verbinding gereed voor gebruik in uw apps.
4. Klik of tik in uw app op het lint, in het tabblad **Weergeven**, op **Gegevensbronnen**. Tik of klik in het rechterdeelvenster op **Een gegevensbron toevoegen**, klik of tik op uw cloud-opslag-verbinding en kies vervolgens de Excel-tabel.
5. Selecteer **Verbinden**.
   
    De tabel wordt vermeld als een gegevensbron:
   
    ![Selecteer de Excel-tabel](./media/cloud-storage-blob-connections/selecttable.png)
   
    > [!NOTE]
> Denk eraan dat Excel-gegevens moeten zijn opgemaakt als tabel.

## <a name="using-the-excel-data-in-your-app"></a>De Excel-gegevens in uw app gebruiken
1. Selecteer op het tabblad **Invoegen** de optie **Galerie** en selecteer vervolgens het galeriebesturingselement **Met tekst**.
2. Stel de eigenschap **[Items](../controls/properties-core.md)** van de galerie in op uw Excel-tabel. Als uw Excel-tabel bijvoorbeeld **Tabel1** heet, stelt u de eigenschap in op Tabel1:  
   
    ![Eigenschap Items](./media/cloud-storage-blob-connections/itemsproperty.png)  
   
    De galerie wordt automatisch bijgewerkt met gegevens uit de Excel-tabel.
3. Selecteer in de galerie het tweede of derde besturingselement **Label**. Standaard ziet u dat de eigenschap **Tekst** van het tweede en derde label automatisch is ingesteld op `ThisItem.something`. U kunt deze labels instellen op elke kolom in de tabel.
   
    In het volgende voorbeeld is het tweede label ingesteld op `ThisItem.Name` en het derde label op `ThisItem.Notes`:  
   
    ![Tweede label](./media/cloud-storage-blob-connections/items-secondtextbox.png)  
   
    ![Derde label](./media/cloud-storage-blob-connections/items-thirdtextbox.png)  
   
    Voorbeelduitvoer:  
    ![Tweede en derde label](./media/cloud-storage-blob-connections/secondthirdtextboxes.png)
   
> [!NOTE]
> Het eerste vak is eigenlijk een afbeeldingsbesturingselement. Als u geen afbeelding in uw Excel-tabel hebt, kunt u het afbeeldingsbesturingselement verwijderen en in plaats daarvan een label toevoegen. [Een besturingselement toevoegen en configureren](../add-configure-controls.md) is een goede informatiebron.

[Tabellen en records begrijpen](../working-with-tables.md) biedt meer informatie en enkele voorbeelden.  

## <a name="sharing-your-app"></a>De app delen
U kunt [de app](../share-app.md), [bronnen](../share-app-resources.md), zoals connectoren, en [uw gegevens](../share-app-data.md) met anderen in uw organisatie delen.

Als u een map deelt in Dropbox, dan moet de gedeelde map zijn gekoppeld aan het Dropbox-account van de gebruiker.

Voor connectoren met betrekking tot Excel-bestanden gelden [bepaalde beperkingen](#sharing-excel-tables).

## <a name="known-limitations"></a>Bekende beperkingen
Als **Niet-ondersteund gegevenstype** of **Niet opgemaakt als een tabel** wordt weergegeven wanneer u een Excel-verbinding probeert te gebruiken in uw app, [maakt u de gegevens op als een tabel](https://support.office.com/article/Create-an-Excel-table-in-a-worksheet-E81AA349-B006-4F8A-9806-5AF9DF0AC664).

Als uw Excel-gegevens een berekende kolom bevatten, kunt u deze niet gebruiken om een app te maken en kunt u die gegevens niet toevoegen aan een bestaande app.

### <a name="sharing-excel-tables"></a>Excel-tabellen delen
Ga als volgt te werk als u gegevens in een Excel-bestand wilt delen:

* In OneDrive voor Bedrijven deelt u het bestand zelf.
* In OneDrive deelt u de map die het bestand bevat en geeft u bestandspaden (geen URL's) voor media op.
* In Dropbox of Google Drive deelt u het bestand of de map.

## <a name="helpful-links"></a>Nuttige koppelingen
Bekijk alle [beschikbare verbindingen](../connections-list.md).  
Lees hoe u [verbindingen toevoegt](../add-manage-connections.md) en [een gegevensbron toevoegt](../add-data-connection.md) aan uw apps.  
[Tabellen en records begrijpen](../working-with-tables.md) met gegevensbronnen in tabelvorm.  
Enkele aanvullende bronnen over galeries zijn [Een lijst met items weergeven](../add-gallery.md) en [Afbeeldingen en tekst in een galerie weergeven](../show-images-text-gallery-sort-filter.md).

<!--Icon references-->
[boxicon]: ./media/cloud-storage-blob-connections/boxicon.png
[dropboxicon]: ./media/cloud-storage-blob-connections/dropboxicon.png
[googledriveicon]: ./media/cloud-storage-blob-connections/googledriveicon.png
[onedriveicon]: ./media/cloud-storage-blob-connections/onedriveicon.png
[onedriveforbusinessicon]: ./media/cloud-storage-blob-connections/onedriveforbusinessicon.png
