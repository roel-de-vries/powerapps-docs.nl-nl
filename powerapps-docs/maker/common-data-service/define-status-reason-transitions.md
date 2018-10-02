---
title: Statusredenovergangen definiëren met PowerApps | MicrosoftDocs
description: Informatie over het definiëren van statusredenovergangen
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="define-status-reason-transitions-for-the-case-or-custom-entities"></a>Statusredenovergangen definiëren voor de aanvraag of aangepaste entiteiten

U kunt statusredenovergangen opgeven voor de entiteit Incident (**Aanvraag**) of voor een aangepaste entiteit.

> [!NOTE]
> Hoewel de entiteit Incident (Aanvraag) niet is opgenomen in een Common Data Service voor Apps-standaardomgeving, wordt deze gebruikt door [Dynamics 365 for Customer Service](https://dynamics.microsoft.com/customer-service/) en gedefinieerd in het [Common Data Model](https://github.com/Microsoft/CDM/blob/master/schemaDocuments/core/applicationCommon/foundationCommon/crmCommon/service/Incident.cdm.json)
  
Statusredenovergangen zijn een optioneel extra niveau van filtering om te definiëren waar de statusreden in kan worden veranderd voor elke statusreden. Het definiëren van een beperkte lijst met geldige opties kan het voor gebruikers makkelijker maken de juiste volgende statusreden van een record te kiezen wanneer er een groot aantal combinaties van geldige statusredenwaarden zijn.  
  
<a name="BKMK_StatusAndStatusReasons"></a>

## <a name="what-is-the-connection-between-status-and-status-reason-fields"></a>Wat is de verbinding tussen de velden Status en Reden van status?  

Entiteiten die verschillende statuswaarden kunnen hebben, hebben twee velden die deze gegevens vastleggen:  
  
|Weergavenaam|Beschrijving|  
|------------------|-----------------|  
|**Status**|Vertegenwoordigt de status van de record. Normaal gesproken **Actief** of **Inactief**. U kunt geen nieuwe statusopties toevoegen.|  
|**Reden van status**|Vertegenwoordigt een reden die is gekoppeld aan een specifieke status. Elke status moet ten minste één mogelijke statusreden hebben. U kunt extra statusredenopties toevoegen.|  
  
De metagegevens voor het veld bepalen welke statuswaarden geldig zijn voor een bepaalde status. Bijvoorbeeld, voor de entiteit Incident (**Aanvraag**) zijn dit de standaardstatus- en statusredenopties:  
  
|Status|Reden van status|  
|------------|-------------------|  
|**Actief**|<li>**Wordt uitgevoerd**</li><li>**In de wacht**</li><li>**Wacht op details**</li><li>**Doet onderzoek**</li>| 
|**Gesloten**|<li>**Probleem opgelost**</li><li>**Opgegeven gegevens**</li>|
|**Geannuleerd**|<li>**Geannuleerd**</li><li>**Samengevoegd**</li>|
  
  
<a name="BKMK_EditStatusReasonTransitions"></a>   

## <a name="edit-status-reason-transitions"></a>Statusredenovergangen bewerken
 
U kunt de statusredenopties voor de aanvraagentiteit en voor aangepaste entiteiten wijzigen om te bepalen welke andere statusredenopties gebruikers kunnen kiezen. De enige beperking is dat elke statusredenoptie voor een actieve status ten minste één pad naar een inactieve status moet toestaan. Anders kunt u een voorwaarde maken waarbij het niet mogelijk is de aanvraag op te lossen of te annuleren.  

> [!NOTE]
> Voor het bewerken van de statusredenovergangen hebt u de oplossingenverkenner nodig. Zie [Velden maken en bewerken voor Common Data Service voor Apps met de PowerApps-oplossingenverkenner](create-edit-field-solution-explorer.md) voor informatie over het bewerken van velden.
  
 Wanneer u een reden van statusredenveld bewerkt, bevindt de knop **Overgangen van reden van status bewerken** zich in het menu. 

![Opdracht Overgangen van reden van status bewerken](media/status-reason-transitions-command.png)

Als u op deze knop klikt, biedt het dialoogvenster **Overgangen van redenen van status** de optie om **Overgangen van redenen van status inschakelen** te kiezen. Als deze optie is geselecteerd, moet u bepalen welke *andere* statusredenwaarden toegestaan zijn voor elke statusreden. Als u de toegepaste filtering wilt verwijderen, verwijdert u de selectie. **Overgangen van redenen van status inschakelen**. De overgangen die u hebt gedefinieerd, blijven behouden maar worden niet toegepast.  
  
De onderstaande schermopname biedt een voorbeeld dat aan de volgende vereisten voldoet: 
 
- Een aanvraag kan op elk gewenst moment worden samengevoegd. U kunt geen aanvragen samenvoegen als een statusredenovergang dat niet toestaat.  
- Een actieve aanvraag kan op elk gewenst moment worden geannuleerd.  
- Een opgeloste of geannuleerde aanvraag kan niet opnieuw worden geactiveerd.  
- Alle aanvragen moeten de volgende fasen doorlopen: **Wordt uitgevoerd** > **In de wacht** > **Wacht op details** > **Doet onderzoek** voordat ze kunnen worden opgelost. In deze configuratie kan een aanvraag niet op een eerdere status worden ingesteld.  
  > [!NOTE]
  >  Dit is geen goed voorbeeld van echt werk, maar het toont hoe de fasen van de status kunnen worden afgedwongen door middel van statusredenovergangen.  
  
 ![Voorbeeld van reden van statusovergangen voor aanvraag](media/status-reason-transitions-example.PNG)  
  
### <a name="see-also"></a>Zie ook  

[Velden maken en bewerken voor Common Data Service voor Apps met de PowerApps-oplossingenverkenner | MicrosoftDocs](create-edit-field-solution-explorer.md)<br />
[Metagegevens entiteit > Entiteitsstatussen](/powerapps/developer/common-data-service/entity-metadata#entity-states)<br />
[Aangepaste statusmodelovergangen definiëren](/dynamics365/customer-engagement/developer/define-custom-state-model-transitions)

