---
title: Overzicht van de Dynamics 365-verbinding | Microsoft Docs
description: Een app maken voor het beheer van gegevens in Dynamics 365
author: Mattp123
ms.service: powerapps
ms.topic: reference
ms.component: canvas
ms.date: 07/12/2017
ms.author: matp
ms.openlocfilehash: 425620f3e20af7945c0e1506cab23a90c5209973
ms.sourcegitcommit: 91a102426f1bc37504142cc756884f3670da5110
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/26/2018
ms.locfileid: "34803047"
---
# <a name="connect-to-dynamics-365-from-powerapps"></a>Verbinding maken met Dynamics 365 vanuit PowerApps
Met PowerApps kunt u snel mobiele apps genereren, aanpassen, delen en uitvoeren, waarbij u slechts weinig of geen code hoeft te gebruiken. Met de Dynamics 365-connector maakt u in slechts enkele minuten handige mobiele apps om te delen met uw hele organisatie.

Als u de stappen in dit onderwerp volgt, maakt u een app waarmee gebruikers contactpersonen in Dynamics 365 kunnen weergeven, toevoegen, verwijderen en bijwerken. Gebruikers kunnen de app uitvoeren [in een browser](../../../user/run-app-browser.md) of [op een mobiel apparaat](../../../user/run-app-client.md), zoals een telefoon.

## <a name="prerequisite"></a>Vereisten
Als u deze zelfstudie wilt volgen, hebt u een Microsoft Office 365-account nodig met een Dynamics 365-abonnement.

