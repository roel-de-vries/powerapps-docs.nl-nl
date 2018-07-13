---
title: Wat zijn formulieren? | Microsoft Docs
description: Gebruik formulieren voor het verzamelen en weergeven van informatie van een gegevensbron.
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 04/27/2016
ms.author: gregli
ms.openlocfilehash: bf66c1f7596b8a3ef4c8495db3f0ac2af8165d8c
ms.sourcegitcommit: 79b8842fb0f766a0476dae9a537a342c8d81d3b3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2018
ms.locfileid: "37899681"
---
# <a name="understand-data-forms-in-microsoft-powerapps"></a>Gegevensformulieren begrijpen in Microsoft PowerApps
Voer drie typen besturingselementen toe zodat de gebruiker naar een record kan bladeren, details over deze record kan weergeven, en een record kan bewerken of maken:

| Activiteit | Besturingselement | Beschrijving |
| --- | --- | --- |
| **Bladeren naar een record** |Het besturingselement **[Galerie](controls/control-gallery.md)** |Filter, orden, zoek in en blader door records in een gegevensbron en selecteer een specifieke record. Geef slechts een paar velden van elke record weer om meerdere records tegelijkertijd te tonen, zelfs op een klein scherm. |
| **Details van een record weergeven** |Het besturingselement **[Formulier weergeven](controls/control-form-detail.md)** |Geef voor één record veel velden of alle velden in die record weer. |
| **Een record maken of bewerken** |Het besturingselement **[Formulier bewerken](controls/control-form-detail.md)** |Werk één of meer velden in een enkel record bij (of maak een record met standaardwaarden) en sla de wijzigingen op in de onderliggende gegevensbron. |

Zet elk besturingselement in een ander scherm zodat ze gemakkelijker te onderscheiden zijn:

![Door records bladeren, en ze weergeven en bewerken op drie verschillende schermen](./media/working-with-forms/three-screens.png)

Zoals in dit onderwerp wordt beschreven, kunt u deze besturingselementen combineren met formules voor het maken van de algehele gebruikerservaring.

## <a name="prerequisites"></a>Vereisten

