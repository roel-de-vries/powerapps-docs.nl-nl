---
title: Overgangen van reden van status definiëren met PowerApps | MicrosoftDocs
description: Meer informatie over het definiëren van overgangen van reden van status
ms.custom: ''
ms.date: 05/25/2018
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
ms.assetid: dbc4f436-0b23-42f9-8079-b0de482aaebe
caps.latest.revision: 11
ms.author: matp
manager: kvivek
ms.openlocfilehash: e21069a86d2ef21e8209fea6ea4a4b05e604cda4
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39678548"
---
# <a name="define-status-reason-transitions-for-the-case-or-custom-entities"></a>Overgangen van reden van status voor de case- of aangepaste entiteiten definiëren

U kunt de overgangen van reden van status voor de incident-entiteit (**case**) of een aangepaste entiteit opgeven.

> [!NOTE]
> Hoewel de incident-entiteit (case) niet is opgenomen in een standaard Common Data Service for Apps-omgeving, wordt deze gebruikt door [Dynamics 365 for Customer Service](https://dynamics.microsoft.com/customer-service/) en gedefinieerd binnen het [Common Data Model](https://github.com/Microsoft/CDM/blob/master/schemaDocuments/core/applicationCommon/foundationCommon/crmCommon/service/Incident.cdm.json)
  
Overgangen van reden van status zijn een optioneel aanvullend niveau van filteren om te definiëren waarin de waarde van de reden van de status kan worden gewijzigd voor elke statusreden. Het definiëren van een beperkte lijst met geldige opties kan het voor gebruikers eenvoudiger maken om de juiste volgende statusreden voor een record te kiezen wanneer u een groot aantal combinaties van waarden voor geldige statusreden hebt.  
  
<a name="BKMK_StatusAndStatusReasons"></a>

## <a name="what-is-the-connection-between-status-and-status-reason-fields"></a>Wat is het verband tussen de velden Status en Reden van status?  

Entiteiten die verschillende statuswaarden kunnen hebben, hebben twee velden die deze gegevens vastleggen:  
  
|Weergavenaam|Beschrijving|  
|------------------|-----------------|  
|**Status**|Geeft de status van de record aan. Meestal **Actief** of **Inactief**. U kunt geen nieuwe statusopties toevoegen.|  
|**Reden van de status**|Dit is een reden die is gekoppeld aan een specifieke status. Elke status moet ten minste één mogelijke statusreden hebben. U kunt aanvullende statusredenopties toevoegen.|  
  
De metagegevens voor het veld definiëren welke statuswaarden geldig zijn voor een bepaalde status. Bijvoorbeeld voor de incident-entiteit (**case**) zijn de opties voor standaardstatus en statusreden:  
  
|Status|Reden van de status|  
|------------|-------------------|  
|**Actief**|<li>**Wordt uitgevoerd**</li><li>**In wachtstand**</li><li>**Wacht op details**</li><li>**Onderzoeken**</li>| 
|**Opgelost**|<li>**Probleem opgelost**</li><li>**Informatie geleverd**</li>|
|**Geannuleerd**|<li>**Geannuleerd**</li><li>**Samengevoegd**</li>|
  
  
<a name="BKMK_EditStatusReasonTransitions"></a>   

## <a name="edit-status-reason-transitions"></a>Overgangen van reden van status bewerken
 
U kunt de veldopties Reden van status voor de entiteit Case en aangepaste entiteiten aanpassen om te definiëren welke andere opties voor reden van status mensen kunnen kiezen. De enige beperking is dat elke optie voor Reden van status voor een actieve status ten minste één pad naar een niet-actieve status moet toestaan. U kunt anders een voorwaarde maken die het onmogelijk maakt om de case op te lossen of te annuleren.  

> [!NOTE]
> Voor het bewerken van de overgangen van Reden van status moet u de Solution Explorer gebruiken. Zie [Velden maken en bewerken voor Common Data Service for Apps met behulp van de PowerApps Solution Explorer](create-edit-field-solution-explorer.md) voor informatie over het bewerken van velden.
  
 Wanneer u een veld voor Reden van status bewerkt, staat de knop **Overgangen van reden van status bewerken** in het menu. 

![Opdracht Overgangen van reden van status bewerken](media/status-reason-transitions-command.png)

Wanneer u klikt op deze knop, biedt het dialoogvenster **Overgangen van reden van status** de mogelijkheid om te kiezen voor **Overgangen van redenen van status inschakelen**. Als deze optie is geselecteerd, moet u definiëren welke *andere* waarden zijn toegestaan voor elke reden van de status. Als u het toegepaste filter wilt verwijderen, schakelt u **Overgangen van redenen van status inschakelen** uit. De overgangen die u hebt gedefinieerd blijven behouden maar worden niet toegepast.  
  
De onderstaande schermafbeelding geeft een voorbeeld dat voldoet aan de volgende vereisten: 
 
- Een case kan op elk gewenst moment worden samengevoegd. U kunt cases niet samenvoegen als een overgang van de reden van de status dit niet toelaat.  
- U kunt een actieve case op elk gewenst moment annuleren.  
- Een opgeloste of geannuleerde case kan niet opnieuw worden geactiveerd.  
- Alle cases moeten de volgende stadia doorlopen: **In voortgang** > **In wachtstand** > **Wacht op details**  >  **Onderzoeken**, voordat ze opgelost worden kunnen. Met deze configuratie kan een case niet worden ingesteld op een eerdere status.  
  > [!NOTE]
  >  Dit is niet een goed voorbeeld van hoe het echt gaat, maar het laat zien hoe statusstadia kunnen worden afgedwongen door overgangen van reden van status.  
  
 ![Voorbeeld van overgangen van reden van status voor case](media/status-reason-transitions-example.PNG)  
  
### <a name="see-also"></a>Zie ook  

[Velden maken en bewerken voor Common Data Service for Apps met behulp van de PowerApps Solution Explorer](create-edit-field-solution-explorer.md)<br />
[Metagegevens van een entiteit > Entiteitsstatuswaarden](/powerapps/developer/common-data-service/entity-metadata#entity-states)<br />
[Aangepaste statusmodelovergangen definiëren](/dynamics365/customer-engagement/developer/define-custom-state-model-transitions)

