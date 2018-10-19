---
title: Beheerde eigenschappen in metagegevens voor Common Data Service voor Apps instellen | MicrosoftDocs
description: Leer hoe u beheerde eigenschappen voor metagegevensitems in een oplossing instelt
ms.custom: ''
ms.date: 05/30/2018
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
ms.assetid: edaa7d4a-a95f-4d66-a9d9-2ad6051332f7
caps.latest.revision: 41
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="set-managed-properties-in-common-data-service-for-apps-metadata"></a>Beheerde eigenschappen in metagegevens voor Common Data Service voor Apps instellen 

Beheerde eigenschappen zijn alleen van toepassing wanneer u metagegevens opneemt met een beheerde oplossing en deze importeert in een andere omgeving. Met deze instellingen kan de maker van een oplossing enige invloed hebben op het niveau van aanpassing dat ze willen toestaan voor mensen die hun beheerde oplossing installeren. 

> [!TIP]
> Het is doorgaans verstandig om gebruikers in staat te stellen om metagegevens die met zakelijke gegevens werken uit te breiden in uw oplossing. Op deze manier kunnen ze uw oplossing op dezelfde manier als standaardentiteiten aan hun wensen aanpassen.
>
>Voor metagegevens die functionaliteit bieden om uw oplossing te ondersteunen, maar geen bedrijfsgegevens bevatten, is het verstandig om te beperken wat mogelijk is met aanpassingen.

Beheerde eigenschappen moeten worden ingesteld via de oplossingenverkenner.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

## <a name="entity-managed-properties"></a>Beheerde eigenschappen van een entiteit

Selecteer de entiteit [terwijl u entiteiten weergeeft](create-edit-entities-solution-explorer.md#view-entities) en selecteer vervolgens **Beheerde eigenschappen** op de menubalk.  Het dialoogvenster **Beheerde eigenschappen instellen** wordt geopend.

![Beheerde eigenschappen van een entiteit instellen](media/set-managed-properties.png)
  
Entiteiten hebben meer beheerde eigenschappen dan iedere andere oplossingsonderdeelsoort. Als de entiteit kan worden aangepast, dan kunt u de volgende opties instellen:  

|Optie|Beschrijving|
|--|--|
|**Kan worden aangepast** |Hiermee beheert u alle andere opties. Als deze optie is `False`, dan is geen van de andere instellingen van toepassing. Wanneer het `True` is, kunt u de andere aanpassingsopties specificeren. Bij `False` is dit hetzelfde als alle andere opties op onwaar instellen.|
|**Weergavenaam kan worden gewijzigd**|Geeft aan of de weergavenaam van de entiteit kan worden gewijzigd.|
|**Kan aanvullende eigenschappen wijzigen** |Is van toepassing op alles wat niet wordt gedekt door andere opties.|
|**Er kunnen nieuwe formulieren worden gemaakt**|Geeft aan of voor de entiteit nieuwe formulieren kunnen worden gemaakt.|
|**Nieuwe grafieken kunnen worden gemaakt**|Geeft aan of voor de entiteit nieuwe grafieken kunnen worden gemaakt.|
|**Er kunnen nieuwe weergaven worden gemaakt** |Geeft aan of voor de entiteit nieuwe weergaven kunnen worden gemaakt.|
|**Kan hiërarchische relatie wijzigen**|Geeft aan of instellingen voor hiërarchische relaties kunnen worden gewijzigd. Meer informatie: [Hiërarchisch gerelateerde gegevens definiëren en opvragen](define-query-hierarchical-data.md)|
|**Kan bijhouden van wijzigingen worden ingeschakeld** |Geeft aan of de eigenschap **Bijhouden van wijzigingen** van de entiteit kan worden gewijzigd.|
|**Kan synchronisatie met externe zoekindex inschakelen** |Geeft aan of de entiteit kan worden geconfigureerd om zoeken op relevantie in te schakelen. Meer informatie: [Zoeken op relevantie configureren om zoekresultaten en prestaties te verbeteren](/dynamics365/customer-engagement/admin/configure-relevance-search-organization) |

## <a name="field-managed-properties"></a>Beheerde eigenschappen voor velden

Zie [Velden maken en bewerken voor Common Data Service voor Apps met de PowerApps-oplossingenverkenner](create-edit-field-solution-explorer.md) voor informatie over het bewerken van velden.

Selecteer terwijl u [velden weergeeft](create-edit-field-solution-explorer.md#view-fields) een aangepast veld van een onbeheerde oplossing en kies **Meer acties** >  **Beheerde eigenschappen** op de menubalk.

![Beheerde eigenschappen voor velden weergeven](media/view-field-managed-properties-solution-explorer.png)  
  
Het dialoogvenster **Beheerde eigenschappen instellen** wordt geopend.

![Beheerde eigenschappen voor velden instellen](media/set-field-managed-property.png)

De optie **Kan worden aangepast** bestuurt alle andere opties. Bij **Onwaar** is geen van de andere instellingen van toepassing. Bij **Waar** kunt u de andere aanpassingsopties opgeven.  
  
Als het veld kan worden aangepast, kunt u de volgende opties instellen op **Waar** of **Onwaar**.  
  
- **Weergavenaam kan worden gewijzigd**
- **Kan het vereistenniveau wijzigen** 
- **Kan aanvullende eigenschappen wijzigen**: deze eigenschap heeft betrekking op andere aanpassingen waarvoor geen specifieke beheerde eigenschap bestaat.

Als u alle afzonderlijke opties op **Onwaar** instelt, komt dit op hetzelfde neer als wanneer u **Kan worden aangepast** instelt op **Onwaar**.  

Configureer de gewenste instellingen en klik op **Instellen** om het dialoogvenster te sluiten.

> [!NOTE]
> Als dit veld een veld van het type **Datum en tijd** is, is een extra eigenschap **Kan datum- en tijdgedrag wijzigen** beschikbaar. Meer informatie: [Gedrag en indeling van het datum- en tijdveld](behavior-format-date-time-field.md)

## <a name="relationship-managed-properties"></a>Beheerde relatie-eigenschappen

Selecteer terwijl u entiteitsrelaties weergeeft een relatie van een onbeheerde oplossing en kies **Meer acties** > **Beheerde eigenschappen** op de menubalk.
  
Bij relaties is de enige beheerde eigenschap **Kan worden aangepast**. Deze instelling beheert alle wijzigingen die kunnen worden toegepast op de entiteitsrelatie. 


### <a name="see-also"></a>Zie ook

[Beheerde eigenschappen](solutions-overview.md#managed-properties)<br />
[Entiteiten maken met de oplossingenverkenner](create-edit-entities-solution-explorer.md)<br />
[Velden maken en bewerken voor Common Data Service voor Apps met de PowerApps-oplossingenverkenner | MicrosoftDocs](create-edit-field-solution-explorer.md)<br />
[1:N- (één-op-veel) of N:1-entiteitsrelaties (veel-op-één) maken en bewerken met de oplossingenverkenner](create-edit-1n-relationships-solution-explorer.md)<br />
[N:N-entiteitsrelaties (veel-op-veel) maken in Common Data Service voor Apps met de oplossingenverkenner](create-edit-nn-relationships-solution-explorer.md)
