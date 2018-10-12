---
title: Hiërarchische gegevens visualiseren met modelgestuurde apps | MicrosoftDocs
description: Meer informatie over hoe u query's uitvoert op hiërarchische gegevens en deze visualiseert
ms.custom: ''
ms.date: 06/02/2018
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
ms.openlocfilehash: bed8662d7d9475215df8e92490702b68e36574e2
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39680020"
---
# <a name="visualize-hierarchical-data-with-model-driven-apps"></a>Hiërarchische gegevens visualiseren met modelgestuurde apps

> [!NOTE]
> Hiërarchische gegevensvisualisaties zijn alleen beschikbaar voor modelgestuurde apps die zijn geconfigureerd voor de **web**-client. Visualisaties zijn niet beschikbaar voor de **Unified Interface**-client. Meer informatie: [Een modelgestuurde app maken met behulp van de app-ontwerper](../model-driven-apps/create-edit-app.md)

Wanneer een entiteit is geconfigureerd om een hiërarchische, zelfrefererende relatie te hebben, kunt u visualisaties configureren met behulp van die hiërarchie. Meer informatie: [Hiërarchisch gerelateerde gegevens definiëren en er query's op uitvoeren](../common-data-service/define-query-hierarchical-data.md)

De entiteiten die standaard over visualisaties beschikken, zijn [Account](/powerapps/developer/common-data-service/reference/entities/account), [Positie](/powerapps/developer/common-data-service/reference/entities/position) en [Gebruiker](/powerapps/developer/common-data-service/reference/entities/systemuser). In de rasterweergave van deze entiteiten ziet u het pictogram dat de hiërarchiegrafiek weergeeft aan de linkerkant van de recordnaam. Het hiërarchiepictogram is niet standaard aanwezig voor alle records. Het pictogram wordt weergegeven voor de records die aan elkaar verwant zijn met behulp van de hiërarchische relatie.  
  
 ![Accounts met hiërarchie](media/account-list-with-hierarchy.png)  
  
 Als u het hiërarchiepictogram selecteert, kunt u de hiërarchie weergeven met de structuurweergave links en de tegelweergave rechts, zoals hieronder wordt weergegeven:  
  
 ![Accountstructuur en tegelweergave](media/hierachy-security-accounts-tile-view.png)  
  
 Enkele andere entiteiten kunnen worden ingeschakeld voor een hiërarchie. Deze entiteiten zijn [Contactpersoon](/powerapps/developer/common-data-service/reference/entities/contact) en [Team](/powerapps/developer/common-data-service/reference/entities/team). Alle aangepaste entiteiten kunnen worden ingeschakeld voor een hiërarchie.  
  
Belangrijke dingen om te onthouden wanneer u visualisaties maakt:  
  
- Per entiteit kan slechts één (1:N) zelfrefererende relatie worden ingesteld als hiërarchisch. In een zelfrefererende relatie moeten de primaire entiteit en de gerelateerde entiteit van hetzelfde type zijn.  
- Een hiërarchie of visualisatie is gebaseerd op één entiteit. U kunt de accounthiërarchie weergeven met accounts op meerdere niveaus, maar u kunt geen accounts en contactpersonen weergeven in dezelfde hiërarchievisualisatie. 
- In een tegel kunnen maximale vier velden worden weergegeven. Als u meer velden toevoegt aan het Snelformulier dat wordt gebruikt voor de tegelweergave, worden alleen de eerste vier velden weergegeven. 

## <a name="hierarchy-settings"></a>Hiërarchie-instellingen

U moet de hiërarchie koppelen aan een snelle-weergaveformulier om visualisaties voor een hiërarchie in te schakelen. Dit kunt u alleen doen met Solution Explorer.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

De hiërarchie-instellingen zijn gekoppeld aan een entiteit in Solution Explorer. 

1. Terwijl u [entiteiten weergeeft](../common-data-service/create-edit-entities-solution-explorer.md#view-entities), selecteert u **Hiërarchie-instellingen**.
2. Als er een bestaande hiërarchie-instelling bestaat, kunt u deze bewerken. Of klik op **Nieuw** om een nieuwe te maken.
    
    > [!NOTE]
    > Als de hiërarchie-instellingen niet bestaan, is de entiteit niet geschikt om er een hiërarchie voor te configureren.
    >Er mag slechts één hiërarchie-instelling zijn 

1. Stel de gegevens in de volgende velden in:

|Veld|Beschrijving|
|--|--|
|**Naam**|*Vereist.* Voeg een unieke naam toe voor de hiërarchie-instellingen. Dit is meestal alleen de naam van de entiteit. Deze waarde omvat het aanpassingsvoorvoegsel van de oplossingsuitgever.|
|**Standaard snelle-weergaveformulier**|*Vereist.* Kies een bestaand snelle-weergaveformulier of kies **Nieuw** om de Editor voor snelle-weergaveformulieren te openen om een nieuwe te maken.|
|**Hiërarchische relatie**|*Vereist.* Als al een hiërarchische relatie is gedefinieerd voor de entiteit, wordt hier de waarde ingesteld. Als er geen waarde is, selecteert u **Een relatie als ingeschakeld markeren voor hiërarchieën** om een dialoogvenster te openen waarin u een van de beschikbare zelfrefererende relaties kunt kiezen.|
|**Description**|Neem een beschrijving op van het doel van deze hiërarchie, zodat mensen die in de toekomst het systeem aanpassen, begrijpen waarom dit is gedaan.|
    

Dezelfde hiërarchische instellingen voor visualisatie worden eenmaal ingesteld, maar zijn van toepassing op zowel webclients als mobiele clients. In tablets worden de visuele elementen weergegeven in een aangepaste indeling die geschikt is voor de kleinere vormfactor. De aanpasbare onderdelen die zijn vereist voor hiërarchische visualisatie hebben ondersteuning voor oplossingen en kunnen daarom worden overgebracht tussen organisaties, zoals alle andere aanpassingen. U kunt de kenmerken configureren die worden weergegeven in de visualisatie door een Snelformulier aan te passen met behulp van de formuliereneditor.
  
## <a name="visualization-walk-through"></a>Overzicht van visualisaties

We bekijken een voorbeeld van het maken van de visualisatie voor een aangepaste entiteit. We hebben een aangepaste entiteit gemaakt met de naam `new_Widget`, een zelfrefererende relatie (1: n) gemaakt `new_new_widget_new_widget` en deze gemarkeerd als hiërarchisch, zoals hier wordt weergegeven.  
  
![Definitie van widgetrelaties](media/widget-relationship-definition.png)  
  
In de rasterweergave **Hiërarchie-instellingen** hebben we daarna de `new_new_widget_new_widget` hiërarchische relatie geselecteerd. In het formulier hebben we de vereiste velden ingevuld. Als u de relatie (1: n) nog niet als hiërarchisch hebt gemarkeerd, brengt de koppeling op het formulier u terug naar het formulier voor relatiedefinities, waar u de relatie als hiërarchisch kunt markeren.  

> [!IMPORTANT]
> Elke entiteit kan slechts één hiërarchische relatie tegelijk hebben. Het kan gevolgen hebben als u dit wijzigt in een andere zelfrefererende relatie. Meer informatie: [Hiërarchische gegevens definiëren](../common-data-service/define-query-hierarchical-data.md#define-hierarchical-data)
  
![Hiërarchie-instellingen](media/hierarchy-settings.png)  
  
Voor het **Snelle-weergaveformulier** hebben we een Snelformulier gemaakt met de naam **Formulier widgethiërarchietegels**. Aan dit formulier hebben we vier velden toegevoegd om in elke tegel weer te geven.  
  
![Snelformulier maken voor widget](media/create-quickform.png)  
  
Nadat we de instellingen hebben voltooid, hebben we twee records gemaakt: *Standaardwidget* en *Premium-widget*. Nadat van de Premium-widget een bovenliggend element van de standaardwidget is gemaakt met behulp van het opzoekveld, gaf de `new_Widget` rasterweergave de hiërarchiepictogrammen weer, zoals hieronder wordt weergegeven:  
  
![Het hiërarchieraster van de widget](media/widget-hierarchy-grid.png)  
  
> [!NOTE]
>  De hiërarchiepictogrammen worden pas weergegeven in de recordrasterweergave als de records aan elkaar zijn gerelateerd met behulp van de hiërarchische relatie.  
  
Als u het hiërarchiepictogram selecteert, wordt de `new_Widget` hiërarchie weergeven met de structuurweergave links en de tegelweergave rechts, waarbij twee records worden weergegeven: Elke tegel bevat vier velden die we hebben opgegeven in het **Formulier widgethiërarchietegels**.  
  
![Structuur en tegelweergaven van de widget](media/widget-tree-tiles.png)  

Op basis van uw behoeften, kunt u kiezen tussen een structuurweergave, die de gehele hiërarchie weergeeft, of een tegelweergave, die een kleiner deel van de hiërarchie weergeeft. Beide weergaven worden naast elkaar weergegeven. U kunt een hiërarchie verkennen door een hiërarchische structuur uit te vouwen en samen te trekken. 

### <a name="see-also"></a>Zie ook 

[Hiërarchisch gerelateerde gegevens definiëren en er query's op uitvoeren](../common-data-service/define-query-hierarchical-data.md)<br />
[Video: Visualisatie van een hiërarchie](http://www.youtube.com/watch?v=_dGBE6icLNw&index=9&list=PLC3591A8FE4ADBE07)