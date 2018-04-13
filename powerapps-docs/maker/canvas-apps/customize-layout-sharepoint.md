---
title: Zelfstudie voor het aanpassen van een galerie | Microsoft Docs
description: In deze zelfstudie past u het standaardscherm voor bladeren aan, met inbegrip van de galerie, van een app die in PowerApps is gegenereerd.
services: ''
suite: powerapps
documentationcenter: na
author: AFTOwen
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/11/2018
ms.author: anneta
ms.openlocfilehash: 30ec6be11b40e01dddfe09cf0ac8af0ed3a8a437
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2018
---
# <a name="tutorial-customize-a-gallery-in-powerapps"></a>Zelfstudie: Een galerie aanpassen in PowerApps
In deze zelfstudie past u het standaardscherm voor bladeren aan, met inbegrip van de galerie, van een app die in PowerApps is gegenereerd. U kunt gegevens beheren met behulp van de standaardapp zonder deze aan te passen, maar deze is veel krachtiger en gebruiksvriendelijker als u deze wijzigingen aanbrengt:

> [!div class="checklist"]
> * De indeling wijzigen
> * De gegevens wijzigen die worden weergegeven
> * De kolommen instellen voor filteren en sorteren
> * Filteren en sorteren testen
> * De titel wijzigen
> * Een schuifbalk weergeven

Deze zelfstudie begint met een app die is gegenereerd op basis van [Common Data Service for Apps](../common-data-service/data-platform-intro.md), maar dezelfde concepten worden toegepast op apps die zijn gegenereerd op basis van SharePoint, Excel en andere gegevensbronnen. 

Als u geen licentie voor PowerApps hebt, kunt u zich [gratis registreren](../signup-for-powerapps.md).

## <a name="prerequisites"></a>Vereisten
Voordat u begint met deze zelfstudie, moet u [een app genereren](data-platform-create-app.md) op basis van Common Data Service for Apps.

