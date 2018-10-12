---
title: Beheerde eigenschappen in Common Data Service voor Apps-metagegevens instellen | MicrosoftDocs
description: Informatie over het instellen van beheerde eigenschappen voor metagegevensitems in een oplossing
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
ms.openlocfilehash: 46727f5a46e3fd518da52fac7d08a6e43992c00d
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39676471"
---
# <a name="set-managed-properties-in-common-data-service-for-apps-metadata"></a>Beheerde eigenschappen in Common Data Service voor Apps-metagegevens instellen 

Beheerde eigenschappen zijn alleen van toepassing wanneer u metagegevens met een beheerde oplossing insluit en deze in een andere omgeving importeert. Met deze instellingen heeft de maker van een oplossing enige controle over het aanpassingsniveau dat deze wil hebben voor gebruikers die hun beheerde oplossing installeren. 

> [!TIP]
> Het is doorgaans een goed idee om te zorgen dat mensen metagegevens mogen uitbreiden in uw oplossing, die werken met zakelijke gegevens. Hierdoor kunnen ze uw oplossing aan hun behoeften aanpassen, net zoals ze dit voor standaardentiteiten kunnen.
>
>Voor metagegevens die functionaliteit ter ondersteuning van uw oplossing bieden, maar geen zakelijke gegevens bevatten, is het een goed idee om te beperken welke aanpassingen zijn toegestaan.

Het instellen van beheerde eigenschappen moet worden uitgevoerd met de Solution Explorer.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

## <a name="entity-managed-properties"></a>Entiteit Beheerde eigenschappen

[Terwijl u entiteiten weergeeft](create-edit-entities-solution-explorer.md#view-entities), selecteert u **Beheerde eigenschappen** op de menubalk.  Hiermee opent u het dialoogvenster **Beheerde eigenschappen instellen**.

![Entiteit Beheerde eigenschappen instellen](media/set-managed-properties.png)
  
Entiteiten hebben meer beheerde eigenschappen dan elk ander type oplossingsonderdeel. Als de entiteit kan worden aangepast, kunt u de volgende opties instellen:  

|Optie|Beschrijving|
|--|--|
|**Kan worden aangepast** |Bepaalt alle andere opties. Als deze optie `False` is, is geen van de andere instellingen van toepassing. Wanneer de optie `True` is, kunt u de andere aanpassingsopties opgeven. Wanneer de optie `False` is, is dit hetzelfde als alle andere opties op Onwaar zetten.|
|**Weergavenaam kan worden gewijzigd**|Wanneer de weergavenaam van de entiteit kan worden gewijzigd.|
|**Kan aanvullende eigenschappen wijzigen** |Is van toepassing op alles wat niet wordt gedekt door andere opties.|
|**Nieuwe formulieren kunnen worden gemaakt**|Of nieuwe formulieren kunnen worden gemaakt voor de entiteit.|
|**Nieuwe grafieken kunnen worden gemaakt**|Of nieuwe grafieken kunnen worden gemaakt voor de entiteit.|
|**Nieuwe weergaven kunnen worden gemaakt** |Of nieuwe weergaven kunnen worden gemaakt voor de entiteit.|
|**Kan hiërarchische relatie wijzigen**|Of de instellingen van de hiërarchische relatie kunnen worden gewijzigd. Meer informatie: [Hiërarchisch gerelateerde gegevens definiëren en er query’s op uitvoeren](define-query-hierarchical-data.md)|
|**Kan Wijzigingen bijhouden worden ingeschakeld** |Of de entiteit-eigenschap **Wijzigingen bijhouden** kan worden gewijzigd.|
|**Kan Synchroniseren met externe zoekindex inschakelen** |Of de entiteit kan worden geconfigureerd om zoeken op relevantie in te schakelen. Meer informatie: [Zoeken op relevantie configureren om zoekresultaten en prestaties te verbeteren](/dynamics365/customer-engagement/admin/configure-relevance-search-organization) |

## <a name="field-managed-properties"></a>Beheerde veldeigenschappen

Zie [Velden maken en bewerken voor Common Data Service for Apps met behulp van de PowerApps Solution Explorer](create-edit-field-solution-explorer.md) voor informatie over het bewerken van velden.

Terwijl [u velden weergeeft](create-edit-field-solution-explorer.md#view-fields), selecteert u een aangepast veld van een niet-beheerde oplossing en kiest u vervolgens **Meer acties** >  **Beheerde eigenschappen** op de menubalk.

![Beheerde veldeigenschappen weergeven](media/view-field-managed-properties-solution-explorer.png)  
  
Hiermee opent u het dialoogvenster **Beheerde eigenschappen instellen**.

![Beheerde veldeigenschappen instellen](media/set-field-managed-property.png)

De optie **Kan worden aangepast** bepaalt alle andere opties. Als deze optie **Onwaar** is, is geen van de andere instellingen van toepassing. Wanneer de optie **Waar** is, kunt u de andere aanpassingsopties opgeven.  
  
Als het veld kan worden aangepast, zet u de volgende opties op **Waar** of **Onwaar**.  
  
- **Weergavenaam kan worden gewijzigd**
- **Kan vereistenniveau wijzigen** 
- **Kan aanvullende eigenschappen wijzigen**: deze eigenschap bepaalt andere aanpassingen die nog geen specifieke beheerde eigenschap hebben.

Alle afzonderlijke opties op **Onwaar** zetten, is gelijk aan **Kan worden aangepast** op **Onwaar** zetten.  

Pas uw keuzen toe en klik op **Instellen** om het dialoogvenster te sluiten.

> [!NOTE]
> Als dit veld een **Datum en tijd**-veld is, is de aanvullende eigenschap **Kan gedrag van Datum en tijd wijzigen** beschikbaar. Meer informatie: [Gedrag en indeling van het veld Datum en tijd](behavior-format-date-time-field.md)

## <a name="relationship-managed-properties"></a>Beheerde relatie-eigenschappen

Terwijl entiteitsrelaties bekijkt, selecteert u een relatie van een niet-beheerde oplossing en kiest u vervolgens **Meer acties** > **Beheerde eigenschappen** op de menubalk.
  
Bij relaties is **Kan worden aangepast** de enige beheerde eigenschap. Met deze ene instelling regelt u alle wijzigingen die aan de entiteitsrelatie kunnen worden aangebracht. 


### <a name="see-also"></a>Zie ook

[Beheerde eigenschappen](solutions-overview.md#managed-properties)<br />
[Entiteiten maken en bewerken met behulp van Solution Explorer](create-edit-entities-solution-explorer.md)<br />
[Velden maken en bewerken voor Common Data Service for Apps met behulp van de PowerApps Solution Explorer](create-edit-field-solution-explorer.md)<br />
[1:N (een-op-veel)- of N:1 (veel-op-een)-relaties maken of bewerken met behulp van Solution Explorer](create-edit-1n-relationships-solution-explorer.md)<br />
[N:N (veel-op-veel)-relaties van entiteiten maken in Common Data Service voor Apps met behulp van Solution Explorer](create-edit-nn-relationships-solution-explorer.md)