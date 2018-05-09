---
title: Een app genereren om projectaanvragen af te handelen | Microsoft Docs
description: In deze taak genereren we een eenvoudige *app met drie schermen* rechtstreeks vanuit een SharePoint-lijst.
documentationcenter: na
author: mgblythe
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 06/12/2017
ms.author: mblythe
ms.openlocfilehash: 4ae16517332864066f5b744e85ce3fe48c97a1df
ms.sourcegitcommit: 45fac73f04aa03b5796ae6833d777f4757e67945
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/03/2018
---
# <a name="generate-an-app-to-handle-project-requests"></a>Een app genereren om projectaanvragen af te handelen
> [!NOTE]
> Dit artikel maakt deel uit van een reeks zelfstudies over het gebruik van PowerApps, Microsoft Flow en Power BI met SharePoint Online. Lees de [inleiding tot de reeks](sharepoint-scenario-intro.md) zodat u een idee van het geheel krijgt en van de betreffende downloads.

De SharePoint-lijsten zijn gereed, dus we kunnen onze eerst app gaan maken en aanpassen. PowerApps is geïntegreerd met SharePoint, dus het is eenvoudig om rechtstreeks vanuit een lijst een eenvoudige *app met drie schermen* te genereren. Met deze app kunt u zowel overzichten als gedetailleerde informatie voor elk lijstitem bekijken, bestaande lijstitems bijwerken en nieuwe lijstitems maken. Als u een app rechtstreeks vanuit een lijst maakt, wordt de app als een *weergave* voor die lijst weergegeven. U kunt de app vervolgens in een browser uitvoeren, en tevens op een mobiele telefoon.

