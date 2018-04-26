---
title: Een volledig nieuwe app maken met een Common Data Service-database | Microsoft Docs
description: Een app maken voor het toevoegen, bijwerken en verwijderen van records.
documentationcenter: na
author: AFTOwen
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 03/18/2018
ms.author: anneta
ms.openlocfilehash: a0aab890e52b49bb0cac382338a8fa02eec736a0
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
---
# <a name="create-an-app-from-scratch-using-a-common-data-service-database"></a>Een volledig nieuwe app maken met een Common Data Service-database
Een app bouwen voor het beheren van gegevens die zijn opgeslagen in de Common Data Service, met (ingebouwde) standaardentiteiten, (door uw organisatie gemaakte) aangepaste entiteiten, of beide.

Wanneer u een app bouwt op basis van de Common Data Service, hoeft u geen verbinding vanuit PowerApps te maken, zoals u dat wel doet met gegevensbronnen als SharePoint, Dynamics 365 en Salesforce. U hoeft alleen de entiteiten op te geven die u wilt weergeven, beheren of gebruiken voor beide activiteiten in de app.

## <a name="prerequisites"></a>Vereisten
- Maak uzelf, voordat u een volledig nieuwe app maakt, de basisprincipes van PowerApps eigen door [een app te genereren](data-platform-create-app.md) en vervolgens de [galerie](customize-layout-sharepoint.md), [formulieren](customize-forms-sharepoint.md), en [kaarten](customize-card.md) van die app aan te passen.
- [Schakel over naar een omgeving](working-with-environments.md) waarin een database is gemaakt met voorbeeldgegevens. Als u over een juiste licentie beschikt, kunt u [ een omgeving maken](../../administrator/create-environment.md) die voldoet aan deze vereiste.

