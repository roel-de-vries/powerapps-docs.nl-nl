---
title: Een app genereren van Excel-gegevens | Microsoft Docs
description: Automatisch een app maken op basis van een Excel-bestand in de cloud, de app aanpassen en vervolgens ontdekken hoe deze werkt.
services: 
suite: powerapps
documentationcenter: na
author: karthik-1
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/16/2016
ms.author: sharik
ms.openlocfilehash: cf90156292985e58e2d68d2828d7c943b45facdf
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/23/2018
---
# <a name="generate-an-app-from-excel-data"></a>Een app genereren van Excel-gegevens
Maak automatisch een app op basis van gegevens in een Excel-bestand dat u uploadt naar een opslagaccount in de cloud, zoals OneDrive. Nadat u de app hebt gegenereerd, past u deze aan uw behoeften aan en voert u de app uit om te zien of deze naar behoren werkt.

Gegenereerde apps hebben standaard drie schermen:

* **BrowseScreen1**: dit toont een subset van een of meer velden, een zoekbalk en een sorteerknop waarmee gebruikers gemakkelijk een bepaalde record kunnen vinden.
* **DetailsScreen1**: dit geeft meer velden of alle velden voor een bepaalde record weer.
* **EditScreen1**: dit bevat UI-elementen waarmee gebruikers een record kunnen maken of bijwerken en hun wijzigingen kunnen opslaan.

> [!NOTE]
> U kunt net zo makkelijk een app genereren op basis van een [aangepaste SharePoint-lijst](app-from-sharepoint.md).

