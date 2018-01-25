---
title: Afbeeldingen toevoegen aan Excel | Microsoft Docs
description: Stapsgewijze instructies voor het toevoegen van afbeeldingsbestanden en pentekeningen aan Excel in een cloudopslagaccount
services: 
suite: powerapps
documentationcenter: 
author: skjerland
manager: anneta
editor: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/25/2016
ms.author: sharik
ms.openlocfilehash: f3e5fdce6948928cdd393e7a9933b3261af4e3f6
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/23/2018
---
# <a name="add-images-to-excel-from-powerapps"></a>Afbeeldingen toevoegen aan Excel via PowerApps
Maak automatisch een app waarin gebruikers afbeeldingen uit bestanden of tekeningen kunnen toevoegen, weergeven of verwijderen met het besturingselement **Pen**. De app is gebaseerd op een Excel-bestand dat u maakt en uploadt naar een cloudopslagaccount.

## <a name="prerequisites"></a>Vereisten

* Vertrouwd zijn met het [toevoegen en configureren van besturingselementen](add-configure-controls.md).
* Vertrouwd zijn met het [configureren van Excel-gegevens in een tabel](https://support.office.com/en-us/article/Format-an-Excel-table-6789619F-C889-495C-99C2-2F971C0E2370?ui=en-US&rs=en-US&ad=US).
* Een [PowerApps-verbinding](add-data-connection.md) met een cloudopslagaccount (bijvoorbeeld bij Dropbox, OneDrive of Google Drive) waarin u een Excel-bestand kunt opslaan.

## <a name="create-the-data-source-and-the-app"></a>De gegevensbron en de app maken
1. In Excel voegt u **Bijschrift** en **Afbeelding [image]** toe aan twee cellen die naast elkaar staan (zoals A1 en B1) en die boven twee lege cellen staan.
2. Formatteer de cellen die u hebt bijgewerkt en de cellen die eronder staan als tabel en geef de tabel een naam (bijvoorbeeld **Afbeeldingen**).
   
    ![Een tabel maken](./media/add-images-to-excel/create-table.png)
3. Sla het bestand op (bijvoorbeeld als **ImageDemo**) en upload het naar uw cloudopslagaccount.
4. In PowerApps klikt of tikt u op **Nieuw** in het menu **Bestand** (aan de linkerkant als u een app nog niet hebt geopend) en klikt of tikt u daarna op **Telefoonindeling** in de tegel van uw cloudopslagaccount.
   
    ![Uw cloudopslagaccount selecteren](./media/add-images-to-excel/select-account.png)
5. Onder **Een Excel-bestand kiezen** klikt of tikt u op het bestand dat u hebt gemaakt.
   
    ![Uw werkmap selecteren](./media/add-images-to-excel/select-workbook.png)
6. Klik of tik onder **Een tabel kiezen** op de tabel die u hebt gemaakt en klik of tik daarna op **Verbinden**.
   
    ![Uw tabel selecteren](./media/add-images-to-excel/select-table.png)
7. Als u PowerApps zojuist hebt geïnstalleerd of geüpgraded, bekijkt u de rondleiding of klikt of tikt u op **Overslaan**.
   
    ![Eerste scherm van de rondleiding](./media/add-images-to-excel/quick-tour.png)

## <a name="add-an-image-from-a-file"></a>Een afbeelding uit een bestand toevoegen
1. Open de preview-modus door op F5 te drukken (of door op het afspeelpictogram rechtsboven te klikken of te tikken). Klik of tik vervolgens op het pluspictogram in de rechterbovenhoek.
   
    ![Pluspictogram](./media/add-images-to-excel/plus-icon.png)
2. In het vak **Bijschrift** typt of plakt u een korte beschrijving van het afbeeldingsbestand dat u wilt toevoegen. Klik of tik daarna eronder om het bestand te specificeren.
3. In het dialoogvenster **Openen** bladert u naar het bestand dat u wilt toevoegen en klikt of tikt u erop. Klik of tik daarna op **Openen**.
   
    ![Een bijschrift en een afbeelding toevoegen](./media/add-images-to-excel/add-image.png)
4. Klik of tik op het vinkje in de rechterbovenhoek om uw wijzigingen op te slaan.
   
    ![Wijzigingen opslaan](./media/add-images-to-excel/checkmark-icon.png)
5. Voeg zo veel afbeeldingen toe als u maar wilt door de laatste drie stappen te herhalen. Druk daarna op ESC om terug te keren naar de standaardwerkruimte.
6. (optioneel) U kunt het besturingselement **Label** met het bijschrift van elke afbeelding verwijderen.

## <a name="add-a-drawing"></a>Een tekening toevoegen
1. Bekijk **EditScreen1** door er in de navigatiebalk links op te klikken of tikken. Klik of tik daarna op de afbeeldingskaart om deze te selecteren.
   
    ![Een afbeeldingskaart selecteren](./media/add-images-to-excel/select-card.png)
2. Klik of tik in het rechterdeelvenster op de kaartselector voor de afbeeldingskaart en klik of tik daarna op **Notities toevoegen**.
   
    ![Notities toevoegen](./media/add-images-to-excel/add-notes.png)
3. Bekijk **BrowseScreen1** door er in de navigatiebalk links op te klikken of tikken. Open daarna de preview-modus.
4. Klik of tik op het pluspictogram in de rechterbovenhoek, voeg een bijschrift toe en teken een afbeelding in het besturingselement **Pen**.
   
    ![Een afbeelding tekenen](./media/add-images-to-excel/draw-picture.png)
5. Klik of tik op het vinkje in de rechterbovenhoek om uw wijzigingen op te slaan.
   
    ![Wijzigingen opslaan](./media/add-images-to-excel/checkmark-icon.png)
6. Voeg zo veel tekeningen toe als u maar wilt door de laatste twee stappen te herhalen. Druk daarna op ESC om terug te keren naar de standaardwerkruimte.

