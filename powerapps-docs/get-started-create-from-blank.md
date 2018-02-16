---
title: Een volledig nieuwe app maken | Microsoft Docs
description: Een app volledig zelf maken door elk UI-element en het gedrag te configureren voor het beheren van de dagelijkse gegevens van uw bedrijf.
services: 
suite: powerapps
documentationcenter: na
author: karthik-1
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
ms.openlocfilehash: d530fb5f77f00cb37322383a3817e9c38533ca1d
ms.sourcegitcommit: e827813cd898ca9a1046b5952ea5e32ce2989a65
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/14/2018
---
# <a name="create-an-app-from-scratch"></a>Een volledig nieuwe app maken
Maak een volledig nieuwe app met een van de vele gegevensbronnen, en voeg later meer bronnen toe indien nodig. Bepaal het uiterlijk en gedrag van elk UI-element om de resultaten te optimaliseren voor uw specifieke doelstellingen en werkstroom. Deze benadering kost veel meer tijd dan [automatisch een app genereren](get-started-create-from-data.md), maar ervaren app-makers kunnen zo de beste app voor hun wensen maken.

> [!NOTE]
> Dit onderwerp is geschreven voor PowerApps Studio voor Windows, maar de stappen zijn vergelijkbaar als u werkt met [PowerApps in een browser](create-app-browser.md).

Wanneer u deze zelfstudie volgt, maakt u een app met twee schermen. In een scherm kunnen gebruikers bladeren door een set records:

![Scherm waarin een gebruiker kan bladeren door een gegevensset](./media/get-started-create-from-blank/first-screen-final.png)

In het andere scherm kunnen gebruikers een record maken, een of meer velden in een record bijwerken of een hele record verwijderen:

![Scherm waarin een gebruiker gegevens kan toevoegen of bijwerken](./media/get-started-create-from-blank/changescreen-final.png)

## <a name="prerequisites"></a>Vereisten
In deze zelfstudie kunt u alleen de algemene concepten doorlezen, of u kunt de zelfstudie precies volgen door de stappen te voltooien.

1. Kopieer deze gegevens en plak ze in een Excel-bestand.

   | Start Day | Start Time | Volunteer 1 | Volunteer 2 |
   | --- | --- | --- | --- |
   | Saturday |10am-noon |Vasquez |Kumashiro |
   | Saturday |noon-2pm |Ice |Singhal |
   | Saturday |2pm-4-pm |Myk |Mueller |
   | Sunday |10am-noon |Li |Adams |
   | Sunday |10am-noon |Singh |Morgan |
   | Sunday |10am-noon |Batye |Nguyen |

