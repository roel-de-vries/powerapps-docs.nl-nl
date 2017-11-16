---
title: Een galerie-indeling aanpassen | Microsoft Docs
description: Opgeven welke besturingselementen worden weergegeven, welke velden worden weergegeven in een besturingselement en welke kolommen worden gebruikt voor het sorteren en zoeken van records.
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
ms.date: 05/02/2017
ms.author: sharik
ms.openlocfilehash: c581abad70012eb66413a31bd765437df69b7a70
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="customize-a-gallery-layout-in-powerapps"></a>Een galerie-indeling aanpassen in PowerApps
Nadat u automatisch een app hebt gegenereerd in PowerApps, kunt u het bladerscherm aanpassen dat standaard wordt weergegeven. U kunt opgeven welke indeling moet worden gebruikt, welke kolommen moeten worden weergegeven en welke kolommen moeten worden gebruikt voor het sorteren en filteren van records.

* Zie [Een app genereren voor het beheren van gegevens in een SharePoint-lijst](app-from-sharepoint.md) voor informatie over het automatisch genereren van een app.
* Zie [Inleiding tot PowerApps](getting-started.md) als u onbekend bent met PowerApps.

## <a name="prerequisites"></a>Vereisten
In deze zelfstudie kunt u alleen de algemene concepten doorlezen, of u kunt de zelfstudie precies volgen door de stappen te voltooien.

1. [Een verbinding maken](connect-to-sharepoint.md) van PowerApps met SharePoint.
2. Maak een SharePoint-lijst genaamd **AppGen**, die deze kolommen bevat.
   
    ![Voorbeeldkolommen van SharePoint](./media/customize-layout-sharepoint/list-columns.png)
3. Voeg deze items toe aan de lijst die u zojuist hebt gemaakt.
   
    ![Voorbeeldgegevens](./media/customize-layout-sharepoint/sample-data.png)
4. [Genereer automatisch een app](app-from-sharepoint.md) op basis van de lijst die u zojuist hebt gemaakt.
5. Klik of tik op een pictogram in de rechterbovenhoek van de linkernavigatiebalk om over te schakelen naar de miniatuurweergave.
   
    ![Schakelen tussen weergaven](./media/customize-layout-sharepoint/toggle-view.png)

## <a name="customize-the-gallery"></a>De galerie aanpassen
1. Klik of tik in de linkernavigatiebalk op de bovenste miniatuur om ervoor te zorgen dat **BrowseScreen1** is geselecteerd.
   
    ![Miniatuur voor BrowseScreen1](./media/customize-layout-sharepoint/browse-thumbnail.png)
   
    Op het bladerscherm (**BrowseScreen1**) worden de **AccountID** en **Title** van elk item in de SharePoint-lijst weergegeven.
   
    ![Bladerscherm geeft titels en account-id’s weer](./media/customize-layout-sharepoint/browse-accountid.png)
   
    Vervolgens geeft u op dat de **OrderDate** voor elk item wordt weergegeven, in plaats van de **AccountID**.
2. Klik of tik op de **AccountID** voor het eerste item op het scherm.
   
    Wanneer u klikt of tikt op een UI-element (ook wel besturingselement genoemd), selecteert u het, en wordt een selectiekader met formaatgrepen weergegeven om het besturingselement.
   
    ![Hoofdtekst van eerste item selecteren](./media/customize-layout-sharepoint/select-body.png)
3. Open in het rechterdeelvenster de lijst **Title1** en klik of tik vervolgens op **OrderDate**.
   
    ![Titel weergeven](./media/customize-layout-sharepoint/bind-data.png)
   
    Uw wijziging wordt doorgevoerd in **BrowseScreen1**.
   
    ![Indeling met datums](./media/customize-layout-sharepoint/browse-dates.png)

Zie [Een lijst met items weergeven in PowerApps](add-gallery.md) voor meer informatie over galerieën.

## <a name="set-the-sort-and-search-columns"></a>Sorteer- en zoekkolommen instellen
1. Selecteer het besturingselement **Gallery** door op een record te klikken of tikken, behalve de eerste record.
   
    ![Galerie selecteren](./media/customize-layout-sharepoint/select-gallery.png)
