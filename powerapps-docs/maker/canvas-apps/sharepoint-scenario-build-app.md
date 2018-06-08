---
title: Een app maken om projecten te beheren  | Microsoft Docs
description: In deze taak gaan we een volledig nieuwe app bouwen. Met deze app kan een gebruiker een manager toewijzen aan projecten en kunnen de details van een project worden bijgewerkt.
documentationcenter: na
author: mgblythe
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 06/12/2017
ms.author: mblythe
ms.openlocfilehash: fca166ef388921e08bf71149a8b1274a31a7dc52
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "32330624"
---
# <a name="create-an-app-to-manage-projects"></a>Een app maken om projecten te beheren
> [!NOTE]
> Dit artikel maakt deel uit van een reeks zelfstudies over het gebruik van PowerApps, Microsoft Flow en Power BI met SharePoint Online. Lees de [inleiding tot de reeks](sharepoint-scenario-intro.md) zodat u een idee van het geheel krijgt en van de betreffende downloads.

In deze taak gaan we een volledig nieuwe app bouwen. Met deze app kan een gebruiker een manager toewijzen aan projecten en kunnen de details van een project worden bijgewerkt. U ziet enkele zelfde besturingselementen en formules die u in de eerste app hebt gezien, maar u gaat deze keer zelf meer van de app bouwen. Het proces is wat ingewikkelder, maar u leert ook meer, dus dat lijkt een goed compromis.

