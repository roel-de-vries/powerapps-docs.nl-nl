---
title: Timerbesturingselement voor modelgestuurde apps in PowerApps | MicrosoftDocs
description: Verkrijg inzicht in hoe u het timerbesturingselement kunt gebruiken
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="model-driven-app-timer-control-overview"></a>Overicht van timerbesturingselement voor modelgestuurde apps

 Gebruik een timerbesturingselement met formulieren waar records moeten voldoen aan een specifieke op tijd gebaseerde mijlpaal. Een timerbesturingselement laat zien hoeveel tijd beschikbaar is om een actie te voltooien bij de oplossing van een actieve record of hoeveel tijd is verlopen sinds de tijd om de actie te voltooien is verstreken. Timerbesturingselementen moeten ten minste worden geconfigureerd om succes of mislukking te tonen bij het uitvoeren van de actie. Bovendien kunnen ze worden geconfigureerd om waarschuwingen weer te geven wanneer zich een mislukking lijkt te gaan voordoen.  
  
 Een timerbesturingselement kan voor een entiteit aan een formulier worden toegevoegd, maar ze worden het meest gebruikt voor de entiteit aanvraag, vooral als ze zijn gekoppeld aan velden die serviceniveau-overeenkomsten bijhouden. U kunt meerdere timerbesturingselementen aan de tekst van een formulier toevoegen. U kunt ze niet toevoegen aan de kop- of voettekst.  
  
 **Gegevensbron**-eigenschappen van timerbesturingselementen gebruiken velden voor de entiteit.  
  
-   Het **Veld voor tijd van storing** gebruikt een datum/tijd-veld om de tijd in te stellen.  
  
-   De drie voorwaardevelden gebruiken een van de velden **Optieset**, **Twee opties**, **Status**, of **Reden van status** voor de entiteit.  

Als u een timerbesturingselement wilt maken, selecteert u in de formulierontwerper het tabblad **Invoegen** en selecteert u **Timer** op de werkbalk. 

  > [!div class="mx-imgBorder"] 
  > ![Timerbesturingselement invoegen](media/insert-timer-control.png)

Op de eigenschappenpagina van het timerbesturingselement kunt u de gewenste eigenschappen invoeren of selecteren en vervolgens selecteert u **OK**. 

  
<a name="BKMK_TimerControlProperties"></a>   

## <a name="timer-control-properties"></a>Eigenschappen van timerbesturingselementen  
 In de volgende tabel worden de eigenschappen van een timerbesturingselement beschreven.  
  
|Groep|Naam|Beschrijving|  
|-----------|----------|-----------------|  
|Naam|Naam|**Vereist**. Een unieke naam voor het besturingselement.|  
||Etiket|**Vereist**. Het label dat moet worden weergegeven voor het timerbesturingselement.|  
|Gegevensbron|Veld voor tijd van storing|**Vereist**. Kies een van de datum/tijd-velden voor de entiteit om aan te geven wanneer een mijlpaal met succes kan worden voltooid.|  
||Slagingsvoorwaarde|**Vereist**. Selecteer een veld voor de entiteit om het succes van de mijlpaal te evalueren en kies vervolgens welke optie succes aangeeft.|  
||Waarschuwingsvoorwaarde|Selecteer een veld voor de entiteit om te evalueren of het succes van de mijlpaal gevaar loopt zodat een waarschuwing moet worden weergegeven. Kies vervolgens welke optie aangeeft dat een waarschuwing moet worden weergegeven.|  
||Voorwaarde annuleren|Selecteer een veld voor de entiteit om te evalueren of de voltooiing van de mijlpaal moet worden geannuleerd. Kies vervolgens welke optie aangeeft dat de mijlpaal is geannuleerd.|  

## <a name="next-steps"></a>Volgende stappen

[Overzicht van de gebruikersinterface van de formuliereneditor](form-editor-user-interface-legacy.md)
