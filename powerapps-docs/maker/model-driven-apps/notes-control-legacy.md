---
title: Het besturingselement voor notities in modelgestuurde apps instellen voor toegang tot informatie over berichten in PowerApps | MicrosoftDocs
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
ms.openlocfilehash: 014f0c2516813b7cbcaa8e44a188455b07056c71
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39681216"
---
# <a name="set-up-the-model-driven-app-notes-control-to-access-information-about-posts"></a>Het besturingselement voor notities in modelgestuurde apps instellen voor toegang tot informatie over berichten

 Bij PowerApps-formulieren voor bepaalde systeementiteiten waarin [Bijgewerkte formulieren](main-form-presentations.md#updated-forms) worden gebruikt, biedt het besturingselement Notities de mogelijkheid om toegang te verkrijgen tot informatie over **berichten**, **activiteiten** en **notities**. Bij aangepaste entiteiten waarvoor u notities en activiteiten hebt ingeschakeld, ziet u alleen **Notities** en **Activiteiten**. Als u **Berichten** wilt opnemen, moet u deze eerst inschakelen voor de aangepaste entiteit.  
  
## <a name="enable-posts-for-a-custom-entity"></a>Berichten inschakelen voor een aangepaste entiteit  
  
1.  Ga naar **[Instellingen](advanced-navigation.md#settings)** > **Configuratie van activiteitsfeeds**. 
  
2.  Open de record van uw aangepaste entiteit.  
  
3.  Zorg ervoor dat **Wanden inschakelen voor dit type recordformulier** is geselecteerd en sla de record op.  
  
4.  Selecteer **Activeren** op de opdrachtbalk.  
  
5.  Als u wanden wilt inschakelen, moet u de entiteit publiceren.  
  
 Bij systeementiteiten wordt het besturingselement voor notities standaard in een sociaal deelvenster geplaatst, in het midden van een tabblad met drie kolommen bovenaan het formulier. Het kan slechts in één formulier tegelijk worden weergegeven. U kunt het besturingselement Notities verplaatsen of verwijderen. Als u het opnieuw wilt toevoegen, gebruikt u de knop **Notities** in de groep **Besturingselement** van het tabblad **Invoegen**.  
  
 In de volgende tabel worden de eigenschappen van het besturingselement Notities beschreven.  
  
|Tabblad|Eigenschap|Beschrijving|  
|---------|--------------|-----------------|  
|**Weergave**|**Label**|**Vereist**: hoewel dit label niet standaard wordt weergegeven, is er wel een label vereist.|  
||**Label weergeven op het formulier**|U kunt ervoor kiezen het label weer te geven.|  
||**Het veld op het formulier vergrendelen**|Hierdoor voorkomt u dat de notities per ongeluk uit het formulier worden verwijderd.|  
||**Standaardtabblad**|Selecteer welk tabblad standaard moet worden weergegeven. De opties zijn:<br /><br /> - **Activiteiten**<br />- **Berichten**<br />- **Opmerkingen**|  
|**Opmaak**|**Selecteer het aantal kolommen dat het besturingselement in beslag neemt**|Als de sectie die het notitiebesturingselement bevat, uit meer dan één kolom bestaat, kunt u het veld zo instellen dat het evenveel kolommen in beslag neemt als de sectie.|  
||**Aantal rijen**|Hiermee wordt de hoogte van het besturingselement voor notities bepaald. Het aantal rijen dat het besturingselement bezet, wordt namelijk geselecteerd.|  
||**Automatisch uitbreiden om beschikbare ruimte te gebruiken**|In plaats van de hoogte in te stellen op een aantal rijen, kunt u het besturingselement Notities de hoogte laten aanpassen aan de beschikbare ruimte.|  
  
## <a name="next-steps"></a>Volgende stappen
[De formuliereneditor openen](open-form-editor.md)
