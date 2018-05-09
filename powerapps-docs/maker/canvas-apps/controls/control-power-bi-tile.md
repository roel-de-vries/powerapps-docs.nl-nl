---
title: 'Tegelbesturingselement voor Power BI: verwijzing | Microsoft Docs'
description: Informatie, waaronder eigenschappen en voorbeelden, over het tegelbesturingselement voor Power BI
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
ms.date: 07/07/2016
ms.author: fikaradz
ms.openlocfilehash: a760dd47cfe703cdf829037d0090c99fc215831e
ms.sourcegitcommit: 4710a56d308efe67fe60a7688143e61f5e5f2b44
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="power-bi-tile-control-in-powerapps"></a>Tegelbesturingselement voor Power BI in PowerApps
Een besturingselement dat een [Power BI](https://powerbi.microsoft.com)-tegel in een app weergeeft.

## <a name="description"></a>Beschrijving
Profiteer van uw bestaande gegevensanalyse en -rapportage door uw **[Power BI-tegels](https://docs.microsoft.com/power-bi/service-dashboard-tiles)** in uw apps weer te geven.  Kies de tegel die u wilt weergeven door op het tabblad **Gegevens** in het deelvenster met opties de eigenschappen voor de **Werkruimte**, het **Dashboard** en de **Tegel** in te stellen.

## <a name="sharing-and-security"></a>Delen en beveiliging
Als de PowerApp is gedeeld, is deze toegankelijk voor alle gebruikers die zijn gemachtigd om de app te openen.  Om de Power BI-inhoud voor deze gebruikers zichtbaar te maken, moet het dashboard waarop de tegel is gebaseerd echter met de gebruiker zijn [gedeeld](https://docs.microsoft.com/power-bi/service-how-to-collaborate-distribute-dashboards-reports) in Power BI.  Dit zorgt ervoor dat de machtigingen voor het delen in Power BI worden gerespecteerd wanneer Power BI-inhoud in een app wordt geopend.

## <a name="key-properties"></a>Belangrijkste eigenschappen
**Werkruimte** – De Power BI-werkruimte waarop de tegel is gebaseerd.

**Dashboard** – Het Power BI-dashboard waarop de tegel is gebaseerd.

**Tegel** – De naam van de Power BI-tegel die u wilt weergeven.

## <a name="additional-properties"></a>Aanvullende eigenschappen
**[BorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement.

**[BorderStyle](properties-color-border.md)**: hiermee wordt aangegeven of de rand van een besturingselement **effen**, **onderbroken** of **gestippeld** is, of dat er **geen** rand is.

**[BorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement.

**[DisplayMode](properties-core.md)**: of invoer van de gebruiker is toegestaan (**Bewerken**), alleen gegevens worden weergegeven (**Weergeven**) of is uitgeschakeld (**Uitgeschakeld**).

**[Height](properties-size-location.md)** : de afstand tussen de boven- en onderrand van een besturingselement.

**[OnSelect](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker op een besturingselement tikt of klikt. Standaardgedrag brengt de gebruiker naar het Power BI-rapport dat aan de tegel is gekoppeld.

**[Visible](properties-core.md)**: hiermee wordt aangegeven of een besturingselement zichtbaar of verborgen is.

**[Width](properties-size-location.md)**: de afstand tussen de linker- en rechterrand van een besturingselement.

**[X](properties-size-location.md)**: de afstand tussen de linkerrand van een besturingselement en de linkerrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

**[Y](properties-size-location.md)**: de afstand tussen de bovenrand van een besturingselement en de bovenrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

## <a name="example"></a>Voorbeeld
1. Voeg een **Power BI-tegelbesturingselement** toe via het menu **Besturingselementen** op het tabblad **Invoegen**.  
2. Kies op het tabblad **Gegevens** in het deelvenster met opties 'Mijn werkruimte' voor de instelling **Werkruimte**.  Kies een dashboard in de lijst met dashboards en een tegel in de lijst met tegels.
   
    Het besturingselement zorgt dat de Power BI-tegel wordt weergegeven.
   
    Weet u niet hoe u [een besturingselement kunt toevoegen of configureren](../add-configure-controls.md)?
   
   Hebt u geen Power BI? [Meld u aan](https://docs.microsoft.com/power-bi/service-self-service-signup-for-power-bi).


## <a name="accessibility-guidelines"></a>Richtlijnen voor toegankelijkheid
De **Power BI-tegel** is eenvoudig een container voor Power BI-inhoud. Informatie over het maken van toegankelijke inhoud met deze [toegankelijkheidstips voor Power BI](https://docs.microsoft.com/power-bi/desktop-accessibility).

### <a name="screen-reader-support"></a>Ondersteuning voor schermlezers
* U kunt een koptekst met een **[Label](control-text-box.md)** toevoegen, als de Power BI-inhoud niet over een titel beschikt. De kop kan direct vóór de **Power BI-tegel** worden geplaatst.
