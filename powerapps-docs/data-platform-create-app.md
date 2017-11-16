---
title: Een app genereren met een Common Data Service-database | Microsoft Docs
description: Genereer een app voor het toevoegen, bijwerken en verwijderen van records.
services: powerapps
documentationcenter: na
author: kfend
manager: kfend
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/06/2016
ms.author: kfend
ms.openlocfilehash: 7fffa909b42dfd23bc4b72d032a524df27d614aa
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="generate-an-app-by-using-a-common-data-service-database"></a>Genereer een app met behulp van een Common Data Service-database
[!VIDEO nb:cid:UUID:6d7aa0a1-cd31-47c6-9a32-93b4e5476ece]


U kunt automatisch een app genereren voor het beheren van gegevens die zijn opgeslagen in Common Data Service. U kunt gegevens beheren in een van de vele standaardentiteiten die zijn ingebouwd in het model of in een aangepaste entiteit die u of iemand anders in uw organisatie heeft gemaakt.

Zie [Entiteiten begrijpen](data-platform-intro.md) als u niet bekend bent met Common Data Service.

In dit onderwerp wordt beschreven hoe u automatisch een app kunt genereren op basis van één enkele entiteit die u opgeeft. Zie [Een volledig nieuwe app bouwen](data-platform-create-app-scratch.md) voor informatie over het bouwen van een app die is gebaseerd op meer dan één entiteit.

Elke app die door Microsoft PowerApps wordt gegenereerd, bestaat standaard uit drie schermen:

* Het bladerscherm toont een subset van een of meer velden, een zoekbalk en een sorteerknop waarmee gebruikers gemakkelijk een bepaalde record kunnen vinden.
* Het detailscherm geeft meer velden of alle velden voor een bepaalde record weer.
* Het bewerkingsscherm bevat UI-elementen waarmee gebruikers een record kunnen maken of bijwerken en hun wijzigingen kunnen opslaan.

**Opmerking**: wanneer u een app genereert op basis van Common Data Service, hoeft u geen verbinding vanuit PowerApps te maken, zoals u dat wel doet voor gegevensbronnen als SharePoint, Dynamics 365 en Salesforce. U hoeft alleen de entiteit op te geven die u in de app wilt weergeven en/of beheren.

## <a name="generate-an-app"></a>Een app genereren
1. Maak een Common Data Service-database. Zie [Create a Common Data Service database (Een Common Data Service-database maken)](create-database.md) voor meer informatie.
2. Klik of tik in PowerApps Studio voor Windows in het menu **File** (aan de linkerkant van het scherm) op **New**.
3. Onder **Start with your data** op de tegel **Common Data Service** klikt of tikt u op **Phone layout**.
4. Klik of tik onder **Choose an entity** op de entiteit **Contact**.
5. Klik of tik op **Connect** om automatisch een app te genereren.
   
    Op dit moment wordt u mogelijk gevraagd of u een inleidende rondleiding wilt volgen. U kunt de rondleiding ook later volgen door op het vraagteken rechtsboven en vervolgens op **Take the intro tour** te klikken of tikken.
6. Klik of tik op een pictogram in de rechterbovenhoek van de linkernavigatiebalk om over te schakelen naar de miniatuurweergave.
   
    ![Schakelen tussen weergaven](./media/data-platform-create-app/toggle-view.png)

## <a name="customize-the-browse-screen"></a>Het bladerscherm aanpassen
1. In het rechterdeelvenster klikt of tikt u op de indeling waarin alleen een kop wordt weergegeven.
   
    ![Een indeling selecteren](./media/data-platform-create-app/choose-gallery-layout.png)
2. Klik of tik onder het zoekvak op het besturingselement **Label** om dat te selecteren.
   
    ![Een label selecteren](./media/data-platform-create-app/select-textbox.png)
3. Selecteer in het rechterdeelvenster **Surname of Given name** in de vervolgkeuzelijst
   
     In het besturingselement **Label** dat u hebt geselecteerd, worden gegevens uit dat veld weergegeven.
4. Selecteer in het bladerscherm de galerie door op een willekeurige naam te klikken of tikken, met uitzondering van de bovenste naam.
   
    Een selectievakje omgeeft de galerie.
   
    ![De galerie selecteren](./media/data-platform-create-app/select-gallery.png)