* [Registreer u](../signup-for-powerapps.md) voor PowerApps en [meld u vervolgens aan](https://web.powerapps.com) door dezelfde referenties in te voeren die u hebt gebruikt om u te registreren.
* Lees hoe u [een besturingselement kunt configureren](add-configure-controls.md) in PowerApps.

## <a name="explore-a-generated-app"></a>Een gegenereerde app verkennen
PowerApps kan automatisch een app genereren op basis van een door u opgegeven gegevensbron. Elke app bevat drie schermen met de besturingselementen die eerder zijn beschreven en formules waarmee ze zijn verbonden. U kunt deze apps uitvoeren zonder ze eerst aan te passen, ze aanpassen aan uw specifieke doelen, of onderzoeken hoe ze werken zodat u nuttige concepten kunt leren die betrekking hebben op uw eigen apps. Inspecteer in de volgende secties de schermen, besturingselementen en formules van een gegenereerde app.  

### <a name="browse-screen"></a>Bladerscherm
![Besturingselementen van bladerscherm](./media/working-with-forms/afd-browse-screen-basic.png)

Dit scherm bevat functies voor deze belangrijke formules:

| Besturingselement | Ondersteund gedrag | Formule |
| --- | --- | --- |
| **BrowseGallery1** |Geef records uit de gegevensbron **Assets** weer. |De eigenschap **[Items](controls/properties-core.md)** van de galerie is ingesteld op een formule die is gebaseerd op de gegevensbron **Assets**. |
| **ImageNewItem1** |Geef het scherm **Bewerken en maken** weer waarbij elk veld is ingesteld op een standaardwaarde zodat de gebruiker eenvoudig een record kan maken. |De eigenschap **[OnSelect](controls/properties-core.md)** van de afbeelding is ingesteld op deze formule:<br> **NewForm (EditForm1);<br>Navigeren (EditScreen1, Geen)** |
| **NextArrow1** (in de galerie) |Geef het venster **Details** weer om veel of alle velden van de geselecteerde record te bekijken. |De eigenschap **[OnSelect](controls/properties-core.md)** van de pijl is ingesteld op deze formule:<br>**Navigeren (DetailScreen1, Geen)** |

Het primaire besturingselement in het scherm **BrowseGallery1** beslaat het grootste gedeelte van het scherm. De gebruiker kan door de galerie bladeren om een specifieke record te vinden om meer velden weer te geven of bij te werken.

Stel de eigenschap **[Items](controls/properties-core.md)** van een galerie in voor weergave van records van een gegevensbron die erin zit. Stel bijvoorbeeld die eigenschap in op **Assets** om records uit een gegevensbron met die naam weer te geven.

> [!NOTE]
> In een gegenereerde app is **[Items](controls/properties-core.md)** standaard ingesteld op een aanzienlijk gecompliceerdere formule zodat de gebruiker records kan sorteren en ernaar zoeken. Verderop in dit onderwerp leert u die formule te bouwen. De eenvoudigere versie is voorlopig voldoende.

In plaats van een record te zoeken om weer te geven of te bewerken, kan de gebruiker een record maken door het symbool '+' boven de galerie te selecteren. U kunt dit effect creëren door een besturingselement voor **[Afbeelding](controls/control-image.md)** toe te voegen, er een '+'-symbool in weer te geven, en de eigenschap **[OnSelect](controls/properties-core.md)** ervan op deze formule in te stellen:
<br>**NewForm (EditForm1); Navigeren (EditScreen1, Geen)**

Met deze formule wordt het scherm **Bewerken en maken** geopend, met een besturingselement **[Formulier bewerken](controls/control-form-detail.md)** met de naam **EditForm1**. De formule verandert dat formulier ook in de modus **Nieuw** waarin het formulier de standaardwaarden van de gegevensbron weergeeft zodat de gebruiker gemakkelijk een record kan maken.

Als u een besturingselement dat wordt weergegeven in **BrowseGallery1** wilt onderzoeken, selecteert u dat besturingselement in de eerste sectie van die galerie, die als een sjabloon voor alle andere secties fungeert. Selecteer bijvoorbeeld het middelste besturingselement **[Label](controls/control-text-box.md)** aan de linkerkant:

![Besturingselementen van bladerscherm](./media/working-with-forms/afd-browse-gallery-controls.png)

In dit voorbeeld is de eigenschap van het besturingselement **[Tekst](controls/properties-core.md)** ingesteld op **ThisItem.AssignedTo**. Dit is een veld in de gegevensbron **Assets**. De eigenschap **[Text](controls/properties-core.md)** van de andere drie besturingselementen **[Label](controls/control-text-box.md)** in de galerie zijn ingesteld op vergelijkbare formules en elk besturingselement toont een ander veld in de gegevensbron.  

Selecteer het besturingselement **[Vorm](controls/control-shapes-icons.md)** (de pijl) en controleer of de eigenschap **[OnSelect](controls/properties-core.md)** is ingesteld op deze formule:
<br>**Navigeren (DetailScreen1, Geen)**

Als de gebruiker een record vindt in **BrowseGallery1** kan de gebruiker de pijl van die record selecteren om meer informatie erover weer te geven in **DetailScreen1**. Als u een pijl selecteert, wijzigt de gebruiker de waarde van de eigenschap **Geselecteerd** van **BrowseGallery1**. In deze app bepaalt die eigenschap welke record wordt weergegeven, niet alleen in **DetailScreen1** maar ook het scherm **Bewerken en maken** als de gebruiker besluit de record bij te werken.

### <a name="detail-screen"></a>Detailscherm
![Besturingselementen van detailscherm](./media/working-with-forms/afd-detail-screen-basic.png)

Dit scherm bevat functies voor deze belangrijke formules:

| Besturingselement | Ondersteund gedrag | Formule |
| --- | --- | --- |
| **DetailForm1** |Geeft een record weer in de gegevensbron **Assets** |Stel de eigenschap **[DataSource](controls/control-form-detail.md)** in op **Assets**. |
| **DetailForm1** |Bepaalt welke record moet worden weergegeven. Toont in een gegenereerde app de record die de gebruiker heeft geselecteerd in de galerie. |Stel de eigenschap **[Item](controls/control-form-detail.md)** van dit besturingselement in op deze waarde:<br>**BrowseGallery1.Selected** |
| **[Kaart](controls/control-card.md)**-besturingselementen |Toont in een besturingselement **[Formulier weergeven](controls/control-form-detail.md)** één veld in een record. |Stel de eigenschap **[DataField](controls/control-card.md)** in op de naam van een veld tussen dubbele aanhalingstekens (bijvoorbeeld **"Naam"**). |
| **ImageBackArrow1** |Wanneer de gebruiker dit besturingselement selecteert, wordt **BrowseScreen1** geopend. |Stel de eigenschap **[OnSelect](controls/properties-core.md)** in op deze formule:<br>**Back()** |
| **ImageDelete1** |Wanneer de gebruiker dit besturingselement selecteert, wordt er een record verwijderd. |Stel de eigenschap **[OnSelect](controls/properties-core.md)** in op deze formule:<br>**Verwijderen (Assets, BrowseGallery1.Selected)** |
| **ImageEdit1** |Wanneer de gebruiker dit besturingselement selecteert, wordt het scherm **Bewerken en maken** in de huidige record geopend. |Stel de eigenschap **[OnSelect](controls/properties-core.md)** in op deze formule:<br>**Navigeren (EditScreen1, Geen)** |

Boven aan het scherm staan drie afbeeldingen buiten **DetailForm1** en deze fungeren als knoppen waarmee u tussen de drie schermen van de app kunt schakelen.

**DetailForm1** is het belangrijkst in dit scherm en geeft de record weer die de gebruiker heeft geselecteerd in de galerie (omdat de eigenschap **[Item](controls/control-form-detail.md)** van het formulier is ingesteld op **BrowseGallery1.Selected**). De eigenschap **[DataSource](controls/control-form-detail.md)** van het formulier bevat ook metagegevens over de gegevensbron, zoals een beschrijvende weergavenaam voor elk veld.

**DetailForm1** bevat verschillende **[Kaart](controls/control-card.md)**-besturingselementen. U kunt een het besturingselement **[Kaart](controls/control-card.md)** zelf selecteren of het besturingselement dat erin zit voor aanvullende informatie.

![Kaarten en kaart-besturingselementen die zijn geselecteerd in de ervaring van de ontwerper](./media/working-with-forms/afd-detail-card-controls.png)

De eigenschap **[DataField](controls/control-card.md)** van een **[Kaart](controls/control-card.md)**-besturingselement bepaalt welk veld van de kaart wordt weergegeven. In dit geval is die eigenschap ingesteld op **AssetID**. De kaart bevat een besturingselement **[Label](controls/control-text-box.md)** waarvoor de eigenschap **[Text](controls/properties-core.md)** is ingesteld op **Parent.Default**. Dit besturingselement toont de **Standaard**waarde voor de kaart. Deze is ingesteld via de eigenschap **[DataField](controls/control-card.md)**.

In een gegenereerde app zijn **[Kaart](controls/control-card.md)**-besturingselementen standaard vergrendeld. Wanneer een kaart is vergrendeld, kunt u enkele eigenschappen zoals **[DataField](controls/control-card.md)** niet wijzigen, en de formulebalk is niet beschikbaar voor deze eigenschappen. Deze beperking zorgt ervoor dat uw aanpassingen de basisfunctionaliteit van de gegenereerde app niet verbreken. U kunt echter enkele eigenschappen van een kaart en de bijbehorende besturingselementen in het rechterdeelvenster wijzigen:

![Detailscherm met geopend deelvenster Opties](./media/working-with-forms/detail-screen-new.png)

In het rechterdeelvenster kunt u bepalen welke velden moeten worden weergegeven en in welk soort besturingselement elk veld wordt getoond.

### <a name="editcreate-screen"></a>Scherm voor bewerken/maken
![Besturingselementen van het scherm Bewerken](./media/working-with-forms/afd-edit-screen-basic.png)

Dit scherm bevat functies voor deze belangrijke formules:

| Besturingselement | Ondersteund gedrag | Formule |
| --- | --- | --- |
| **EditForm1** |Geeft een record weer in de gegevensbron **Assets**. |Stel de eigenschap **[DataSource](controls/control-form-detail.md)** in op **Assets**. |
| **EditForm1** |Bepaalt welke record moet worden weergegeven. Toont in een gegenereerde app de record die de gebruiker heeft geselecteerd in **BrowseScreen1**. |Stel de eigenschap **[Item](controls/control-form-detail.md)** in op deze waarde:<br>**BrowseGallery1.Selected** |
| **[Kaart](controls/control-card.md)**-besturingselementen |Biedt in een besturingselement **[Formulier bewerken](controls/control-form-detail.md)** besturingselementen waarmee een gebruiker een of meer velden in een record kan bewerken. |Stel de eigenschap **[DataField](controls/control-card.md)** in op de naam van een veld tussen dubbele aanhalingstekens (bijvoorbeeld **"Naam"**). |
| **ImageCancel1** |Wanneer de gebruiker dit besturingselement selecteert, worden wijzigingen die worden uitgevoerd genegeerd en wordt het scherm **Details** geopend. |Stel de eigenschap **[OnSelect](controls/properties-core.md)** in op deze formule:<br>**ResetForm (EditForm1); Terug()** |
| **ImageAccept1** |Wanneer de gebruiker dit besturingselement selecteert, worden wijzigingen aan de gegevensbron verzonden. |Stel de eigenschap **[OnSelect](controls/properties-core.md)** in op deze formule:<br>**SubmitForm (EditForm1)** |
| **EditForm1** |Als wijzigingen worden geaccepteerd, wordt u teruggeleid naar het vorige scherm. |Stel de eigenschap **[OnSuccess](controls/control-form-detail.md)** in op deze formule:<br>**Back()** |
| **EditForm1** |Als er wijzigingen niet worden geaccepteerd, blijft u op het huidige scherm zodat de gebruiker eventuele problemen kan herstellen en de wijzigingen opnieuw indienen. |Laat de eigenschap **[OnFailure](controls/control-form-detail.md)** leeg. |
| **LblFormError1** |Als de wijzigingen niet zijn geaccepteerd, wordt er een foutbericht weergegeven. |Stel de eigenschap **[Text](controls/properties-core.md)** in op deze waarde:<br>**EditForm1.Error** |

Zoals in het scherm **Details** bepaalt een formulierbesturingselement met de naam **EditForm1** het scherm **Bewerken en maken**. Bovendien is de eigenschap **[Item](controls/control-form-detail.md)** van **EditForm1** ingesteld op **BrowseGallery1.Selected** zodat het formulier de record weergeeft die de gebruiker heeft geselecteerd geeft in **BrowseScreen1**. Het scherm **Details** toont elk veld als alleen-lezen, maar de gebruiker kan de waarde van een of meer velden bijwerken met behulp van de besturingselementen in **EditForm1**. Ook de eigenschap **[DataSource](controls/control-form-detail.md)** wordt gebruikt voor toegang tot metagegevens voor deze gegevensbron, zoals de beschrijvende weergavenaam voor elk veld en de locatie waar de wijzigingen moeten worden opgeslagen.

Als de gebruiker het pictogram 'X' selecteert om een update te annuleren, negeert de functie **[ResetForm](functions/function-form.md)** alle niet-opgeslagen wijzigingen. Met de functie **[Back](functions/function-navigate.md)** wordt het scherm **Details** geopend. Zowel het scherm **Details** als het scherm **bewerken en maken** toont dezelfde record totdat de gebruiker een andere selecteert op **BrowseScreen1**. De velden in die record blijven ingesteld op de waarden die het laatst zijn opgeslagen, en niet de wijzigingen die de gebruiker heeft gemaakt en vervolgens heeft weggegooid.

Als de gebruiker een of meer waarden in het formulier wijzigt en vervolgens het vinkje selecteert, verzendt de functie **[SubmitForm](functions/function-form.md)** de wijzigingen van de gebruiker naar de gegevensbron.

* Als de wijzigingen zijn opgeslagen, wordt de formule van het formulier **[OnSuccess](controls/control-form-detail.md)** uitgevoerd. De functie **Back** opent het detailscherm om de bijgewerkte record te tonen.
* Als de wijzigingen niet zijn opgeslagen, wordt de formule van het formulier **[OnFailure](controls/control-form-detail.md)** uitgevoerd, maar hierdoor wijzigt er niets omdat het *leeg* is. Het scherm **Bewerken en maken** blijft geopend zodat de gebruiker de wijzigingen kan annuleren of de fout kan oplossen. **LblFormError1** toont een beschrijvend foutbericht waarop de eigenschap **Fout** van het formulier is ingesteld.

Net als bij een besturingselement **[Formulier weergeven](controls/control-form-detail.md)** bevat een besturingselement **[Formulier bewerken](controls/control-form-detail.md)** **[Kaart](controls/control-card.md)**-besturingselementen die weer andere besturingselementen bevatten die verschillende velden in een record weergeven:

![Kaarten en kaart-besturingselementen bewerken die zijn geselecteerd in de ervaring van de ontwerper](./media/working-with-forms/afd-edit-card-controls.png)

In de voorgaande afbeelding toont de geselecteerde kaart het veld **AssetID** en een besturingselement **[Tekstinvoer](controls/control-text-input.md)** zodat de gebruiker de waarde van dat veld kan bewerken. (Het detailscherm toont daarentegen hetzelfde veld in een besturingselement **[Label](controls/control-text-box.md)**, die alleen-lezen is.) Het besturingselement **[Tekstinvoer](controls/control-text-input.md)** heeft een eigenschap **[Standaard](controls/properties-core.md)** die is ingesteld op **Parent.Default**. Als de gebruiker een record zou maken in plaats van bewerken, zou dat besturingselement een aanvankelijke waarden weergeven die waarde de gebruiker voor een nieuwe record kan wijzigen.

In het rechterdeelvenster kunt u elke kaart weergeven of verbergen, rangschikken of ze configureren om velden weer te geven in verschillende typen besturingselementen.

![Scherm Bewerken met geopend deelvenster Opties](./media/working-with-forms/edit-screen.png)

## <a name="build-an-app-from-scratch"></a>Een volledig nieuwe app bouwen
Door te begrijpen hoe PowerApps een app genereert, kunt u er zelf eentje bouwen die gebruikmaakt van dezelfde bouwstenen en formules die eerder in dit onderwerp zijn besproken.

## <a name="identify-test-data"></a>Testgegevens identificeren
Begin met een gegevensbron die u kunt gebruiken om te experimenteren om het meeste uit dit onderwerp te halen. De gegevensbron moet testgegevens bevatten die u zonder consequenties kunt lezen en bijwerken.

> [!NOTE]
> Als u een gegevensbron gebruikt die bestaat uit een SharePoint-lijst of een Excel-tabel met kolomnamen met spaties, worden de spaties in PowerApps vervangen door **‘\_x0020\_’**. **'Kolom twaalf'** in SharePoint of Excel wordt bijvoorbeeld weergegeven als **'Kolom_x0020_twaalf'** in PowerApps wanneer de naam wordt weergegeven in de gegevensindeling of wordt gebruikt in een formule.

Om de rest van dit onderwerp exact te kunnen volgen, maakt u een SharePoint-lijst met de naam "Ice Cream" met deze gegevens:

![SharePoint-lijst Ice Cream](./media/working-with-forms/sharepointlist-icecream.png)

* Maak een volledig nieuwe app, voor telefoons, en [verbind deze met uw gegevensbron](add-data-connection.md).
  
    > [!NOTE]
  > Tablet-apps zijn vergelijkbaar, maar u wilt wellicht een andere [indeling van het startscherm](#screen-design) om de extra ruimte te benutten.
  
    De voorbeelden in de rest van het onderwerp zijn gebaseerd op een gegevensbron met de naam **Ice Cream**.

## <a name="browse-records"></a>Bladeren in records
U kunt snel wat informatie uit een record halen door deze te zoeken in een galerie op een bladerscherm.

1. Voeg een galerie van het type **Verticaal** toe en wijzig de indeling in **Alleen titel**.
   
    ![Galerie verbonden met de gegevensbron Ice Cream](./media/working-with-forms/new-gallery.png)
2. Stel de eigenschap **[Items](controls/properties-core.md)** van de galerie in op **Ice Cream**.
3. Stel de eigenschap **[Tekst](controls/properties-core.md)** van het eerste label in de galerie in op **ThisItem.Title** als de eigenschap nu op iets anders is ingesteld.
   
    Het label bevat nu de waarde in het veld **Titel** voor elke record.
   
    ![Galerie verbonden met de gegevensbron Ice Cream](./media/working-with-forms/new-gallery-2.png)
4. Maak de galerie schermvullend en stel de eigenschap **[TemplateSize](controls/control-gallery.md)** van de galerie in op **60**.
   
    Het scherm lijkt op dit voorbeeld met alle records in de gegevensbron:
   
    ![Galerie verbonden met de gegevensbron Ice Cream](./media/working-with-forms/new-gallery-icecream.png)

## <a name="view-details"></a>Details weergeven
Als de galerie niet de informatie weergeeft die u wilt, selecteert u de pijl zodat de record het detailscherm opent. Een besturingselement **[Formulier weergeven](controls/control-form-detail.md)** op dit scherm bevat meer, zo niet alle, velden voor de record die u hebt geselecteerd.

Het besturingselement **[Formulier weergeven](controls/control-form-detail.md)** gebruikt twee eigenschappen voor weergave van de record:

* eigenschap **[DataSource](controls/control-form-detail.md)**.  De naam van de gegevensbron die de record bevat. Deze eigenschap vult het rechterdeelvenster met velden en bepaalt de weergavenaam en het gegevenstype (tekenreeks, getal, datum enz.) van elk veld.  
* eigenschap **[Item](controls/control-form-detail.md)**.  De record die moet worden weergegeven.  Deze eigenschap is vaak verbonden met de eigenschap **Geselecteerd** van het besturingselement **[Galerie](controls/control-gallery.md)** zodat de gebruiker een record kan selecteren in het besturingselement **[Galerie](controls/control-gallery.md)** en vervolgens omlaag gaan in die record.

Wanneer de eigenschap **[DataSource](controls/control-form-detail.md)** is ingesteld, kunt u velden toevoegen en verwijderen in het rechterdeelvenster en wijzigen hoe ze worden weergegeven.

In dit scherm kunnen gebruikers niet per ongeluk of met opzet waarden van de record wijzigen. Het besturingselement **[Formulier weergeven](controls/control-form-detail.md)** is alleen-lezen, dus er worden geen records gewijzigd.

Een besturingselement **[Formulier weergeven](controls/control-form-detail.md)** toevoegen:

1. Voeg een scherm toe, en voeg er vervolgens een besturingselement **[Formulier weergeven](controls/control-form-detail.md)** aan toe
2. Stel de eigenschap **[DataSource](controls/control-form-detail.md)** van het formulierbesturingselement in op **'Ice Cream'**.

U kunt in het rechterdeelvenster de velden selecteren die u op uw scherm wilt weergeven en welk type kaart voor elk veld moet worden weergegeven. Wanneer u wijzigingen aanbrengt in het rechterdeelvenster wordt de eigenschap **[DataField](controls/control-card.md)** op elk **[Kaart](controls/control-card.md)**-besturingselement ingesteld op het veld waarmee de gebruiker gaat communiceren. Het scherm moet lijken op het volgende voorbeeld:

![Formulier weergeven voor gegevensbron Ice Cream](./media/working-with-forms/ice-cream-new.png)

Ten slotte moet we het besturingselement **[Formulier weergeven](controls/control-form-detail.md)** verbinden met het besturingselement **[Galerie](controls/control-gallery.md)** zodat we details voor een bepaalde record kunnen bekijken.  Als we klaar zijn met het instellen van de eigenschap **[Item](controls/control-form-detail.md)** wordt de eerste record uit de galerie weergegeven in het formulier.

* Stel de eigenschap **[Item](controls/control-form-detail.md)** van het besturingselement **[Formulier weergeven](controls/control-form-detail.md)** in op **Gallery1.Selected**.
   
    De details voor het geselecteerde item worden in het formulier weergegeven.
   
    ![Formulier weergeven voor de gegevensbron Ice Cream, verbonden met het besturingselement Galerie](./media/working-with-forms/view-form-select-coconut.png)

Geweldig!  We gaan nu naar navigatie: hoe een gebruiker het detailscherm vanaf het galeriescherm opent en andersom.

* Voeg een **[knop](controls/control-button.md)** besturingselement toe aan het scherm, stel de eigenschap **[Tekst](controls/properties-core.md)** in op de weergave van **[Terug](functions/function-navigate.md)** en stel de bijbehorende eigenschap **[OnSelect](controls/properties-core.md)** in op **Terug()**.
   
    Met deze formule gaat de gebruiker terug naar de galerie wanneer hij de details heeft bekeken.

    ![Formulier weergeven voor gegevensbron Ice Cream met knop Terug](./media/working-with-forms/viewform-icecream-back.png)

Nu gaan we terug naar het besturingselement **[Galerie](controls/control-gallery.md)** en voegen navigatie toe aan ons detailscherm.

1. Schakel naar het eerste scherm, dat als host fungeert voor ons besturingselement **[Galerie](controls/control-gallery.md)** en selecteer de pijl in het eerste item in de galerie.

2. Stel de eigenschap **[OnSelect](controls/properties-core.md)** van de vorm in op deze formule:
   <br>**Navigeren (Screen2, Geen)**
   
    ![Formulier weergeven voor gegevensbron Ice Cream met knop Terug](./media/working-with-forms/gallery-icecream-nav-new.png)

3. Druk op F5 en selecteer vervolgens een pijl in de galerie om de details van het item weer te geven.

4. Selecteer de knop **[Terug](functions/function-navigate.md)** om terug te keren naar de galerie met producten en druk op Esc.

## <a name="editing-details"></a>Details bewerken
Ten slotte is onze laatste belangrijke activiteit het wijzigen van de inhoud van een record. Gebruikers kunnen dit doen in een besturingselement **[Formulier bewerken](controls/control-form-detail.md)**.

Het besturingselement **[Formulier bewerken](controls/control-form-detail.md)** gebruikt twee eigenschappen voor weergave en bewerking van de record:

* eigenschap **[DataSource](controls/control-form-detail.md)**.  De naam van de gegevensbron die de record bevat.  Net als met het besturingselement **[Formulier weergeven](controls/control-form-detail.md)** vult deze eigenschap het rechterdeelvenster met velden en bepaalt de weergavenaam en het gegevenstype (tekenreeks, getal, datum enz.) voor elk veld. Deze eigenschap bepaalt ook of de waarde van elk veld geldig is voordat deze naar de onderliggende gegevensbron wordt verzonden.
* eigenschap **[Item](controls/control-form-detail.md)**.  De record om te bewerken, die vaak is verbonden met de eigenschap **Geselecteerd** van het besturingselement **[Galerie](controls/control-gallery.md)**. Op die manier kunt u een record in het besturingselement **[Galerie](controls/control-gallery.md)** selecteren, deze weergeven in het detailscherm en bewerken in het scherm **Bewerken en maken**.

Een besturingselement **[Formulier bewerken](controls/control-form-detail.md)** toevoegen:

1. Voeg een scherm toe, voeg een besturingselement **[Formulier bewerken](controls/control-form-detail.md)** toe en stel vervolgens de eigenschap **[DataSource](controls/control-form-detail.md)** van het formulier in op **'Ice Cream'**.
2. Stel de eigenschap **[Item](controls/control-form-detail.md)** in op **Gallery1.Selected**.

Nu kunt u de velden selecteren die u wilt weergeven op uw scherm. U kunt ook het type kaart selecteren dat u wilt weergeven voor elk veld. Wanneer u wijzigingen aanbrengt in het rechterdeelvenster wordt de eigenschap **[DataField](controls/control-card.md)** op elk **[Kaart](controls/control-card.md)**-besturingselement ingesteld op het veld waarmee uw gebruiker gaat communiceren.  Het scherm moet lijken op het volgende voorbeeld:

![Formulier weergeven voor gegevensbron Ice Cream](./media/working-with-forms/icecream-edit.png)

Deze twee eigenschappen zijn dezelfde als de eigenschappen op het besturingselement **[Formulier weergeven](controls/control-form-detail.md)**.  En met alleen deze kunnen we de details van een record weergeven.  

Het besturingselement **[Formulier bewerken](controls/control-form-detail.md)** gaat verder door de mogelijkheid voor de functie **[SubmitForm](functions/function-form.md)** om wijzigingen terug te schrijven naar de gegevensbron. U gebruikt dit met een knop- of afbeeldingsbesturingselement voor het opslaan van wijzigingen van een gebruiker.

* Voeg een **[knop](controls/control-button.md)** besturingselement toe, stel de eigenschap **[Tekst](controls/properties-core.md)** in op de weergave van **Opslaan** en stel de bijbehorende eigenschap **[OnSelect](controls/properties-core.md)** in op deze formule:<br>
  **SubmitForm (Form1)**

![Formulier bewerken voor gegevensbron Ice Cream](./media/working-with-forms/edit-icecream-save.png)

Navigatie toevoegen naar en vanaf dit scherm:

1. Voeg nog een **[knop](controls/control-button.md)** besturingselement toe, stel de eigenschap **[Tekst](controls/properties-core.md)** in op de weergave van **Annuleren** en stel de bijbehorende eigenschap **[OnSelect](controls/properties-core.md)** in op deze formule: <br>**ResetForm (Form1 ); Terug()**
   
    Met deze formule worden alle niet-opgeslagen wijzigingen geannuleerd en opent u het vorige scherm.
   
    ![Formulier weergeven voor gegevensbron Ice Cream](./media/working-with-forms/edit-icecream-cancel.png)
2. Stel de eigenschap **[OnSuccess](controls/control-form-detail.md)** van het formulier in op **Terug()**.
   
    Wanneer updates zijn opgeslagen opent het vorige scherm (in dit geval wordt het detailscherm details) automatisch.
   
    ![Formulier bewerken met toegevoegde "OnSuccess"-regel](./media/working-with-forms/edit-icecream-onsuccess.png)
3. Voeg op het scherm **Weergave** een knop toe, stel de eigenschap **[Tekst](controls/properties-core.md)** in op de weergave van **Bewerken** en stel de bijbehorende eigenschap **[OnSelect](controls/properties-core.md)** in op deze formule:<br> **Navigeren (Screen3, Geen)**
   
    ![Formulier weergeven met toegevoegde knop 'Bewerken'](./media/working-with-forms/viewform-icecream-edit.png)

U hebt een basic app gemaakt met drie schermen voor de weergave en het invoeren van gegevens.  Probeer het uit, geef het scherm Galerie weer en druk vervolgens op F5 (of selecteer de knop "Voorbeeld"-knop met de pijl naar rechts nabij de linkerbovenhoek van het scherm). De roze stip geeft aan waar de gebruiker klikt of op het scherm tikt bij op elke stap.

![De app Ice Cream uitproberen](./media/working-with-forms/try-icecream.png)

## <a name="create-a-record"></a>Een record maken
De gebruiker communiceert met hetzelfde formulier **Bewerken** voor zowel het bijwerken als het maken van records. Wanneer de gebruiker een record wil maken, schakelt de functie **[NewForm](functions/function-form.md)** het formulier naar de modus **Nieuw**.

Wanneer het formulier in de modus **Nieuw** staat, wordt de waarde van elk veld ingesteld op de standaardinstellingen van de gegevensbron. De record die wordt opgegeven voor de eigenschap **[Item](controls/control-form-detail.md)** van het formulier wordt genegeerd.  

Wanneer de gebruiker gereed is de nieuwe record op te slaan, wordt **[SubmitForm](functions/function-form.md)** uitgevoerd. Nadat het formulier is verzonden, schakelt het formulier naar **EditMode**.  

Op het eerste scherm, voegt u een knop **Nieuw** toe:

1. Voeg op het scherm met de galerie een besturingselement **[Knop](controls/control-button.md)** toe.
2. Stel de eigenschap **[Text](controls/properties-core.md)** van de knop in op **Nieuw** en de eigenschap **[OnSelect](controls/properties-core.md)** ervan in op deze formule:<br>
   **NewForm (Form1); Navigeren (Screen3, Geen)**
   
    Deze formule schakelt het besturingselement **[Formulier bewerken](controls/control-form-detail.md)** op **Screen3** naar de modus **Nieuw** en opent dat scherm zodat de gebruiker het kan invullen.

![Formulier weergeven met toegevoegde knop 'Bewerken'](./media/working-with-forms/gallery-icecream-new.png)

Wanneer het scherm Bewerken en maken wordt geopend, is het formulier leeg zodat de gebruiker een item kan toevoegen. Wanneer de gebruiker de knop **Opslaan** selecteert, zorgt de functie **[SubmitForm](functions/function-form.md)** ervoor dat er een record wordt gemaakt in plaats van wordt bijgewerkt. Als de gebruiker kiest voor de knop **Annuleren**, schakelt de functie **[ResetForm](functions/function-form.md)** het formulier terug naar de modus **Bewerken** en opent de functie **[Back](functions/function-navigate.md)** het scherm voor het zoeken in de galerie.

## <a name="delete-a-record"></a>Een record verwijderen
1. Voeg op het scherm **Weergave** een knop toe en stel de eigenschap **[Tekst](controls/properties-core.md)** in voor het weergeven van **Verwijderen**...
2. Stel de eigenschap **[OnSelect](controls/properties-core.md)** van de knop in op deze formule:
   <br>**Verwijderen ('Ice Cream', Gallery1.Selected ); Terug()**
   
    ![Formulier weergeven met toegevoegde knop 'Bewerken'](./media/working-with-forms/viewform-icecream-remove.png)

## <a name="handling-errors"></a>Afhandeling van fouten
In deze app treedt een fout op wanneer de waarde van een veld niet geldig is, een verplicht veld leeg is, u niet bent verbonden met het netwerk of er zich andere problemen voordoen.  

Als **[SubmitForm](functions/function-form.md)** om een bepaalde reden mislukt, bevat de eigenschap **Fout** van het besturingselement **[Formulier bewerken](controls/control-form-detail.md)** een foutbericht dat aan de gebruiker wordt getoond. Met deze informatie moet de gebruiker het probleem kunnen oplossen en de wijziging opnieuw verzenden. De gebruiker kan ook de update annuleren.

1. Voeg op het scherm Bewerken en maken een besturingselement **[Label](controls/control-text-box.md)** toe en verplaatst dit naar vlak onder de knop **Opslaan**. Eventuele foutmeldingen zijn duidelijk zichtbaar nadat de gebruiker dit besturingselement selecteert voor het opslaan van wijzigingen.

2. Stel de eigenschap **[Text](controls/properties-core.md)** van het besturingselement **[Label](controls/control-text-box.md)** in voor weergave van **Form1.Error**.

    ![Formulier weergeven met toegevoegde knop 'Bewerken'](./media/working-with-forms/edit-icecream-error.png)

In een app die PowerApps genereert op basis van gegevens, wordt de eigenschap **[AutoHeight](controls/control-text-box.md)** voor dit besturingselement ingesteld op *true* zodat er geen ruimte wordt gebruikt als er geen fout optreedt. De eigenschappen **[Hoogte](controls/properties-size-location.md)** en **[Y](controls/properties-size-location.md)** van het besturingselement **[Formulier bewerken](controls/control-form-detail.md)** worden ook dynamisch aangepast zodat dit besturingselement kan groeien wanneer er een fout optreedt. Genereer voor meer informatie een app uit de bestaande gegevens en inspecteer deze eigenschappen. Het tekstvakbesturingselement voor fouten is zeer kort wanneer er geen fout is opgetreden. U moet mogelijk de weergave **Geavanceerd** openen (beschikbaar op het tabblad **Weergave**) om dit besturingselement te selecteren.

![App van formulier voor het bewerken van gegevens met tekstvak met fout geselecteerd](./media/working-with-forms/edit-assets-error1.png)

![App van formulier voor het bewerken van gegevens met formulierbesturingselement geselecteerd](./media/working-with-forms/edit-assets-error2.png)

## <a name="refresh-data"></a>Gegevens vernieuwen
De gegevensbron wordt vernieuwd wanneer de gebruiker de app opent, maar de gebruiker wil mogelijk de records in de galerie vernieuwen zonder de app te sluiten. Voeg een knop **Vernieuwen** toe waarmee de gebruiker de gegevens handmatig kan vernieuwen:

1. Voeg op het scherm met het besturingselement **[Galerie](controls/control-gallery.md)** een **[Knop](controls/control-button.md)**-besturingselement toe en stel de eigenschap **[Tekst](controls/properties-core.md)** in zodat **Vernieuwen** wordt weergegeven.

2. Stel de eigenschap **[OnSelect](controls/properties-core.md)** van dit besturingselement in op deze formule:<br> **Vernieuwen ('Ice Cream')**

    ![De gegevensbron vernieuwen](./media/working-with-forms/browse-icecream-refresh.png)

## <a name="search-and-sort-the-gallery"></a>De galerie sorteren en doorzoeken
In de app die PowerApps heeft gegenereerd op basis van gegevens, zijn we vergeten twee besturingselementen te bespreken die boven aan het scherm Bladeren staan. Met deze besturingselementen kan de gebruiker een of meer records zoeken, de lijst met records sorteren in oplopende of aflopende volgorde of allebei.

![Besturingselementen sorteren en zoeken op het scherm Bladeren](./media/working-with-forms/afd-browse-search-sort.png)

Wanneer de gebruiker de knop Sorteren selecteert, wordt de sorteervolgorde van de galerie omgekeerd. We gebruiken voor het maken van dit gedrag een *contextvariabele* voor het bijhouden van de volgorde waarin de galerie wordt gesorteerd. Wanneer de gebruiker de knop selecteert, wordt de variabele bijgewerkt en de volgorde omgekeerd. De eigenschap **[OnSelect](controls/properties-core.md)** van de knop Sorteren is ingesteld op deze formule: **UpdateContext( {SortDescending1: !SortDescending1} )**

De functie **[UpdateContext](functions/function-updatecontext.md)** maakt de contextvariabele **SortDescending1** als deze nog niet bestaat. De functie leest de waarde van de variabele en stelt deze in op het logische tegenovergestelde met behulp van het **!** . Als de waarde *true* is, wordt deze *false*. Als de waarde *false* is, wordt deze *true*.

De formule voor de eigenschap **[Items](controls/properties-core.md)** van het besturingselement **[Galerie](controls/control-gallery.md)** maakt gebruik van deze contextvariabele, samen met de tekst in het besturingselement **TextSearchBox1**:

    Gallery1.Items = Sort( If( IsBlank(TextSearchBox1.Text),
                               Assets,
                               Filter( Assets,
                                       TextSearchBox1.Text in Text(ApproverEmail) ) ),
                            ApproverEmail,
                            If(SortDescending1, Descending, Ascending) )

Laten we dit eens onderverdelen:

* Aan de buitenkant hebben we de functie **[Sort](functions/function-sort.md)** waarvoor drie argumenten zijn: een tabel, een veld waarop moet worden gesorteerd en de sorteervolgorde.  
  
  * De sorteervolgorde wordt uit de contextvariabele gehaald die omschakelt wanneer de gebruiker het besturingselement **ImageSortUpDown1** selecteert. De waarde *true*/*false* wordt omgezet naar de constanten **Aflopend** en **Oplopend**.
  * Het veld waarop wordt gesorteerd is vast ingesteld op **ApproverEmail**. Als u de velden die worden weergegeven in de galerie wijzigt, moet u dit argument ook wijzigen.
* Aan de binnenkant hebben we de functie **[Filter](functions/function-filter-lookup.md)**, waarbij een tabel een argument is en een expressie om te evalueren voor elke record.
  
  * De tabel is de onbewerkte gegevensbron **Assets**. Dit is het beginpunt voordat er wordt gefilterd of gesorteerd.
  * De expressie zoekt een exemplaar van de tekenreeks in **TextSearchBox1** binnen het veld **ApproverEmail**.  Ook hier geldt weer: als u de velden die worden weergegeven in de galerie wijzigt, moet u ook dit argument bijwerken.
  * Als **TextSearchBox1** leeg is, wil de gebruiker alle records weergeven en wordt de functie **[Filteren](functions/function-filter-lookup.md)** overgeslagen.

Dit is maar één voorbeeld. U kunt uw eigen formule maken voor de eigenschap **[Items](controls/properties-core.md)**, afhankelijk van de behoeften van uw app, door de eigenschappen  **[Filteren](functions/function-filter-lookup.md)**, **[Sorteren](functions/function-sort.md)** en andere functies en operators samen te maken.    

## <a name="screen-design"></a>Schermontwerp
Tot nu toe hebben we nog geen andere manieren besproken om besturingselementen over meerdere schermen te distribueren. Dit komt omdat er veel opties zijn, en de beste selectie is afhankelijk van de behoeften van uw specifieke app.

Onroerend goed is op telefoonschermen nogal beperkt dus mogelijk wilt u op verschillende schermen kunnen bladeren, weergeven en bewerken/maken. In dit onderwerp, openen de functies **[Navigate](functions/function-navigate.md)** en **[Back](functions/function-navigate.md)** elk van de schermen.  

Op een tablet kunt u bladeren, weergeven en bewerken/maken op twee of zelfs één scherm. Voor de laatstgenoemde zijn de functies **[Navigate](functions/function-navigate.md)** of **[Back](functions/function-navigate.md)** vereist.

Als de gebruiker op hetzelfde scherm werkt, moet u erop letten dat de gebruiker de selectie in de **[Galerie](controls/control-gallery.md)** niet kan wijzigen en mogelijk bewerkingen in het besturingselement **[Formulier bewerken](controls/control-form-detail.md)** kan kwijtraken.  Om te voorkomen dat de gebruiker een andere record selecteert wanneer wijzigingen aan een andere record nog niet zijn opgeslagen, stelt u de eigenschap **[Uitgeschakeld](controls/properties-core.md)** van de galerie in op deze formule:<br>
**EditForm.Unsaved**

