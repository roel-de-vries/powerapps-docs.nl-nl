---
title: Beheerde eigenschappen voor modelgestuurde apps voor weergaven met PowerApps | MicrosoftDocs
description: Instructies voor het instellen van beheerde eigenschappen voor een weergave
ms.custom: ''
ms.date: 06/12/2018
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
ms.assetid: a9014576-8fb2-4f28-b8bb-5d2d49d76e12
caps.latest.revision: 25
ms.author: matp
manager: kvivek
ms.openlocfilehash: 9f33212ae81de0418dfc3695d5ae3c8e5acf36da
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39677191"
---
# <a name="model-driven-app-managed-properties-for-views"></a>Beheerde eigenschappen voor modelgestuurde apps voor weergaven

<a name="BKMK_ManagedProperties"></a>   
 
 Als u in PowerApps een aangepaste openbare weergave maakt die u wilt opnemen in een beheerde oplossing die u wilt distribueren, kunt u voor iedereen die uw oplossing installeert, de mogelijkheid beperken om de weergave aan te passen.  
  
 Bij de meeste weergaven is de beheerde eigenschap **Aanpasbaar** standaard ingesteld op waar, zodat gebruikers de weergaven kunnen aanpassen. Tenzij u een zeer goede reden hebt om dit te wijzigen, wordt u aangeraden toe te staan dat gebruikers weergaven in uw app kunnen aanpassen.  
  
## <a name="set-managed-properties-for-a-view"></a>Beheerde eigenschappen voor een weergave instellen  
  
1.  Open [Solutions Explorer](advanced-navigation.md#solution-explorer), vouw **Entiteiten** uit, selecteer de gewenste entiteit en selecteer vervolgens **Weergaven**.  
  
2.  Selecteer een aangepaste openbare weergave.  
  
3.  Selecteer op de menubalk **Meer acties** > **Beheerde eigenschappen**.  

    ![menu beheerde eigenschappen](media/managed-properties.png)
  
4.  Stel de optie **Aanpasbaar** of **Kan worden verwijderd** in op **Waar** of **Onwaar**.  

    ![Beheerde eigenschappen instellen](media/set-managed-properties.png)
  
> [!NOTE]
> Deze instelling wordt pas van kracht als u een oplossing exporteert die de weergave als een beheerde oplossing bevat en deze in een andere omgeving installeert.  

## <a name="next-steps"></a>Volgende stappen
[Weergaven begrijpen](create-edit-views.md)
