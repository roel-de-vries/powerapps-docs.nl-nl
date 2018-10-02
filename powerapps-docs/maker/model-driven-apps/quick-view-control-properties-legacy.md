---
title: Eigenschappen van besturingselement Snelle weergave voor hoofdformulieren voor modelgestuurde apps in PowerApps | MicrosoftDocs
description: Verwerf inzicht in de eigenschappen van besturingselement Snelle weergave voor hoofdformulieren
Keywords: Quick view control properties; Dynamics 365; Main forms
author: Mattp123
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.author: matp
manager: kvivek
ms.date: 06/06/2018
ms.service: crm-online
ms.topic: article
ms.assetid: 68f68d5b-6c71-4b95-bb46-d48c59d9008e
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="model-driven-app-quick-view-control-properties"></a>Eigenschappen van besturingselement Snelle weergave voor modelgestuurde apps

Een besturingselement voor snelle weergave op een formulier in een modelgestuurde app geeft gegevens weer van een record die is geselecteerd in een opzoekveld op het formulier. De gegevens die in het besturingselement worden weergegeven, worden gedefinieerd met een snelle-weergaveformulier. De gegevens die worden weergegeven zijn niet te bewerken, maar als het primaire veld in het snelle-weergaveformulier wordt opgenomen, wordt het een koppeling om de gerelateerde record te openen. Meer informatie: [Snelle-weergaveformulieren maken en bewerken](create-edit-quick-view-forms.md)  

> [!div class="mx-imgBorder"] 
> ![Snelle-weergaveformulier Contactpersoon op het accountformulier](media/quick-view-form-contact.png "Snelle-weergaveformulier Contactpersoon op het accountformulier")  

U opent **Eigenschappen van besturingselement snelle weergave** via de PowerApps-site. 
1.  Op de site [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) selecteert u **Modelgestuurd** (linkerbenedenhoek van het navigatievenster).  

     ![Modelgestuurde ontwerpmodus](media/model-driven-switch.png)

2.  Vouw **Gegevens** uit, selecteer **Entiteiten**, selecteer de gewenste entiteit en selecteer het tabblad **Formulieren**. 

3. In de lijst met formulieren opent u het formulier van het type **Hoofd**. Selecteer vervolgens op het tabblad **Invoegen** de optie **Snelle-weergaveformulier** om de eigenschappen van het besturingselement Snelle weergave weer te geven.

    ![quick-view-control](media/quick-view-control.png)
  
|Eigenschap|Beschrijving|  
|--------------|-----------------|  
|**Name**|**Vereist**: De unieke naam voor het snelle-weergaveformulier die wordt gebruikt wanneer ernaar wordt verwezen in scripts.|  
|**Label**|**Vereist**: Een label dat wordt weergegeven voor het snelle-weergaveformulier.|  
|**Label in het formulier weergeven**|Geeft het label op het formulier weer.|  
|**Opzoekveld**|Kies een van de opzoekvelden die opgenomen zijn in het formulier.|  
|**Gerelateerde entiteit**|Deze waarde is afhankelijk van het **Opzoekveld** dat u selecteert. Dit is normaal gesproken de primaire entiteit voor de 1:N-entiteitsrelatie voor de zoekactie.<br /><br /> Als de entiteit een **Potentiële klant**-opzoekveld heeft dat een account of een contactpersoon kan accepteren in het veld **Snelle-weergaveformulier**, kunt u een snelle-weergaveformulier voor zowel het account als het contactpersoon kiezen door deze waarde te wijzigen en vervolgens een ander snelle-weergaveformulier te kiezen.|  
|**Snelle-weergaveformulier**|Als de **Gerelateerde entiteit** snelle-weergaveformulieren heeft, kunt u deze hier selecteren. Als dat niet zo is, selecteert u **Nieuw** om er een te maken.<br /><br /> Selecteer **Bewerken** om het geselecteerde snelle-weergaveformulier te wijzigen.|  
|**Extra eigenschappen**|U kunt de standaardstijl voor rendering opgeven door het selectievakje in te schakelen.|

## <a name="next-steps"></a>Volgende stappen

[Het hoofdformulier en de onderdelen ervan gebruiken](use-main-form-and-components.md)
 
