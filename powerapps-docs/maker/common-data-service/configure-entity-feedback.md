---
title: Een entiteit configureren voor feedback met PowerApps | MicrosoftDocs
description: Meer informatie over het inschakelen van feedback voor een entiteit
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
ms.openlocfilehash: efb1cf167353d5928564b42aeb7a49f43cf272d6
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39676700"
---
# <a name="configure-an-entity-for-feedbackratings"></a>Een entiteit configureren voor feedback/beoordelingen

Laat klanten of medewerkers feedback schrijven voor een entiteitsrecord of entiteitsrecords binnen een bepaald beoordelingsbereik beoordelen door feedback voor entiteiten in te schakelen.  

Deze mogelijkheid wordt veelal gebruikt met een systeem dat gegevens van klanten vastlegt via een portal of enquête. Gegevens over tevredenheid met de service of het product kunnen worden toegepast bij entiteiten die dat soort gegevens vertegenwoordigen.

Feedback kan ook door werknemers worden gebruikt om feedback te geven over een gezamenlijke inspanning.

> [!NOTE]
> U moet de beveiligingsrol Systeembeheerder of Systeemaanpasser of equivalente rechten hebben om deze stappen uit te voeren.
  
## <a name="enable-feedback"></a>Feedback geven  
  
Bewerk de entiteit om **Feedback** in te schakelen. Meer informatie: [Een entiteit bewerken](edit-entities.md)
  
## <a name="add-a-subgrid-for-feedback-on-the-entity-form"></a>Een subraster voor feedback op het entiteitsformulier toevoegen  

Standaard moeten gebruikers naar de lijst met gekoppelde records gaan van de record waaraan u feedback wilt toevoegen. Om het voor gebruikers gemakkelijker te maken om feedback toe te voegen, kunt u een feedbacksubraster toevoegen aan de entiteit waarvoor u feedback inschakelt.  

<!-- This is the closest I could find to a topic about adding an subgrid to a form. -->Meer informatie: [Overzicht van subrastereigenschappen](../model-driven-apps/sub-grid-properties-legacy.md)

## <a name="add-a-rollup-field--to-the-entity-form-to-show-the-ratings"></a>Een samengeteld veld aan het entiteitformulier toevoegen om de waarderingen te tonen  

Afhankelijk van hoe u de beoordeling voor de entiteit wilt berekenen, kunt u een samengeteld veld maken dat de beoordeling berekent en dit vervolgens toevoegen aan het formulier van de entiteit waarvoor u feedback wilt inschakelen. Meer informatie: [Samengetelde velden voor het aggregeren van waarden definiëren](define-rollup-fields.md)
  
### <a name="see-also"></a>Zie ook  
 [Feedback of beoordelingen geven voor Dynamics 365-records](/dynamics365/customer-engagement/basics/submit-feedback-ratings)