2. Controleer of de eigenschappenlijst linksboven de optie **Items** bevat.
   
    ![Eigenschap Items](./media/customize-layout-sharepoint/items-property.png)
   
    De waarde van deze eigenschap, die in de formulebalk wordt weergegeven, bepaalt niet alleen de bron van de gegevens die op het scherm worden weergegeven, maar ook welke filter- en sorteerkolommen worden gebruikt.
   
    De formulebalk kan bijvoorbeeld standaard deze formule bevatten.
   
    ![Eigenschap Default Items](./media/customize-layout-sharepoint/default-items.png)
   
    Gebruikers kunnen op basis van deze formule alleen die records weergeven die beginnen met een of meer letters in de kolom **AccountID**.
   
    ![Standaardzoekkolommen](./media/customize-layout-sharepoint/default-search.png)
   
    Als een gebruiker bijvoorbeeld de letter 'A' in de zoekbalk typt, wordt op het scherm de record voor Europa weergegeven. De titel van die record komt niet overeen met het zoekcriterium, maar de AccountID wel. Verderop in deze procedure gaat u de formule wijzigen om records te filteren op basis van de kolom **Title**.
   
    In elke gegenereerde app kunnen gebruikers de records in oplopende of aflopende alfabetische volgorde sorteren door te klikken of tikken op de sorteerknop rechtsboven. De formule geeft aan dat de records worden gesorteerd op basis van de kolom **AccountID**.
   
    ![Standaardsorteerkolom](./media/customize-layout-sharepoint/default-sort.png)
   
    Verderop in deze procedure gaat u de formule aanpassen om de records te sorteren op basis van de kolom **Title**.
3. Vervang in de formulebalk beide vermeldingen van **AccountID** door **Title** (inclusief de dubbele aanhalingstekens rond de tweede vermelding).
   
    De formulebalk moet nu een formule bevatten die er ongeveer zo uitziet:<br>
    **SortByColumns(Filter(AppGen, StartsWith(Title, TextSearchBox1.Text)), "Title", If(SortDescending1, Descending, Ascending))**
   
    **Opmerking**: het getal achter **TextSearchBox** kan hoger zijn, afhankelijk van acties die u eerder hebt uitgevoerd. Desondanks moet de formule werken zoals verwacht.

## <a name="test-sorting-and-searching"></a>Sorteren en zoeken testen
1. Open de Preview-modus door op F5 te drukken (of klik of tik op het afspeelpictogram rechtsboven).
   
    ![Preview-modus openen](./media/customize-layout-sharepoint/open-preview.png)
2. Klik of tik rechtsboven in **BrowseScreen1** een of meerdere malen op de sorteerknop, om de alfabetische sortering oplopend of aflopend te maken.
   
    ![De sorteerknop testen](./media/customize-layout-sharepoint/test-sort.png)
3. Typ een of meer letters in het zoekvak om alleen die records weer te geven waarvan de titel begint met de letter of letters die u typt.
   
    ![De zoekbalk testen](./media/customize-layout-sharepoint/test-search.png)
4. Sluit de Preview-modus door op F5 te drukken (of klik of tik op het pictogram voor sluiten in de rechterbovenhoek, *onder* de titelbalk voor PowerApps).
   
    ![Preview-modus sluiten](./media/customize-layout-sharepoint/close-preview.png)

## <a name="change-the-title-of-the-screen"></a>De schermtitel wijzigen
1. Klik of tik op de schermtitel om die te selecteren.
   
    ![Schermtitel selecteren](./media/customize-layout-sharepoint/select-screen-title.png)
2. Controleer of de eigenschappenlijst **Text** bevat en typ vervolgens de gewenste naam tussen dubbele aanhalingstekens in de formulebalk.
   
    ![Schermtitel bijwerken](./media/customize-layout-sharepoint/update-screen-title.png)
   
    Uw wijziging wordt doorgevoerd in **BrowseScreen1**.
   
    ![Nieuwe schermtitel](./media/customize-layout-sharepoint/new-screen-title.png)

## <a name="next-steps"></a>Volgende stappen
* Druk op Ctrl+S om uw wijzigingen op te slaan.
* [De formulieren aanpassen](customize-forms-sharepoint.md) in de app door de velden in het formulier weer te geven, te verbergen of een andere volgorde te geven.

