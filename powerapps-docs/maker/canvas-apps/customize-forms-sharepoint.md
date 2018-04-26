---
title: Formulieren aanpassen | Microsoft Docs
description: Geef op welke gegevens u wilt tonen, in welke volgorde en in welke besturingselementen.
documentationcenter: na
author: AFTOwen
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 03/17/2018
ms.author: anneta
ms.openlocfilehash: 98162ce4d291b976c816326efc5d4c6d4d18c870
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
---
# <a name="customize-forms-in-powerapps"></a>Formulieren aanpassen in PowerApps
Pas de besturingselementen **Formulier weergeven** en **Formulier bewerken** zodanig aan dat de belangrijkste gegevens worden getoond, in de meest logische volgorde. Op die manier kunnen gebruikers de gegevens gemakkelijk begrijpen en bijwerken.

Elk formulier bestaat uit een of meer kaarten en op elke kaart staan de gegevens uit een bepaalde kolom in de gegevensbron. Als u de stappen in dit onderwerp volgt, kunt u opgeven welke kaarten in een formulier moeten worden weergegeven en kaarten in een formulier omhoog en omlaag verplaatsen.

Zie [Introduction to PowerApps](getting-started.md) (Inleiding tot PowerApps) als u onbekend bent met PowerApps.

## <a name="prerequisites"></a>Vereisten
[Genereer een app](data-platform-create-app.md) via Common Data Service en [pas vervolgens de galerie in die app aan](customize-layout-sharepoint.md).

## <a name="show-and-hide-cards"></a>Kaarten weergeven en verbergen
1. Meld u aan bij [PowerApps](http://web.powerapps.com).

    ![Startpagina van de PowerApps-site](./media/customize-forms-sharepoint/sign-in.png)


1. Open de app die u hebt gegenereerd en aangepast.

1. In de linkernavigatiebalk typt of plakt u **D** in de zoekbalk om de lijst elementen te filteren. Klik of tik vervolgens op **DetailForm1** om deze optie te selecteren.

    ![Scherm met details selecteren](./media/customize-forms-sharepoint/select-detailform.png)

1. Klik of tik in het rechterdeelvenster op **Accounts** om het deelvenster **Gegevens** te tonen.

    ![Gegevensdeelvenster weergeven](./media/customize-forms-sharepoint/show-data-pane.png)

1. In het deelvenster **Gegevens** schakelt u de selectievakjes bij **Primaire contactpersoon**, **Beschrijving** en **Adres 1: straat 2** uit om die velden te verbergen.

    ![Lijst velden](./media/customize-forms-sharepoint/hide-fields.png)

1.  In het deelvenster **Gegevens** schakelt u het selectievakje bij **Adres 1: postcode** in om dat veld weer te geven.

    ![Lijst velden](./media/customize-forms-sharepoint/show-field.png)

## <a name="reorder-the-cards"></a>De volgorde van de kaarten wijzigen
1. In het deelvenster **Gegevens** sleept u het veld **Accountnaam** naar de bovenkant van de lijst met velden.

    ![Kaart verplaatsen](./media/customize-forms-sharepoint/move-card.png)

    Op de kaarten in **DetailForm1** wordt dezelfde wijziging weergegeven.

    ![Opnieuw gerangschikte kaarten](./media/customize-forms-sharepoint/reordered-card.png)

1. Rangschik de kaarten zodat ze deze volgorde hebben:

    - Accountnaam
    - Adres 1: straat 1
    - Adres 1: stad
    - Adres 1: postcode
    - Aantal werknemers
    - Jaarlijkse omzet

1. In de linkernavigatiebalk typt of plakt u **Ed** in de zoekbalk. Klik of tik vervolgens op **EditForm1** om deze optie te selecteren.

1. Herhaal de stappen uit de vorige procedure en deze zodat de velden in **EditForm1** overeenkomen met die in **DetailForm1**.

## <a name="run-the-app"></a>De app uitvoeren
1. In de navigatiebalk links typt of plakt u **Br** om de lijst te filteren. Klik of tik vervolgens op **BrowseScreen1** om deze optie te selecteren.

2. Open de previewmodus door op F5 te drukken (of door het pictogram **Preview** in de rechterbovenhoek te selecteren).

    ![Pictogram Preview](./media/customize-forms-sharepoint/open-preview.png)

3. Klik of tik in de rechterbovenhoek op het pictogram met het plusteken om een record toe te voegen in **EditScreen1**.

    ![Record toevoegen](./media/customize-forms-sharepoint/add-record.png)

4. Voeg de gewenste gegevens toe en klik of tik op het pictogram met het selectievakje in de rechterbovenhoek om uw wijzigingen op te slaan en terug te gaan naar **BrowseScreen1**.

    ![Record opslaan](./media/customize-forms-sharepoint/save-record.png)

5. Klik of tik op de pijl voor het item dat u zojuist hebt gemaakt om de details over dat item weer te geven in **DetailScreen1**.  

    ![Pijl-rechts](./media/customize-forms-sharepoint/right-arrow.png)

6. Klik of tik in de rechterbovenhoek op het pictogram voor bewerken om de record bij te werken in **EditScreen1**.

    ![Record bewerken](./media/customize-forms-sharepoint/edit-record.png)

7. Wijzig de informatie in een of meer velden en klik of tik op het selectievakje in de rechterbovenhoek om de wijzigingen in de SharePoint-lijst op te slaan en terug te gaan naar **DetailScreen1**.  

    ![Wijzigingen opslaan](./media/customize-forms-sharepoint/save-record.png)

8. Klik of tik op het prullenbakpictogram in de rechterbovenhoek om de record te verwijderen die u zojuist hebt bijgewerkt en terug te gaan naar **BrowseScreen1**.

    ![Record verwijderen](./media/customize-forms-sharepoint/delete-record.png)

9. Sluit de Preview-modus door op Esc te drukken (of klik of tik op het pictogram Sluiten bij de linkerbovenhoek).

## <a name="next-steps"></a>Volgende stappen
- [Sla uw app op en publiceer deze](save-publish-app.md).
- [Pas een kaart aan](customize-card.md) in uw app.
