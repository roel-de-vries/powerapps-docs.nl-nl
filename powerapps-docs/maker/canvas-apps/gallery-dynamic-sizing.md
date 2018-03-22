---
title: Items met verschillende hoogten weergeven in een galerie | Microsoft Docs
description: Een galerie met flexibele hoogte toevoegen en zo configureren dat deze automatisch wordt aangepast aan de hoeveelheid inhoud in elk item van de galerie
services: ''
suite: powerapps
documentationcenter: na
author: fikaradz
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/01/2017
ms.author: fikaradz
ms.openlocfilehash: 2f4f4867fa9d1fb13dfd613cc3564703b0c220e2
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2018
---
# <a name="show-items-of-different-heights-in-a-powerapps-gallery"></a>Items met verschillende hoogten weergeven in een PowerApps-galerie
Als verschillende items in uw gegevensset verschillende hoeveelheden gegevens in hetzelfde veld bevatten, kunt u items volledig weergeven die meer gegevens bevatten zonder lege ruimte toe te voegen na items die minder gegevens bevatten. Voeg het galeriebesturingselement **Flexibele hoogte** toe en configureer dit zodat u:

* **Label**-besturingselementen zo kunt configureren dat ze worden vergroot of verkleind op basis van de inhoud.
* Elk besturingselement zo kunt plaatsen dat dit automatisch wordt weergegeven net onder het besturingselement erboven.

In deze zelfstudie geeft u gegevens weer over vloerproducten in het galeriebesturingselement **Flexibele hoogte**. De afbeelding van elk product wordt 5 pixels onder het overzicht weergegeven, ongeacht of het overzicht vijf of twee tekstregels bevat.

![Definitieve app](./media/gallery-dynamic-sizing/dynamic-app.png)

**Aanbevolen onderwerpen**

Als u nog nooit besturingselementen hebt toegevoegd aan een galerie, volgt u de stappen in [Een lijst met items weergeven](add-gallery.md) voordat u verdergaat met dit onderwerp.

## <a name="add-data-to-a-blank-app"></a>Gegevens toevoegen aan een lege app
1. Download [dit Excel-bestand](https://az787822.vo.msecnd.net/documentation/get-started-from-data/FlooringEstimates.xlsx), dat namen, overzichten en koppelingen naar afbeeldingen van vloerproducten bevat.

    ![Vloerproducten](./media/gallery-dynamic-sizing/flooring-products.png)

2. Upload het Excel-bestand naar een cloudopslagaccount, zoals OneDrive, Dropbox of Google Drive.

3. Klik of tik in PowerApps Studio op **Nieuw** in het menu **Bestand**.

4. Klik of tik onder **Lege app** op **Telefoonindeling**.

    ![Optie Nieuw in het menu Bestand](./media/gallery-dynamic-sizing/blank-app.png)

5. Voeg een verbinding toe aan de tabel **FlooringEstimates** in het Excel-bestand.

    Zie [Een verbinding toevoegen](add-data-connection.md) voor meer informatie.

## <a name="add-data-to-a-gallery"></a>Gegevens toevoegen aan een galerie
1. Ga naar het tabblad **Invoegen**, klik of tik op **Galerie** en klik of tik vervolgens op **Flexibele hoogte**.

    ![Galerie toevoegen](./media/gallery-dynamic-sizing/add-flexible.png)
2. Pas de grootte van de galerie aan, zodat deze het hele scherm vult.

3. Stel de eigenschap **[Items](controls/properties-core.md)** van de galerie in op **FlooringEstimates**.

## <a name="show-the-product-names"></a>De productnamen weergeven
1. Klik of tik linksboven in de galerie op het potloodpictogram om de galeriesjabloon te selecteren.

    ![Potloodpictogram](./media/gallery-dynamic-sizing/edit-template.png)

2. Selecteer de galeriesjabloon en voeg er een besturingselement **[Label](controls/control-text-box.md)** aan toe.

3. Stel de eigenschap **Text** van het besturingselement **Label** in op deze expressie:<br>
   **ThisItem.Name**

    ![Label toevoegen](./media/gallery-dynamic-sizing/add-text-box.png)

## <a name="show-the-product-overviews"></a>De productoverzichten weergeven
1. Selecteer de galeriesjabloon en voeg nog een besturingselement **Label** toe. Plaatst dit besturingselement onder het eerste besturingselement **Label**.  

2. Stel de eigenschap **Text** van het besturingselement **Label** in op deze expressie:<br> **ThisItem.Overview**

3. Selecteer het tweede besturingselement **Label** en klik of tik op het pictogram met het naamkaartje op het tabblad **Inhoud** en wijzig de naam van het besturingselement in **OverviewText**.

    ![De naam van het label wijzigen](./media/gallery-dynamic-sizing/rename-text-box.png)

4. Stel de eigenschap **AutoHeight** van het vak **OverviewText** in op **Waar**.

    Met deze stap zorgt u ervoor dat de grootte van het vak wordt aangepast aan de inhoud.

      ![Automatische teksthoogte](./media/gallery-dynamic-sizing/autoheight-text.png)

## <a name="show-the-product-images"></a>De productafbeeldingen weergeven
1. Wijzig de grootte van de sjabloon, zodat deze twee keer zo lang is al eerst.

    U kunt besturingselementen eenvoudiger toevoegen aan de sjabloon terwijl u de app maakt. Deze wijziging heeft geen invloed op het uiterlijk van de app wanneer deze wordt uitgevoerd.

2. Terwijl u de galeriesjabloon hebt geselecteerd, voegt u het besturingselement **[Afbeelding](controls/control-image.md)** toe en plaatst u dit onder het vak **OverviewText**.

3. Zorg ervoor dat de eigenschap **Image** van het besturingselement **Afbeelding** is ingesteld op deze expressie:<br>
    **ThisItem.Image**

4. Stel de **[Y](controls/properties-core.md)**-eigenschap van het besturingselement **Afbeelding** in op basis van de positie en de grootte van het vak **OverviewText**, zoals in deze expressie:
   <br>**OverviewText.Y + OverviewText.Height + 5**

    ![Definitieve app](./media/gallery-dynamic-sizing/final-app.png)

Pas hetzelfde concept toe als u meer besturingselementen wilt toevoegen: stel de eigenschap **Y** van elk besturingselement in op basis van de eigenschappen **Y** en **Height** van het besturingselement erboven.

## <a name="next-steps"></a>Volgende stappen
Lees meer over het werken met een [galerie](working-with-forms.md)besturingselement en [formules](working-with-formulas.md).
