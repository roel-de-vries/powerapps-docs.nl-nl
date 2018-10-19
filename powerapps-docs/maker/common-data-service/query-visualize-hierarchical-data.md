---
title: Query uitvoeren op hiërarchische gegevens en deze visualiseren met PowerApps | MicrosoftDocs
description: Lees hoe u een query kunt uitvoeren op hiërarchisch gerelateerde gegevens en deze kunt visualiseren
ms.custom: ''
ms.date: 06/20/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: 0cf62817-5ff5-40bb-ad17-e1f6b0921720
caps.latest.revision: 42
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="query-and-visualize-hierarchically-related-data"></a>Hiërarchische gegevens opvragen en visualiseren

U kunt waardevol bedrijfsinzicht verkrijgen door hiërarchisch gerelateerde gegevens te visualiseren. De mogelijkheden voor hiërarchische modellering en visualisatie bieden u een aantal voordelen:  
  
-   Bekijk en onderzoek complexe hiërarchische informatie.  
  
-   Bekijk KPI's (Key Performance Indicators) in de contextuele weergave van een hiërarchie.  
  
-   Voer een visuele analyse uit van belangrijke informatie op het web en de tablets.  
  
Voor bepaalde entiteiten, zoals account en gebruiker, worden de visualisaties standaard meegeleverd. Andere entiteiten, met inbegrip van aangepaste entiteiten, kunnen worden ingeschakeld voor een hiërarchie en u kunt visualisaties voor hen maken. Op basis van uw behoeften, kunt u kiezen tussen het gebruik van een boomstructuurweergave met de hele hiërarchie en een tegelweergave. Dat is een gedetailleerde weergave van een kleiner deel van de hiërarchie. Beide weergaven worden naast elkaar getoond. U kunt een hiërarchie bekijken door een hiërarchiestructuur uit te vouwen en samen te vouwen. Dezelfde hiërarchische instellingen voor visualisatie worden eenmaal ingesteld, maar gelden voor zowel webtoepassing als mobiele clients. Op tablets worden visuele weergaven in een gewijzigde vorm aangeboden die geschikt is voor het kleinere formaat. De aanpasbare onderdelen die zijn vereist voor hiërarchische visualisatie zijn oplossingsbewust. Hierdoor kunnen zijn worden getransporteerd tussen organisaties, zoals elke andere aanpassing. U kunt de kenmerken die in de visualisatie worden weergegeven configureren door een snelformulier aan te passen met behulp van de formuliereneditor. Het is niet vereist dat u code schrijft.  
  
<a name="BKMK_Querydata"></a>   
## <a name="query-hierarchical-data"></a>Hiërarchische gegevens opvragen  
 Met Common Data Service voor Apps worden hiërarchische gegevensstructuren ondersteund door zelfreferentiële een-op-veel-relaties (1:N) van de gerelateerde records. In het verleden moest u regelmatig de gerelateerde records opvragen om hiërarchische gegevens te kunnen bekijken. Momenteel kunt u de bijbehorende gegevens opvragen als hiërarchie, in één stap. U kunt records opvragen met de logica voor **Onder** en **Niet onder**. De hiërarchische operators **Onder** en **Niet onder** zijn beschikbaar via Geavanceerd zoeken en de werkstroomeditor. Voor meer informatie over hoe u deze operatoren gebruikt, raadpleegt u [Werkstroomstappen configureren](/flow/configure-workflow-steps). Zie [Een geavanceerde zoekopdracht maken, bewerken of opslaan](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search) voor meer informatie over geavanceerd zoeken.  
  
 De volgende voorbeelden illustreren verschillende scenario's voor het opvragen van hiërarchieën:  
  
 Hiërarchie van queryaccount  
  
 ![Accounts opvragen in de accounthiërarchie](media/query-accounts.png "Accounts opvragen in de accounthiërarchie")  
  
 De hiërarchie van het queryaccount, inclusief gerelateerde activiteiten  
  
 ![Gerelateerde activiteiten van queryaccount](media/query-account-related-activities.png "Gerelateerde activiteiten van queryaccount")  
  
 De hiërarchie van het queryaccount, inclusief gerelateerde verkoopkansen  
  
 ![Gerelateerde verkoopkansen van queryaccount](media/query-account-related-opportunities.png "Gerelateerde verkoopkansen van queryaccount")  
  
 Als u de gegevens wilt opvragen als een hiërarchie, moet u een van de zelfreferentiële een-op-veel-relaties (1:N) van de entiteit als hiërarchisch instellen. De hiërarchie inschakelen:  
  
