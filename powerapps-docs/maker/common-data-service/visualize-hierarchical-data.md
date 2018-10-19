---
title: Hiërarchische gegevens visualiseren met modelgestuurde apps | MicrosoftDocs
description: Lees hoe u een query kunt uitvoeren op hiërarchisch gerelateerde gegevens en deze kunt visualiseren
ms.custom: ''
ms.date: 09/19/2018
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
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="visualize-hierarchical-data-with-model-driven-apps"></a>Hiërarchische gegevens visualiseren met modelgestuurde apps

Wanneer een entiteit is geconfigureerd voor een hiërarchische zelfreferentiële relatie, kunt u visualisaties configureren met die hiërarchie. Meer informatie: [Hiërarchisch gerelateerde gegevens definiëren en opvragen](../common-data-service/define-query-hierarchical-data.md)

Entiteiten waarvoor standaard visualisaties beschikbaar zijn, zijn onder andere [Account](/powerapps/developer/common-data-service/reference/entities/account), [Positie](/powerapps/developer/common-data-service/reference/entities/position) en [Gebruiker](/powerapps/developer/common-data-service/reference/entities/systemuser). In de rasterweergave van deze entiteiten kunt u het pictogram zien dat het hiërarchiediagram voorstelt, links van de recordnaam. Het hiërarchiepictogram is niet standaard aanwezig voor alle records. Het pictogram wordt weergegeven voor de records in een hiërarchische relatie.  
> [!div class="mx-imgBorder"] 
> ![Knop Hiërarchie weergeven](media/view-hierarchy-button.png)  
  
 Als u het hiërarchiepictogram kiest, kunt u de hiërarchie bekijken met de structuurweergave aan de linkerkant en de tegelweergave aan de rechterkant, zoals hieronder wordt weergegeven:  
  
> [!div class="mx-imgBorder"] 
> ![Structuur- en tegelweergave in hiërarchie](media/tree-view-and-tile-view-in-hierarchy.png)  
  
 Enkele andere entiteiten kunnen ook worden ingeschakeld voor een hiërarchie. Dit zijn de entiteiten [Contactpersoon](/powerapps/developer/common-data-service/reference/entities/contact) en [Team](/powerapps/developer/common-data-service/reference/entities/team). Alle aangepaste entiteiten kunnen worden ingeschakeld voor een hiërarchie.  
  
Belangrijke dingen om te onthouden bij het maken van visualisaties:  
  
- Er kan slechts één (1:N) zelfreferentiële relatie per entiteit worden ingesteld als hiërarchisch. In een zelfreferentiële relatie moeten de primaire entiteit en gerelateerde entiteit van hetzelfde type zijn.  
- Een hiërarchie of visualisatie is gebaseerd op slechts één entiteit. U kunt de accounthiërarchie weergeven die accounts op meerdere niveaus laat zien, maar u kunt geen accounts en contactpersonen weergegeven in dezelfde hiërarchievisualisatie. 
- Het maximum aantal velden dat in een tegel kan worden weergegeven, is vier. Als u meer velden toevoegt aan het snelformulier dat voor de tegelweergave wordt gebruikt, worden alleen de eerste vier velden weergegeven. 

## <a name="hierarchy-settings"></a>Instellingen voor hiërarchie

Als u voor een hiërarchie visualisaties wilt inschakelen, moet u de hiërarchie verbinden met een snelle-weergaveformulier. Dit kan alleen worden gedaan met de oplossingenverkenner.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

De hiërarchie-instellingen worden gekoppeld aan een entiteit in de oplossingenverkenner. 

