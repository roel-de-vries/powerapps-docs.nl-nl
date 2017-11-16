---
title: Formulieren aanpassen | Microsoft Docs
description: Geef op welke gegevens u wilt tonen, in welke volgorde en in welke besturingselementen.
services: 
suite: powerapps
documentationcenter: na
author: skjerland
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/16/2016
ms.author: sharik
ms.openlocfilehash: 7c2b8149d32d488e389eec273158870f0b1c5d34
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="customize-forms-in-powerapps"></a>Formulieren aanpassen in PowerApps
Pas de besturingselementen **Formulier weergeven** en **Formulier bewerken** zodanig aan dat de belangrijkste gegevens worden getoond, in de meest logische volgorde en in de besturingselementen waarmee gebruikers de gegevens makkelijk kunnen begrijpen en bijwerken.

Elk formulier bestaat uit een of meer kaarten en op elke kaart staan de gegevens uit een bepaalde kolom in de gegevensbron. Als u de stappen in dit onderwerp volgt, kunt u opgeven welke kaarten in een formulier moeten worden weergegeven. Daarnaast kunt u kaarten in een formulier omhoog en omlaag verplaatsen en configureren hoe gegevens uit een kolom op een kaart worden weergegeven.

Zie [Introduction to PowerApps](getting-started.md) (Inleiding tot PowerApps) als u onbekend bent met PowerApps.

## <a name="prerequisites"></a>Vereisten
In deze zelfstudie kunt u alleen de algemene concepten doorlezen, of u kunt de zelfstudie precies volgen door de stappen te voltooien.

1. [Create a connection](connect-to-sharepoint.md) (Een verbinding maken) van PowerApps naar SharePoint.
2. Maak de SharePoint-lijst die wordt beschreven in [Customize a layout](customize-layout-sharepoint.md) (Een indeling aanpassen).
3. [Generate an app automatically](app-from-sharepoint.md) (Automatisch een app genereren) op basis van die lijst.
4. Klik of tik op een pictogram in de rechterbovenhoek van de linkernavigatiebalk om over te schakelen naar de miniatuurweergave.
   
    ![Schakelen tussen weergaven](./media/customize-forms-sharepoint/toggle-view.png)

## <a name="show-and-hide-cards"></a>Kaarten weergeven en verbergen
1. Klik of tik in de linker navigatiebalk op de middelste miniatuur om **DetailsScreen1** te selecteren.
   
    ![Scherm met details selecteren](./media/customize-forms-sharepoint/details-thumbnail.png)
2. Klik of tik op een kaart om deze te selecteren en toon de opties voor het aanpassen van formulieren in het rechter deelvenster.
   
    ![Een kaart selecteren](./media/customize-forms-sharepoint/select-card.png)
3. Klik of tik in het rechterdeelvenster op het selectievakje van de kaart **AccountID** om deze te verbergen. Klik of tik op het selectievakje van de kolom **ID** om deze weer te geven.
   
    ![Kaart weergeven](./media/customize-forms-sharepoint/checkbox.png)

## <a name="reorder-the-cards"></a>De volgorde van de kaarten wijzigen
* Klik of tik op de kaart **Titel** om deze te selecteren en sleep de titelbalk daarvan vervolgens omhoog totdat de kaart **OrderDate** is gemarkeerd.
  
    ![Kaart verplaatsen](./media/customize-forms-sharepoint/move-card.png)
  
    De kaart die u verplaatst, verschijnt vlak boven de kaart die wordt gemarkeerd als u de muisknop loslaat.
  
    ![Opnieuw gerangschikte kaarten](./media/customize-forms-sharepoint/reordered-card.png)

## <a name="run-the-app"></a>De app uitvoeren
1. Klik of tik in de linker navigatiebalk op de bovenste miniatuur om **BrowseScreen1** te selecteren.
   
    ![Miniatuur voor BrowseScreen1](./media/customize-forms-sharepoint/browse-thumbnail.png)
2. Open de previewmodus door op F5 te drukken (of door het pictogram **Preview** in de rechterbovenhoek te selecteren).  
   
    ![Pictogram Preview](./media/customize-forms-sharepoint/open-preview.png)
3. Klik of tik in de rechterbovenhoek op het pictogram met het plusteken om een record toe te voegen in **EditScreen1**.
   
    ![Record toevoegen](./media/customize-forms-sharepoint/add-record.png)
4. Voeg de gewenste gegevens toe en klik of tik op het pictogram met het selectievakje in de rechterbovenhoek om de nieuwe record op te slaan in de SharePoint-lijst en terug te gaan naar **BrowseScreen1**.
   
    ![Record opslaan](./media/customize-forms-sharepoint/save-record.png)
5. Klik of tik op de pijl voor het item dat u zojuist hebt gemaakt om de details over dat item weer te geven in **DetailScreen1**.  
   
    ![Pijl-rechts](./media/customize-forms-sharepoint/right-arrow.png)
6. Klik of tik in de rechterbovenhoek op het pictogram voor bewerken om de record bij te werken in **EditScreen1**.
   
    ![Record bewerken](./media/customize-forms-sharepoint/edit-record.png)
7. Wijzig de informatie in een of meer velden en klik of tik op het selectievakje in de rechterbovenhoek om de wijzigingen in de SharePoint-lijst op te slaan en terug te gaan naar **DetailScreen1**.  
   
    ![Wijzigingen opslaan](./media/customize-forms-sharepoint/save-record.png)
8. Klik of tik op het prullenbakpictogram in de rechterbovenhoek om de record te verwijderen die u zojuist hebt bijgewerkt en terug te gaan naar **BrowseScreen1**.
   
    ![Record verwijderen](./media/customize-forms-sharepoint/delete-record.png)
9. Sluit de preview-modus door op Esc te drukken (of door te klikken of tikken op het pictogram voor sluiten in de rechterbovenhoek, *onder* de titelbalk voor PowerApps).
   
    ![Preview-modus sluiten](./media/customize-forms-sharepoint/close-preview.png)

## <a name="next-steps"></a>Volgende stappen
* Druk op Ctrl+S om de app op te slaan, zodat u deze op andere apparaten kunt uitvoeren.
* [Deel de app](share-app.md) zodat anderen deze kunnen uitvoeren.

