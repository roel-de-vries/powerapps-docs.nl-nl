---
title: Een gegenereerde app verkennen (SharePoint-lijst) | Microsoft Docs
description: Schermen en besturingselementen van de app verkennen
services: 
suite: powerapps
documentationcenter: na
author: mgblythe
manager: anneta
editor: 
tags: 
featuredvideoid: OJ8a9VINeKU
courseduration: 5m
ms.service: powerapps
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/09/2016
ms.author: mblythe
ms.openlocfilehash: b6a6597970845aa16e75d83468a987992692c561
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="explore-the-generated-app-sharepoint-list"></a>De gegenereerde app verkennen (SharePoint-lijst)
In dit onderwerp gaan we dieper in op de gegenereerde app en bekijken we de schermen en besturingselementen die het gedrag van de app bepalen. We behandelen niet alle details, maar als u meer weet over de werking van deze app, kan dat helpen bij het ontwikkelen van uw eigen apps. In een later onderwerp kijken we naar de formules die zijn bedoeld voor schermen en besturingselementen.

## <a name="understanding-controls-in-powerapps"></a>Over besturingselementen in PowerApps
Een besturingselement is simpelweg een UI-element waaraan gedrag is gekoppeld. Veel besturingselementen in PowerApps zijn gelijk aan de besturingselementen die u in andere apps hebt gebruikt: labels, tekstinvoervakken, vervolgkeuzelijsten, navigatie-elementen enzovoort. Maar PowerApps heeft besturingselementen die meer gespecialiseerd zijn, zoals **galerieën** (voor de weergave van samenvattingsgegevens) en **formulieren** (die gedetailleerde gegevens weergeven en waarin u items kunt maken en bewerken). Er zijn ook andere interessante besturingselementen, zoals voor **afbeelding**, **camera** en **streepjescode**. Als u wilt nagaan welke besturingselementen er beschikbaar zijn, klikt of tikt u op **Invoegen** op het lint en klikt of tikt u vervolgens op elk van de opties, van **Tekst** tot en met **Pictogrammen**.

![Tabblad voor besturingselementen op het lint van PowerApps Studio](./media/learning-spo-app-explore-controls/ribbon-controls.png)

## <a name="explore-the-browse-screen"></a>Het bladerscherm testen
Elk van de drie app-schermen heeft een hoofdbesturingselement en enkele extra besturingselementen. Het eerste venster van de app is het bladerscherm, dat standaard de naam **BrowseScreen1** heeft. Het hoofdbesturingselement in dit scherm is een galerie met de naam **BrowseGallery1**. **BrowseGallery1** bevat andere besturingselementen, zoals **NextArrow1** (in de vorm van een pictogram: klik of tik erop om naar het detailscherm te gaan). Er zijn ook afzonderlijke besturingselementen in het scherm, zoals **IconNewItem1** (in de vorm van een pictogram: klik of tik erop om een item te maken in het scherm voor bewerken/maken).

![Bladerscherm met besturingselementen](./media/learning-spo-app-explore-controls/browse-screen.png)

PowerApps heeft verschillende typen galerieën. Gebruik de galerie die het beste aansluit bij de indelingsvereisten voor uw app. Verderop in deze sectie ziet u nog meer manieren om de indeling te bepalen.

![Opties voor PowerApps-galerie](./media/learning-spo-app-explore-controls/galleries.png)

## <a name="explore-the-details-screen"></a>Het detailscherm verkennen
Vervolgens is het de beurt aan het detailscherm, dat standaard de naam **DetailScreen1** heeft. Het hoofdbesturingselement in dit scherm is een weergaveformulier met de naam **DetailForm1**. **DetailForm1** bevat andere besturingselementen, zoals **DataCard1** (in de vorm van een kaart, waarbij in dit geval als categorie vloermateriaal (Flooring Estimates) wordt weergegeven). Het scherm bevat ook afzonderlijke besturingselementen, zoals **IconEdit1** (in de vorm van een pictogram: klik of tik erop om het huidige item te bewerken in het scherm voor bewerken/maken).

![Detailscherm met besturingselementen](./media/learning-spo-app-explore-controls/details-screen.png)

Er zijn tal van opties voor de galerie, maar voor formulieren zijn er slechts twee typen: een bewerkingsformulier of een weergaveformulier.

![Opties voor PowerApps-formulieren](./media/learning-spo-app-explore-controls/forms.png)

## <a name="explore-the-editcreate-screen"></a>Het scherm voor bewerken/maken verkennen
Het derde scherm in de app is het scherm voor bewerken/maken, dat standaard de naam **EditScreen1** heeft. Het hoofdbesturingselement in dit scherm is een bewerkingsformulier met de naam **EditForm1**. **EditForm1** bevat andere besturingselementen, zoals **DataCard8** (in de vorm van een kaart, waarmee u in dit geval de categorie vloermateriaal (Flooring Estimates) kunt bewerken). Het scherm bevat ook afzonderlijke besturingselementen, zoals **IconAccept1** (in de vorm van een pictogram: klik of tik erop voor het opslaan van de wijzigingen die u hebt aangebracht in het scherm voor bewerken/maken).

![Bewerkingsscherm met besturingselementen](./media/learning-spo-app-explore-controls/edit-screen.png)

Nu u een beeld hebt van de manier waarop de app is samengesteld uit schermen en besturingselementen, gaan we in het volgende onderwerp bekijken hoe u de app kunt aanpassen.