## <a name="prerequisites"></a>Vereisten
* [Meld u aan](signup-for-powerapps.md) voor PowerApps en voer een van de volgende stappen uit:
  * Installeer [PowerApps Studio voor Windows](http://aka.ms/powerappsinstall) op een computer met Windows 8, Windows 8.1 of Windows 10.
  * Open [de webversie van PowerApps Studio](create-app-browser.md) (preview-versie) in een browser.
* Meld u aan bij PowerApps met dezelfde referenties die u hebt gebruikt om u te registreren.
* Als u deze zelfstudie exact wilt volgen, kunt u dit [Excel-bestand](https://az787822.vo.msecnd.net/documentation/get-started-from-data/FlooringEstimates.xlsx) downloaden.
  
    > [!IMPORTANT]
> U kunt uw eigen Excel-bestand gebruiken als de gegevens als een tabel zijn opgemaakt. Zie [Een Excel-tabel maken in een werkblad](https://support.office.com/en-us/article/Create-an-Excel-table-in-a-worksheet-E81AA349-B006-4F8A-9806-5AF9DF0AC664) voor meer informatie.
* Upload het Excel-bestand naar OneDrive of een ander [cloudopslagaccount](connections/cloud-storage-blob-connections.md).

## <a name="create-an-app"></a>Een app maken
1. Klik of tik in PowerApps Studio op **Nieuw** in het menu **Bestand** (aan de linkerkant).
   
    ![Optie Nieuw in het menu Bestand](./media/get-started-create-from-data/file-new.png)
2. Volg deze stappen:
   
   * Als uw cloudopslagaccount wordt weergegeven onder **Beginnen met uw gegevens**, klikt of tikt u op **Telefoonindeling**.
     
     ![Optie voor het maken van een app op basis van gegevens](./media/get-started-create-from-data/create-from-data.png)
   * Als uw cloudopslagaccount niet wordt weergegeven onder **Beginnen met uw gegevens**, klikt u op de pijl aan het eind van de rij met tegels. Als uw account wordt weergegeven in de lijst met verbindingen, klikt of tikt u op die vermelding.
   * Als uw cloudopslagaccount niet wordt weergegeven onder **Beginnen met uw gegevens** of in de lijst met verbindingen, klikt of tikt u op **Nieuwe verbinding** en klikt of tikt u vervolgens op de vermelding voor uw account. Klik of tik op **Verbinden** en volg de aanwijzingen om de verbinding te configureren.
     
     ![Verbinden met OneDrive](./media/get-started-create-from-data/connect-onedrive.png)
3. Klik of tik onder **Choose an Excel file** op **FlooringEstimates.xlsx**.
   
    ![Excel-bestand FlooringEstimates](./media/get-started-create-from-data/choose-spreadsheet.png)  
4. Klik of tik onder **Een tabel kiezen** op **FlooringEstimates**.  
   
    ![Tabel FlooringEstimates selecteren](./media/get-started-create-from-data/choose-table.png)
5. Klik of tik op **Connect** om de app te genereren.
6. Als u wordt voorgesteld een inleidende rondleiding te volgen, klikt of tikt u op **Volgende** om vertrouwd te raken met de belangrijkste gedeelten van de PowerApps-gebruikersinterface (of klik of tik op **Overslaan**).
   
    ![Kies Volgende voor de rondleiding](./media/get-started-create-from-data/quick-tour.png)
   
    > [!NOTE]
> U kunt de rondleiding altijd later volgen door op het vraagtekenpictogram in de rechterbovenhoek te klikken of tikken en vervolgens op **Take the intro tour**.

## <a name="change-the-gallery-layout"></a>De galerie-indeling wijzigen
Als een app wordt gemaakt, heeft deze een standaardindeling die is gebaseerd op uw gegevens, maar u kunt de galerie-indeling naar wens aanpassen.

1. Klik of tik op een pictogram in de rechterbovenhoek van de linkernavigatiebalk om over te schakelen naar de miniatuurweergave.
   
    ![Schakelen tussen weergaven](./media/get-started-create-from-data/toggle-view.png)
2. Klik of tik op de bovenste miniatuur om het bladerscherm (**BrowseScreen1**) weer te geven.
3. Klik op of tik op een willekeurige plaats in de galerie, bijvoorbeeld op de eerste afbeelding.
   
    ![Afbeelding selecteren](./media/get-started-create-from-data/select-image.png)
4. Open in het rechterdeelvenster de lijst **Indeling** en klik of tik vervolgens op de indeling die een afbeelding, een titel en een ondertitel bevat.
   
    ![Indeling selecteren](./media/get-started-create-from-data/select-layout.png)
   
    De indeling van de app wordt aangepast op basis van uw keuze.
   
    ![BrowseScreen1 met nieuwe indeling](./media/get-started-create-from-data/browse-layout.png)

## <a name="change-the-data-that-appears"></a>De gegevens wijzigen die worden weergegeven
1. Klik of tik onder **Naar items zoeken** op **Carpet** om het besturingselement **Label** te selecteren.
   
   De bijbehorende lijst wordt in het rechterdeelvenster gemarkeerd.
   
   ![Eerste label selecteren](./media/get-started-create-from-data/select-gallery-textbox.png)
2. Open de gemarkeerde lijst in het rechterdeelvenster en klik of tik op **Naam**.
   
    ![Eerste label instellen](./media/get-started-create-from-data/set-gallery-textbox.png)
3. Open de onderste lijst en klik of tik op **Categorie**.
   
    ![Categorie instellen](./media/get-started-create-from-data/set-category.png)
   
    **BrowseScreen1** wordt gewijzigd en er worden een naam en een categorie voor elke record weergegeven.
   
    ![BrowseScreen1 met nieuwe inhoud](./media/get-started-create-from-data/browse-content.png)
   
    > [!NOTE]
> Standaard is ingesteld dat u door de lijst (een galerie genoemd) kunt schuiven met een muiswiel of, op een touchscreen, omhoog of omlaag te swipen. Als u een trackpad of een muis zonder schuifwieltje wilt gebruiken, selecteert u de galerie, klikt of tikt u op **ShowScrollbar** in de lijst met eigenschappen en vervangt u **onwaar** door **waar** in de formulebalk.

## <a name="change-the-order-of-fields-in-a-form"></a>De volgorde van velden op een formulier wijzigen
1. Klik of tik in de linkernavigatiebalk op de middelste miniatuur om het detailvenster (**DetailsScreen1**) te openen.
   
    ![Miniatuur DetailScreen1](./media/get-started-create-from-data/detail-screen-thumbnail.png)
2. Klik of tik op de afbeelding om opties weer te geven waarmee u het formulier kunt aanpassen.
   
    ![Een kaart selecteren](./media/get-started-create-from-data/select-card.png)
3. Sleep in het rechterdeelvenster het veld **Naam** naar de bovenkant van de lijst.
   
    ![Een kaart verplaatsen](./media/get-started-create-from-data/move-card.png)
   
    Het scherm wordt aangepast aan de wijzigingen die u hebt gemaakt.
   
    ![Naam boven aan het scherm](./media/get-started-create-from-data/name-first.png)

## <a name="change-a-control"></a>Een besturingselement wijzigen
1. Klik of tik in de linkernavigatiebalk op de onderste miniatuur om het bewerkingsscherm (**EditScreen1**) te openen.
   
    ![Miniatuur EditScreen1](./media/get-started-create-from-data/edit-screen-thumbnail.png)
2. Klik of tik op **Overzicht**.
   
    In deze stap wordt de kaart Overzicht geselecteerd. Elke kaart bevat tekst waarmee het doel van de kaart wordt beschreven. U kunt ook de besturingselementen op de kaart aanpassen. Zie [Card control in PowerApps](controls/control-card.md) (Kaarten bedienen in PowerApps) voor meer informatie.
   
    ![Overview-kaart selecteren](./media/get-started-create-from-data/select-overview.png)
3. Klik of tik in het rechterdeelvenster op de pijl-omlaag voor de kaart, schuif omlaag en klik of tik op **Tekst van meerdere regels bewerken**.
   
    In deze stap wordt een overzicht getoond van elk product in een besturingselement dat groot genoeg is om de tekst weer te geven.
   
    ![Kaart wijzigen](./media/get-started-create-from-data/card-selector.png)

## <a name="run-the-app"></a>De app uitvoeren
Tijdens het aanpassen van de app kunt u uw wijzigingen testen door de app uit te voeren in de Preview-modus.

1. Klik of tik in de linkernavigatiebalk op de bovenste miniatuur om het bladerscherm (**BrowseScreen1**) te openen.
2. Open de Preview-modus door op F5 te drukken of door rechtsboven op de knop **Afspelen** te tikken of klikken.
   
    ![Pictogram Preview](./media/get-started-create-from-data/open-preview.png)
3. Klik of tik in **BrowseScreen1** op de pijl rechts van een record om de record weer te geven in het detailscherm (**DetailsScreen1**).
   
    ![Een pijl selecteren op BrowseScreen1](./media/get-started-create-from-data/select-record.png)
4. Klik of tik in **DetailsScreen1** op het potloodpictogram in de rechterbovenhoek om de record in het bewerkingsscherm (**EditScreen1**) weer te geven.
   
    ![Een record bewerken](./media/get-started-create-from-data/edit-record.png)
5. Wijzig in **EditScreen1** de informatie in een of meer velden en klik of tik op het selectievakje in de rechterbovenhoek om de wijzigingen op te slaan.
   
    ![Wijzigingen opslaan in EditScreen1](./media/get-started-create-from-data/save-record.png)
6. Sluit de Preview-modus door op Esc te drukken (of door op het sluitpictogram onder de titelbalk te klikken of te tikken).
   
    ![Preview-modus sluiten](./media/get-started-create-from-data/close-preview.png)

### <a name="known-limitations"></a>Bekende beperkingen
[Lees deze beperkingen door](connections/cloud-storage-blob-connections.md#sharing-excel-tables) voor informatie over het delen van Excel-gegevens binnen uw organisatie.

## <a name="next-steps"></a>Volgende stappen
* Druk op Ctrl+S om de app op te slaan, zodat u deze op andere apparaten kunt uitvoeren.
* U hebt nu geleerd om een app te maken op basis van uw gegevens. Zie hiervoor [Create an app from scratch](get-started-create-from-blank.md) (Een volledig nieuwe app maken).
* [Deel de app](share-app.md) zodat anderen deze kunnen uitvoeren.

