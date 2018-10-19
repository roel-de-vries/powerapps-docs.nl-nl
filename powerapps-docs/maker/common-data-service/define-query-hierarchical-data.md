---
title: Hiërarchische gegevens definiëren en opvragen met Common Data Service voor Apps | MicrosoftDocs
description: Leer hoe u hiërarchische gegevens definieert en opvraagt
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="define-and-query-hierarchically-related-data"></a>Hiërarchische gegevens definiëren en opvragen

U kunt waardevolle zakelijke inzichten verkrijgen door hiërarchisch gerelateerde gegevens te definiëren en op te vragen. De mogelijkheden voor hiërarchische modellering en visualisatie bieden u een aantal voordelen:  
  
- Bekijk en onderzoek complexe hiërarchische informatie.  
- Bekijk KPI's (Key Performance Indicators) in de contextuele weergave van een hiërarchie.  
- Voer een visuele analyse uit van belangrijke informatie op het web en de tablets.  
  
Voor sommige standaardentiteiten zijn al hiërarchieën gedefinieerd. Andere entiteiten, met inbegrip van aangepaste entiteiten, kunnen worden ingeschakeld voor een hiërarchie en u kunt visualisaties voor hen maken. 

## <a name="define-hierarchical-data"></a>Hiërarchische gegevens definiëren

Met Common Data Service voor Apps worden hiërarchische gegevensstructuren ondersteund door *zelfreferentiële* een-op-veel-relaties (1:N) van de gerelateerde records. 

> [!NOTE]
> *Zelfreferentieel* betekent dat de entiteit aan zichzelf is gerelateerd. De accountentiteit heeft bijvoorbeeld een opzoekveld zodat deze aan een andere accountentiteitsrecord kan worden gekoppeld.

Wanneer een zelfreferentiële een-op-veel-relatie (1:N) bestaat, is in de relatiedefinitie de optie **Hiërarchisch** beschikbaar om te worden ingesteld op **Ja**.

![Hiërarchische instelling in definitie van relatie](media/self-referential-relationship-car-solution-explorer.png)

Als u de gegevens wilt opvragen als een hiërarchie, moet u een van de zelfreferentiële een-op-veel-relaties (1:N) van de entiteit als hiërarchisch instellen. Dit kan alleen worden gedaan met de oplossingenverkenner.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

De hiërarchie inschakelen:  
  
1. Selecteer tijdens het [weergeven van 1:N-relaties](create-edit-1n-relationships-solution-explorer.md#view-entity-relationships) de zelfreferentiële relatie die u wilt bewerken.
2. Stel in **Relatiedefinitie** de optie **Hiërarchisch** in op **Ja**.  
  
> [!NOTE]
> - Sommige van de standaardrelaties (1:N) kunnen niet worden aangepast. Hierdoor wordt voorkomen dat u deze relaties instelt als hiërarchisch.  
> - U kunt een hiërarchische relatie voor de zelfreferentiële relaties van het systeem opgeven. Dit omvat de zelfreferentiële 1:N-relaties van het systeemtype, zoals de relatie "contactpersoon_master_contactpersoon".  

> [!IMPORTANT]
> U kunt meerdere zelfreferentiële relaties hebben, maar per entiteit kan slechts één relatie als de hiërarchische relatie worden gedefinieerd. Als u de eenmaal toegepaste instelling probeert te wijzigen, wordt een waarschuwing weergegeven:
>
> - **Bij uitschakelen:** Als u de hiërarchie-instelling uitschakelt voor deze relatie, werken alle samentellingsdefinities, processen en weergaven waarin deze hiërarchie wordt gebruikt niet. Wilt u doorgaan? 
> - **Bij inschakelen:** Als u de hiërarchie-instelling inschakelt voor deze relatie, worden alle samentellingsdefinities waarin de bestaande hiërarchie wordt gebruikt ongeldig. Wilt u doorgaan?
>
> Tenzij u zeker weet dat er geen andere afhankelijkheden zijn voor de bestaande hiërarchie, moet u voordat u doorgaat de documentatie over de installatie raadplegen of overleggen met andere aanpassers om te begrijpen hoe de bestaande hiërarchische relatie wordt gebruikt.

<a name="BKMK_Querydata"></a> 
  
## <a name="query-hierarchical-data"></a>Hiërarchische gegevens opvragen  

Zonder een gedefinieerde hiërarchie moet u de gerelateerde records herhaaldelijk opvragen om hiërarchische gegevens op te halen. Met een gedefinieerde hiërarchie kunt u de gerelateerde gegevens opvragen als hiërarchie, in één stap. U kunt records opvragen met de logica voor **Onder** en **Niet onder**. De hiërarchische operators **Onder** en **Niet onder** zijn beschikbaar via Geavanceerd zoeken en de werkstroomeditor. Voor meer informatie over hoe u deze operatoren gebruikt, raadpleegt u [Werkstroomstappen configureren](/flow/configure-workflow-steps#setting-conditions-for-workflow-actions). Zie [Een geavanceerde zoekopdracht maken, bewerken of opslaan](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search) voor meer informatie over geavanceerd zoeken.  

> [!NOTE]
> Ontwikkelaars kunnen deze operators ook in code gebruiken. Meer informatie [Documentatie voor ontwikkelaars: Hiërarchische gegevens opvragen](/dynamics365/customer-engagement/developer/org-service/query-hierarchical-data)
  
De volgende voorbeelden illustreren scenario's voor het opvragen van hiërarchieën:  
  
### <a name="query-account-hierarchy"></a>Hiërarchie van queryaccount  
  
![Query uitvoeren op accounts in de accounthiërarchie](media/query-accounts.png)  
  
### <a name="query-account-hierarchy-including-related-activities"></a>De hiërarchie van het queryaccount, inclusief gerelateerde activiteiten  
  
![Gerelateerde activiteiten van de queryaccount](media/query-account-related-activities.png)  
  
###  <a name="query-account-hierarchy-including-related-opportunities"></a>De hiërarchie van het queryaccount, inclusief gerelateerde verkoopkansen  
  
![Gerelateerde verkoopkansen van de queryaccount](media/query-account-related-opportunities.png)  
  
## <a name="see-also"></a>Zie ook 
[1:N- (één-op-veel) of N:1-entiteitsrelaties (veel-op-één) maken en bewerken](create-edit-1n-relationships.md)<br />
[1:N- (één-op-veel) of N:1-entiteitsrelaties (veel-op-één) maken en bewerken met de oplossingenverkenner](create-edit-1n-relationships-solution-explorer.md)<br />
[Hiërarchische gegevens visualiseren met modelgestuurde apps](visualize-hierarchical-data.md)<br />
[Video: Hiërarchische beveiligingsmodellering](http://www.youtube.com/watch?v=kx5So32DrCo&index=10&list=PLC3591A8FE4ADBE07)<br />
[Video: Hiërarchievisualisatie](http://www.youtube.com/watch?v=_dGBE6icLNw&index=9&list=PLC3591A8FE4ADBE07)
