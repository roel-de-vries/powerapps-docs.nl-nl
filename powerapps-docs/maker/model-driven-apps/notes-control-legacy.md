---
title: Het notitiebesturingselement voor modelgestuurde apps instellen voor toegangsinformatie over berichten in PowerApps | MicrosoftDocs
ms.custom: ''
ms.date: 05/06/2018
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
ms.assetid: f10cdf1c-3540-439c-a171-27a10e72da45
caps.latest.revision: 63
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="set-up-the-model-driven-app-notes-control-to-access-information-about-posts"></a>Het notitiebesturingselement voor modelgestuurde apps instellen voor toegangsinformatie over berichten

 In PowerApps-formulieren voor bepaalde systeementiteiten die [Bijgewerkte formulieren](main-form-presentations.md#updated-forms) gebruiken, biedt het notitiebesturingselement de mogelijkheid voor toegang tot informatie over **berichten**, **activiteiten** en **notities**. Voor aangepaste entiteiten waarvoor u notities en activiteiten hebt ingeschakeld, kunt u alleen **Notities** en **Activiteiten** zien. Om **Berichten** op te nemen, moet u ze voor de aangepaste entiteit inschakelen.  
  
## <a name="enable-posts-for-a-custom-entity"></a>Berichten inschakelen voor een aangepaste entiteit  
  
1.  Ga naar **[Instellingen](advanced-navigation.md#settings)** > **Configuratie van activiteitsfeeds**. 
  
2.  Open de record voor uw aangepaste entiteit.  
  
3.  Controleer of **Prikborden inschakelen voor dit type recordformulier** is geselecteerd en sla de record op.  
  
4.  Selecteer in de opdrachtbalk de optie **Activeren**.  
  
5.  Als u prikborden moet inschakelen, moet u de entiteit publiceren.  
  
 Voor systeementiteiten is het notitiebesturingselement standaard in een sociaal deelvenstersectie geplaatst in het midden van een tabblad met drie kolommen boven aan het formulier. Het kan maar één keer worden weergegeven in een formulier. U kunt het notitiebesturingselement verplaatsen of verwijderen. Om het opnieuw toe te voegen, gebruikt u de knop **Notities** in de groep **Besturingselement** van het tabblad **Invoegen**.  
  
 In de volgende tabel worden de eigenschappen voor het Notitiebesturingselement beschreven.  
  
|Tabblad|Eigenschap|Beschrijving|  
|---------|--------------|-----------------|  
|**Weergeven**|**Label**|**Vereist**: Hoewel het label niet standaard wordt weergegeven, is een label vereist.|  
||**Label in het formulier weergeven**|U kunt ervoor kiezen het label weer te geven.|  
||**Het het veld in het formulier vergrendelen**|Hierdoor wordt voorkomen dat de notities per ongeluk uit het formulier worden verwijderd.|  
||**Standaardtabblad**|Selecteer welk tabblad standaard moet worden weergegeven. De opties zijn:<br /><br /> - **Activiteiten**<br />- **Berichten**<br />- **Notities**|  
|**Opmaak**|**Selecteer het aantal kolommen dat het besturingselement in beslag neemt**|Als de sectie die het notitiebesturingselement bevat meer dan één kolom heeft, kunt u het veld zo instellen dat het evenveel kolommen bezet als sectie.|  
||**Aantal rijen**|Beheer de hoogte van het notitiebesturingselement door het aantal rijen te selecteren dat het besturingselement in beslag neemt.|  
||**Vouw automatisch uit om de beschikbare ruimte te gebruiken**|In plaats van de hoogte in te stellen met een aantal rijen, kunt u toestaan dat de hoogte van het notitiebesturingselement wordt uitgevouwen tot de beschikbare ruimte.|  
  
## <a name="next-steps"></a>Volgende stappen
[De formuliereneditor openen.](open-form-editor.md)
