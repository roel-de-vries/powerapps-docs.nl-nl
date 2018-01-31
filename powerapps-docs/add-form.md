---
title: Een record uit een tabel weergeven, bewerken of toevoegen | Microsoft Docs
description: Gebruik een formulier om een record uit een tabel in uw gegevensbron weer te geven, te bewerken of toe te voegen.
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
ms.date: 10/06/2017
ms.author: sharik
ms.openlocfilehash: 52fa30b95b076e9a37f92499041206a3d99d48a8
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/23/2018
---
# <a name="show-edit-or-add-a-record-from-a-table-in-powerapps"></a>Een record uit een tabel weergeven, bewerken of toevoegen in PowerApps
Als u alle velden in een record wilt weergeven, voegt u het besturingselement **[Weergaveformulier](controls/control-form-detail.md)** toe en configureert u dit. Als u een veld in een record wilt bewerken (of als u een record wilt toevoegen) en u de wijzigingen wilt opslaan in een gegevensbron, voegt u het besturingselement **[Formulier](controls/control-form-detail.md)** bewerken toe en configureert u dit.

## <a name="prerequisites"></a>Vereisten

* Lees hoe u [een besturingselement kunt toevoegen en configureren](add-configure-controls.md) in PowerApps.
* Download [dit Excel-bestand](https://az787822.vo.msecnd.net/documentation/get-started-from-data/FlooringEstimates.xlsx), dat voorbeeldgegevens bevat voor deze zelfstudie.
* Upload het Excel-bestand naar een [cloudopslagaccount](connections/cloud-storage-blob-connections.md), bijvoorbeeld bij OneDrive voor Bedrijven.
* In een nieuwe of bestaande app [voegt u een verbinding toe](add-data-connection.md) aan de tabel **FlooringEstimates** in het Excel-bestand.
* Als u een bestaande app gebruikt, [voegt u er een scherm aan toe](add-screen-context-variables.md).

## <a name="add-a-form-and-show-data"></a>Een formulier toevoegen en gegevens weergeven
1. Voeg het besturingselement **[Vervolgkeuzelijst](controls/control-drop-down.md)** toe, geef het de naam **ChooseProduct** en stel de eigenschap **[Items](controls/properties-core.md)** van het besturingselement in op deze waarde:

    **FlooringEstimates.Name**

    > [!NOTE]
> Als u niet zeker weet hoe u een besturingselement toevoegt, hoe u de naam wijzigt of hoe u een eigenschap instelt, bekijkt u [Besturingselementen toevoegen en configureren](add-configure-controls.md).

    In de lijst staan de namen van vloerproducten uit de gegevensbron.

2. Voeg het besturingselement **Formulier bewerken** toe, plaats het onder **ChooseProduct** en wijzig de grootte van het formulier, zodat dit het grootste deel van het scherm beslaat.

    ![Een formulier toevoegen](./media/add-form/add-a-form.png)

    > [!NOTE]
> In dit onderwerp wordt het besturingselement **Formulier bewerken** beschreven, maar er zijn vergelijkbare principes van toepassing op het besturingselement **Formulier weergeven**.

3. Stel de eigenschap **[DataSource](controls/control-form-detail.md)** van het formulier in op **FlooringEstimates** en stel de eigenschap **[Item](controls/control-form-detail.md)** van het formulier in op deze formule:

   **First(Filter(FlooringEstimates, Name=ChooseProduct.Selected.Value))**

   In deze formule wordt opgegeven dat, wanneer u klaar bent met het configureren van het formulier, de record wordt weergegeven die de gebruiker selecteert in **ChooseProduct**.

4. Klik of tik in het deelvenster **Gegevens** op het selectievakje voor elk veld om het weer te geven.

    > [!NOTE]
> Als het deelvenster **Gegevens** is gesloten, opent u het door het formulier te selecteren in het linkerdeelvenster en vervolgens op **Gegevens** in het rechterdeelvenster te klikken of te tikken.

    ![Velden weergeven in formulier](./media/add-form/checkbox.png)

5. Sleep in het deelvenster **Gegevens** de vermelding **Naam** naar de bovenkant van de lijst.

    ![Een kaart verplaatsen](./media/add-form/drag-field.png)

    Uw wijzigingen worden toegepast op het besturingselement **Formulier bewerken**.

    ![Naam bovenaan](./media/add-form/move-card-form.png)

## <a name="set-the-card-type-for-a-field"></a>Het kaarttype voor een veld instellen
1. Wanneer u het formulier hebt geselecteerd, klikt of tikt u op de kaartselector voor **Prijs** in het deelvenster **Gegevens**.

    ![De kaartselector selecteren](./media/add-form/price-card2.png)

2. Scroll omlaag en klik of tik op de optie **Tekst weergeven** om het veld Alleen-lezen te maken.

    ![Tekst weergeven](./media/add-form/view-text.png)

    De wijziging wordt in het formulier weergegeven.

    ![Alleen-lezennummer](./media/add-form/read-only.png)  

## <a name="edit-form-only-save-changes"></a>(alleen voor Formulier bewerken) Wijzigingen opslaan
1. Selecteer het formulier in het linkerdeelvenster en klik of tik vervolgens op het beletselteken (...).

   ![Selecteer het formulier](./media/add-form/select-form.png)

2. Klik of tik **Naam wijzigen** en wijzig de naam van het formulier **EditForm**.

3. Voeg een besturingselement van het type **[Knop](controls/control-button.md)** toe en stel de bijbehorende eigenschap **[Text](controls/properties-core.md)** in op **Opslaan**.

    ![Een knop Save toevoegen](./media/add-form/save-button.png)  

4. Stel de eigenschap **[OnSelect](controls/properties-core.md)** van de knop **Opslaan** in op deze formule:

   **SubmitForm(EditForm)**

5. Open de preview-modus door de afspeelknop bij de rechterbovenhoek te selecteren (of door op F5 te drukken).

    ![Preview-modus openen](./media/add-form/open-preview.png)

6. Wijzig de naam van een product en klik of tik op de knop **Opslaan** die u hebt gemaakt.

    Met de functie **[SubmitForm](functions/function-form.md)** worden uw wijzigingen opgeslagen in de gegevensbron waarmee u het formulier hebt geconfigureerd.

7. (optioneel) Selecteer het pictogram Sluiten om het voorbeeld te sluiten (of druk op ESC).

    ![Het voorbeeld sluiten](./media/add-form/close-preview.png)

## <a name="next-steps"></a>Volgende stappen
Meer informatie over het werken met [formulieren](working-with-forms.md) en [formules](working-with-formulas.md).
