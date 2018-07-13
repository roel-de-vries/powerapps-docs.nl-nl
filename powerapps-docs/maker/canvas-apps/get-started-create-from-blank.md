---
title: Een volledig nieuwe Excel-app maken | Microsoft Docs
author: AFTOwen
ms.service: powerapps
ms.topic: conceptual
ms.component: canvas
ms.date: 04/23/2018
ms.author: anneta
ms.openlocfilehash: bf802668ff56729c1d28fc460495a680fc3c6570
ms.sourcegitcommit: 79b8842fb0f766a0476dae9a537a342c8d81d3b3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2018
ms.locfileid: "37896806"
---
# <a name="create-an-excel-app-from-scratch"></a>Een volledig nieuwe Excel-app maken
Maak uw eigen volledig nieuwe app op basis van Excel-gegevens, opgemaakt als een tabel, en voeg vervolgens desgewenst gegevens uit andere bronnen toe. Wanneer u deze zelfstudie volgt, maakt u een app met twee schermen. In het ene scherm kunnen gebruikers bladeren door een set records. In het andere scherm kunnen gebruikers een record maken, een of meer velden in een record bijwerken of een heel record verwijderen. Deze benadering kost meer tijd dan [een app automatisch genereren](get-started-create-from-data.md), maar ervaren app-makers kunnen hiermee de beste app voor hun wensen maken.

## <a name="prerequisites"></a>Vereisten
Als u de onderstaande stappen in deze zelfstudie precies wilt volgen, maakt u een Excel-bestand met deze voorbeeldgegevens.

1. Kopieer deze gegevens en plak ze in een Excel-bestand.

    | StartDay | StartTime | Vrijwilliger | Backup |
    | --- | --- | --- | --- |
    | Saturday |10am-noon |Vasquez |Kumashiro |
    | Saturday |noon-2pm |Ice |Singhal |
    | Saturday |2pm-4-pm |Myk |Mueller |
    | Sunday |10am-noon |Li |Adams |
    | Sunday |10am-noon |Singh |Morgan |
    | Sunday |10am-noon |Batye |Nguyen |

2. Maak deze gegevens op als tabel met de naam **Schedule**, zodat de gegevens kunnen worden geparseerd door PowerApps.

    Zie voor meer informatie [Een tabel opmaken in Excel](how-to-excel-tips.md).

3. Sla het bestand op onder de naam **eventsignup.xls**, sluit het en upload het naar een [cloudopslagaccount](connections/cloud-storage-blob-connections.md), zoals OneDrive.

> [!IMPORTANT]
> U kunt uw eigen Excel-bestand gebruiken en deze zelfstudie raadplegen voor informatie over algemene concepten. De gegevens in het Excel-bestand moet echter zijn opgemaakt als een tabel. Zie voor meer informatie [Een tabel opmaken in Excel](how-to-excel-tips.md).