## <a name="create-a-connection"></a>Een verbinding maken
1. [Meld u aan bij PowerApps](https://web.powerapps.com/).
2. Klik in het linkernavigatiedeelvenster op **Verbindingen**.
   
    ![Optie Verbinding in menu Bestand](./media/connection-dynamics-crmonline/file-connections.png)
3. Klik in de rechterbovenhoek op **Nieuwe verbinding**.
   
    ![Nieuwe verbinding](./media/connection-dynamics-crmonline/new-connection.png)
4. Klik in de lijst met verbindingen op **Dynamics 365**.
   
    ![Optie Verbinding in menu Bestand](./media/connection-dynamics-crmonline/connection-d365.png)
5. Klik in het dialoogvenster op **Maken**.
   
    ![Verbinding maken](./media/connection-dynamics-crmonline/create-connection.png)
6. Geef in het dialoogvenster **Aanmelden bij uw account** uw referenties voor de (online) Dynamics 365-tenant op.
   
    Er wordt een verbinding gemaakt.

## <a name="generate-an-app-automatically"></a>Automatisch een app genereren
1. [Meld u aan bij PowerApps](https://web.powerapps.com/) en klik linksonder op **Nieuwe app**.
   
    ![Nieuwe app](./media/connection-dynamics-crmonline/new-app.png)
2. Klik onder **Beginnen met uw gegevens** op **Telefoonindeling** op de tegel **Dynamics 365**.
   
    ![Dynamics 365-connector selecteren in PowerApps](./media/connection-dynamics-crmonline/phonelayout.png)
3. Selecteer onder **Verbindingen** de gewenste verbinding en kies een gegevensset die overeenkomt met het exemplaar van Dynamics 365 dat u met de app wilt beheren.
4. Klik onder **Een tabel kiezen** op **Contactpersonen** en klik vervolgens op **Verbinden**.
5. Klik of tik op een pictogram in de rechterbovenhoek van de linkernavigatiebalk om over te schakelen naar de miniatuurweergave.
   
    ![Schakelen tussen weergaven](./media/connection-dynamics-crmonline/toggle-view.png)

PowerApps genereert een app met drie schermen op basis van de contactrecords.

* **BrowseScreen1**. Dit scherm wordt standaard weergegeven wanneer een gebruiker de app opent. In de navigatiebalk aan de linkerkant staat de miniatuur voor dit scherm boven de twee andere schermen.
* **DetailScreen1**. Dit scherm wordt weergegeven wanneer de gebruiker op een item klikt in **BrowseScreen1**.  In de navigatiebalk aan de linkerkant staat de miniatuur voor **DetailScreen1** tussen de twee andere schermen.
* **EditScreen1**. Dit scherm wordt weergegeven wanneer de gebruiker klikt op het pictogram voor het bewerken van een item in **DetailScreen1**. In de navigatiebalk aan de linkerkant staat de miniatuur voor **EditScreen1** onder de twee andere schermen.

U kunt de app uitvoeren in de oorspronkelijke staat, maar we kunnen deze wat handiger maken door het verfijnen van de weergegeven informatie in ieder scherm.

## <a name="customize-browsescreen1"></a>BrowseScreen1 aanpassen
In deze procedure configureert u **BrowseScreen1** voor het weergeven van de voor- en achternaam van elke contactpersoon. De gegevens worden alfabetisch gesorteerd op achternaam en bevatten ook afbeeldingen, in een raster met twee kolommen.

1. Selecteer in **BrowseScreen1** de galerie door op een record te klikken, behalve de eerste record.
   
    ![Indeling selecteren](./media/connection-dynamics-crmonline/select-gallery.png)
2. Klik of tik in het rechterdeelvenster op het tabblad **Gegevens**.
3. Klik in de lijst met indelingen op de indeling waarin afbeeldingen en tekst in twee kolommen worden weergegeven.
   
    Mogelijk moet u omlaag schuiven om de optie te vinden.
   
    ![Indeling selecteren](./media/connection-dynamics-crmonline/select-layout.png)
4. Kopieer de formule en plak deze, terwijl de galerie nog is geselecteerd, in de formulebalk (rechts van de knop **fx**):
   
    `SortByColumns(Search(Filter(Contacts,statuscode=1), TextSearchBox1.Text, "lastname"), "lastname", If(SortDescending1, Descending, Ascending))`
5. Selecteer in het rechterdeelvenster de optie **voornaam** in de bovenste vervolgkeuzelijst en **achternaam** in de middelste vervolgkeuzelijst.
   
    ![Body1 selecteren](./media/connection-dynamics-crmonline/firstname-lastname.png)
6. (Optioneel) klik in het menu **Bestand** op **Opslaan als**, typ een naam voor de app en klik op **Opslaan**.
   
    De app wordt standaard in de cloud opgeslagen. Klik op **Deze computer** om uw app lokaal op te slaan.

## <a name="customize-detailsscreen1-and-editscreen1"></a>DetailsScreen1 en EditScreen1 aanpassen
1. Klik of tik in de linkernavigatiebalk op de middelste miniatuur om **DetailScreen1** te selecteren.
2. Klik in **DetailScreen1** ergens onder de titelbalk om de aanpassingsopties weer te geven in het rechterdeelvenster.
   
    ![Aanpassen formulier weergeven](./media/connection-dynamics-crmonline/show-customization.png)
3. Klik of tik in het rechterdeelvenster op het oogpictogram voor elk veld om het te verbergen.
   
    ![Velden verbergen](./media/connection-dynamics-crmonline/hide-field.png)
4. Klik ergens onder de titelbalk om **Form1** te selecteren.
   
    ![Form1 selecteren](./media/connection-dynamics-crmonline/select-form1.png)
5. Klik in het rechterdeelvenster op het oogpictogram voor elk van deze velden, zodat er op een scherm een afbeelding (mits de tabel er een bevat) en vier andere velden voor elke contactpersoon worden weergegeven:
   
   * **entityimage**
   * **firstname**
   * **lastname**
   * **mobilephone**
   * **emailaddress1**
     
     Het rechterdeelvenster moet eruitzien zoals in deze afbeelding:
     
     ![Form1 selecteren](./media/connection-dynamics-crmonline/show-fields.png)
6. Klik in de linkernavigatiebalk op de onderste miniatuur om **EditScreen1** te selecteren.
7. Herhaal de stappen in deze procedure om **EditScreen1** op dezelfde manier aan te passen als **DetailScreen1**.
8. (Optioneel) Sla de app op.

## <a name="next-steps"></a>Volgende stappen
* Test uw app in de voorbeeldmodus door op **BrowseScreen1** te klikken in de linkernavigatiebalk en vervolgens op F5 te drukken of te klikken op ![Voorbeeldmodus](./media/connection-dynamics-crmonline/runpowerapp.png) rechtsboven.
* [Uw app delen](../share-app.md).
* [Een tweede gegevensbron toevoegen](../add-data-connection.md).

