---
title: Modelgestuurde app-timer control in PowerApps | MicrosoftDocs
description: Informatie over het gebruik van de timer control
ms.custom: ''
ms.date: 06/06/2018
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
ms.assetid: b2b64771-083b-42f9-a3d5-2218f9d8a713
caps.latest.revision: 63
ms.author: matp
manager: kvivek
ms.openlocfilehash: 7df13482e7773abc3e6762f80bd9f6b99c7ba9e6
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39674975"
---
# <a name="model-driven-app-timer-control-overview"></a>Overzicht van de modelgestuurde app-timer control

 Gebruik een timer control voor formulieren waarvoor records aan een specifieke mijlpaal op tijdbasis moeten voldoen. Met een timer control kunnen mensen zien hoeveel tijd beschikbaar is voor het voltooien van een actie in de resolutie van een actieverecord of hoeveel tijd is verstreken sinds de tijd voor het voltooien van de actie is verstreken. Timer controls moeten zo worden geconfigureerd dat in ieder geval te zien is of het voltooien van de actie is gelukt of mislukt. Daarnaast kunt u configureren of waarschuwingen moeten worden weergegeven als de actie dreigt te mislukken.  
  
 Timer controls kunnen worden toegevoegd aan formulieren van alle entiteiten. Ze worden voornamelijk gebruikt voor de case-entiteit, met name wanneer ze zijn gekoppeld aan velden die serviceovereenkomsten bijhouden. U kunt meerdere timer controls toevoegen in de hoofdtekst van een formulier. U kunt ze niet toevoegen aan de koptekst of voettekst.  
  
 Voor de eigenschappen van de **gegevensbron** van timer controls worden velden voor de entiteit gebruikt.  
  
-   Voor het **veld voor tijd van mislukte poging** wordt een datum-/tijdveld gebruikt om de tijd in te stellen.  
  
-   Voor de drie voorwaardevelden wordt een van de velden **Optieset**, **Twee opties**, **Status** of **Reden van status** voor de entiteit gebruikt.  

Als u een timer control wilt maken, selecteert u in de formulierontwerper het tabblad **Invoegen** en selecteert u vervolgens op de werkbalk **Timer**. 

  ![Timer control invoegen](media/insert-timer-control.png)

Op de eigenschappenpagina van de timer control voert u de gewenste eigenschappen in of selecteert u deze. Selecteer vervolgens **OK**. 

  
<a name="BKMK_TimerControlProperties"></a>   

## <a name="timer-control-properties"></a>Eigenschappen van de timer control  
 In de volgende tabel worden de eigenschappen van een timer control beschreven.  
  
|Groep|Naam|Beschrijving|  
|-----------|----------|-----------------|  
|Naam|Naam|**Vereist**. Een unieke naam voor de control.|  
||Label|**Vereist**. Het label dat voor de timer control wordt weergegeven.|  
|Gegevensbron|Veld voor tijd van mislukte poging|**Vereist**. Kies een van de datum-/tijdvelden voor de entiteit die weergegeven wanneer een mijlpaal moet zijn voltooid.|  
||Slagingsvoorwaarde|**Vereist**. Selecteer een veld voor de entiteit om het succes van de mijlpaal te beoordelen. Kies vervolgens welke optie aangeeft of de actie is geslaagd.|  
||Waarschuwingsvoorwaarde|Selecteer een veld voor de entiteit om te beoordelen of het slagen van de mijlpaal dreigt te mislukken, zodat een waarschuwing kan worden weergegeven. Kies vervolgens welke optie aangeeft of een waarschuwing moet worden weergegeven.|  
||Annuleringsvoorwaarde|Selecteer een veld voor de entiteit om te beoordelen of het bereiken de mijlpaal moet worden geannuleerd. Kies vervolgens welke optie aangeeft dat de mijlpaal is geannuleerd.|  

## <a name="next-steps"></a>Volgende stappen

[Overzicht van gebruikersinterface van de formuliereneditor](form-editor-user-interface-legacy.md)