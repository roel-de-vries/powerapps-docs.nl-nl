---
title: Een app genereren (SharePoint-lijst) | Microsoft Docs
description: Een app met drie schermen genereren op basis van een SharePoint-lijst
services: 
suite: powerapps
documentationcenter: na
author: mgblythe
manager: anneta
editor: 
tags: 
featuredvideoid: m6KfAwEdtYU
courseduration: 3m
ms.service: powerapps
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/09/2016
ms.author: mblythe
ms.openlocfilehash: a6ae0ec73d659563275be5670c4aeda9dc3e172a
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="generate-an-app-sharepoint-list"></a>Een app genereren (SharePoint-lijst)
In deze sectie van de cursus maken we een app op basis van de SharePoint-lijst 'Flooring Estimates'. De app kan bijvoorbeeld worden gebruikt door een taxateur die bij een klant op bezoek is, om te kunnen verwijzen naar de lijst en deze up-to-date te houden. In de sectie Aan de slag hebben we al laten zien hoe een app op basis van dezelfde lijst kan worden gegeneerd, dus waarom moet dat nu weer? In de eerste plaats beginnen we niet in PowerApps Studio, maar laten we u nu zien hoe PowerApps is geïntegreerd in SharePoint Online. In de tweede plaats gaan we dieper in op het samenstellen van de app en laten we u zien hoe u de app kunt aanpassen. Dat zal zeker enkele nieuwe inzichten opleveren, dus laten we beginnen!

## <a name="generate-the-app"></a>De app genereren
In de volgende afbeelding ziet u de SharePoint-lijst 'Flooring Estimates', met basisgegevens zoals naam en prijs, en een afbeelding voor elk type vloermateriaal. U kunt zien hoe PowerApps en Microsoft Flow nu zijn geïntegreerd in SharePoint Online, zodat u eenvoudig apps en stromen op basis van uw lijsten kunt ontwikkelen.

![Lijst Flooring Estimates](./media/learning-spo-app-generate/flooring-estimates-list.png)

U begint met het bouwen van een app door te klikken of tikken op **PowerApps** en vervolgens op **Een app maken**. Voer in het rechterdeelvenster een naam voor de app in en klik of tik op **Maken**. Nadat u **Maken** hebt gekozen, begint PowerApps met het genereren van de app. PowerApps trekt allerlei conclusies op basis van uw gegevens om een nuttige app als uitgangspunt te genereren.

![App genereren op basis van een lijst](./media/learning-spo-app-generate/generate-app.png)

## <a name="view-the-app-in-powerapps-studio"></a>De app in PowerApps Studio weergeven
Uw nieuwe app met drie schermen wordt geopend in PowerApps Studio. Alle apps die worden gegenereerd op basis van gegevens hebben dezelfde reeks schermen:

* Het **blader**scherm: voor het zoeken, sorteren, filteren en vernieuwen van de gegevens die zijn opgehaald uit de lijst en voor het toevoegen van items door op het pluspictogram (+) te klikken of te tikken.
* Het **detail**scherm: voor het weergeven van meer informatie over een item en waar u het item kunt verwijderen of bewerken.
* Het scherm voor **bewerken/maken**: waar u een bestaand item bewerkt of een nieuw item maakt.

Klik of tik op een pictogram in de rechterbovenhoek van de linkernavigatiebalk om over te schakelen naar de miniatuurweergave.

![Schakelen tussen weergaven](./media/learning-spo-app-generate/toggle-view.png)

Klik of tik op een miniatuur om de besturingselementen in het betreffende scherm weer te geven.

![De gegenereerde app](./media/learning-spo-app-generate/generate-finished-app.png)

## <a name="run-the-app-in-preview-mode"></a>De app in de voorbeeldmodus uitvoeren
Klik of tik op ![de pijl Voorbeeld van app starten](./media/learning-spo-app-generate/f5-arrow-sm.png) rechtsboven om de app uit te voeren. Als u door de app navigeert, ziet u dat deze alle gegevens uit de lijst bevat en een goed uitgangspunt biedt.

![De app in de voorbeeldmodus uitvoeren](./media/learning-spo-app-generate/generate-run-app.png)

Vervolgens gaan we de app nader verkennen en deze later aanpassen uitgaande van onze behoeften.