## <a name="open-a-blank-app"></a>Een lege app openen
1. Meld u aan bij [PowerApps](http://web.powerapps.com).

    ![PowerApps-startpagina](./media/data-platform-create-app-scratch/sign-in.png)

1. Beweeg onder **Apps zoals deze maken** de muisaanwijzer over de tegel **Beginnen met een lege app**, klik of tik op het telefoonpictogram en klik of tik op **Deze app maken**.

    ![Lege-apptegel](./media/data-platform-create-app-scratch/blank-app.png)

    U kunt een volledig nieuwe app ontwerpen voor telefoons of andere apparaten (zoals tablets). In dit onderwerp wordt de nadruk gelegd op het ontwerpen van een app voor telefoons.

## <a name="specify-an-entity"></a>Een entiteit opgeven
1. Klik of tik in het midden van het scherm op **verbinding maken met gegevens** en klik of tik vervolgens in het deelvenster **Gegevens** op de verbinding **Common Data Service**.

1. Typ of plak in het zoekvak de eerste letters van **Accounts** om de lijst met entiteiten te filteren, schakel het selectievakje **Accounts** in en klik of tik daarna op **Verbinding maken**.

    ![De entiteit Accounts opgeven](./media/data-platform-create-app-scratch/cds-connect.png)

1. Klik of tik op het pictogram voor sluiten in de rechterbovenhoek om het deelvenster **Gegevens** te sluiten.

## <a name="add-a-list-screen"></a>Een lijstscherm toevoegen
1. Klik of tik in het tabblad **Start** op de pijl omlaag voor **Nieuw scherm** en vervolgens op **Lijstscherm**.

    ![Een lijstscherm toevoegen](./media/data-platform-create-app-scratch/list-screen.png)

1. Klik of tik in de linkernavigatiebalk op **TemplateGalleryList1** om dit item te selecteren en stel de waarde van de eigenschap **Items** in op deze formule:

    `SortByColumns(Search(Accounts, TextSearchBox1.Text, "name"), "name", If(SortDescending1, SortOrder.Descending, SortOrder.Ascending))`

    Deze formule geeft aan dat:

    - De galerie moet gegevens weergeven van de entiteit **Accounts**.
    - De gegevens moeten worden gesorteerd in oplopende volgorde, totdat de gebruiker op de knop voor sorteren klikt of tikt om de sorteervolgorde om te schakelen.
    - Als een gebruiker een of meer tekens in de zoekbalk typt of plakt, worden in de lijst alleen accounts weergegeven waarvoor het naamveld de tekens bevat die de gebruiker heeft opgegeven.

    U kunt [deze en vele andere functies](formula-reference.md) gebruiken om op te geven hoe uw app wordt weergegeven en functioneert.

    ![De eigenschap Items van de galerie instellen](./media/data-platform-create-app-scratch/gallery-items.png)

1. Stel de indeling van de galerie zo in dat alleen de naam van elk account wordt weergegeven en configureer de titelbalk zodanig dat het woord **Bladeren** wordt weergegeven, zoals in het item [Een galerie aanpassen](customize-layout-sharepoint.md) wordt beschreven.

    ![Bladerscherm](./media/data-platform-create-app-scratch/final-browse.png)

1. Beweeg in de linkernavigatiebalk de muisaanwijzer over **Scherm1**, klik of tik op het beletselteken (...) en klik of tik vervolgens op **Verwijderen**.

1. Beweeg in de linkernavigatiebalk de muisaanwijzer over **Scherm2**, klik of tik op het beletselteken (...) en klik of tik vervolgens op **Naam wijzigen**.

1. Typ of plak **BrowseScreen** en wijzig daarna de naam van de galerie in dit scherm in **BrowseGallery**.

    ![De naam wijzigen van het scherm Bladeren, galerie](./media/data-platform-create-app-scratch/rename-browse.png)

## <a name="add-a-form-screen"></a>Een formulierscherm toevoegen
1. Herhaal de eerste stap van de vorige procedure, maar voeg hierbij een **formulierscherm** toe in plaats van een **lijstscherm**.

1. Stel de eigenschap **DataSource** van het formulier in op **Accounts** en de bijbehorende eigenschap **Item** op **BrowseGallery.Selected**, zoals wordt weergegeven op het **tabblad Geavanceerd** van het rechter deelvenster.

    ![De eigenschap Datasource en Item van het formulier instellen](./media/data-platform-create-app-scratch/form-datasource.png)

1. Klik of tik in het tabblad **Eigenschappen** van het rechterdeelvenster op **Accounts** om het deelvenster **Gegevens** te openen en schakel vervolgens de selectievakjes in voor deze velden:

    - Accountnaam
    - Adres 1: straat 1
    - Adres 1: stad
    - Adres 1: postcode
    - Aantal werknemers
    - Jaarlijkse omzet

1. Stel de eigenschap **Tekst** in van de titelbalk om **Maken/Bewerken** weer te geven.

    Uw wijzigingen worden in het scherm weergegeven.

    ![De eigenschap Datasource en Item van het formulier instellen](./media/data-platform-create-app-scratch/field-list.png)

1. Wijzig de naam van dit scherm **FormScreen**.

## <a name="configure-icons"></a>Pictogrammen Configureren
1. Klik of tik in het **BrowseScreen** op het cirkelvormige pictogram aan de bovenkant van het scherm en stel de eigenschap **OnSelect** in op deze formule:<br>
`Refresh(Accounts)`

    ![Pictogram Vernieuwen](./media/data-platform-create-app-scratch/refresh-icon.png)

1. Klik of tik op het plus-pictogram en stel de bijbehorende eigenschap **OnSelect** in op deze formule:<br>
`NewForm(EditForm1); Navigate(FormScreen, ScreenTransition.None)`

    ![Pictogram Toevoegen](./media/data-platform-create-app-scratch/plus-icon.png)

1. Klik of tik op de eerste pijl naar rechts en stel de bijbehorende eigenschap **OnSelect** in op deze formule:<br>
`EditForm(EditForm1); Navigate(FormScreen, ScreenTransition.None)`

    ![Het pictogram Volgende](./media/data-platform-create-app-scratch/next-icon.png)

1. Klik of tik in **FormScreen** op het pictogram Annuleren en stel de bijbehorende eigenschap **OnSelect** in op deze formule:<br>
`ResetForm(EditForm1);Navigate(BrowseScreen, ScreenTransition.None)`

    ![Pictogram Annuleren](./media/data-platform-create-app-scratch/cancel-icon.png)

1. Klik of tik op het vinkje en stel de bijbehorende eigenschap **OnSelect** in op deze formule:<br>
`SubmitForm(EditForm1); Navigate(BrowseScreen, ScreenTransition.None)`

    ![Pictogram Vinkje](./media/data-platform-create-app-scratch/checkmark-icon.png)

1. Klik of tik in het tabblad **Invoegen** op **Pictogrammen** en vervolgens op het pictogram **Prullenbak**.

1. Stel de eigenschap **Kleur** van het pictogram **Prullenbak** in op **Wit** en stel de bijbehorende eigenschap **OnSelect** in op deze formule:<br>
`Remove(Accounts, BrowseGallery.Selected); Navigate(BrowseScreen, ScreenTransition.None)`

    ![Pictogram Prullenbak](./media/data-platform-create-app-scratch/trash-icon.png)

## <a name="test-the-app"></a>De app testen
1. Selecteer in het linker navigatiedeelvenster **BrowseScreen** en open vervolgens de Preview-modus door op F5 te drukken (of door te klikken of tikken op het pictogram Afspelen rechtsboven).

    ![Preview openen](./media/data-platform-create-app-scratch/open-preview.png)

1. Schakel in de lijst tussen de oplopende en aflopende sorteervolgorde en filter de lijst op bepaalde tekens in accountnamen.

1. Voeg een account toe, bewerk het account dat u hebt toegevoegd, begin met het account bij te werken, maar annuleer uw wijzigingen en verwijder vervolgens het account.

## <a name="next-steps"></a>Volgende stappen
[Open een of meer voorbeeldapps](open-and-run-a-sample-app.md) en verken de verschillende typen apps die u kunt maken.

