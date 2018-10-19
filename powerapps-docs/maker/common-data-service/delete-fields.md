---
title: Velden verwijderen in PowerApps | MicrosoftDocs
description: Informatie over het verwijderen van velden
ms.custom: ''
ms.date: 06/20/2018
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
ms.assetid: 578ac950-da16-4ec6-a0a4-25f3aaa3b96e
caps.latest.revision: 33
ms.author: matp
manager: kvivek
tags: null
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="delete-fields"></a>Velden verwijderen

<a name="BKMK_DeletingFields"></a>   
 
 Omdat u de beveiligsrol systeembeheerder hebt, kunt u alle aangepaste veldne verwijderen die geen deel uitmaken van een beheerde oplossing. Wanneer u een veld verwijdert, gaan de opgeslagen gegevens in het veld verloren. De enige manier om gegevens te herstellen uit een veld dat is verwijderd, is door de database te herstellen vanuit een punt voordat het veld werd verwijderd.  
  
 Voordat u een aangepaste entiteit kunt verwijderen, moet u afhankelijkheden verwijderen die in andere oplossingsonderdelen kunnen zijn. Open het veld en gebruik de knop **Afhankelijkheden weergeven** in de menubalk als u **Afhankelijke onderdelen** wilt weergeven. Als het veld bijvoorbeeld in een formulier of een weergave wordt gebruikt, moet u eerst referenties naar het veld in deze oplossingsonderdelen verwijderen.  
  
 Als u een opzoekveld verwijdert, wordt de 1:N-entiteitsrelatie voor dat veld automatisch verwijderd.  

 ## <a name="next-steps"></a>Volgende stappen

 [Een aangepaste entiteit verwijderen](data-platform-delete-entity.md)