> [!TIP]
> Het [downloadpakket](https://aka.ms/o4ia0f) voor dit scenario omvat een voltooide versie van deze app: project-requests-app.msapp.

## <a name="step-1-generate-an-app-from-a-sharepoint-list"></a>Stap 1: Een app genereren op basis van een SharePoint-lijst

1. Klik of tik in de lijst **Projectaanvragen** die u hebt gemaakt op **PowerApps** en vervolgens op **App maken**.
   
    ![Een app maken](./media/sharepoint-scenario-generate-app/02-01-01-create-app.png)

2. Geef de app een naam, bijvoorbeeld Projectaanvraag-app, en klik of tik op **Create**. Als de app klaar is, wordt deze geopend in PowerApps Studio.
   
    ![Een naam opgeven voor de app](./media/sharepoint-scenario-generate-app/02-01-02-create-app-name.png)

## <a name="step-2-review-the-app-in-powerapps-studio"></a>Stap 2: De app in PowerApps Studio controleren

1. In PowerApps Studio toont het linker navigatiedeelvenster standaard een hiërarchische weergave van de schermen en besturingselementen van de app.
   
    ![PowerApps Studio met hiërarchische weergave](./media/sharepoint-scenario-generate-app/02-02-01-studio-screens-hierarchy.png)

2. Klik of tik op het miniatuurpictogram om weergaven te schakelen.
   
    ![Weergaveselectie van PowerApps Studio](./media/sharepoint-scenario-generate-app/02-02-02-studio-view-selector.png)

3. Klik of tik op een scherm om het in het middelste deelvenster te bekijken. Er zijn drie schermen:
   
    (a). Het **bladerscherm**: voor het bladeren in, sorteren en filteren van gegevens die uit de lijst zijn opgehaald.
    
    (b). Het **detailscherm**: voor het weergeven van meer informatie over een item.
    
    (c). Het scherm voor **bewerken/maken**: waar u een bestaand item bewerkt of een nieuw item maakt.
      
      ![PowerApps Studio met miniatuurweergave](./media/sharepoint-scenario-generate-app/02-02-03-studio-screens-thumbnails.png)

## <a name="step-3-customize-the-apps-browse-screen"></a>Stap 3: Het bladerscherm van de app aanpassen

1. Klik of tik op het bladerscherm.
   
    Het scherm heeft een *indeling* met een *galerie* voor het weergeven van lijstitems en andere *besturingselementen*, zoals een zoekbalk en een sorteerknop.

2. Selecteer de galerie **BrowseGallery1** door op een record te klikken of tikken, behalve de eerste record.
   
    ![Bladergalerie](./media/sharepoint-scenario-generate-app/02-03-01-browse-gallery.png)

3. Klik in het rechterdeelvenster onder **eigenschappen** op **Project aanvragen**. 

4. Werk de velden bij zodat ze overeenkomen met de volgende lijst:
   
   * **RequestDate**

   * **Requestor**

   * **Title**

     ![Galerievelden](./media/sharepoint-scenario-generate-app/02-03-02-gallery-fields.png)

5. Selecteer de eigenschap **Items**, waarbij **BrowseGallery1** nog steeds is geselecteerd.
   
    ![Eigenschap Items](./media/sharepoint-scenario-generate-app/02-03-03-items.png)

6. Wijzig de formule in **SortByColumns(Filter('Projectaanvragen', StartsWith(Title, TextSearchBox1.Text)), "Title", If(SortDescending1, Descending, Ascending))**.
   
    ![Formulebalk](./media/sharepoint-scenario-generate-app/02-03-04-formula.png)
   
    Hiermee kunt u op het veld **Title** sorteren en zoeken in plaats van op de uitgekozen standaardwaarde. Zie [De formule nader bekeken](#formula-deep-dive) voor meer informatie.

6. Klik of tik op **Bestand** en vervolgens op **Opslaan**. Klik of tik op ![Pictogram Terug naar app](./media/sharepoint-scenario-generate-app/icon-back-to-app.png) om naar de app terug te gaan.

## <a name="step-4-review-the-apps-details-screen-and-edit-screen"></a>Stap 4: het detailscherm en het scherm voor bewerken van de app controleren
1. Klik of tik op het detailscherm.
   
    Dit scherm heeft een andere indeling. Het bevat een *weergaveformulier* om de details te tonen van een in de galerie geselecteerd item. Het bevat besturingselementen om items te bewerken en verwijderen en om terug te gaan naar het bladerscherm.
   
    ![Weergaveformulier met details](./media/sharepoint-scenario-generate-app/02-04-01-details.png)

4. Klik of tik op het scherm voor bewerken.
   
    Dit scherm bevat een *bewerkingsformulier* waar u het geselecteerde item kunt bewerken of een nieuw item kunt maken (als u hier rechtstreeks vanuit het bladerscherm terechtkomt). Het bevat besturingselementen om wijzigingen op te slaan of te negeren.

    ![Bewerkingsformulier](./media/sharepoint-scenario-generate-app/02-04-03-edit.png)

## <a name="step-5-run-the-app-from-the-list"></a>Stap 5: De app vanuit de lijst uitvoeren

1. Klik of tik in de lijst **Projectaanvragen** op **Alle items** en vervolgens op **App Projectaanvragen**.
   
    ![App Projectaanvragen weergeven](./media/sharepoint-scenario-generate-app/02-05-01-view-app.png)
2. Klik op **Openen**. Hiermee wordt de app in een nieuw browsertabblad geopend.
   
    ![App Projectaanvragen openen](./media/sharepoint-scenario-generate-app/02-05-02-open-app.png)

3. Klik of tik in de app op ![Pictogram Naar details](./media/sharepoint-scenario-generate-app/icon-details-arrow.png) voor het eerste item in de bladergalerie.
   
    ![Eerste galerie-item](./media/sharepoint-scenario-generate-app/02-05-04-first-item.png)

4. Klik of tik op ![Pictogram Pen (bewerken)](./media/sharepoint-scenario-generate-app/icon-pencil.png) om het item te bewerken.

5. Werk het veld **Description** bij; wijzig het laatste woord ('groep') in 'team' en klik of tik vervolgens op ![vinkje](./media/sharepoint-scenario-generate-app/icon-check-mark.png)
   
   ![Veld Description bijwerken](./media/sharepoint-scenario-generate-app/02-05-07-edit.png)

6. Sluit het browsertabblad.

7. Ga terug naar de lijst **Projectaanvragen**, klik of tik op **App Projectaanvragen** en vervolgens op **Alle items**.
   
   ![Alle items bekijken](./media/sharepoint-scenario-generate-app/02-05-08-view-all.png)
8. Controleer de wijziging die u hebt gemaakt vanuit de app.
   
    ![De bewerking controleren](./media/sharepoint-scenario-generate-app/02-05-09-verify-edit.png)

Dit is een tamelijk eenvoudige app en we hebben slechts een paar eenvoudige aanpassingen gedaan. U ziet echter dat het mogelijk is snel iets leuks te maken. We gaan door naar de volgende taak, maar bekijk rustig de app nog even om te zien hoe de besturingselementen en de formules samenwerken om de app te laten functioneren.

## <a name="formula-deep-dive"></a>De formule nader bekeken
Deze sectie is optioneel, maar het biedt meer inzicht in de werking van de formules. In stap 3 van deze taak hebben we de formule gewijzigd voor de eigenschap **Items** van **BrowseGallery1**. We hebben met name de sorteer- en zoekfunctie gewijzigd zodat het veld **Title** kan worden gebruikt in plaats van het door PowerApps gekozen veld. Hier ziet u de gewijzigde formule:

**SortByColumns ( Filter ( 'Projectaanvragen', StartsWith ( Title, TextSearchBox1.Text ) ), "Title", If ( SortDescending1, Descending, Ascending ) )**

Wat doet deze formule? De formule stelt de gegevensbron vast die in de galerie wordt weergegeven, filtert de gegevens die zijn gebaseerd op in het zoekvak ingevoerde tekst en sorteert de resultaten op basis van de sorteerknop in de app. De formule maakt voor de uitvoering gebruik van *functies*. Functies gebruiken parameters (invoer), voeren een bewerking uit (bijvoorbeeld filteren) en geven een waarde als resultaat terug (uitvoer):

* De [functie **SortByColumns**](functions/function-sort.md) sorteert een tabel die is gebaseerd op een of meer kolommen.
* De [functie **Filter**](functions/function-filter-lookup.md) zoekt de records in een tabel die aan een formule voldoen die u hebt opgegeven.
* De [functie **StartsWith**](functions/function-startswith.md) test of een tekenreeks begint met een andere tekenreeks.
* De [functie **If**](functions/function-if.md) retourneert een waarde als een voorwaarde waar is en retourneert een andere waarde als dezelfde voorwaarde onwaar is.

Als de functies samen in een formule worden gestopt, gebeurt het volgende:

1. Als u tekst in het zoekvak invoert, vergelijkt de functie **StartsWith** de tekst met het begin van elke tekenreeks in de kolom **Title** van de lijst.
   
    **StartsWith ( Title, TextSearchBox1.Text )**
   
    Als u bijvoorbeeld 'app' in het zoekvak invoert, ziet u een aantal resultaten, waaronder items die beginnen met 'Apparaat' en 'App'. De items met 'Mobiele apparaten' ziet u niet omdat deze niet *beginnen met* 'app'.

2. De functie **Filter** *geeft als resultaat* rijen terug uit de tabel **Projectaanvragen**. Als het zoekvak geen tekst ter vergelijking bevat, geeft **Filter** alle rijen als resultaat terug.
   
    **Filter ( 'Projectaanvragen', StartsWith ( Title, TextSearchBox1.Text )**

3. De functie **If** kijkt of de variabele **SortDescending1** is ingesteld op waar of onwaar (ingesteld door de sorteerknop in de app). De functie geeft vervolgens de waarde **Aflopend** of **Oplopend** als resultaat terug.
   
    **If ( SortDescending1, Aflopend, Oplopend )**

4. De functie **SortByColumns** kan de galerie nu sorteren. In dit geval wordt er gesorteerd op basis van het veld **Title**, maar dit kan een ander veld zijn dan het veld waarnaar u zoekt.

Als u dit nog allemaal kunt volgen, dan hebt u waarschijnlijk een beter idee van hoe de formule werkt en hoe u functies en andere elementen kunt combineren om uw apps naar wens te laten functioneren. Zie [Formuleverwijzingen voor PowerApps](formula-reference.md) voor meer informatie.

## <a name="next-steps"></a>Volgende stappen
De volgende stap in deze reeks zelfstudies bestaat uit het [maken van een stroom voor het beheren van projectgoedkeuringen](sharepoint-scenario-approval-flow.md).