1.  Open [oplossingenverkenner](../model-driven-apps/advanced-navigation.md#solution-explorer). 
  
2.  Selecteer de gewenste entiteit, selecteer **1:N-relaties**, en selecteer vervolgens een (1:N-)relatie. 

3.  Stel in **Relatiedefinitie** de optie **Hiërarchisch** in op **Ja**.  
  
> [!NOTE]
> - Sommige van de standaardrelaties (1:N) kunnen niet worden aangepast. Hierdoor wordt voorkomen dat u deze relaties instelt als hiërarchisch.  
> - U kunt een hiërarchische relatie voor de zelfreferentiële relaties van het systeem opgeven. Dit omvat de zelfreferentiële 1:N-relaties van het systeemtype, zoals de relatie "contactpersoon_master_contactpersoon".  
  
<a name="BKMK_Visualizedata"></a>   
## <a name="visualize-hierarchical-data"></a>Hiërarchische gegevens visualiseren  
 Voor de volgende systeementiteiten zijn standaardvisualisaties beschikbaar: `Account`, `Position`, `Product` en `User`. In de rasterweergave van deze entiteiten kunt u het pictogram zien dat het hiërarchiediagram voorstelt, links van de recordnaam. Het hiërarchiepictogram is niet standaard aanwezig voor alle records. Het pictogram wordt weergegeven voor de records met een bovenliggende record, een onderliggende record of allebei.  
 
 > [!div class="mx-imgBorder"] 
 > ![Actieve accounts](media/cust-hs-active-account.png "Actieve accounts")  
  
 Als u het hiërarchiepictogram kiest, kunt u de hiërarchie bekijken met de structuurweergave aan de linkerkant en de tegelweergave aan de rechterkant, zoals hieronder wordt weergegeven:  
  
> [!div class="mx-imgBorder"] 
> ![Accountstructuur- en tegelweergave](media/hierachy-security-accounts-tile-view.png "Accountstructuur- en tegelweergave")  
  
 Een paar andere standaardsysteementiteiten kunnen eveneens worden ingeschakeld voor een hiërarchie. Deze entiteiten omvatten `Case`, `Contact`, `Opportunity`, `Order`, `Quote`, `Campaign` en `Team`. Alle aangepaste entiteiten kunnen worden ingeschakeld voor een hiërarchie.  
  
> [!TIP]
>  Als een entiteit kan worden ingeschakeld voor een hiërarchie:  
>  Vouw in oplossingsverkenner de entiteit uit die u wilt. Het entiteitsonderdeel genaamd **Instellingen voor hiërarchie** wordt weergegeven. De entiteiten die niet kunnen worden ingeschakeld voor een hiërarchie hebben dit onderdeel niet, met uitzondering van de entiteit Verkooprayon van Dynamics 365 Customer Engagement. Hoewel **Instellingen voor hiërarchie** wordt weergegeven voor de entiteit Verkooprayon, kan de entiteit niet worden ingeschakeld voor een hiërarchie.  
  
 Belangrijke dingen om te onthouden bij het maken van visualisaties:  
  
-   Er kan slechts één (1:N) zelfreferentiële relatie per entiteit worden ingesteld als hiërarchisch. In deze relatie moeten de primaire entiteit en de gerelateerde entiteit van hetzelfde type zijn, zoals account_parent_account of new_new_widget_new_widget.  
  
-   Momenteel is een hiërarchie of visualisatie gebaseerd op slechts één entiteit. U kunt de accounthiërarchie weergeven die accounts op meerdere niveaus laat zien, maar u kunt geen accounts en contactpersonen weergegeven in dezelfde hiërarchievisualisatie.  
  
-   Er kunnen maximaal vier velden worden weergegeven in een tegel. Als u meer velden toevoegt aan het snelformulier dat voor de tegelweergave wordt gebruikt, worden alleen de eerste vier velden weergegeven.  
  
### <a name="visualization-example"></a>Voorbeeld van visualisatie  
 Laten we een voorbeeld van het maken van de visualisatie voor een aangepaste entiteit gaan bekijken. We hebben een aangepaste entiteit gemaakt met de naam new_Widget, een (1:N) zelfreferentiële relatie **new_new_widget_new_widget** vervaardigd en deze als hiërarchisch gemarkeerd, zoals hier weergegeven.  
  
 ![Definitie van widgetrelatie](media/widget-relationship-definition.png "Definitie van widgetrelatie")  
  
 Vervolgens hebben we in de rasterweergave van **Hiërarchie-instellingen** de hiërarchische relatie **new_new_widget_new_widget** geselecteerd. In het formulier hebben we de vereiste velden ingevuld. Als u de (1:N) relatie nog niet als hiërarchisch hebt gemarkeerd, voert de koppeling op het formulier u terug naar het formulier voor de relatiedefinitie, waar u de relatie als hiërarchisch kunt markeren.  
  
 Voor **Snelle-weergaveformulier** hebben we een snelformulier gemaakt met de naam **Tegelformulier voor widgethiërarchie**. Op dit formulier hebben we vier velden toegevoegd voor weergave in elke tegel:  
  
> [!div class="mx-imgBorder"] 
> ![Snelformulier voor widget maken](media/create-quickf-orm.png "Snelformulier voor widget maken")  
  
 Nadat we de setup hebben voltooid, hebben we twee records gemaakt: Standaardwidget en Premiumwidget. Nadat we de Premiumwidget tot een bovenliggend element van de Standaardwidget hebben gemaakt met het opzoekveld, geeft de rasterweergave new_Widget de hiërarchieknoppen weer, zoals hieronder weergegeven:  
  
> [!div class="mx-imgBorder"] 
> ![Hiërarchieraster van widget](media/widget-hierarchy-grid.png "Hiërarchieraster van widget")  
  
> [!TIP]
>  De hiërarchiepictogrammen worden niet weergegeven in de recordrasterweergave totdat de records zijn gekoppeld in de hiërarchische relatie.  
  
 Als u het hiërarchiepictogram kiest, wordt de hiërarchie van new_Widget weergegeven met de structuurweergave aan de linkerkant en de tegelweergave aan de rechterkant. Er zijn hierbij twee records te zien. Elke tegel bevat vier velden die we in het **Tegelformulier voor widgethiërarchie** hebben verstrekt:  
 
 > [!div class="mx-imgBorder"] 
 > ![Structuur en tegelweergaven van widget](media/widget-tree-tiles.png "Structuur en tegelweergaven van widget")  
  
## <a name="see-also"></a>Zie ook  
 [Video: Hiërarchische beveiligingsmodellering in](http://www.youtube.com/watch?v=kx5So32DrCo&index=10&list=PLC3591A8FE4ADBE07)   
 [Video: Hiërarchievisualisatie](http://www.youtube.com/watch?v=_dGBE6icLNw&index=9&list=PLC3591A8FE4ADBE07)
