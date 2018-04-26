---
title: Een nieuwe app insluiten in een Power BI-rapport | Microsoft Docs
description: Een app insluiten die gebruikmaakt van dezelfde gegevensbron en waarop kan worden gefilterd, net als bij andere rapportitems
documentationcenter: na
author: mgblythe
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 03/15/2018
ms.author: mblythe
ms.openlocfilehash: 33656e44f782a626eecc28787af984ace7339cd6
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
---
# <a name="tutorial-embed-a-new-app-in-a-power-bi-report"></a>Zelfstudie: een nieuwe app insluiten in een Power BI-rapport

U kunt de mogelijkheden van Power BI uitbreiden door *aangepaste visuals* toe te voegen aan een rapport. In deze zelfstudie gebruikt u de aangepaste PowerApps-visual om een nieuwe app te maken die wordt ingesloten in een voorbeeldrapport. Deze app communiceert met andere items in het rapport.

Als u geen PowerApps-abonnement hebt, [maakt u een gratis account](../signup-for-powerapps.md) voordat u begint.

In deze zelfstudie leert u de volgende zaken:
> [!div class="checklist"]
> * De aangepaste PowerApps-visual importeren in een Power BI-rapport
> * Een nieuwe app maken waarin gebruik wordt gemaakt van gegevens uit het rapport
> * De app in het rapport weergeven

## <a name="prerequisites"></a>Vereisten

* [Google Chrome](https://www.google.com/chrome/browser/)- of [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge)-browser
* Een [Power BI-abonnement](https://docs.microsoft.com/power-bi/service-self-service-signup-for-power-bi) waarin het [voorbeeld van een verkoopkansanalyse](https://docs.microsoft.com/power-bi/sample-opportunity-analysis#get-the-content-pack-for-this-sample) is geïnstalleerd
* Een goed begrip van hoe u [apps maakt in PowerApps](data-platform-create-app-scratch.md) en hoe u [Power BI-rapporten bewerkt](https://docs.microsoft.com/power-bi/service-the-report-editor-take-a-tour)

## <a name="import-the-powerapps-custom-visual"></a>De aangepaste PowerApps-visual importeren

De eerste stap is het importeren van de aangepaste PowerApps-visual zodat u deze kunt gebruiken in het voorbeeldrapport.

1. In het voorbeeldrapport van een verkoopkansanalyse klikt of tikt u op het tabblad **Toekomstige verkoopkansen**.

2. Boven in het rapport klikt of tikt u op **Rapport bewerken**.

3. In het deelvenster **Visualisaties** klikt of tikt u op de beletseltekens (**. . .**) > **Importeren vanuit de marketplace**. 

    ![Importeren vanuit de marketplace](media/embed-powerapps-powerbi/import-visual.png)

4. In het scherm **Visuele Power BI-elementen** zoekt u naar PowerApps en klikt of tikt u op **Toevoegen**. In Power BI wordt het pictogram voor de aangepaste visual toegevoegd aan de onderzijde van het deelvenster **Visualisaties**.

    ![Pictogram voor de PowerApps-visual](media/embed-powerapps-powerbi/powerapps-icon.png)

5. Sla het rapport op.

## <a name="create-a-new-app"></a>Een nieuwe app maken
U voegt de aangepaste visual nu toe aan uw rapport en u maakt in het rapport een nieuwe app op basis van gegevens. Wanneer u de app maakt, wordt PowerApps Studio gestart met een live gegevensverbinding tussen PowerApps en Power BI.

1. Verplaats en wijzig het formaat van enkele van de rapporttegels om ruimte te maken voor een app.

    ![Rapporttegels verplaatsen en het formaat wijzigen](media/embed-powerapps-powerbi/move-resize.png)

2. Klik of tik op het pictogram van de aangepaste PowerApps-visual en wijzig dan de grootte van de tegel zodat deze in de ruimte past die u hebt gemaakt.

3. In het deelvenster **Velden** selecteert u **Naam**, **Productcode** en vervolgens **Verkoopfase**. 

    ![Velden selecteren](media/embed-powerapps-powerbi/select-fields.png)

4. In de tegel van de aangepaste visual selecteert u de PowerApps-omgeving waarin u de app wilt maken. Klik of tik vervolgens op **Nieuw**.

    ![Een nieuwe app maken](media/embed-powerapps-powerbi/create-new-app.png)

    In PowerApps Studio ziet u dat er een basis-app wordt gemaakt met een *galerie* waarin één van de geselecteerde velden uit Power BI wordt getoond.

5.  Wijzig de grootte van de galerie zodat deze slechts de helft van het scherm in beslag neemt. 

6. Klik of tik in het linkerdeelvenster op **Screen1** en stel de eigenschap **Vullen** van het scherm in op LightBlue (voor een betere zichtbaarheid in het rapport).

    ![App met een galerie waarvan het formaat is gewijzigd](media/embed-powerapps-powerbi/app-gallery.png)

6. Voeg het besturingselement Label toe onder de galerie. Stel daarvoor de eigenschap **Tekst** in op `"Opportunity Count: " & CountRows(Gallery1.AllItems)`. Nu wordt het totale aantal verkoopkansen weergegeven in de gegevensset.

    ![Aantal verkoopkansen](media/embed-powerapps-powerbi/opportunity-count.png)

7. Sla de app op met de naam Opportunities. 


## <a name="view-the-app-in-the-report"></a>De app in het rapport weergeven
De app is nu beschikbaar in het rapport. De app communiceert met andere visuals omdat er gebruik wordt gemaakt van dezelfde gegevensbron.

In het Power BI-rapport selecteert u **Jan** in de slicer. Hiermee wordt het volledige rapport gefilterd, inclusief de gegevens uit de app.

![Gefilterd rapport](media/embed-powerapps-powerbi/filtered-report.png)

Het aantal verkoopkansen uit de app komt overeen met het aantal in de linkerbovenhoek van het rapport. U kunt andere items in het rapport en gegevens uit de app-updates selecteren.


## <a name="clean-up-resources"></a>Resources opschonen
Als u het voorbeeld van een verkoopanalyse niet meer wilt gebruiken, kunt u het dashboard, het rapport en de gegevensset verwijderen.


## <a name="next-steps"></a>Volgende stappen
In deze zelfstudie hebt u de volgende zaken geleerd:
> [!div class="checklist"]
> * De aangepaste PowerApps-visual importeren in een Power BI-rapport
> * Een nieuwe app maken waarin gebruik wordt gemaakt van gegevens uit het rapport
> * De app in het rapport weergeven

Ga naar het volgende artikel voor meer informatie
> [!div class="nextstepaction"]
> [Aangepaste PowerApps-visual voor Power BI](powerapps-custom-visual.md)

