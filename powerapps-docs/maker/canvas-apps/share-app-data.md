---
title: Excel-bestanden delen die worden gebruikt door een app | Microsoft Docs
description: Deel Excel-bestanden via Dropbox, OneDrive en Google Drive. Gebruikers kunnen bestanden en mappen weergeven en bewerken.
documentationcenter: na
author: jamesol-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 10/16/2016
ms.author: jamesol
ms.openlocfilehash: 8c96a83ae67a8a06aa96b4f4ba091e361430683d
ms.sourcegitcommit: 79b8842fb0f766a0476dae9a537a342c8d81d3b3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2018
ms.locfileid: "37896116"
---
# <a name="share-excel-data-used-by-your-app"></a>Excel-gegevens delen die worden gebruikt door uw app
U kunt Excel-gegevens delen met uw app-gebruikers via een [cloud-account](connections/cloud-storage-blob-connections.md), zoals OneDrive.

U kunt bijvoorbeeld een app maken die de namen en telefoonnummers van de technische ondersteuning van uw bedrijf weergeeft. De informatie wordt opgeslagen in een Excel-werkblad, dat u opslaat in een map op Dropbox. U kunt deze map vervolgens delen met uw app-gebruikers, zodat ze de namen en telefoonnummers kunnen zien.

U moet deze gegevens delen, zodat gebruikers uw app kunnen uitvoeren en zelfs wijzigen. Gebruikers die geen machtigingen voor delen hebben, kunnen de gegevens in het Excel-bestand niet zien.

In dit onderwerp wordt beschreven hoe u gegevens in een Excel-werkblad kunt delen met behulp van Dropbox, OneDrive en Google Drive. Zie voor het maken van een app die gegevens uit een Excel-bestand weergeeft [Generate an app from Excel data (Een app maken op basis van Excel-gegevens)](get-started-create-from-data.md).

## <a name="share-data-in-dropbox"></a>Gegevens delen via Dropbox
1. Meld u aan bij Dropbox met hetzelfde account dat u hebt gebruikt om een verbinding te maken van PowerApps naar Dropbox.
2. Selecteer de map waarin het Excel-bestand staat en selecteer vervolgens **Delen**:  
   
    ![Opdracht Delen](./media/share-app-data/dropbox-share.png)
3. Voer in het dialoogvenster de e-mailadressen in waarmee uw app-gebruikers zich aanmelden bij Dropbox.  
   
    ![Delen via Dropbox](./media/share-app-data/dropbox-perms.png)
4. Als uw app-gebruikers gegevens in uw app mogen toevoegen, wijzigen of verwijderen, selecteert u **Can edit**. Anders selecteert u **Can view**.
5. Selecteer **Delen**.

Zie voor meer informatie [Sharing folders on Dropbox (mappen delen op Dropbox)](https://www.dropbox.com/en/help/19).

## <a name="share-data-in-onedrive"></a>Gegevens delen via OneDrive
1. Meld u aan bij OneDrive met hetzelfde account dat u hebt gebruikt om een verbinding te maken van PowerApps naar OneDrive.
2. Selecteer de map waarin het bestand staat en selecteer vervolgens **Delen**:  
   
    ![Opdracht Delen](./media/share-app-data/onedrive-share.png)
   
    > [!NOTE]
   > In OneDrive voor Bedrijven deelt u het bestand zelf, niet de map met het bestand.
3. Selecteer in het dialoogvenster **E-mail**.
   
    ![Delen via e-mail](./media/share-app-data/onedrive-email.png)
4. Geef de e-mailadressen op waarmee uw app-gebruikers zich aanmelden bij OneDrive en selecteer vervolgens **Delen**.  
   
    ![Een gebruiker opgeven](./media/share-app-data/onedrive-perms.png)

Zie voor meer informatie [Bestanden en mappen in OneDrive delen](https://support.office.com/article/Share-OneDrive-files-and-folders-and-change-permissions-9fcc2f7d-de0c-4cec-93b0-a82024800c07).

## <a name="share-data-in-google-drive"></a>Gegevens delen via Google Drive
1. Meld u aan bij Google Drive met hetzelfde account dat u hebt gebruikt om een verbinding te maken van PowerApps naar Google Drive.
2. Klik met de rechtermuisknop op de map waarin het Excel-bestand staat en selecteer vervolgens **Delen**.  
   
    ![Opdracht Delen](./media/share-app-data/googledrive-share.png)
3. Voer in het dialoogvenster de e-mailadressen in waarmee uw app-gebruikers zich aanmelden bij Google Drive:  
   
    ![Een gebruiker opgeven](./media/share-app-data/googledrive-perms.png)
4. Als uw app-gebruikers gegevens in uw app mogen toevoegen, wijzigen of verwijderen, selecteert u **Can edit** in de lijst met machtigingen. Anders selecteert u **Can view**.
5. Selecteer **Gereed**.

Zie voor meer informatie [Bestanden uit Google Drive delen](https://support.google.com/drive/answer/2494822).

### <a name="known-limitations"></a>Bekende beperkingen
[Lees deze beperkingen door](connections/cloud-storage-blob-connections.md#known-limitations) voor informatie over het delen van Excel-gegevens binnen uw organisatie.

