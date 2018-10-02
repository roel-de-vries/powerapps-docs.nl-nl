---
title: Beheerde eigenschappen voor weergaven in modelgestuurde apps met PowerApps | MicrosoftDocs
description: Lees hoe u beheerde eigenschappen kunt instellen voor een weergave
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="model-driven-app-managed-properties-for-views"></a>Beheerde eigenschappen voor weergaven in modelgestuurde apps

<a name="BKMK_ManagedProperties"></a>   
 
 Als u een aangepaste openbare weergave maakt in PowerApps die u wilt opnemen in een beheerde oplossing die u wilt distribueren, hebt u de optie om het vermogen van gebruikers die uw oplossing installeren om de weergave aan te passen te beperken.  
  
 Standaard, is voor de meeste weergaven de beheerde eigenschappenset **Aanpasbaar** ingesteld op waar zodat gebruikers deze kunnen aanpassen. Tenzij u een zeer goede reden hebt om dit te wijzigen, raden we u aan om gebruikers toe te staan weergaven in uw app aan te passen.  
  
## <a name="set-managed-properties-for-a-view"></a>Beheerde eigenschappen voor een weergave instellen  
  
1.  Open [oplossingenverkenner](advanced-navigation.md#solution-explorer) vouw **Entiteiten** uit, selecteer de gewenste entiteit en selecteer **Weergaven**.  
  
2.  Selecteer een aangepaste openbare weergave.  
  
3.  Selecteer **Meer acties** > **Beheerde eigenschappen** op de werkbalk.  

    > [!div class="mx-imgBorder"] 
    > ![menu beheerde eigenschappen](media/managed-properties.png)
  
4.  Stel de optie **Aanpasbaar** of **Kan worden verwijderd** in op **Waar** of **Onwaar**.  

    > [!div class="mx-imgBorder"] 
    > ![Beheerde eigenschappen instellen](media/set-managed-properties.png)
  
> [!NOTE]
> De instelling wordt pas van kracht wanneer u een oplossing die de weergave bevat exporteert als beheerde oplossing en vervolgens installeert in een andere omgeving.  

## <a name="next-steps"></a>Volgende stappen
[Inzicht in weergaven](create-edit-views.md)
