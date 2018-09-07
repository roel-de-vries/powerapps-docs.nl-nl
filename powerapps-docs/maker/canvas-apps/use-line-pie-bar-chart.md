---
title: Een diagram maken in een canvas-app | Microsoft Docs
description: In PowerApps gegevenscategorieën weergeven als een lijn-, cirkel- of staafdiagram
author: lonu
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/23/2016
ms.author: lonu
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 142bb0e19fb8b9647c1808dcca10e781c4f69d4a
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42862030"
---
# <a name="show-data-in-a-line-pie-or-bar-chart-in-powerapps"></a>Gegevens in PowerApps weergeven in een lijn-, cirkel- of staafdiagram

Gebruik lijn-, cirkel- en staafdiagrammen om uw gegevens weer te geven in een canvas-app. Wanneer u met diagrammen werkt, moet u de gegevens die u importeert aan de hand van de volgende criteria indelen:

* Elke reeks moet zich in de eerste rij bevinden.
* Labels moeten zich in de meest linkse kolom bevinden.

Uw gegevens zouden er ongeveer als volgt uit moeten zijn:

![][9]

U kunt dergelijke diagrammen maken en gebruiken in PowerApps. Aan de slag.

## <a name="prerequisites"></a>Vereisten

* [Registreer u](../signup-for-powerapps.md) voor PowerApps en [meld u vervolgens aan](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) met dezelfde referenties die u hebt gebruikt om u te registreren.
* Maak een app op basis van een [sjabloon](get-started-test-drive.md) of op basis van [gegevens](get-started-create-from-data.md), of maak een [volledig nieuwe](get-started-create-from-blank.md) app.
* Lees hoe u [een besturingselement kunt configureren](add-configure-controls.md) in PowerApps.
* Download de map [ChartData.zip](http://pwrappssamples.blob.core.windows.net/samples/ChartData.zip), die voorbeeldgegevens bevat in de XML-bestandsindeling. Volg de stappen in dit onderwerp om deze rechtstreeks in uw app te importeren. Ook kunt u het ZIP-bestand uitpakken, het XML-bestand in Excel openen en het vervolgens opslaan naar een [cloudopslagaccount](connections/cloud-storage-blob-connections.md).

## <a name="import-the-sample-data"></a>De voorbeeldgegevens importeren
In deze stappen worden de voorbeeldgegevens geïmporteerd naar een verzameling met de naam **ProductRevenue**.

1. Selecteer op het tabblad **Invoegen** de optie **Besturingselementen** en selecteer vervolgens **Importeren**:  

    ![][11]  

2. Stel de eigenschap **[OnSelect](controls/properties-core.md)** van het besturingselement in op de volgende functie:  

   ```Collect(ProductRevenue, Import1.Data)```

3. Druk op F5 om de voorbeeldmodus te openen en selecteer vervolgens de knop **Gegevens importeren**.

4. Selecteer in het dialoogvenster **Openen** het bestand ChartData.zip, selecteer **Openen** en druk op Esc.

5. Selecteer **Verzamelingen** in het menu **Bestand**.

    De verzameling ProductRevenue wordt getoond met de grafiekgegevens die u hebt geïmporteerd:

    ![][1]  

   > [!NOTE]
   > Het besturingselement importeren wordt gebruikt om op Excel-achtige wijze gegevens te importeren en de verzameling te maken. Het besturingselement importeren importeert gegevens wanneer u uw app maakt en wanneer u een voorbeeldweergave van uw app genereert. Het besturingselement importeren importeert momenteel geen gegevens wanneer u uw app publiceert.
   >

6. Druk op Esc om terug te gaan naar de standaardwerkruimte.

## <a name="add-a-pie-chart"></a>Een cirkeldiagram toevoegen
1. Selecteer op het tabblad **Invoegen** de optie **Grafieken** en selecteer vervolgens **Cirkeldiagram**.

2. Plaats de cirkeldiagram onder de knop **Gegevens importeren**.

3. Selecteer in het besturingselement voor cirkeldiagrammen het midden van de cirkeldiagram:   

    ![][10]

4. Stel de eigenschap **[Items](controls/properties-core.md)** van de cirkeldiagram in op deze expressie: `ProductRevenue.Revenue2014`

    ![][2]  

    De cirkeldiagram bevat de inkomstengegevens voor 2014.

    ![][3]  

## <a name="add-a-bar-chart-to-display-your-data"></a>Een staafdiagram toevoegen om uw gegevens weer te geven
Nu gaan we deze verzameling ProductRevenue gebruiken in een staafdiagram:

1. Voeg op het tabblad **Start** een scherm toe.

2. Selecteer op het tabblad **Invoegen** de optie **Grafieken** en selecteer vervolgens **Staafdiagram**.

3. Selecteer het midden van de staafdiagram. Stel de eigenschap **[Items](controls/properties-core.md)** van de staafdiagram in op ```ProductRevenue```:

    ![][12]  

    De staafdiagram bevat de inkomstengegevens voor 2012:

    ![][4]  

4. Selecteer in de staafdiagram het middelste vak:

    ![][5]

5. Selecteer op het tabblad **Grafiek** **Aantal reeksen** en voer vervolgens in de formulebalk **3** in:

    ![][6]  

    De staafdiagram bevat per product inkomstengegevens voor drie jaar:

    ![][7]  

[1]: ./media/use-line-pie-bar-chart/productrevenuecollection.png
[2]: ./media/use-line-pie-bar-chart/itemsexpression.png
[3]: ./media/use-line-pie-bar-chart/piechart.png
[4]: ./media/use-line-pie-bar-chart/columnchart.png
[5]: ./media/use-line-pie-bar-chart/columnchartseries.png
[6]: ./media/use-line-pie-bar-chart/columnchartseriesfunction.png
[7]: ./media/use-line-pie-bar-chart/columnchartthreeyears.png
[8]: ./media/use-line-pie-bar-chart/preview.png
[9]: ./media/use-line-pie-bar-chart/tableformat.png
[10]: ./media/use-line-pie-bar-chart/middlepiechart.png
[11]: ./media/use-line-pie-bar-chart/import.png
[12]: ./media/use-line-pie-bar-chart/itemscolumnchart.png
