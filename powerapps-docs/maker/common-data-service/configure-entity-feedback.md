---
title: Een entiteit configureren voor feedback met PowerApps | MicrosoftDocs
description: Lees hoe u feedback voor een entiteit kunt inschakelen
ms.custom: ''
ms.date: 05/18/2018
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
ms.assetid: 5b25cf09-d43b-4165-9eaa-7549f4855e7c
caps.latest.revision: 13
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="configure-an-entity-for-feedbackratings"></a>Een entiteit configureren voor feedback/beoordelingen

U kunt klanten of werknemers feedback laten schrijven voor elke entiteitsrecord of entiteitsrecords laten beoordelen binnen een gedefinieerd beoordelingsbereik door entiteiten in te schakelen voor feedback.  

Deze mogelijkheid wordt meestal gebruikt met een systeem waarin gegevens van klanten via een portal of onderzoek worden vastgelegd. Gegevens over service- of producttevredenheid kunnen worden toegepast met entiteiten die dat type gegevens vertegenwoordigen.

Feedback kan ook door werknemers worden gebruikt om feedback over een samenwerking te bieden.

> [!NOTE]
> U moet beschikken over de beveiligingsrol Systeembeheerder of Systeemaanpasser of gelijkwaardige machtigingen om deze stappen te kunnen uitvoeren.
  
## <a name="enable-feedback"></a>Feedback inschakelen  
  
Bewerk de entiteit om **Feedback** in te schakelen. Meer informatie: [Een entiteit bewerken](edit-entities.md)
  
## <a name="add-a-subgrid-for-feedback-on-the-entity-form"></a>Een subraster voor feedback op het entiteitformulier toevoegen  

Standaard moeten gebruikers naar de lijst met gekoppelde records van de record gaan waaraan u feedback wilt toevoegen. Om het eenvoudiger te maken voor gebruikers om feedback toe te voegen, kunt u een subraster voor feedback toevoegen aan het formulier van de entiteit waarvoor u feedback wilt inschakelen.  

<!-- This is the closest I could find to a topic about adding an subgrid to a form. --> Meer informatie:  [Overzicht van eigenschappen van het subraster](../model-driven-apps/sub-grid-properties-legacy.md)

## <a name="add-a-rollup-field--to-the-entity-form-to-show-the-ratings"></a>Een samengeteld veld aan het entiteitformulier toevoegen om de beoordelingen weer te geven  

Afhankelijk van de manier waarop u de beoordeling voor de entiteit wilt berekenen, kunt u een samengeteld veld maken waarmee de beoordeling wordt berekend, en deze vervolgens aan het formulier toevoegen van de entiteit toe waarvoor u feedback inschakelt. Meer informatie: [Samengetelde velden definiëren waarmee waarden worden samengevoegd](define-rollup-fields.md)
  
### <a name="see-also"></a>Zie ook  
 [Feedback of beoordelingen indienen voor Dynamics 365-records](/dynamics365/customer-engagement/basics/submit-feedback-ratings)