5. Kopieer de volgende formule door deze te selecteren en vervolgens op Ctrl+C te drukken.
   
    **SortByColumns(Search(Contact, TextSearchBox1.Text, "Name_Surname"), "Name_Surname", If(SortDescending1, Descending, Ascending))**
6. Controleer of de eigenschappenlijst linksboven de optie **Items** bevat.
7. Selecteer de standaardformule in de formulebalk.
   
    ![Standaardwaarde van de eigenschap Items](./media/data-platform-create-app/default-items.png)
8. Druk op Delete om de standaardformule te verwijderen en plak vervolgens de formule die u hebt gekopieerd. De namen in de galerie worden alfabetisch gesorteerd.

## <a name="test-the-browse-screen"></a>Het bladerscherm testen
1. Open de preview-modus door op F5 te drukken of door op het **afspeel**pictogram rechtsboven te klikken of te tikken.
2. Schuif door alle records met behulp van een aanraakscherm of een muiswieltje, of door de galerie aan te wijzen met een muis zodat de schuifbalk wordt weergegeven.
3. Klik of tik een of meer keer op de sorteerknop rechtsboven om de volgorde te wijzigen waarin de namen worden weergegeven.
   
    ![De sorteervolgorde wijzigen](./media/data-platform-create-app/sort-button.png)
4. Typ in het zoekvak een letter om alleen namen weer te geven die deze letter bevatten.
5. Verwijder alle tekst uit het zoekvak en klik of tik op de pijl rechts van de eerste naam in de lijst.
   
    Het detailscherm wordt geopend met meer informatie over de contactpersoon die u hebt geselecteerd.
6. Ga terug naar het ontwerpgebied door op Esc te drukken of door te klikken of tikken op de knop **Sluiten** in de rechterbovenhoek, onder de titelbalk.

## <a name="customize-the-other-screens"></a>De andere schermen aanpassen
1. Klik of tik op de middelste miniatuur in de linkernavigatiebalk als **DetailScreen** niet wordt weergegeven.
2. Klik of tik bovenin **DetailScreen** op **Full name** om opties voor het aanpassen van het formulier in dat scherm weer te geven.
3. Klik of tik in het rechterdeelvenster op de knop met het oog voor **Name_MiddleName** om dat veld te verbergen.
4. Klik of tik in het rechterdeelvenster op de knop met het oog voor **Name_Surname** om dat veld weer te geven.
5. Sleep in het rechterdeelvenster **Name_Surname** naar boven en zet deze neer precies onder **Name_GivenName**.
   
    De wijzigingen worden weergegeven in het **DetailScreen**.
6. Klik of tik in de linkernavigatiebalk op de onderste miniatuur om **EditScreen** weer te geven en herhaal de vorige stappen in deze procedure zodat **EditScreen** overeenkomt met **DetailScreen**.

## <a name="test-the-app"></a>De app testen
1. Klik of tik in de linkernavigatiebalk op de bovenste miniatuur om het bladerscherm te openen.
2. Open de preview-modus door op F5 te drukken of door op het **afspeel**pictogram rechtsboven te klikken of te tikken.
3. Klik of tik in de rechterbovenhoek van het bladerscherm op de knop met het plusteken (**+**) om een record te maken.
4. Voeg tekst toe in de velden **Given name** en **Surname** en klik of tik op het vinkje om de nieuwe record op te slaan en terug te keren naar het bladerscherm.
5. Zoek naar de record die u zojuist hebt gemaakt en klik of tik op de pijl rechts ervan om de record in het detailscherm weer te geven.
6. Klik of tik in de rechterbovenhoek op het potloodpictogram om de record weer te geven in het bewerkingsscherm.
7. Wijzig de gegevens in het veld **Given name** en klik of tik op het vinkje om de wijzigingen op te slaan.
8. Klik of tik in de rechterbovenhoek op het prullenbakpictogram om de record te verwijderen die u hebt gemaakt en bijgewerkt.

## <a name="next-steps"></a>Volgende stappen
[Een volledig nieuwe app maken met behulp van een Common Data Service-database](data-platform-create-app-scratch.md)

