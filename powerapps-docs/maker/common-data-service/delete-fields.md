---
title: Velden verwijderen in PowerApps | MicrosoftDocs
description: Instructies voor het verwijderen van velden
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
tags: ''
ms.openlocfilehash: 82e560f063f2e46190420b6be5cef4cc55d9ab4f
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39676484"
---
# <a name="delete-fields"></a>Velden verwijderen

<a name="BKMK_DeletingFields"></a>   
 
 Als iemand met de beveiligingsrol Systeembeheerder kunt u alle aangepaste velden verwijderen die geen deel uitmaken van een beheerde oplossing. Wanneer u een veld verwijdert, gaan alle gegevens die in het veld zijn opgeslagen verloren. De enige manier om gegevens uit een verwijderd veld te herstellen is de database te herstellen naar een punt waarop het veld nog niet was verwijderd.  
  
 Voordat u een aangepaste entiteit kunt verwijderen, moet u afhankelijkheden verwijderen die in andere oplossingsonderdelen kunnen bestaan. Open het veld en gebruik de knop **Afhankelijkheden weergeven** in de menubalk om **Afhankelijke onderdelen** te bekijken. Als het veld bijvoorbeeld in een formulier of weergave wordt gebruikt, moet u eerst verwijzingen naar het veld in die oplossingsonderdelen verwijderen.  
  
 Als u een zoekveld verwijdert, wordt de 1:N-entiteitsrelatie daarvoor automatisch verwijderd.  

 ## <a name="next-steps"></a>Volgende stappen

 [Een aangepaste entiteit verwijderen](data-platform-delete-entity.md)
