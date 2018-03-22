---
title: Een lijst met items weergeven | Microsoft Docs
description: Gebruik een galerie om een lijst met items in uw app weer te geven, en filter de lijst door een criterium op te geven.
services: ''
suite: powerapps
documentationcenter: na
author: karthik-1
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/28/2017
ms.author: sharik
ms.openlocfilehash: 04499f276e179fe6b57103a3d28a68ba6fe6b7bb
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2018
---
# <a name="show-a-list-of-items-in-powerapps"></a>Een lijst met items weergeven in PowerApps
U kunt een lijst met items van een gegevensbron weergeven door het besturingselement **[Galerie](controls/control-gallery.md)** toe te voegen aan uw app. In dit onderwerp wordt Excel gebruikt als gegevensbron. Filter de lijst door het besturingselement **Galerie** zodanig te configureren dat alleen de items die voldoen aan het filtercriterium worden weergegeven in een besturingselement **[Tekstinvoer](controls/control-text-input.md)**.

## <a name="prerequisites"></a>Vereisten
* Lees hoe u [een besturingselement kunt toevoegen en configureren](add-configure-controls.md) in PowerApps.

* De voorbeeldgegevens instellen:
    1. Download [dit Excel-bestand](https://az787822.vo.msecnd.net/documentation/get-started-from-data/FlooringEstimates.xlsx), dat voorbeeldgegevens bevat voor deze zelfstudie.

    2. Upload het Excel-bestand naar een [cloudopslagaccount](connections/cloud-storage-blob-connections.md), bijvoorbeeld bij OneDrive voor Bedrijven.

## <a name="add-a-gallery-control"></a>Een besturingselement Galerie toevoegen
1. Open PowerApps en klik of tik vervolgens bij de linkerrand op **New**.

2. Klik of tik onder **Lege app** op **Telefoonindeling**.

3. Klik of tik in het dialoogvenster **Welkom bij PowerApps Studio** op **Overslaan**.

4. [Voeg een verbinding toe](add-data-connection.md) aan de tabel **FlooringEstimates** in het Excel-bestand.

5. (optioneel) Voeg een besturingselement **Galerie** toe aan het standaardscherm door te klikken of te tikken op het tabblad **Invoegen**. Klik of tik vervolgens op het tabblad **Galerie** en klik of tik tenslotte op een besturingselement **Galerie** dat leeg is of een standaardset besturingselementen bevat.

    Bij deze opties vindt u ook **Galerie**besturingselementen die horizontaal of verticaal schuiven. U kunt ook een besturingselement **Galerie** toevoegen waarvan de grootte automatisch wordt aangepast aan de hoeveelheid inhoud in elk item.

    ![Galerie toevoegen](./media/add-gallery/gallery-dropdown.png)

6. Op het tabblad **Startpagina** klikt of tikt u op **Nieuw scherm**.

    U kunt een scherm toevoegen dat leeg is, dat schuift of dat een besturingselement **Galerie** of formulier bevat.

7. Klik of tik op **Lijstscherm** om een scherm toe te voegen met een besturingselement **Galerie** en andere besturingselementen, zoals een zoekbalk.

    > [!NOTE]
> Of u nu een **Galerie**-besturingselement toevoegt aan een nieuw of een bestaand scherm, u kunt in de buurt van de onderkant van het **Galerie**-besturingselement klikken of tikken om het te selecteren. Daarna kunt u in het rechterdeelvenster op **Flooring Estimates** klikken of tikken en vervolgens op een andere indeling in het venster **Gegevens** klikken of tikken. In deze zelfstudie gebruikt u de standaardindeling.

    ![De galerie-indeling kiezen](./media/add-gallery/select-layout.png)

8. Klik of tik op het besturingselement **Galerie** in het scherm dat u zojuist hebt toegevoegd.

9. Klik of tik op het tabblad **Eigenschappen** van het rechterdeelvenster op **CustomGallerySample**.

10. Klik of tik in het deelvenster **Gegevens** op **CustomGallerySample** en klik of tik vervolgens op **FlooringEstimates**.

    ![Gegevensbron selecteren](./media/add-gallery/choose-data.png)

    In het besturingselement **Galerie** worden de voorbeeldgegevens weergegeven.

    ![Gegevens weergeven](./media/add-gallery/show-data-default.png)

    Het configureren van sorteren en zoeken wordt verderop in dit onderwerp behandeld.

## <a name="add-a-control-to-the-gallery-control"></a>Een besturingselement toevoegen aan het besturingselement Galerie
Voordat u iets gaat aanpassen, moet u besluiten welke indeling u wilt van de **Galerie**besturingselementen. De eerste set besturingselementen in een **Galerie**besturingselement is de sjabloon die bepaalt hoe alle gegevens in het **Galerie**besturingselement worden weergegeven.

1. Selecteer de sjabloon door onderaan het **Galeriebesturingselement** te klikken of te tikken en vervolgens op het potloodpictogram in de linkerbovenhoek te klikken of te tikken.

    ![Galeriesjabloon bewerken](./media/add-gallery/edit-item.png)

2. Voeg een besturingselement **[Label](controls/control-text-box.md)** toe terwijl de sjabloon nog is geselecteerd en verplaats het en wijzig de grootte zodat deze geen overlap heeft met andere besturingselementen in de sjabloon.

    ![Label toevoegen](./media/add-gallery/add-text-box.png)
3. Open het deelvenster **Gegevens** door de sjabloon te selecteren en vervolgens te klikken of tikken op **Flooring Estimates** in het rechterdeelvenster.

4. Selecteer het label dat u eerder in deze procedure hebt toegevoegd en open vervolgens de gemarkeerde lijst in het deelvenster **Gegevens**.

    ![Vervolgkeuzelijst openen](./media/add-gallery/open-dropdown.png)

5. Klik of tik in die lijst op **Prijs**.

    ![Binding van label wijzigen](./media/add-gallery/change-binding.png)

    In het besturingselement **Galerie** worden de nieuwe gegevens weergegeven.

    ![Definitieve galerie](./media/add-gallery/final-gallery.png)

## <a name="filter-the-gallery-control"></a>Het Galeriebesturingselement filteren
De eigenschap **[Items](controls/properties-core.md)** van een **Galerie**besturingselement bepaalt welke items worden weergegeven. In deze procedure configureert u de eigenschap zodanig dat in het besturingselement **Galerie** alleen de items worden weergegeven waarvan de productnaam de tekst uit **TextSearchBox1** bevat.

![Tekstzoekvak](./media/add-gallery/text-search-box.png)

1. Selecteer het besturingselement **Galerie** door in de buurt van de onderkant van dat besturingselement te klikken of te tikken.

2. Stel op het tabblad **Geavanceerd** de eigenschap **[Items](controls/properties-core.md)** van het besturingselement **Galerie** in op deze formule:

    **If(IsBlank(TextSearchBox1.Text), FlooringEstimates, Filter(FlooringEstimates, TextSearchBox1.Text in Text(Name)))**

    Voor meer informatie over de functies in deze formule raadpleegt u de [naslaginformatie over formules](formula-reference.md).

3. Typ een deel van een productnaam of de volledige productnaam in het zoekvak.

    Het besturingselement **Galerie** bevat alleen de items die voldoen aan het filtercriterium.

## <a name="sort-the-gallery-control"></a>Het Galeriebesturingselement sorteren
De eigenschap **[Items](controls/properties-core.md)** van een **Galerie**besturingselement bepaalt de volgorde waarin de items worden weergegeven. In deze procedure configureert u de eigenschap zodanig dat het besturingselement **Galerie** de volgorde van de items weergeeft volgens **ImageSortUpDown1**.

![Afbeelding voor sorteren](./media/add-gallery/image-sorting.png)

1. Stel de eigenschap **[Items](controls/properties-core.md)** van het besturingselement **Galerie** in op deze formule:

    **Sort(If(IsBlank(TextSearchBox1.Text), FlooringEstimates, Filter(FlooringEstimates, TextSearchBox1.Text in Text(Name))), Name, If(SortDescending1, SortOrder.Descending, SortOrder.Ascending))**

2. Selecteer het sorteerpictogram om de sorteervolgorde van het besturingselement **Galerie** te wijzigen op basis van de namen van de producten.

Ga als volgt te werk om het besturingselement **Galerie** te sorteren *en* te filteren:

* Vervang beide exemplaren van *Gegevensbron* in deze formule door de naam van uw gegevensbron.

* Vervang beide exemplaren van *ColumnName* door de naam van de kolom waarop u wilt sorteren en filteren.

**Sort(If(IsBlank(TextSearchBox1.Text),** *DataSource*, **Filter(** *DataSource*, **TextSearchBox1.Text in Text(** *ColumnName* **))),** *ColumnName*, **If(SortDescending1, SortOrder.Descending, SortOrder.Ascending))**

## <a name="highlight-the-selected-item"></a>Markeer het geselecteerde item
Stel de eigenschap **TemplateFill** van het besturingselement **Galerie** in op een formule die vergelijkbaar is met het volgende voorbeeld:

**If(ThisItem.IsSelected, LightCyan, White)**

## <a name="change-the-default-selection"></a>De standaardselectie wijzigen
Stel de eigenschap **Default** van het besturingselement **Galerie** in op de record die u standaard wilt selecteren. U kunt bijvoorbeeld het vijfde item in de gegevensbron **FlooringEstimates** opgeven:

**Last(FirstN(FlooringEstimates, 5))**

In dit voorbeeld geeft u het eerste item op in de categorie **Hardwood** van de gegevensbron **FlooringEstimates**:

**First(Filter(FlooringEstimates, Category = "Hardwood"))**

## <a name="next-steps"></a>Volgende stappen
Meer informatie over het werken met [formulieren](working-with-forms.md) en [formules](working-with-formulas.md).