1. Selecteer terwijl [entiteiten worden weergegeven](../common-data-service/create-edit-entities-solution-explorer.md#view-entities) de optie **Instellingen voor hiërarchie**.
2. Als een bestaande hiërarchie-instelling bestaat, kunt u deze bewerken. Klik anders op **Nieuw** om een nieuwe hiërarchie te maken.
    
    > [!NOTE]
    > Als de hiërarchie-instellingen niet bestaan, kan voor de entiteit geen hiërarchie worden geconfigureerd.
    >Er kan slechts één hiërarchie-instelling zijn 

1. Stel de gegevens in de volgende velden in:

|Veld|Beschrijving|
|--|--|
|**Name**|*Vereist.* Voeg een unieke naam toe voor de hiërarchie-instellingen. Dit is doorgaans de naam van de entiteit. Deze waarde bevat het aanpassingsvoorvoegsel van de oplossingsuitgever.|
|**Standaard snelle-weergaveformulier**|*Vereist.* Kies een bestaand snelle-weergaveformulier of kies **Nieuw maken** om de editor Snelle-weergaveformulier te openen en een nieuw formulier te maken.|
|**Hiërarchische relatie**|*Vereist.* Als er al een hiërarchische relatie voor de entiteit is gedefinieerd, wordt de waarde hier ingesteld. Als er geen waarde is, selecteert u **Een relatie als ingeschakeld markeren voor hiërarchieën** om een dialoogvenster te openen waarin u een van de beschikbare zelfreferentiële relaties kunt kiezen.|
|**Beschrijving**|Neem een beschrijving van het doel voor deze hiërarchie op zodat persoon die het systeem willen aanpassen, begrijpen waarom dit is gedaan.|
    

Dezelfde hiërarchische instellingen voor visualisatie worden eenmaal ingesteld, maar gelden voor zowel webtoepassing als mobiele clients. Op tablets worden visuele weergaven in een gewijzigde vorm aangeboden die geschikt is voor het kleinere formaat. De aanpasbare onderdelen die zijn vereist voor hiërarchische visualisatie zijn oplossingsbewust. Hierdoor kunnen zijn worden getransporteerd tussen organisaties, zoals elke andere aanpassing. U kunt de kenmerken die in de visualisatie worden weergegeven configureren door een snelformulier aan te passen met behulp van de formuliereneditor.
  
## <a name="visualization-walk-through"></a>Visualisatievoorbeeld

Laten we een voorbeeld van het maken van de visualisatie voor een aangepaste entiteit gaan bekijken. We hebben een aangepaste entiteit met de naam `new_Widget` gemaakt, een (1:N) zelfreferentiële relatie met de naam `new_new_widget_new_widget` gemaakt en deze als hiërarchisch gemarkeerd, zoals hieronder weergegeven:  
  
![Relatiedefinitie van widget](media/widget-relationship-definition.png)  
  
Vervolgens hebben we in de rasterweergave van **Hiërarchie-instellingen** de hiërarchische relatie `new_new_widget_new_widget` geselecteerd. In het formulier hebben we de vereiste velden ingevuld. Als u de (1:N) relatie nog niet als hiërarchisch hebt gemarkeerd, voert de koppeling op het formulier u terug naar het formulier voor de relatiedefinitie, waar u de relatie als hiërarchisch kunt markeren.  

> [!IMPORTANT]
> Elke entiteit kan slechts één hiërarchische relatie tegelijk hebben. Als u een andere zelfreferentiële relatie instelt, kan dit gevolgen hebben. Meer informatie: [Hiërarchische gegevens opgeven](../common-data-service/define-query-hierarchical-data.md#define-hierarchical-data)

> [!div class="mx-imgBorder"] 
> ![Instellingen voor hiërarchie](media/hierarchy-settings.png)  
  
Voor **Snelle-weergaveformulier** hebben we een snelformulier gemaakt met de naam **Tegelformulier voor widgethiërarchie**. Op dit formulier hebben we vier velden toegevoegd voor weergave in elke tegel:  

> [!div class="mx-imgBorder"] 
> ![Snelformulier voor widget maken](media/create-quickform.png)  
  
Nadat we de setup hebben voltooid, hebben we twee records gemaakt: *Standaardwidget* en *Premiumwidget*. Nadat we van Premiumwidget een bovenliggend element van Standaardwidget hebben gemaakt met het opzoekveld, worden in de rasterweergave `new_Widget` de hiërarchiepictogrammen weergegeven, zoals hieronder weergegeven:  

> [!div class="mx-imgBorder"] 
> ![Hiërarchieraster van de widget](media/widget-hierarchy-grid.png)  
  
> [!NOTE]
>  De hiërarchiepictogrammen worden pas weergegeven in de recordrasterweergave als de records zijn gekoppeld in de hiërarchische relatie.  
  
Als u het hiërarchiepictogram kiest, wordt de hiërarchie `new_Widget` weergegeven met de structuurweergave aan de linkerkant en de tegelweergave aan de rechterkant. Er zijn hierbij twee records te zien. Elke tegel bevat vier velden die we in het **Tegelformulier voor widgethiërarchie** hebben verstrekt:  

> [!div class="mx-imgBorder"] 
> ![Structuur en tegelsweergaven van de widget](media/widget-tree-tiles.png)  

Op basis van uw behoeften, kunt u kiezen tussen het gebruik van een boomstructuurweergave met de hele hiërarchie en een tegelweergave. Dat is een gedetailleerde weergave van een kleiner deel van de hiërarchie. Beide weergaven worden naast elkaar getoond. U kunt een hiërarchie bekijken door een hiërarchiestructuur uit te vouwen en samen te vouwen. 

### <a name="see-also"></a>Zie ook 

[Hiërarchische gegevens definiëren en opvragen](../common-data-service/define-query-hierarchical-data.md)<br />
[Video: Hiërarchievisualisatie](http://www.youtube.com/watch?v=_dGBE6icLNw&index=9&list=PLC3591A8FE4ADBE07)
