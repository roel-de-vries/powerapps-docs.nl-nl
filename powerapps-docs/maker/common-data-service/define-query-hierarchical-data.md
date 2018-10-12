---
title: Hiërarchische gegevens definiëren en opvragen met Common Data Service voor Apps | MicrosoftDocs
description: Leer hiërarchisch gerelateerde gegevens definiëren en er query’s op uitvoeren
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
ms.assetid: 0cf62817-5ff5-40bb-ad17-e1f6b0921720
caps.latest.revision: 42
ms.author: matp
manager: kvivek
ms.openlocfilehash: 4dad7da635156350d104d68108ac4acfbb991862
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39674540"
---
# <a name="define-and-query-hierarchically-related-data"></a>Hiërarchisch gerelateerde gegevens definiëren en er query’s op uitvoeren

U kunt waardevolle zakelijke inzichten verkrijgen door hiërarchisch gerelateerde gegevens te definiëren en te er query’s op uit te voeren. De hiërarchische modellerings- en visualisatiemogelijkheden bieden u diverse voordelen:  
  
- Bekijken en verkennen van complexe hiërarchische gegevens.  
- Key performance indicators (KPI's) in de contextuele weergave van een hiërarchie weergeven.  
- Belangrijke informatie op internet en op de tablets visueel analyseren.  
  
Voor sommige standaardentiteiten zijn al hiërarchieën gedefinieerd. Andere entiteiten, inclusief aangepaste entiteiten, kunnen worden ingeschakeld voor een hiërarchie en u kunt de visualisaties voor deze entiteiten maken. 

## <a name="define-hierarchical-data"></a>Hiërarchische gegevens definiëren

Met Common Data Service voor Apps worden hiërarchische gegevensstructuren ondersteund door *naar zichzelf verwijzende* één-op-veel (1:N) relaties van de gerelateerde records. 

> [!NOTE]
> *Naar zichzelf verwijzend* betekent dat de entiteit is gerelateerd aan zichzelf. De accountentiteit heeft bijvoorbeeld een opzoekveld om deze te koppelen aan een andere accountentiteitsrecord.

Wanneer er een naar zichzelf verwijzende één-op-veel (1:N) relatie bestaat, is in de relatiedefinitie de optie **Hiërarchisch** beschikbaar om in te stellen op **Ja**.

![Hiërarchische instelling in relatiedefinitie](media/self-referential-relationship-car-solution-explorer.png)

Als u de gegevens wilt opvragen als een hiërarchie, moet u een van de naar zichzelf verwijzende één-op-veel (1:N) relaties van de entiteit instellen als hiërarchisch. Dit kan alleen worden gedaan met Solution Explorer.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

De hiërarchie inschakelen:  
  
1. Terwijl u [1:N-relaties](create-edit-1n-relationships-solution-explorer.md#view-entity-relationships) bekijkt, selecteert u de naar zichzelf verwijzende relatie die u wilt bewerken.
2. Stel **Hiërarchisch** in op **Ja** in de **Relatiedefinitie**.  
  
> [!NOTE]
> - Sommige vooraf gedefinieerde (1:N) relaties kunnen niet worden aangepast. Dit voorkomt dat u die relaties als hiërarchisch kunt instellen.  
> - U kunt een hiërarchische relatie opgeven voor de naar zichzelf verwijzende relaties van het systeem. Dit geldt ook voor de 1:N naar zichzelf verwijzende relaties van het systeemtype, zoals de relatie "contact_master_contact".  

> [!IMPORTANT]
> U kunt meerdere naar zichzelf verwijzende relaties hebben, maar er kan slechts één relatie per entiteit worden gedefinieerd als de hiërarchische relatie. Als u de instelling probeert te wijzigen nadat deze is toegepast, krijgt u een waarschuwing:
>
> - **Bij het uitschakelen:** Als u de hiërarchie-instelling voor deze relatie uitschakelt, werken de samengetelde definities, processen en weergaven die gebruikmaken van deze hiërarchie niet meer. Wilt u doorgaan? 
> - **Bij het inschakelen:** Als u de hiërarchie-instelling voor deze relatie inschakelt, worden alle samengetelde definities die de bestaande hiërarchie gebruiken ongeldig. Wilt u doorgaan?
>
> Tenzij u er zeker van bent dat er geen andere afhankelijkheden zijn van de bestaande hiërarchie, moet u alle documentatie over de implementatie bekijken of overleggen met andere aanpassers om te begrijpen hoe de bestaande hiërarchische relatie wordt gebruikt voordat u doorgaat.

<a name="BKMK_Querydata"></a> 
  
## <a name="query-hierarchical-data"></a>Query’s uitvoeren op hiërarchische gegevens  

Zonder een gedefinieerde hiërarchie moet u iteratief naar de gerelateerde records zoeken om hiërarchische gegevens op te vragen. Met een gedefinieerde hiërarchie kunt u de gerelateerde gegevens in één stap als een hiërarchie opvragen. U kunt records opvragen met behulp van de logica **Onder** en **Niet onder**. De hiërarchische operators **Onder** en **Niet onder** zijn beschikbaar in Geavanceerd zoeken en in de werkstroom-editor. Zie [Configure workflow steps](/flow/configure-workflow-steps#setting-conditions-for-workflow-actions) (werkstroomstappen configureren) voor meer informatie over het gebruik van deze operators. Zie [Een geavanceerde zoekopdracht maken, bewerken of opslaan](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search) voor meer informatie over geavanceerd zoeken  

> [!NOTE]
> Ontwikkelaars kunnen deze operators ook gebruiken in hun code. Meer informatie: [Documentatie voor ontwikkelaars: query’s uitvoeren op hiërarchische gegevens](/dynamics365/customer-engagement/developer/org-service/query-hierarchical-data)
  
De volgende voorbeelden illustreren scenario's voor het uitvoeren van query’s op hiërarchieën:  
  
### <a name="query-account-hierarchy"></a>Query uitvoeren op accounthiërarchie  
  
![Query uitvoeren op accounts in de accounthiërarchie](media/query-accounts.png)  
  
### <a name="query-account-hierarchy-including-related-activities"></a>Query uitvoeren op accounthiërarchie, inclusief gerelateerde activiteiten  
  
![Query uitvoeren op gerelateerde activiteiten van account](media/query-account-related-activities.png)  
  
###  <a name="query-account-hierarchy-including-related-opportunities"></a>Query uitvoeren op accounthiërarchie, inclusief gerelateerde verkoopkansen  
  
![Query uitvoeren op gerelateerde verkoopkansen van account](media/query-account-related-opportunities.png)  
  
## <a name="see-also"></a>Zie ook 
[1:N (een-op-veel)- of N:1 (veel-op-een)-relaties maken of bewerken](create-edit-1n-relationships.md)<br />
[1:N (een-op-veel)- of N:1 (veel-op-een)-relaties maken of bewerken met behulp van Solution Explorer](create-edit-1n-relationships-solution-explorer.md)<br />
[Hiërarchische gegevens visualiseren met modelgestuurde apps](visualize-hierarchical-data.md)<br />
[Video: Hiërarchische beveiligingsmodellering](http://www.youtube.com/watch?v=kx5So32DrCo&index=10&list=PLC3591A8FE4ADBE07)<br />
[Video: Visualisatie van een hiërarchie](http://www.youtube.com/watch?v=_dGBE6icLNw&index=9&list=PLC3591A8FE4ADBE07)