> [!TIP]
> Het [downloadpakket](https://aka.ms/o4ia0f) voor dit scenario omvat een voltooide versie van deze app: project-details-app.msapp.

## <a name="quick-review-of-powerapps-studio"></a>Kort overzicht van PowerApps Studio
PowerApps Studio heeft drie deelvensters en een lint waardoor het maken van apps lijkt op het maken van een PowerPoint-presentatie:

1. Linkernavigatiebalk, met een hiërarchische weergave van alle schermen en besturingselementen van de app, evenals de miniaturen op de schermen
2. Middelste deelvenster, met het app-scherm waaraan u werkt
3. Rechterdeelvenster, waar u opties instelt, zoals indeling en gegevensbronnen
4. Vervolgkeuzelijst voor eigenschappen, waar u de eigenschappen selecteert waarop de formules betrekking hebben
5. Formulebalk, waar u formules toevoegt (zoals in Excel) die het app-gedrag bepalen
6. Lint, waar u besturingselementen toevoegt en ontwerpelementen aanpast

![PowerApps Studio](./media/sharepoint-scenario-build-app/04-00-00-powerapps-studio.png)

## <a name="step-1-create-screens"></a>Stap 1: Schermen maken
Nu we de stof hebben herhaald, gaan we een app bouwen.

### <a name="create-and-save-the-app"></a>De app maken en opslaan
1. Klik of tik in PowerApps Studio op **Nieuw** en vervolgens onder **Lege app** op **Telefoonindeling**.
   
    ![Lege app: telefoonindeling](./media/sharepoint-scenario-build-app/04-01-01-blank-phone-app.png)
2. Klik of tik op **Bestand**, waarna dit wordt geopend als het tabblad **App-instellingen**. Voer de naam 'App Projectbeheer' in.
   
    ![Naam van app](./media/sharepoint-scenario-build-app/04-01-02-app-name.png)
3. Klik of tik op **Opslaan als**, controleer of de app in de cloud wordt opgeslagen en klik vervolgens linksonder op **Opslaan**.
   
    ![Opslaan in de cloud](./media/sharepoint-scenario-build-app/04-01-03-save-to-cloud.png)

4. Klik of tik op ![Pictogram Terug naar app](./media/sharepoint-scenario-build-app/icon-back-to-app.png) om naar de app terug te gaan.

### <a name="add-four-screens-to-the-app"></a>Vier schermen aan de app toevoegen
In deze stap maken we vier schermen voor de app. We gebruiken verschillende indelingen, afhankelijk van de functie van het scherm. Later werken we verder met de schermen.

| **Scherm** | **Functie** |
| --- | --- |
| **SelectTask** |Scherm openen; navigeren naar andere schermen |
| **AssignManager** |Manager toewijzen aan een goedgekeurd project |
| **ViewProjects** |Een lijst met projecten weergeven, met beknopte informatie |
| **UpdateDetails** |De details van een project weergeven en bijwerken |

1. Klik op het tabblad **Start** op **NewScreen** en vervolgens op **Doorscrolbaar scherm**.
   
    ![Doorscrolbaar scherm](./media/sharepoint-scenario-build-app/04-01-03a-scrollable-screen.png)
2. Wijzig de naam van het scherm in **SelectTask**.
   
    ![Naam van scherm wijzigen](./media/sharepoint-scenario-build-app/04-01-04-rename-screen.png)
3. Maak aanvullende schermen en geef deze een andere naam:
   
   1. Klik of tik op **NewScreen** en vervolgens op **Doorscrolbaar scherm**. Wijzig de naam van het scherm in **AssignManager**.
   2. Klik of tik op **NewScreen** en vervolgens op **Lijstscherm**. Wijzig de naam van het scherm in **ViewProjects**.
   3. Klik of tik op **NewScreen** en vervolgens op **Formulierscherm**. Wijzig de naam van het scherm in **UpdateDetails**.
4. Selecteer het beletselteken (**. . .**) naast **Scherm1** en klik of tik op **Verwijderen**.
   
    ![Scherm verwijderen](./media/sharepoint-scenario-build-app/04-01-04a-delete-screen.png)

De app moet er nu uitzien zoals in de volgende afbeelding.

![Alle app-schermen](./media/sharepoint-scenario-build-app/04-01-05-all-screens.png)

## <a name="step-2-connect-to-a-sharepoint-list"></a>Stap 2: Verbinding maken met een SharePoint-lijst
In deze stap gaan we verbinding maken met de SharePoint-lijst **Productdetails**. In deze app gebruiken we slechts één lijst, maar u kunt gemakkelijk met beide lijsten verbinding maken als u de app wilt uitbreiden.

1. Klik of tik in de linkernavigatiebalk op het scherm **SelectTask**.
2. Klik of tik in het rechterdeelvenster op **Gegevensbron toevoegen**.
   
    ![Verbinding maken met gegevens](./media/sharepoint-scenario-build-app/04-02-01-connect.png)
3. Klik of tik op **Nieuwe verbinding**.
   
    ![Nieuwe verbinding](./media/sharepoint-scenario-build-app/04-02-02-new-connection.png)
4. Klik of tik op **SharePoint**.
   
    ![SharePoint-verbinding](./media/sharepoint-scenario-build-app/04-02-03-sharepoint-connection.png)
5. Selecteer **Rechtstreeks verbinding maken (cloudservices)** en klik of tik op **Maken**.
   
    ![Rechtstreeks verbinding maken (cloudservices)](./media/sharepoint-scenario-build-app/04-02-03a-sharepoint-cloud.png)
6. Voer een SharePoint-URL in en klik of tik op **Start**.
   
    ![SharePoint-URL voor verbinding](./media/sharepoint-scenario-build-app/04-02-04-sharepoint-url.png)
7. Selecteer de lijst **Projectdetails** en klik of tik op **Verbinding maken**.
   
    ![Lijst Projectdetails selecteren](./media/sharepoint-scenario-build-app/04-02-05-sharepoint-lists.png)
   
    Het tabblad **Gegevensbronnen** in het rechterdeelvenster toont de verbinding die u hebt gemaakt.
   
    ![Tabblad Gegevensbronnen](./media/sharepoint-scenario-build-app/04-02-06-data-sources.png)

## <a name="step-3-build-the-selecttask-screen"></a>Stap 3: Scherm SelectTask maken
In deze stap gaan we een manier vinden om naar de andere schermen in de app te navigeren en werken we met een aantal besturingselementen, formules en opmaakopties in PowerApps.

### <a name="update-the-title-and-insert-introductory-text"></a>Titel bijwerken en inleidende tekst invoegen
1. Selecteer in de linkernavigatiebalk het scherm **SelectTask**.
2. Selecteer in het middelste venster de standaardwaarde **[Title]** en werk vervolgens in de formulebalk de eigenschap **Text** bij naar 'Contoso-projectbeheer'.
   
    ![Eigenschap Tekst in formulebalk](./media/sharepoint-scenario-build-app/04-03-02-text-property.png)
3. Klik of tik op het tabblad **Invoegen** op **Label** en sleep het label onder de bovenste banner.
   
    ![Label toevoegen](./media/sharepoint-scenario-build-app/04-03-03-text-default.png)
4. Stel in de formulebalk de volgende eigenschappen voor het label in:
   
   * Eigenschap **Color** = **DarkGray**

   * Eigenschap **Size** = **18**

   * Eigenschap **Text** = **Klik of tik op een taak om door te gaan...**
     
     ![Labeltekst bijwerken](./media/sharepoint-scenario-build-app/04-03-04-text-updated.png)

### <a name="add-two-navigation-buttons"></a>Twee navigatieknoppen toevoegen
1. Klik of tik op het tabblad **Invoegen** op **Knop** en sleep de knop onder het label.
   
    ![De knop toevoegen](./media/sharepoint-scenario-build-app/04-03-05-button-default.png)
2. Stel in de formulebalk de volgende eigenschappen voor de knop in:
   
   * Eigenschap **OnSelect** = **Navigate(AssignManager, Fade)**. Als u de app uitvoert en op deze knop klikt, navigeert u naar het tweede scherm in de app, waarbij de overgang tussen de schermen vervaagt.

   * Eigenschap **Text** = **Manager toewijzen**

3. Wijzig de grootte van de knop om de tekst in te kunnen passen.
   
    ![Knoptekst bijwerken](./media/sharepoint-scenario-build-app/04-03-06-button-updated.png)
4. Voeg een andere knop in met de volgende eigenschappen:
   
   * Eigenschap **OnSelect** = **Navigate(ViewProjects, Fade)**.

   * Eigenschap **Text** = **Details bijwerken**
     
     ![Knoptekst bijwerken](./media/sharepoint-scenario-build-app/04-03-08-buttons-final.png)
     
     > [!NOTE]
> De knop heeft het label **Details bijwerken**, maar eerst navigeren we naar het scherm **ViewProjects** om een bij te werken project te selecteren.

### <a name="run-the-app"></a>De app uitvoeren
De app doet nog niet veel, maar u kunt de app al wel uitvoeren:

1. Klik of tik op het scherm **SelectTask** (de app wordt altijd gestart vanuit het geselecteerde scherm in de Preview-modus in PowerApps Studio).

2. Klik of tik op ![Pictogram App uitvoeren](./media/sharepoint-scenario-build-app/icon-run-arrow.png) in de rechterbovenhoek om de app uit te voeren.

3. Klik of tik op een van de knoppen om naar een ander scherm te navigeren.

4. Klik of tik op ![Pictogram App-overzicht sluiten](./media/sharepoint-scenario-build-app/icon-close-preview.png) in de rechterbovenhoek om de app te sluiten.

## <a name="step-4-build-the-assignmanager-screen"></a>Stap 4: Het scherm AssignManager bouwen
In deze stap gebruiken we een galerie om alle projecten weer te geven die zijn goedgekeurd maar nog geen manager hebben. We voegen ook andere besturingselementen toe, zodat u een manager kunt toewijzen.

> [!NOTE]
>  Later bouwen we een pagina in de app waarmee u alle velden voor een project kunt bewerken (inclusief het managersveld). Het leek ons wel leuk om ook een scherm zoals dit te bouwen.

1. Sla uw wijzigingen op.

2. Klik of tik in de linkernavigatiebalk op het scherm **AssignManager**.

### <a name="update-the-title-and-insert-introductory-text"></a>Titel bijwerken en inleidende tekst invoegen

1. Wijzig **[Title]** in **Manager toewijzen**.

2. Voeg een label toe met de volgende eigenschappen:
   
   * Eigenschap **Color** = **DarkGray**

   * Eigenschap **Size** = **18**

   * Eigenschap **Text** = **Selecteer een project en wijs vervolgens een manager toe**
     
     ![Indeling Manager toewijzen](./media/sharepoint-scenario-build-app/04-04-01-layout.png)

### <a name="add-a-back-arrow-to-return-to-the-selecttask-screen"></a>Een pijl-terug toe toevoegen om terug te gaan naar het scherm SelectTask

1. Klik of tik op de blauwe balk bovenaan het scherm.

2. Klik of tik op het tabblad **Invoegen** op **Pictogrammen** en vervolgens op **Links**.
   
    ![Pijl-links invoegen](./media/sharepoint-scenario-build-app/04-04-02-icon-left.png)

3. Verplaats de pijl naar de linkerkant van de blauwe balk en stel de volgende eigenschappen in:
   
   * Eigenschap **Color** = **White**

   * Eigenschap **Height** = **40**

   * Eigenschap **OnSelect** = **Navigate(SelectTask, Fade)**

   * Eigenschap **Width** = **40**
     
     ![Knop Terug toevoegen](./media/sharepoint-scenario-build-app/04-04-03-left-arrow.png)

### <a name="add-and-modify-a-gallery"></a>Galerie toevoegen en wijzigen

1. Klik of tik op het tabblad **Invoegen** op **Galerie** en vervolgens op **Verticaal**.
   
    ![Verticale galerie toevoegen](./media/sharepoint-scenario-build-app/04-04-04-gallery.png)

2. Selecteer in het rechterdeelvenster, in het menu **Indeling**, de optie **Titel, subtitel en hoofdtekst**. 
   
    ![De galerie-indeling wijzigen](./media/sharepoint-scenario-build-app/04-04-04a-gallery-layout.png)
   
    De galerie heeft nu de juiste indeling, maar bevat nog wel de standaardvoorbeeldtekst. Daar gaan we nu iets aan doen.
   
    ![Galerie met standaardtekst](./media/sharepoint-scenario-build-app/04-04-05-gallery-default.png)

3. Stel de volgende eigenschappen voor de galerie in:
   
   * Eigenschap **BorderThickness** = **1**

   * Eigenschap **BorderStyle** = **Dotted**

   * Eigenschap **Items** = **Filter('Projectdetails', PMAssigned="Niet toegewezen")**. Allen projecten waaraan geen manager is toegewezen, worden in de galerie opgenomen.
     
     ![Galerie met tekst uit lijst](./media/sharepoint-scenario-build-app/04-04-06-gallery-updated.png)

4. Werk in het rechterdeelvenster de velden bij zodat ze overeenkomen met de volgende lijst:
   
   * **ApprovedDate**

   * **Status**

   * **Title**
     
     ![Galerievelden](./media/sharepoint-scenario-build-app/04-04-07-gallery-fields.png)

5. Pas de grootte van de labels naar wens aan en verwijder de pijl van het eerste galerie-item (vanuit deze galerie hoeven we nergens heen te navigeren).
   
    ![Picogram Pijl verwijderen](./media/sharepoint-scenario-build-app/04-04-07a-remove-arrow.png)
   
    Het scherm moet nu lijken op de volgende afbeelding.
   
    ![Opgemaakte galerie](./media/sharepoint-scenario-build-app/04-04-07b-gallery-size-text.png)

### <a name="change-the-color-of-an-item-if-its-selected"></a>De kleur van een item wijzigen als dit wordt geselecteerd

1. Selecteer de galerie en stel vervolgens de eigenschap **TemplateFill** in op **If (ThisItem.IsSelected=true, Orange, White)**.

2. Selecteer een item in de galerie. Het scherm moet nu lijken op de volgende afbeelding.
   
    ![Galerie met geselecteerd item](./media/sharepoint-scenario-build-app/04-04-08-gallery-selected.png)

### <a name="add-a-label-text-input-and-ok-button-to-submit-manager-assignments"></a>Een label, tekstinvoer en knop OK toevoegen om managertoewijzingen in te dienen

1. Klik of tik buiten de galerie waaraan u hebt gewerkt.

2. Klik of tik op het tabblad **Invoegen** op **Label**. Sleep het label onder de galerie, naar de linkerkant. Stel de volgende eigenschappen voor het label in:
   
   * Eigenschap **Size** = **20**

   * Eigenschap **Text** = **"Manager:"**
   
   ![Label Manager toevoegen](./media/sharepoint-scenario-build-app/04-04-09-controls-text.png)

3. Klik of tik op het tabblad **Invoegen** op **Tekst** en vervolgens op **Tekstinvoer**. Sleep de tekstinvoer onder de galerie, in het midden. Stel de volgende eigenschappen voor de vervolgkeuzelijst in:
   
   * Eigenschap **Default** = **""**

   * Eigenschap **Height** = **60**

   * Eigenschap **Size** = **20**

   * Eigenschap **Width** = **250**
   
   ![Tekstinvoer toevoegen](./media/sharepoint-scenario-build-app/04-04-10-controls-text-box.png)

4. Klik of tik op het tabblad **Invoegen** op **Knop**. Sleep de knop onder de galerie, naar de rechterkant. Stel de volgende eigenschappen voor de knop in:
   
   * Eigenschap **Height** = **60**

   * Eigenschap **OnSelect** = **Patch('Projectdetails', LookUp('Projectdetails', ID = Gallery1.Selected.ID), {PMAssigned: TextInput1.Text})**. Zie [De formule nader bekeken](#formula-deep-dive) voor meer informatie.

   * Met deze formule wordt de lijst **Projectdetails** bijgewerkt door een waarde voor het veld PMAssigned in te stellen.

   * Eigenschap **Size** = **20**

   * Eigenschap **Text** = **"OK"**

   * Eigenschap **Width** = **80**
   
   ![Knop OK toevoegen](./media/sharepoint-scenario-build-app/04-04-11-controls-button.png)

Het voltooide scherm moet nu lijken op de volgende afbeelding.

![Voltooid scherm Manager toewijzen](./media/sharepoint-scenario-build-app/04-04-12-complete.png)

## <a name="step-5-build-the-viewprojects-screen"></a>Stap 5: scherm ViewProjects bouwen
In deze stap wijzigen we de eigenschappen voor de galerie in het scherm **ViewProjects**. Deze galerie toont items uit de lijst **Projectdetails**. In dit scherm selecteert u een item en vervolgens bewerkt u de details ervan in het scherm **UpdateDetails**.

1. Klik of tik in de linkernavigatiebalk op het scherm **ViewProjects**.

2. Wijziging **[Title]** in **Projecten weergeven**.

3. Tik of klik in de linkernavigatiebalk op **BrowserGallery1** onder **ViewProjects**.

4. Selecteer in het rechterdeelvenster, in het menu **Indeling**, de optie **Titel, subtitel en hoofdtekst**. 
   
    ![De galerie-indeling wijzigen](./media/sharepoint-scenario-build-app/04-04-04a-gallery-layout.png)
   
    De galerie heeft nu de juiste indeling, met de standaardvoorbeeldtekst.
   
    ![Galerie met standaardtekst](./media/sharepoint-scenario-build-app/04-04-04b-gallery-default.png)

5. Selecteer de vernieuwknop ![Pictogram Vernieuwen](./media/sharepoint-scenario-build-app/icon-refresh.png) en stel de eigenschap **OnSelect** in op **Refresh('Projectdetails')**.

6. Selecteer de knop over het nieuwe item ![Pictogram Nieuwe toevoegen](./media/sharepoint-scenario-build-app/icon-add-item.png) en de stel de eigenschap **OnSelect** in op **NewForm(EditForm1); Navigate(UpdateDetails, ScreenTransition.None)**.

### <a name="add-a-back-arrow-to-return-to-the-selecttask-screen"></a>Een pijl-terug toe toevoegen om terug te gaan naar het scherm SelectTask

1. Klik of tik in de linkernavigatiebalk op het scherm **AssignManager**.

2. Selecteer de pijl-terug die u hier hebt toegevoegd en kopieer deze.

3. Plak de pijl in het scherm **ViewProjects** en plaats deze aan de linkerkant van de vernieuwknop. 
   
    ![Knop Terug](./media/sharepoint-scenario-build-app/04-05-04-left-arrow-v.png)
   
    De pijl bezit nu alle eigenschappen, inclusief de eigenschap **OnSelect** van **Navigate(SelectTask, Fade)**.

### <a name="change-the-data-source-for-the-browsegallery1-gallery"></a>De gegevensbron wijzigen voor de galerie BrowseGallery1

1. Selecteer de galerie **BrowseGallery1** en stel de eigenschap **Items** van de galerie in op **SortByColumns(Filter('Projectdetails', StartsWith(Title, TextSearchBox1.Text)), "Titel", If(SortDescending1, Descending, Ascending))**.
   
    Hierdoor wordt de gegevensbron van de galerie ingesteld op de lijst **Projectdetails**. Er wordt gebruikgemaakt van het veld **Titel** om te zoeken en sorteren.

2. Selecteer het ![Pijlpictogram Details](./media/sharepoint-scenario-build-app/icon-details-arrow.png) in het eerste galerie-item en stel de eigenschap **OnSelect** in op **Navigate(UpdateDetails, None)**.
   
    ![ Galerie Projecten weergeven; eerste item geselecteerd](./media/sharepoint-scenario-build-app/04-05-05b-gallery-arrow-v.png)

3. Werk in het rechterdeelvenster de velden bij zodat ze overeenkomen met de volgende lijst:
   
   * **Status**

   * **PMAssigned**

   * **Title**
     
     ![Galerievelden](./media/sharepoint-scenario-build-app/04-05-06-gallery-fields.png)
     
     Het voltooide scherm moet nu lijken op de volgende afbeelding.
     
     ![Voltooid scherm Projecten weergeven](./media/sharepoint-scenario-build-app/04-05-07-viewprojects-final.png)

## <a name="step-6-build-the-updatedetails-screen"></a>Stap 6: Scherm UpdateDetails bouwen
In deze stap verbinden we het bewerkingsformulier in het scherm **UpdateDetails** met de gegevensbron en brengen we enkele wijzigingen aan eigenschappen en velden aan. In dit scherm bewerkt u de details van een project dat u hebt geselecteerd in het scherm **Projecten weergeven**.

1. Klik of tik in de linkernavigatiebalk op het scherm **UpdateDetails**.

2. Wijzig **[Title]** in **Details bijwerken**.

3. Klik of tik in de linkernavigatiebalk op **EditForm1** onder **UpdateDetails**.

4. Stel de volgende eigenschappen voor het formulier in:
   
   * Eigenschap **DataSource** = **'Projectdetails'**

   * Eigenschap **Item** = **BrowseGallery1.Selected**

5. Terwijl u het formulier nog hebt geselecteerd, selecteert u in het rechterdeelvenster het selectievakje voor de volgende velden en in de aangegeven volgorde:
   
   * **Title**

   * **PMAssigned**

   * **Status**

   * **ProjectedStartDate**

   * **ProjectedEndDate**

   * **ProjectedDays**

   * **ActualDays**
     
     ![Formuliervelden bewerken](./media/sharepoint-scenario-build-app/04-06-03-edit-fields.png)
6. Selecteer de annuleerknop ![Pictogram Annuleren](./media/sharepoint-scenario-build-app/icon-cancel.png) en stel de eigenschap **OnSelect** in op **ResetForm(EditForm1); Back()**.

7. Select de knop voor opslaan ![Pictogram met selectievakje voor opslaan](./media/sharepoint-scenario-build-app/icon-check-mark.png) en bekijk de **OnSelect**-formule: **SubmitForm(EditForm1)**. We gebruiken het besturingselement voor formulierbewerking, dus we kunnen gebruikmaken van **Submit()** in plaats van **Patch()**, zoals we eerder deden.

Het voltooide scherm moet er nu uitzien zoals in de volgende afbeelding (als de velden leeg zijn, selecteert u een item in het scherm **Projecten weergeven**).

![Voltooid scherm Details bijwerken](./media/sharepoint-scenario-build-app/04-06-06-edit-final.png)

## <a name="step-7-run-the-app"></a>Stap 7: De app uitvoeren
De app is voltooid, dus we gaan de app uitvoeren om te zien hoe deze werkt. We voegen een koppeling naar de app toe op de SharePoint-site. U kunt de app in de browser uitvoeren, maar mogelijk wilt u de app met anderen delen. Zie [Uw apps delen](https://powerapps.microsoft.com/guided-learning/learning-manage-share-apps) voor meer informatie.

### <a name="add-a-link-to-the-app"></a>Een koppeling aan de app toevoegen
1. Klik of tik in het startprogramma voor Office 365-apps op **PowerApps**.
   
    ![PowerApps in startprogramma voor Office 365-apps](./media/sharepoint-scenario-build-app/04-07-02a-waffle.png)

2. Klik of tik in PowerApps op het beletselteken (**. . .**) voor **Projectbeheer-app** en vervolgens op **Openen**.
   
    ![Projectbeheer-app selecteren](./media/sharepoint-scenario-build-app/04-07-02b-select-app.png)

3. Kopieer het adres (URL) voor de app in de browser.
   
    ![App-URL kopiëren](./media/sharepoint-scenario-build-app/04-07-02ba-copy-url.png)

4. Klik of tik in SharePoint op **KOPPELINGEN BEWERKEN**.
   
    ![SharePoint-sitekoppelingen bewerken](./media/sharepoint-scenario-build-app/04-07-02c-edit-links.png)

5. Klik of tik op **(+) koppeling**.
   
    ![App-koppeling aan SharePoint-site toevoegen](./media/sharepoint-scenario-build-app/04-07-02d-add-link.png)

6. Voer 'Projectbeheer-app' in en plak het adres voor de app in.
   
    ![Eigenschappen van koppeling bewerken](./media/sharepoint-scenario-build-app/04-07-02e-link-dialog.png)

7. Klik of tik op **OK** en vervolgens op **Opslaan**.
   
    ![Wijzigingen aan koppeling opslaan](./media/sharepoint-scenario-build-app/04-07-02f-save.png)

### <a name="assign-a-manager-to-a-project"></a>Een manager aan een project toewijzen
We hebben de app aan de SharePoint-site toegevoegd en spelen nu de rol van projectfiatteur. We zoeken projecten waaraan nog geen manager is toegewezen en wijzen een manager toe aan een van die projecten. Vervolgens spelen we de rol van de projectmanager en voegen wat gegevens toe over een project dat aan ons is toegewezen.

1. Eerst kijken we naar de lijst **Projectdetails** in SharePoint. Twee projecten hebben de waarde **Unassigned** in de kolom **PMAssigned**. Die zien we in de app.
   
    ![Niet-toegewezen projecten in SharePoint-lijst](./media/sharepoint-scenario-build-app/04-07-01-unassigned.png)

2. Klik of tik op de koppeling die u in de app hebt gemaakt.

3. Klik of tik in het eerste scherm op **Manager toewijzen**.
   
    ![Introductiescherm van app](./media/sharepoint-scenario-build-app/04-07-03-intro-screen.png)

4. In het scherm **Manager toewijzen** ziet u de twee niet-toegewezen projecten uit de lijst. Selecteer het project **Nieuw BI-software**.
   
    ![Galerie met geselecteerd item](./media/sharepoint-scenario-build-app/04-07-04-selected.png)

5. Voer in de tekstinvoer naast **Manager** 'Femke van Nuil' in en klik op **OK**.
   
    De wijziging wordt in de lijst doorgevoerd en de galerie wordt vernieuwd, dus alleen het resterende niet-toegewezen project wordt nog weergegeven.
   
    ![Manager toewijzen aan project](./media/sharepoint-scenario-build-app/04-07-05-updated.png)

6. Ga terug naar de SharePoint-lijst en vernieuw de pagina. U ziet dat de projectvermelding nu is bijgewerkt met de naam van de projectmanager.
   
    ![Projectmanager toegewezen in SharePoint-lijst](./media/sharepoint-scenario-build-app/04-07-07-assigned.png)

### <a name="update-details-for-the-project"></a>Details bijwerken voor het project

1. Klik of tik op ![Pictogram Terug](./media/sharepoint-scenario-build-app/icon-back.png) om naar het eerste scherm terug te gaan en klik of tik vervolgens op **Details bijwerken**.
   
   ![Introductiescherm van app](./media/sharepoint-scenario-build-app/04-07-08-intro-screen.png)

2. Voer in het scherm **Projecten weergeven** 'Nieuw' in het zoekvak in.
   
   ![Zoeken in app-galerie](./media/sharepoint-scenario-build-app/04-07-09-search-new.png)

3. Klik op ![Pijlpictogram Details](./media/sharepoint-scenario-build-app/icon-details-arrow.png) voor het item **Nieuwe BI-software**.
   
   ![Galerie-item geselecteerd](./media/sharepoint-scenario-build-app/04-07-10-select-project.png)

4. Stel in het scherm **Details bijwerken** de volgende waarden in:
   
   * Het veld **ProjectedStartDate** = "3/6/2017"

   * Het veld **ProjectedEndDate** = "3/24/2017"

   * Het veld **ProjectedDays** = "15"
   
   ![Itemdetails bijwerken](./media/sharepoint-scenario-build-app/04-07-11-update.png)

5. Klik of tik op ![Pictogram Vinkje](./media/sharepoint-scenario-build-app/icon-check-mark.png) om de wijziging op de SharePoint-lijst toe te passen.

6. Sluit de app en ga terug naar de lijst. De projectvermelding is bijgewerkt met de wijzigingen voor de datum en de dag.
   
    ![Bijgewerkte SharePoint-lijst](./media/sharepoint-scenario-build-app/04-07-11-updated-list.png)

## <a name="formula-deep-dive"></a>De formule nader bekeken
Dit is de tweede optionele sectie over PowerApps-formules. In de eerste sectie hebben we gekeken naar een van de formules die PowerApps genereert voor de bladergalerie in een app met drie schermen. In deze sectie kijken we naar een formule die we gebruiken voor het scherm **AssignManager** van de tweede app. Dit is de formule:

**Patch ( 'Projectdetails', LookUp ( 'Projectdetails', ID = Gallery1.Selected.ID ), {PMAssigned: TextInput1.Text} )**

Wat doet deze formule? Als u een item in de galerie selecteert en op de knop **OK** klikt, werkt de formule de lijst **Projectdetails** bij, waarbij de kolom **PMAssigned** wordt ingesteld op de waarde die u in de tekstinvoer opgeeft. De formule maakt voor de uitvoering gebruik van functies:

* De [functie **Patch**](functions/function-patch.md) wijzigt een of meer records in een gegevensbron.

* De [functie **LookUp**](functions/function-filter-lookup.md) vindt de eerste record in een tabel die aan een formule voldoet.

Als de functies samen in een formule worden gestopt, gebeurt het volgende:

1. Als u op de knop **OK** klikt, wordt de functie **Patch** aangeroepen om de lijst **Projectdetails** bij te werken.

2. Binnen de functie **Patch** identificeert de functie **LookUp** welke rij in de lijst **Projectdetails** moet worden bijgewerkt. Hiertoe wordt de id van het geselecteerde galerie-item vergeleken met de id in de lijst. Bijvoorbeeld: een id van 12 betekent dat de vermelding voor **Nieuwe BI-software** moet worden bijgewerkt.

3. De functie **Patch** heeft de juiste id, dus het veld **PMAssigned** wordt bijgewerkt naar de waarde in **TextInput1.Text**.

## <a name="next-steps"></a>Volgende stappen
De volgende stap in deze reeks zelfstudies gaat over het [maken van een Power BI-rapport om projecten te analyseren](sharepoint-scenario-build-report.md).

