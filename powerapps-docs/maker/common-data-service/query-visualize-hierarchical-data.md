---
title: Hiërarchische gegevens visualiseren en query’s hierin uitvoeren met PowerApps | MicrosoftDocs
description: Meer informatie over hoe u query’s uitvoert op hiërarchische gegevens en deze visualiseert
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
ms.openlocfilehash: ec45f43266c1920d05301c92bdd67838b40b7734
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39674991"
---
# <a name="query-and-visualize-hierarchically-related-data"></a>Query's uitvoeren en hiërarchisch gerelateerde gegevens visualiseren

U kunt waardevolle zakelijke inzichten verkrijgen door hiërarchisch gerelateerde gegevens te visualiseren. De hiërarchische modellerings- en visualisatiemogelijkheden bieden u diverse voordelen:  
  
-   Bekijken en verkennen van complexe hiërarchische gegevens.  
  
-   Key performance indicators (KPI's) in de contextuele weergave van een hiërarchie weergeven.  
  
-   Belangrijke informatie op internet en op de tablets visueel analyseren.  
  
Voor sommige entiteiten, zoals het account en de gebruiker, worden gebruiksklare visualisaties meegeleverd. Andere entiteiten, inclusief aangepaste entiteiten, kunnen worden ingeschakeld voor een hiërarchie en u kunt de visualisaties voor deze entiteiten maken. Op basis van uw behoeften, kunt u kiezen tussen een structuurweergave, die de gehele hiërarchie weergeeft, of een tegelweergave, die een kleiner deel van de hiërarchie weergeeft. Beide weergaven worden naast elkaar weergegeven. U kunt een hiërarchie verkennen door een hiërarchische structuur uit te vouwen en samen te trekken. Dezelfde hiërarchische instellingen voor visualisatie worden eenmaal ingesteld, maar zijn van toepassing op zowel webclients als mobiele clients. In tablets worden de visuele elementen weergegeven in een aangepaste indeling die geschikt is voor de kleinere vormfactor. De aanpasbare onderdelen die zijn vereist voor hiërarchische visualisatie hebben ondersteuning voor oplossingen en kunnen daarom worden overgebracht tussen organisaties, zoals alle andere aanpassingen. U kunt de kenmerken configureren die worden weergegeven in de visualisatie door een Snelformulier aan te passen met behulp van de formuliereneditor. U hoeft geen code te schrijven.  
  
<a name="BKMK_Querydata"></a>   
## <a name="query-hierarchical-data"></a>Query’s uitvoeren op hiërarchische gegevens  
 Met Common Data Service voor Apps worden hiërarchische gegevensstructuren ondersteund door naar zichzelf verwijzende één-op-veel (1:N) relaties van de gerelateerde records. In het verleden moest u om hiërarchische gegevens weer te geven een query steeds opnieuw uitvoeren voor de bijbehorende records. Tegenwoordig kun u de gerelateerde gegevens in één stap als een hiërarchie opvragen. U kunt records opvragen met behulp van de logica **Onder** en **Niet onder**. De hiërarchische operators **Onder** en **Niet onder** zijn beschikbaar in Geavanceerd zoeken en in de werkstroom-editor. Zie [Werkstroomstappen configureren](/flow/configure-workflow-steps) voor meer informatie over het gebruik van deze operators. Zie [Een geavanceerde zoekopdracht maken, bewerken of opslaan](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search) voor meer informatie over geavanceerd zoeken  
  
 De volgende voorbeelden illustreren scenario's voor het uitvoeren van query’s op verschillende hiërarchieën:  
  
 Query uitvoeren op accounthiërarchie  
  
 ![Query uitvoeren op accounthiërarchie](media/query-accounts.png "Query uitvoeren op accounthiërarchie")  
  
 Query uitvoeren op accounthiërarchie, inclusief gerelateerde activiteiten  
  
 ![Query uitvoeren op gerelateerde activiteiten van account](media/query-account-related-activities.png "Query uitvoeren op gerelateerde activiteiten van account")  
  
 Query uitvoeren op accounthiërarchie, inclusief gerelateerde kansen  
  
 ![Query uitvoeren op gerelateerde kansen van account](media/query-account-related-opportunities.png "Query uitvoeren op gerelateerde kansen van account")  
  
 Als u de gegevens wilt opvragen als een hiërarchie, moet u een van de naar zichzelf verwijzende één-op-veel (1:N) relaties van de entiteit instellen als hiërarchisch. De hiërarchie inschakelen:  
  
1.  Open [Solution Explorer](../model-driven-apps/advanced-navigation.md#solution-explorer). 
  
2.  Selecteer de gewenste entiteit, selecteer **1:N relaties** en selecteer vervolgens een relatie (1:N). 

3.  Stel **Hiërarchisch** in op **Ja** in de **Relatiedefinitie**.  
  
> [!NOTE]
> - Sommige vooraf gedefinieerde (1:N) relaties kunnen niet worden aangepast. Dit voorkomt dat u die relaties als hiërarchisch kunt instellen.  
> - U kunt een hiërarchische relatie opgeven voor de naar zichzelf verwijzende relaties van het systeem. Dit geldt ook voor de 1:N naar zichzelf verwijzende relaties van het systeemtype, zoals de relatie ‘contact_master_contact’.  
  
<a name="BKMK_Visualizedata"></a>   
## <a name="visualize-hierarchical-data"></a>Hiërarchische gegevens visualiseren  
 De systeementiteiten waarvoor gebruiksklare visualisaties beschikbaar zijn, zijn `Account`, `Position`, `Product` en `User`. In de rasterweergave van deze entiteiten ziet u het pictogram dat de hiërarchiegrafiek weergeeft, aan de linkerkant van de recordnaam. Het hiërarchiepictogram is niet standaard aanwezig voor alle records. Het pictogram wordt weergegeven voor de records die een bovenliggende record en/of een onderliggende record hebben.  
  
 ![Actieve accounts](media/cust-hs-active-account.png "Actieve accounts")  
  
 Als u het hiërarchiepictogram selecteert, kunt u de hiërarchie weergeven, met de structuurweergave links en de tegelweergave rechts, zoals hieronder getoond:  
  
 ![Accountstructuur en tegelweergave](media/hierachy-security-accounts-tile-view.png "Accountstructuur en tegelweergave")  
  
 Enkele andere gebruiksklare entiteiten kunnen worden ingeschakeld voor een hiërarchie. Dit zijn de entiteiten `Case`, `Contact`, `Opportunity`, `Order`, `Quote`, `Campaign` en `Team`. Alle aangepaste entiteiten kunnen worden ingeschakeld voor een hiërarchie.  
  
> [!TIP]
>  Als een entiteit kan worden ingeschakeld voor een hiërarchie:  
>  Vouw in Solution Explorer de gewenste entiteit uit. Ziet u het entiteitonderdeel genaamd **Hiërarchie-instellingen**. De entiteiten die niet kunnen worden ingeschakeld voor een hiërarchie, beschikken niet over dit onderdeel, met uitzondering van de entiteit Verkooprayon van Dynamics 365-klantcontacten. Hoewel **Hiërarchie-instellingen** wordt weergegeven voor de entiteit Verkooprayon, kan de entiteit niet worden ingeschakeld voor een hiërarchie.  
  
 Belangrijke dingen om te onthouden wanneer u visualisaties maakt:  
  
-   Per entiteit kan slechts één (1:N) zelfrefererende relatie worden ingesteld als hiërarchisch. In deze relatie moeten de primaire entiteit en de gerelateerde entiteit van hetzelfde type zijn, zoals account_parent_account of new_new_widget_new_widget.  
  
-   Op dit moment is een hiërarchie of visualisatie gebaseerd op één entiteit. U kunt de accounthiërarchie weergeven met accounts op meerdere niveaus, maar u kunt geen accounts en contactpersonen weergeven in dezelfde hiërarchievisualisatie.  
  
-   In een tegel kunnen maximaal vier velden worden weergegeven. Als u meer velden toevoegt aan het Snelformulier dat wordt gebruikt voor de tegelweergave, worden alleen de eerste vier velden weergegeven.  
  
### <a name="visualization-example"></a>Voorbeeld van visualisatie  
 We bekijken een voorbeeld van het maken van de visualisatie voor een aangepaste entiteit. We hebben een aangepaste entiteit gemaakt met de naam new_Widget, een zelfrefererende relatie (1:N) **new_new_widget_new_widget** gemaakt en deze gemarkeerd als hiërarchisch, zoals hier wordt weergegeven.  
  
 ![Definitie van widgetrelaties](media/widget-relationship-definition.png "Definitie van widgetrelaties")  
  
 In de rasterweergave **Hiërarchie-instellingen** hebben we daarna de hiërarchische relatie **new_new_widget_new_widget** geselecteerd. In het formulier hebben we de vereiste velden ingevuld. Als u de relatie (1:N) nog niet als hiërarchisch hebt gemarkeerd, brengt de koppeling op het formulier u terug naar het formulier voor relatiedefinities, waar u de relatie als hiërarchisch kunt markeren.  
  
 Voor het **Formulier voor snelle weergave** hebben we een Snelformulier gemaakt met de naam **Formulier widgethiërarchietegels**. Aan dit formulier hebben we vier velden toegevoegd om in elke tegel weer te geven.  
  
 ![Snelformulier voor widget maken](media/create-quickf-orm.png "Snelformulier voor widget maken")  
  
 Na het voltooien van de instellingen hebben we twee records gemaakt: Standaardwidget en Premium-widget. Nadat van de Premium-widget een bovenliggend element van de standaardwidget is gemaakt met behulp van het opzoekveld, gaf de rasterweergave new_Widget de hiërarchiepictogrammen weer, zoals hieronder wordt weergegeven:  
  
 ![Hiërarchieraster van widget](media/widget-hierarchy-grid.png "Hiërarchieraster van widget")  
  
> [!TIP]
>  De hiërarchiepictogrammen worden pas weergegeven in de recordrasterweergave als de records zijn gekoppeld in de hiërarchische relatie.  
  
 Als u het hiërarchiepictogram selecteert, wordt de hiërarchie new_Widget weergeven met de structuurweergave links en de tegelweergave rechts, waarbij twee records worden weergegeven. Elke tegel bevat vier velden die we hebben opgegeven in het **Formulier widgethiërarchietegels**.  
  
 ![Structuur en tegelweergaven van de widget](media/widget-tree-tiles.png "Structuur en tegelweergaven van de widget")  
  
## <a name="see-also"></a>Zie ook  
 [Video: Modellering van hiërarchische beveiliging](http://www.youtube.com/watch?v=kx5So32DrCo&index=10&list=PLC3591A8FE4ADBE07)   
 [Video: Visualisatie van een hiërarchie](http://www.youtube.com/watch?v=_dGBE6icLNw&index=9&list=PLC3591A8FE4ADBE07)