## <a name="open-the-generated-app"></a>De gegenereerde app openen
1. Meld u aan bij [PowerApps](https://web.powerapps.com) en klik of tik vervolgens bij de linkerrand op **Apps**.

    ![PowerApps-startpagina](./media/customize-layout-sharepoint/sign-in.png)

1. Zoek de app op die u hebt gegenereerd en klik of tik op het bijbehorende pictogram van het beletselteken (**...** ) bij de rechterrand.

    ![Lijst met apps](./media/customize-layout-sharepoint/open-for-edit.png)

1. Klik of tik in het menu dat verschijnt op de optie voor het bewerken van de app. 

## <a name="customize-the-gallery"></a>De galerie aanpassen
1. Klik of tik in het scherm voor bladeren op een willekeurig item, met uitzondering van het eerste item in de lijst van accounts.

    Met deze stap selecteert u het besturingselement **Galerie** waarin de lijst van accounts wordt weergegeven.

    ![Geselecteerde galerie](./media/customize-layout-sharepoint/select-gallery.png)

1. Klik of tik in het rechterdeelvenster op **Accounts** aan de rechterkant van het label **Gegevens**.

    ![Open het deelvenster **Gegevens**](./media/customize-layout-sharepoint/open-data-pane.png)

1. Klik of tik in het deelvenster **Gegevens** op de pijl omlaag om de lijst met opties onder **Indeling** te openen.

    ![Indelingsopties weergeven](./media/customize-layout-sharepoint/show-layouts.png)

1. Klik of tik in de lijst met opties op de optie die alleen een titel toont.

    ![Indeling met alleen titel selecteren](./media/customize-layout-sharepoint/choose-layout.png)

1. Klik of tik in het deelvenster **Gegevens** op de pijl omlaag om de lijst met opties voor de titel te openen.

    ![Indeling met alleen titel selecteren](./media/customize-layout-sharepoint/show-title-options.png)

1. Klik of tik in de lijst met opties op **Naam** om die gegevens weer te geven in het besturingselement **Galerie**.

    ![Definitieve galerie](./media/customize-layout-sharepoint/final-gallery.png)


## <a name="set-the-sort-and-search-columns"></a>Sorteer- en zoekkolommen instellen
1. Selecteer het besturingselement **Galerie** zoals in de vorige sectie wordt beschreven.

    ![Galerie selecteren](./media/customize-layout-sharepoint/select-gallery-title.png)

2. Controleer of de eigenschappenlijst linksboven de optie **Items** bevat.

    ![Eigenschap Items](./media/customize-layout-sharepoint/items-property.png)

    De waarde van deze eigenschap wordt weergegeven in de formulebalk. Deze bepaalt niet alleen de gegevensbron van de galerie, maar ook de filter- en sorteerkolommen.

1. Vervang in de formulebalk beide instanties van **emailaddress1** voor **Naam** en behoud de dubbele aanhalingstekens rondom elke instantie.

    De formule moet overeenkomen met dit voorbeeld:

    ![Formule voor de eigenschap Items](./media/customize-layout-sharepoint/items-value.png)

    De eerste instantie van **Naam** geeft aan dat de gebruiker de lijst zo kan filteren dat deze alleen records toont waarvan de accountnaam tekst bevat die de gebruiker in de zoekbalk heeft ingevoerd. De tweede instantie van **Naam** geeft aan dat de gebruiker de lijst alfabetisch op naam kan sorteren. Zie de [naslaginformatie over formules](formula-reference.md) voor meer informatie over deze en andere functies.

## <a name="test-sorting-and-searching"></a>Sorteren en zoeken testen
1. Open de Preview-modus door op F5 te drukken (of klik of tik op het afspeelpictogram rechtsboven).

    ![Preview-modus openen](./media/customize-layout-sharepoint/open-preview.png)

1. Klik of tik in de hoek rechtsboven van het scherm voor bladeren een of meer keer op het sorteerpictogram om de alfabetische sorteervolgorde te wijzigen in oplopend of aflopend.

    ![Het sorteerpictogram testen](./media/customize-layout-sharepoint/sort-button.png)

1. Typ in het zoekvak **k** om alleen accounts weer te geven waarvan de naam de letter bevat die u hebt getypt.

    ![De zoekbalk testen](./media/customize-layout-sharepoint/test-filter.png)

1. Sluit de Preview-modus door op F5 te drukken (of klik of tik op het pictogram voor sluiten in de rechterbovenhoek, *onder* de titelbalk voor PowerApps).

## <a name="change-the-title-of-the-screen"></a>De schermtitel wijzigen
1. Klik of tik op de schermtitel om die te selecteren.

    ![Schermtitel selecteren](./media/customize-layout-sharepoint/select-title.png)

1. Controleer of in de eigenschappenlijst **Text** wordt weergegeven en typ vervolgens **Bladeren** tussen dubbele aanhalingstekens in de formulebalk.

    ![Schermtitel bijwerken](./media/customize-layout-sharepoint/change-screen-title.png)

    De wijziging wordt in het scherm weergegeven.

    ![Nieuwe schermtitel](./media/customize-layout-sharepoint/new-screen-title.png)

## <a name="show-a-scroll-bar"></a>Een schuifbalk weergeven
Als uw gebruikers mogelijk niet over een aanraakscherm of muiswiel beschikken, configureert u het besturingselement **Galerie** om een schuifbalk weer te geven wanneer de gebruiker de muisaanwijzer erover beweegt. Op die manier kunnen gebruikers alle accounts weergeven, zelfs als het scherm deze niet in één keer kan weergegeven.

1. Selecteer het besturingselement **Galerie** zoals in de eerste procedure wordt beschreven.

    ![Galerie selecteren](./media/customize-layout-sharepoint/select-gallery-sorted.png)

1. Klik of tik in het tabblad **Galerie** op **Schuifbalk weergeven** en bevestig dat de waarde van deze eigenschap is gewijzigd in **true**. 

    ![Schuifbalk weergeven](./media/customize-layout-sharepoint/show-scrollbar.png)

## <a name="next-steps"></a>Volgende stappen
In deze zelfstudie hebt u het besturingselement **Galerie** en de titel aangepast van het standaardscherm voor bladeren van een gegenereerde app. U kunt ook de standaardschermen aanpassen om details weer te geven en voor het maken of bijwerken van accounts. Deze schermen bevatten de besturingselementen **Weergaveformulier** en **Formulier bewerken** waarin u (bijvoorbeeld) wijzigingen kunt aanbrengen in de typen en in de volgorde van de gegevens die worden weergegeven.

> [!div class="nextstepaction"]
> [Formulieren aanpassen](customize-forms-sharepoint.md)