## <a name="open-a-blank-app"></a>Een lege app openen
1. Meld u aan bij [PowerApps](http://web.powerapps.com).

    ![PowerApps-startpagina](./media/get-started-create-from-blank/sign-in.png)

    U kunt een volledig nieuwe app ontwerpen voor telefoons of voor andere apparaten (zoals tablets). Dit onderwerp richt zich op het ontwerpen van een app voor telefoons.

1. Beweeg onder **Apps zoals deze maken** de muisaanwijzer over de tegel **Beginnen met een lege app**, selecteer het telefoonpictogram en selecteer **Deze app maken**.

    ![Lege-apptegel](./media/get-started-create-from-blank/blank-app.png)

    PowerApps Studio maakt een lege app voor telefoons.

1. Selecteer **Overslaan** in het dialoogvenster **Welkom bij PowerApps Studio**.

## <a name="connect-to-data"></a>Verbinding maken met gegevens
1. Selecteer **Verbinding maken met gegevens** in het midden van het scherm.

1. Selecteer in het deelvenster **Gegevens** de verbinding voor uw cloudopslagaccount als deze wordt weergegeven. Volg anders deze stappen om een verbinding toe te voegen:

    1. Selecteer **Nieuwe verbinding**, selecteer de tegel voor uw cloudopslagaccount en selecteer vervolgens **Maken**.
    2. Geef uw referenties voor het account op als u hierom wordt gevraagd.

1. Typ of plak onder **Een Excel-bestand kiezen** de eerste letters van **eventsignup** om de lijst te filteren en selecteer vervolgens het bestand dat u hebt geüpload.

1. Selecteer onder **Een tabel kiezen** het selectievakje voor **Planning**, en selecteer vervolgens **Verbinden**.

## <a name="create-the-view-screen"></a>Het weergavescherm maken

1. Selecteer op het tabblad **Start** de pijl omlaag naast **Nieuw scherm** om een lijst met schermtypen te openen en selecteer vervolgens **Lijstscherm**.

    ![Een lijstscherm toevoegen](./media/get-started-create-from-blank/add-list-screen.png)

    Er wordt een scherm toegevoegd met verschillende standaardbesturingselementen, zoals een zoekvak en een besturingselement **[Galerie](controls/control-gallery.md)**. De galerie vult het volledige scherm onder het zoekvak.

2. Selecteer de galerie door in de buurt van het middelpunt te tikken of te klikken.

    De galerie wordt omgeven door een selectiekader met grepen.

    ![Een lijstscherm toevoegen](./media/get-started-create-from-blank/select-gallery.png)

3. Selecteer in het rechterdeelvenster **CustomGallerySample** om het deelvenster **Gegevens** te openen.

    ![Deelvenster Gegevens openen](./media/get-started-create-from-blank/custom-gallery-sample.png)

4. Selecteer onder **Gegevensbron** de pijl omlaag om de lijst van gegevensbronnen voor de app te openen en selecteer vervolgens **Planning**.

    ![Een gegevensbron selecteren](./media/get-started-create-from-blank/select-schedule.png)

5. Selecteer onder **Indeling** de pijl omlaag om de lijst met indelingen te openen en selecteer vervolgens **Titel, subtitel en hoofdtekst**.

    ![Indeling selecteren](./media/get-started-create-from-blank/select-layout.png)

6. Wijzig onder **Title2** de kolom die wordt weergegeven van **Back-up** in **Vrijwilliger**.

     ![Kolom wijzigen in label](./media/get-started-create-from-blank/change-title2.png)

7. Selecteer het pictogram voor sluiten in de rechterbovenhoek om het deelvenster **Gegevens** te sluiten.

    De galerie geeft de naam van elke vrijwilliger en de dag en tijd van de dienst van die vrijwilliger weer.

    ![De planningsgegevens in de galerie, niet gesorteerd](./media/get-started-create-from-blank/show-data-unsorted.png)

8. Selecteer de galerie en controleer of in de eigenschappenlijst **[Items](controls/properties-core.md)** worden weergegeven.

    Zoals u in de formulebalk ziet, is de waarde van die eigenschap **Planning**.

    ![De planningsgegevens in de galerie, niet gesorteerd](./media/get-started-create-from-blank/set-property.png)

9. Wijzig de waarde van de eigenschap **Items** door deze formule te kopiëren en te plakken in de formulebalk:

    **SortByColumns(Search(Schedule, TextSearchBox1.Text, "Volunteer"), "Volunteer", If(SortDescending1, SortOrder.Descending, SortOrder.Ascending))**

    De galerie toont gegevens in alfabetische volgorde op de naam van de vrijwilliger.

    ![De planningsgegevens in de galerie, gesorteerd](./media/get-started-create-from-blank/show-data-sorted.png)

    Gebruikers kunnen de galerie sorteren en filteren op de naam van de vrijwilliger op basis van de **SortByColumns**- en **zoek**functies in deze formule.

   - Als een gebruiker ten minste één letter in het zoekvak typt, geeft de galerie alleen de records weer waarin het veld **Vrijwilliger** de tekst bevat die de gebruiker heeft getypt.
   - Als een gebruiker de sorteerknop selecteert, wordt de galerie weergegeven met de records in oplopende of aflopende volgorde (afhankelijk van hoe vaak de gebruiker de knop selecteert) op basis van het veld **Vrijwilliger**.

     Zie de [naslaginformatie over formules](formula-reference.md) voor meer informatie over deze en andere functies.

10. Typ een **i** in het zoekvak, selecteer de sorteerknop door erop te klikken of te tikken en selecteer deze vervolgens nog een keer (of nog een oneven aantal keren).

     De resultaten worden weergegeven in de galerie.

     ![De galerie sorteren en filteren](./media/get-started-create-from-blank/sort-filter.png)

11. Wis alle tekst in het zoekvak.

12. Selecteer boven aan het scherm het besturingselement **[Label](controls/control-text-box.md)** en vervang **[Titel]** door **Records weergeven**.

     ![Titelbalk wijzigen](./media/get-started-create-from-blank/change-title-bar.png)

## <a name="create-the-change-screen"></a>Het wijzigingsscherm maken
1. Selecteer op het tabblad **Start** de pijl omlaag naast **Nieuw scherm**, en selecteer vervolgens **Formulierscherm**.

     ![Formulierscherm toevoegen](./media/get-started-create-from-blank/add-form-screen.png)

1. Selecteer in het scherm dat u zojuist hebt toegevoegd de optie **Verbinding maken met gegevens** om het deelvenster **Gegevens** te selecteren en stel de gegevensbron vervolgens in op **Planning**.

1. Selecteer onder **Velden** alle selectievakjes om alle velden in het formulier weer te geven.

     ![Velden weergeven](./media/get-started-create-from-blank/show-fields.png)

1. Sleep het veld **Vrijwilliger** omhoog zodat het bovenaan de lijst met velden wordt weergegeven.

     ![Velden opnieuw ordenen](./media/get-started-create-from-blank/reorder-fields.png)

1. Selecteer het formulier en stel de eigenschap **Item** in op deze expressie door het in de formulebalk te typen of plakken:<br>**BrowseGallery1.Selected**

1. Selecteer boven aan het scherm het besturingselement **[Label](controls/control-text-box.md)** en vervang **[Titel]** door **Records wijzigen**.

    ![Titelbalk wijzigen](./media/get-started-create-from-blank/change-title-bar2.png)

## <a name="delete-and-rename-screens"></a>Schermen verwijderen en de naam van schermen wijzigen
1. Selecteer in de linkernavigatiebalk het weglatingsteken (...) voor **Screen1** en selecteer vervolgens **Verwijderen**.

    ![Scherm verwijderen](./media/get-started-create-from-blank/delete-screen.png)

1. Selecteer het weglatingsteken (...) voor **Screen2**, selecteer **Naam wijzigen**, en typ of plak **ViewScreen**.

1. Selecteer het weglatingsteken (...) voor **Screen3**, selecteer **Naam wijzigen**, en typ of plak **ChangeScreen**.

## <a name="configure-icons-on-the-view-screen"></a>Pictogrammen configureren op het weergavescherm
1. Selecteer bovenaan **ViewScreen** het pictogram in de vorm van een ronde pijl.

    ![Record toevoegen](./media/get-started-create-from-blank/refresh-icon.png)

1. Stel de eigenschap **OnSelect** voor dat pictogram in op deze formule:<br>**Refresh(Schedule)**

    Wanneer de gebruiker dit pictogram selecteert, worden de gegevens uit **Planning** vernieuwd vanuit het Excel-bestand.

    Zie de [naslaginformatie over formules](formula-reference.md) voor meer informatie over deze en andere functies.

1. Selecteer in de rechterbovenhoek van **ViewScreen** het plusteken.

    ![Record toevoegen](./media/get-started-create-from-blank/add-record.png)

1. Stel de eigenschap **OnSelect** voor dat pictogram in op deze formule:<br>**NewForm(EditForm1);Navigate(ChangeScreen,ScreenTransition.None)**

    Wanneer de gebruiker dit pictogram selecteert, wordt **ChangeScreen** weergegeven met lege velden, zodat de gebruiker eenvoudig een nieuw record kan maken.

1. Selecteer de pijl naar rechts voor het eerste record in de galerie.

    ![Pijl selecteren](./media/get-started-create-from-blank/select-arrow.png)

1. Stel de eigenschap **OnSelect** van de pijl in op deze formule:<br>**EditForm(EditForm1); Navigate(ChangeScreen, ScreenTransition.None)**

    Wanneer de gebruiker dit pictogram selecteert, wordt **ChangeScreen** weergegeven met elk veld waarin de gegevens voor het geselecteerde record worden weergegeven, zodat de gebruiker het record eenvoudiger kan bewerken of verwijderen.

## <a name="configure-icons-on-the-change-screen"></a>Pictogrammen configureren op het wijzigingsscherm
1. Selecteer in **ChangeScreen** het pictogram 'x' in de linkerbovenhoek.

    ![Pictogram Annuleren](./media/get-started-create-from-blank/cancel-icon.png)

1. Stel de eigenschap **OnSelect** voor dat pictogram in op deze formule:<br>**ResetForm(EditForm1);Navigate(ViewScreen, ScreenTransition.None)**

    Wanneer de gebruiker dit pictogram selecteert, worden eventuele wijzigingen die de gebruiker heeft aangebracht in dit scherm verwijderd en wordt het weergavescherm geopend.

1. Selecteer het vinkje in de rechterbovenhoek.

    ![Pictogram Vinkje](./media/get-started-create-from-blank/checkmark-icon.png)

1. Stel de eigenschap **OnSelect** van het vinkje in op deze formule:<br>**SubmitForm(EditForm1); Navigate(ViewScreen, ScreenTransition.None)**

    Wanneer de gebruiker dit pictogram selecteert, worden eventuele wijzigingen die de gebruiker heeft aangebracht in dit scherm opgeslagen en wordt het weergavescherm geopend.

1. Selecteer op het tabblad **Invoegen** de optie **Pictogrammen** en selecteer het **Prullenbak**-pictogram.

1. Stel de eigenschap **Kleur** van het nieuwe pictogram in op **Wit** en verplaats het nieuwe pictogram, zodat het naast het vinkje wordt weergegeven.

    ![Pictogram Prullenbak](./media/get-started-create-from-blank/trash-icon.png)

1. Stel de eigenschap **OnSelect** voor het prullenbakpictogram in op deze formule:<br>**Remove(Schedule, BrowseGallery1.Selected); Navigate(ViewScreen, ScreenTransition.None)**

    Wanneer de gebruiker dit pictogram selecteert, wordt het geselecteerde record verwijderd uit de gegevensbron en wordt het weergavescherm geopend.

## <a name="test-the-app"></a>De app testen
1. Selecteer het **ViewScreen** en open de preview door op F5 te drukken (of door het pictogram **Preview** in de rechterbovenhoek te selecteren).

    ![Preview-modus openen](./media/get-started-create-from-blank/open-preview.png)

1. Voeg een record toe.

1. Werk het record dat u hebt toegevoegd bij, en sla de wijzigingen op.

1. Werk het record dat u hebt toegevoegd bij, en annuleer de wijzigingen.

1. Verwijder het record dat u hebt toegevoegd.

1. Sluit de previewmodus door op Esc te drukken (of door het pictogram voor sluiten in de rechterbovenhoek te selecteren).

## <a name="next-steps"></a>Volgende stappen
* Druk op Ctrl+S om de app op te slaan in de cloud, zodat u deze op andere apparaten kunt uitvoeren.
* [Deel de app](share-app.md) zodat anderen deze kunnen uitvoeren.
* Meer informatie over [functies](working-with-formulas.md) zoals **Patch**, die u kunt gebruiken om gegevens te beheren zonder een standaardformulier te maken.
