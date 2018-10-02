---
title: Een entiteit bewerken in PowerApps | MicrosoftDocs
description: Lees op welke verschillende manieren een entiteit kan worden bewerkt
ms.custom: ''
ms.date: 05/15/2018
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
ms.assetid: 8b00780c-74f0-4e3a-b570-b9289d0d5383
caps.latest.revision: 41
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="edit-an-entity"></a>Een entiteit bewerken

U kunt elke aangepaste entiteit bewerken die u maakt. Voor standaardentiteiten of beheerde aangepaste entiteiten kunnen beperkingen gelden met betrekking tot de wijzigingen die u kunt doorvoeren.  
  
> [!NOTE]
> **Standaardentiteiten**zijn algemene entiteiten die in uw omgeving zijn opgenomen en geen **systeementiteiten** of **aangepaste entiteiten** zijn. *Beheerde aangepaste entiteiten* zijn entiteiten die aan het systeem zijn toegevoegd door een oplossing te importeren. De mate waarin u deze entiteiten kunt bewerken wordt bepaald door de beheerde eigenschappen die voor elke entiteit zijn ingesteld. Alle eigenschappen die niet kunnen worden bewerkt worden uitgeschakeld. 

U kunt een entiteit op twee manieren bewerken met een ontwerper:

|Ontwerper|Beschrijving|
|--|--|
|[PowerApps-portal](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)|Biedt een eenvoudig gestroomlijnde ervaring, maar een aantal speciale instellingen is niet beschikbaar.|
|Oplossingenverkenner|Deze ontwerper is niet zo eenvoudig, maar biedt meer flexibiliteit en heeft minder algemene vereisten.|

Zowel in de PowerApps-portal als in de oplossingenverkenner kunt u het volgende doen:

- **De entiteitsvelden bewerken**. Meer informatie: [Velden maken en bewerken voor Common Data Service voor Apps](create-edit-fields.md)
  
- **De entiteitsrelaties bewerken**. Meer informatie: [Relaties tussen entiteiten maken en bewerken](create-edit-entity-relationships.md)

- **Sleutels**. [Alternatieve sleutels definiëren om te verwijzen naar records](define-alternate-keys-reference-records.md)
  
U kunt ook records wijzigen die de entiteit ondersteunen:  

- **Bedrijfsregels**. Meer informatie: [Bedrijfsregels en aanbevelingen maken om logica in een formulier toe te passen](../model-driven-apps/create-business-rules-recommendations-apply-logic-form.md)

- **Weergaven**. Meer informatie: [Een weergave maken of bewerken](../model-driven-apps/create-edit-views.md)
  
- **Formulieren**. Meer informatie: [Formulieren maken en ontwerpen](../model-driven-apps/create-design-forms.md)

- **Dashboards**. Meer informatie: [Dashboards maken of bewerken](../model-driven-apps/create-edit-dashboards.md)

- **Grafieken**. [Een systeemgrafiek maken of bewerken](../model-driven-apps/create-edit-system-chart.md)

## <a name="edit-using-powerapps-portal-designer"></a>Bewerken met de PowerApps-portalontwerper

In de PowerApps-portalontwerper zijn er slechts drie entiteitseigenschappen die u kunt bewerken:
 - Weergavenaam
 - Meervoudsweergavenaam
 - Beschrijving

Selecteer in de ontwerper de entiteit die u wilt bewerken en klik er vervolgens op om de entiteitontwerper te openen. Als u de entiteitseigenschappen wilt wijzigen, klikt u op de opdracht **Instellingen** om het formulier **Entiteit bewerken** weer te geven, zoals hieronder aangegeven:

![Entiteitseigenschappen bewerken](media/edit-entity-properties-powerapps-portal-designer.png)

> [!NOTE]
>  De naam van veel standaardentiteiten kan ook in andere tekst in de toepassing worden gebruikt. Zie [Standaardentiteitsberichten bewerken](edit-system-entity-messages.md) als u tekst wilt vinden en wijzigen waarin deze naam is gebruikt.

Voor andere wijzigingen in entiteitsopties moet u de entiteit bewerken via de oplossingenverkenner.

## <a name="edit-using-solution-explorer"></a>Bewerken via oplossingenverkenner

Wanneer u een entiteit wilt bewerken in de oplossingenverkenner, moet u de onbeheerde oplossing vinden waaraan u deze wilt toevoegen.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]
  
<a name="BKMK_ChangeEntityName"></a> 
  
## <a name="change-the-name-of-an-entity"></a>De entiteitsnaam wijzigen  

Gebruik de eigenschappen van **Weergavenaam** en **Meervoudsnaam** om de naam van de entiteit in de toepassing te wijzigen. 

> [!NOTE]
>  De naam van veel standaardentiteiten kan ook in andere tekst in de toepassing worden gebruikt. Zie [Standaardentiteitsberichten bewerken](edit-system-entity-messages.md) als u tekst wilt vinden en wijzigen waarin deze naam is gebruikt.
  
<a name="BKMK_ChangeEntityIcon"></a>   

###  <a name="change-the-icons-used-for-custom-entities"></a>De pictogrammen wijzigen die voor aangepaste entiteiten worden gebruikt  

Gewoonlijk hebben alle aangepaste entiteiten in de webtoepassing dezelfde pictogrammen. U kunt afbeeldingswebresources maken voor de pictogrammen die u voor uw aangepaste entiteiten wilt. Meer informatie:  [Pictogrammen wijzigen voor aangepaste entiteiten](../model-driven-apps/change-custom-entity-icons.md).  
  
<a name="BKMK_EnableOptions"></a>  
 
###  <a name="entity-options-that-can-only-be-enabled"></a>Entiteitopties die alleen kunnen worden ingeschakeld  

In de volgende tabel worden de opties opgesomd die u voor een entiteit kunt inschakelen, maar nadat deze items zijn ingeschakeld kunnen ze niet worden uitgeschakeld:  

[!INCLUDE [cc_entity-set-once-options-table](../../includes/cc_entity-set-once-options-table.md)] 
  
<a name="BKMK_EnableDisableOptions"></a>  
 
###  <a name="enable-or-disable-entity-options"></a>Entiteitopties in- of uitschakelen  

In de volgende tabel worden de entiteitopties opgesomd die u later op elk moment kunt in- of uitschakelen.  

[!INCLUDE [cc_entity-changeable-options-table](../../includes/cc_entity-changeable-options-table.md)] 

### <a name="see-also"></a>Zie ook

[Een entiteit maken](create-edit-entities.md)<br />
[Entiteiten maken met de oplossingenverkenner](create-edit-entities-solution-explorer.md)
