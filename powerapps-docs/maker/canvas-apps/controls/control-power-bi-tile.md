---
title: 'Tegelbesturingselement voor Power BI: verwijzing | Microsoft Docs'
description: Informatie, waaronder eigenschappen en voorbeelden, over het tegelbesturingselement voor Power BI
author: fikaradz
manager: kfile
ms.service: powerapps
ms.topic: reference
ms.component: canvas
ms.date: 07/07/2016
ms.author: fikaradz
ms.openlocfilehash: 9df201f5d2fd4017debe47626aedaaa2c735682f
ms.sourcegitcommit: 16a2eeaa4ad9218682143411b609cb961dbcfa91
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/06/2018
ms.locfileid: "37886373"
---
# <a name="power-bi-tile-control-in-powerapps"></a>Tegelbesturingselement voor Power BI in PowerApps

Een besturingselement dat een [Power BI](https://powerbi.microsoft.com)-tegel in een app weergeeft.

Hebt u geen Power BI? [Meld u aan](https://docs.microsoft.com/power-bi/service-self-service-signup-for-power-bi).

## <a name="description"></a>Beschrijving

Profiteer van uw bestaande gegevensanalyse en -rapportage door uw **[Power BI-tegels](https://docs.microsoft.com/power-bi/service-dashboard-tiles)** in uw apps weer te geven. Geef de tegel op die u wilt weergeven door op het tabblad **Gegevens** in het deelvenster met opties de eigenschappen voor de **Werkruimte**, het **Dashboard** en de **Tegel** in te stellen.

## <a name="sharing-and-security"></a>Delen en beveiliging

Wanneer u een app deelt die Power BI-inhoud bevat, moet u niet alleen de app zelf delen, maar ook het [dashboard](https://docs.microsoft.com/power-bi/service-how-to-collaborate-distribute-dashboards-reports) waarop de tegel is gebaseerd. Anders wordt de Power BI-inhoud niet weergegeven, zelfs niet voor gebruikers die de app openen. Apps die Power BI-inhoud bevatten, respecteren de machtigingen voor die inhoud.

## <a name="performance"></a>Prestaties

Het wordt niet aangeraden meer dan drie Power BI-tegels op hetzelfde moment in een app te hebben geladen. U kunt het laden en verwijderen van de tegel beheren door de eigenschap **LoadPowerBIContent** in te stellen.

## <a name="key-properties"></a>Belangrijkste eigenschappen

**Werkruimte** – De Power BI-werkruimte waarop de tegel is gebaseerd.

**Dashboard** – Het Power BI-dashboard waarop de tegel is gebaseerd.

**Tegel**: de naam van de Power BI-tegel die u wilt weergeven.

**LoadPowerBIContent**: wanneer deze is ingesteld op true, wordt de Power BI-inhoud geladen en weergegeven. Wanneer deze is ingesteld op false, wordt de Power BI-inhoud verwijderd, waardoor geheugen wordt vrijgegeven en prestaties worden geoptimaliseerd.

## <a name="additional-properties"></a>Aanvullende eigenschappen

**[BorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement.

**[BorderStyle](properties-color-border.md)**: hiermee wordt aangegeven of de rand van een besturingselement **effen**, **onderbroken** of **gestippeld** is, of dat er **geen** rand is.

**[BorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement.

**[DisplayMode](properties-core.md)**: of invoer van de gebruiker is toegestaan (**Bewerken**), alleen gegevens worden weergegeven (**Weergeven**) of is uitgeschakeld (**Uitgeschakeld**).

**[Height](properties-size-location.md)** : de afstand tussen de boven- en onderrand van een besturingselement.

**[OnSelect](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker op een besturingselement tikt of klikt. Standaard wordt het Power BI-rapport geopend dat is gekoppeld aan de tegel.

**[Visible](properties-core.md)**: hiermee wordt aangegeven of een besturingselement zichtbaar of verborgen is.

**[Width](properties-size-location.md)**: de afstand tussen de linker- en rechterrand van een besturingselement.

**[X](properties-size-location.md)**: de afstand tussen de linkerrand van een besturingselement en de linkerrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

**[Y](properties-size-location.md)**: de afstand tussen de bovenrand van een besturingselement en de bovenrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

## <a name="example"></a>Voorbeeld

1. Open op het tabblad **Invoegen** het menu **Besturingselementen** en voeg een **Power BI-tegel**-besturingselement toe.

    Weet u niet hoe u [een besturingselement kunt toevoegen of configureren](../add-configure-controls.md)?

2. Klik of tik op het tabblad **Gegevens** in het deelvenster met opties op **Mijn werkruimte** voor de instelling **Werkruimte**.

3. Selecteer een dashboard in de lijst met dashboards en selecteer vervolgens een tegel in de lijst met tegels.

    Het besturingselement zorgt dat de Power BI-tegel wordt weergegeven.

## <a name="accessibility-guidelines"></a>Richtlijnen voor toegankelijkheid

De **Power BI-tegel** is eenvoudig een container voor Power BI-inhoud. Informatie over het maken van toegankelijke inhoud met deze [toegankelijkheidstips voor Power BI](https://docs.microsoft.com/power-bi/desktop-accessibility).

Als de Power BI-inhoud niet beschikt over een titel, kunt u een koptekst toevoegen met een **[Label](control-text-box.md)**-besturingselement om schermlezers te ondersteunen. U kunt het label direct vóór de Power BI-tegel plaatsen.