2. Maak deze gegevens op als tabel met de naam **Schedule**, zodat de gegevens kunnen worden geparseerd door PowerApps.

    Zie [Een Excel-tabel maken in een werkblad](https://support.office.com/article/Create-an-Excel-table-in-a-worksheet-E81AA349-B006-4F8A-9806-5AF9DF0AC664) voor meer informatie.

3. Sla het bestand op onder de naam **eventsignup.xls** en upload het naar een [cloudopslagaccount](connections/cloud-storage-blob-connections.md), zoals OneDrive.

4. Als PowerApps nieuw voor u is:

   * Informatie over het [toevoegen van een besturingselement en het instellen van de eigenschappen](add-configure-controls.md), die het uiterlijk en gedrag van het besturingselement bepalen.
   * Informatie over het [toevoegen van een scherm en wijzigen van de naam](add-screen-context-variables.md).

## <a name="create-a-blank-app-and-connect-to-data"></a>Een lege app maken en verbinding maken met gegevens
1. Klik of tik in PowerApps Studio op **Nieuw** in het menu **Bestand** (aan de linkerkant van het scherm).

    ![Optie Nieuw in het menu Bestand](./media/get-started-create-from-blank/file-new.png)

2. Klik of tik onder **Lege app** op **Telefoonindeling**.

    ![Optie voor het maken van een app op basis van gegevens](./media/get-started-create-from-blank/create-from-blank.png)

3. Volg wanneer u daarom wordt gevraagd de rondleiding, om te begrijpen wat de hoofdgebieden van PowerApps zijn (of klik of tik op **Skip**).

    ![Korte rondleiding](./media/get-started-create-from-blank/quick-tour.png)

    U kunt de rondleiding altijd later nog volgen door eerst op het vraagtekenpictogram in de rechterbovenhoek en vervolgens op **Take the intro tour** te klikken of tikken.

4. Klik of tik op een pictogram in de rechterbovenhoek van de linkernavigatiebalk om over te schakelen naar de miniatuurweergave.

    ![Schakelen tussen weergaven](./media/get-started-create-from-blank/toggle-view.png)

5. Klik of tik in het rechterdeelvenster op **Gegevensbron toevoegen**.

    ![Gegevensbron toevoegen](./media/get-started-create-from-blank/add-data-source.png)

6. Voer een van de volgende stappen uit:

   * Als u al een verbinding met uw cloudopslagaccount hebt, klikt of tikt u daarop.
   * Als u nog geen verbinding hebt met uw cloudopslagaccount, klikt of tikt u op **Add connection**, klikt of tikt u op uw accounttype, klikt of tikt u op **Connect** en geeft u vervolgens (wanneer u daarom wordt gevraagd) uw referenties op.

7. Klik of tik onder **Choose an Excel file** op **eventsignup.xlsx**.

    ![Het Excel-bestand opgeven dat u wilt gebruiken](./media/get-started-create-from-blank/select-excel-file.png)

8. Selecteer onder **Choose a table** het selectievakje **Schedule** en klik of tik op **Connect**.

    ![De Excel-tabel opgeven die u wilt gebruiken](./media/get-started-create-from-blank/select-table.png)

    Op het tabblad **Data sources** in het rechter deelvenster worden de gegevensbronnen weergegeven die u hebt toegevoegd aan uw app.

    ![Verbonden gegevensbronnen weergeven](./media/get-started-create-from-blank/data-connect.png)

    Voor deze zelfstudie is slechts één gegevensbron nodig, maar u kunt er later meer toevoegen.

## <a name="show-the-data"></a>Gegevens weergeven
1. Ga naar het tabblad **Start** en klik of tik op **Nieuw scherm** en vervolgens op **Lijstscherm**.

    ![Een indeling toevoegen met elementen voor een koptekst, ondertitel en hoofdtekst](./media/get-started-create-from-blank/add-gallery.png)

    Er wordt een scherm toegevoegd met verschillende standaardbesturingselementen, zoals een zoekvak en een besturingselement **[Galerie](controls/control-gallery.md)**. De galerie vult het volledige scherm onder het zoekvak.

2. Klik op of tik op een willekeurige plaats in de galerie (behalve op een pijl), bijvoorbeeld vlak onder het zoekvak.

    ![Galerie selecteren](./media/get-started-create-from-blank/select-gallery.png)

3. Open in het rechterdeelvenster de lijst **Indelingen** en klik of tik vervolgens op de optie voor een titel, een ondertitel en hoofdtekst.

    ![Galerie selecteren](./media/get-started-create-from-blank/select-layout.png)

4. Klik of tik in de lijst met eigenschappen op **[Items](controls/properties-core.md)**, kopieer deze formule en plak die in de formulebalk:

    **SortByColumns(Search(Schedule, TextSearchBox1.Text, "Volunteer_x0020_1"), "Volunteer_x0020_1", If(SortDescending1, SortOrder.Descending, SortOrder.Ascending))**

    Als u niet zeker weet waar u de eigenschappenlijst vindt, raadpleegt u [Besturingselementen toevoegen en configureren](add-configure-controls.md).

    > [!NOTE]
> Kolomnamen met spaties in gegevensbronnen van Excel of SharePoint worden in PowerApps vervangen door **‘\_x0020\_’**. In dit voorbeeld wordt de kolom **'Volunteer 1'** in een formule weergegeven als **'Volunteer_x0020_1'**.

    Deze galerie laat de gegevens uit de tabel **Schedule** zien.

    ![De standaardweergave van de Schedule-gegevens in de galerie](./media/get-started-create-from-blank/show-data-default.png)

    Met het zoekvak kan een filter worden toegepast op de galerie, op basis van de tekst die de gebruiker typt. Als een gebruiker ten minste één letter in het zoekvak typt, geeft de galerie alleen de records weer waarin het veld **Volunteer 1** de tekst bevat die de gebruiker heeft getypt.

    Met de sorteerknop kunnen de records worden gesorteerd op basis van de gegevens in de kolom **Volunteer 1**. Wanneer een gebruiker op deze knop klikt of tikt, verandert de sorteervolgorde van oplopend naar aflopend of omgekeerd.

    Deze formule bevat de functies **Sort**, **If**, **IsBlank**, **Filter** en **Text**. Voor meer informatie over deze en andere functies raadpleegt u de [naslaginformatie over formules](formula-reference.md)

5. Typ een **i** in het zoekvak en klik of tik eenmaal (of een oneven aantal malen) op de knop Sorteren.

    De resultaten worden weergegeven in de galerie.

    ![De galerie sorteren en filteren](./media/get-started-create-from-blank/sort-filter.png)

    Meer informatie over **[Sorteren](functions/function-sort.md)**, **[Filteren](functions/function-filter-lookup.md)** en [andere functies](formula-reference.md)

6. Selecteer het besturingselement **[Label](controls/control-text-box.md)** boven aan het scherm door erop te klikken of tikken.

    ![Titelbalk selecteren](./media/get-started-create-from-blank/select-title-bar.png)

7. Klik of tik in de lijst met eigenschappen op **[Text](controls/properties-core.md)**, kopieer deze tekst en plak die in de formulebalk:<br>
   **"Records weergeven"**

    ![Titelbalk wijzigen](./media/get-started-create-from-blank/change-title-bar.png)

## <a name="create-the-changescreen-and-its-banner"></a>Het ChangeScreen en de banner maken
1. Verwijder **Screen1** en wijzig de naam van **Screen2** in **ViewScreen**.

    ![Naam van scherm wijzigen](./media/get-started-create-from-blank/rename-screen.png)

2. Voeg een scherm toe en noem het **ChangeScreen**.

    ![Scherm toevoegen en de naam wijzigen](./media/get-started-create-from-blank/add-screen.png)

3. Ga naar het tabblad **Invoegen** en klik of tik op **Tekst** en vervolgens op **[Label](controls/control-text-box.md)**.

4. Configureer het besturingselement **Label** dat u zojuist hebt toegevoegd:

   * Stel de eigenschap **Text** in op deze formule:
     <br>**"Record wijzigen"**

   * Stel de eigenschap **Fill** in op deze formule:
     <br>**RGBA(62, 96, 170, 1)**.

   * Stel de eigenschap **Color** in op deze formule:
     <br>**RGBA(255, 255, 255, 1)**

   * Stel de eigenschap **Align** in op **Center**.
   * Stel de eigenschap **X** in op **0**.

   * Stel de eigenschap **Width** in op **640**.
     Uw wijzigingen wordt toegepast op het besturingselement **Label**.

     ![ChangeScreen met banner](./media/get-started-create-from-blank/change-screen-blank.png)

## <a name="add-and-configure-a-form"></a>Een formulier toevoegen en configureren
1. Klik of tik op het tabblad **Invoegen** op **Tekst** en klik of tik vervolgens op **Tekstvak**.

2. Verplaats het formulier en wijzig de grootte zodat het vrijwel het gehele scherm vult.

    ![Een formulier toevoegen](./media/get-started-create-from-blank/add-form.png)

    Het formulier heet standaard **Form1**, tenzij u al eerder een formulier hebt toegevoegd en weer verwijderd. In dat gevel wijzigt u de naam van het formulier in **Form1**.

3. Stel de eigenschap **[DataSource](controls/control-form-detail.md)** van **Form1** in op **Schedule**.

4. Stel de eigenschap **Item** van **Form1** in op deze expressie:
   <br>**BrowseGallery1.Selected**

5. Klik of tik in het rechterdeelvenster op het selectievakje voor elk veld om het weer te geven.

    ![Velden weergeven in formulier](./media/get-started-create-from-blank/schedule-checkbox.png)

6. Klik of tik onder aan het scherm op **Een aangepaste kaart toevoegen**.

    ![Een aangepaste kaart toevoegen](./media/get-started-create-from-blank/add-custom-card.png)

7. Voeg een besturingselement **[Label](controls/control-text-box.md)** toe aan de nieuwe kaart.

8. Stel de eigenschap **[AutoHeight](controls/control-text-box.md)** van het nieuwe besturingselement in op **true** en de eigenschap **[Text](controls/properties-core.md)** op deze formule:
   <br>**Form1.Error**

    In het label worden eventuele fouten in het formulier weergegeven.

9. Klik of tik in de linkernavigatiebalk op de bovenste miniatuur om **ChangeScreen** te selecteren.

10. Klik of tik op het tabblad **Invoegen** op **Pictogrammen**, klik of tik op de optie om een **Pijl-terug** toe te voegen en verplaats de pijl naar de linkerbenedenhoek van het scherm.

11. Stel de eigenschap **[OnSelect](controls/properties-core.md)** van de pijl in op deze formule:

     **ResetForm(Form1);Navigate(ViewScreen,ScreenTransition.None)**

      Wanneer de gebruiker op de pijl klikt of tikt, opent de functie **[Navigate](functions/function-navigate.md)** het **ViewScreen**.

12. Voeg een besturingselement **[Button](controls/control-button.md)** toe onder het formulier en stel de eigenschap **[Text](controls/properties-core.md)** van de knop in op **”Save”**.

     ![Een knop Save toevoegen](./media/get-started-create-from-blank/add-save-button.png)

13. Stel de eigenschap **[OnSelect](controls/properties-core.md)** van deze knop in op deze formule:

    **SubmitForm(Form1); If(Form1.ErrorKind = ErrorKind.None, Navigate(ViewScreen, ScreenTransition.None))**

    Wanneer de gebruiker op de knop klikt of tikt, slaat de functie **[SubmitForm](functions/function-form.md)** alle wijzigingen in de gegevensbron op en wordt het **ViewScreen** opnieuw weergegeven.

14. Voeg onderaan het scherm nog een knop toe, stel de eigenschap **[Text](controls/properties-core.md)** in op **”Remove”** en stel de eigenschap **[OnSelect](controls/properties-core.md)** in op deze formule:

    **Remove(Schedule,BrowseGallery1.Selected);<br>If(IsEmpty(Errors(Schedule)),Navigate(ViewScreen,ScreenTransition.None))**

    Wanneer de gebruiker op de knop klikt of tikt, verwijdert de functie **[Remove](functions/function-remove-removeif.md)** de record en wordt het **ViewScreen** opnieuw weergegeven.

15. Stel de eigenschap **[Visible](controls/properties-core.md)** van de knop **Remove** in op deze formule:
    <br>**Form1.Mode=FormMode.Edit**

    Met deze stap verbergt u de knop **Remove** wanneer de gebruiker een record maakt.

    Het **ChangeScreen** komt overeen met dit voorbeeld:

    ![Definitief ChangeScreen](./media/get-started-create-from-blank/changescreen-final.png)

## <a name="set-navigation-from-viewscreen"></a>Navigatie van ViewScreen instellen
1. Klik of tik in de linkernavigatiebalk op de bovenste miniatuur voor het **ViewScreen**.

    ![ViewScreen openen](./media/get-started-create-from-blank/select-viewscreen.png)

2. Klik of tik op **Pijl-vooruit** voor de eerste record in de galerie.

    ![Pijl-vooruit](./media/get-started-create-from-blank/next-arrow.png)

3. Stel de eigenschap **[OnSelect](controls/properties-core.md)** van de pijl in op deze formule:

    **Navigate(ChangeScreen,ScreenTransition.None)**

4. Klik of tik op het pluspictogram in de rechterbovenhoek.

    ![Record toevoegen](./media/get-started-create-from-blank/add-record.png)

5. Stel de eigenschap **[OnSelect](controls/properties-core.md)** van het geselecteerde pictogram in op deze formule:

    **NewForm(Form1);Navigate(ChangeScreen,ScreenTransition.None)**`

     Wanneer de gebruiker op dit pictogram klikt of tikt, wordt het **ChangeScreen** weergegeven met lege velden, zodat de gebruiker eenvoudig een nieuwe record kan maken.

## <a name="run-the-app"></a>De app uitvoeren
Tijdens het aanpassen van de app kunt u uw wijzigingen testen door de app uit te voeren in de Preview-modus, zoals de stappen in deze sectie laten zien.

1. Klik of tik in de linkernavigatiebalk op de bovenste miniatuur om het **ViewScreen** te selecteren.

    ![ViewScreen selecteren](./media/get-started-create-from-blank/select-viewscreen.png)

2. Open de Preview-modus door op F5 te drukken (of klik of tik op het pictogram **Preview** rechtsboven).

    ![Preview-modus openen](./media/get-started-create-from-blank/open-preview.png)

3. Klik of tik op de pijl-vooruit voor een record om de details van de record weer te geven.

4. Wijzig in het **ChangeScreen** de informatie in een of meer velden, sla uw wijzigingen op door te klikken of tikken op **Opslaan** of verwijder de record door te klikken of tikken op **Verwijderen**.

5. Sluit de Preview-modus door op Esc te drukken (of klik of tik op het pictogram sluiten onder de titelbalk).

    ![Preview-modus sluiten](./media/get-started-create-from-blank/close-preview.png)

## <a name="next-steps"></a>Volgende stappen
* Druk op Ctrl+S om de app op te slaan in de cloud, zodat u deze op andere apparaten kunt uitvoeren.
* [Deel de app](share-app.md) zodat anderen deze kunnen uitvoeren.
* Meer informatie over [galerieën](add-gallery.md), [formulieren](add-form.md) en [formules](working-with-formulas.md).
