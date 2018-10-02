---
title: Typen entiteiten | MicrosoftDocs
ms.custom: ''
ms.date: 05/30/2018
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
ms.assetid: 2f3f6053-0b9e-41e7-bd94-2239351e9f4b
caps.latest.revision: 41
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="types-of-entities"></a>Typen van entiteiten

Voordat u entiteiten maakt of bewerkt in Common Data Service voor Apps, moet u weten dat er verschillende soorten entiteiten zijn. Als een aangepaste entiteit is gemaakt, kunnen deze soorten niet worden gewijzigd. De twee algemene distincties zijn gebaseerd op entiteiteigendom en of de entiteiten activiteitsentiteiten zijn.  
  
<a name="BKMK_EntityOwnership"></a>

## <a name="entity-ownership"></a>Entiteiteigendom  

Er zijn vier verschillende typen entiteiteigendom. Als u een aangepaste entiteit maakt dan zijn de enige opties **eigendom van een gebruiker of een team** of **eigendom van de organisatie**, maar u moet bedenken dat andere entiteiten verschillende eigendomtypen hebben.  
  
|Eigendom|Beschrijving|  
|---------------|-----------------|  
|**Eigendom van het bedrijf**|Gegevens in deze entiteiten horen bij de business unit. De toegang tot de gegevens kan worden beheerd op business unit-niveau.|  
|**Geen**|Gegevens die niet het eigendom van een andere entiteit zijn.|  
|**Eigendom van de organisatie**|Gegevens zijn van de organisatie. De toegang tot de gegevens wordt beheerd op organisatieniveau.|  
|**Eigendom van gebruiker of team**|Gegevens behoren toe aan een gebruiker of team. De acties die voor deze records kunnen worden uitgevoerd, kunnen worden beheerd op gebruikersniveau.|  
  
  
> [!IMPORTANT]
>  Nadat een entiteit is gemaakt, kunt u het eigendom niet wijzigen. Voordat u een entiteit maakt, moet u ervoor zorgen dat u het juiste type eigendom kiest. Als u vaststelt dat uw aangepaste entiteit van een ander type moet zijn, dan moet u deze verwijderen en een nieuwe maken.
  
<a name="BKMK_ActivityEntities"></a>

## <a name="activity-entities"></a>Activiteitsentiteiten

Een activiteit kan worden gedacht als een actie waarvoor een vermelding in een agenda kan worden gemaakt. Een activiteit heeft tijddimensies (begintijd, eindtijd, einddatum en duur) waarmee kan worden bepaald wanneer de actie gebeurde of zal gebeuren. Activiteiten bevatten ook gegevens die helpen bij het bepalen welke actie de activiteit vertegenwoordigt, bijvoorbeeld, onderwerp en beschrijving. Een activiteit kan worden geopend, worden geannuleerd, of zijn voltooid. Aan de voltooidheid van een activiteit zullen enkele substatuswaarden zijn gekoppeld om de wijze te verhelderen waarop de activiteit werd voltooid.  
  
Activiteitentiteiten kunnen alleen eigendom zijn van een gebruiker of een team, ze kunnen ze niet eigendom zijn van een organisatie.  
  
In de onderstaande tabel worden activiteitsentiteiten weergegeven die beschikbaar zijn in een standaardomgeving van CDS voor Apps.
  
|Naam|Beschrijving|Weergeven in activiteitenmenu's|Verwijzing|
|----------|-----------------|----------------|---------------|  
|**Afspraak**|Een verplichting die verwijst naar een tijdsinterval met begin-/eindtijden en een tijdsduur.|Ja|[Afspraak](/powerapps/developer/common-data-service/reference/entities/appointment)|
|**E-mail**|Activiteit die wordt geleverd met e-mailprotocollen.|Ja|[E-mail](/powerapps/developer/common-data-service/reference/entities/email)|
|**Fax**|De activiteit waarmee het resultaat van gesprekken en het aantal faxpagina's wordt bijgehouden. Optioneel kan een elektronisch exemplaar van het document worden opgeslagen.|Ja|[Fax](/powerapps/developer/common-data-service/reference/entities/fax)|
|**Brief**|Activiteit die de levering van een brief bijhoudt. De activiteit kan de elektronische kopie van de brief bevatten.|Ja|[Brief](/powerapps/developer/common-data-service/reference/entities/letter)|
|**Telefoongesprek**|De activiteit waarmee een telefoongesprek wordt bijgehouden.|Ja|[PhoneCall ](/powerapps/developer/common-data-service/reference/entities/phonecall)|
|**Terugkerende afspraak**|De hoofdafspraak van een terugkerende afspraakreeks.|Ja|[RecurringAppointmentMaster](/powerapps/developer/common-data-service/reference/entities/recurringappointmentmaster)|
|**Taak**|Een algemene activiteit die aangeeft welke werkzaamheden moeten worden uitgevoerd.|Ja|[Taak](/powerapps/developer/common-data-service/reference/entities/task)|
  
U kunt nieuwe aangepaste activiteitsentiteiten maken. U kunt bijvoorbeeld een aangepaste activiteitsentiteit maken om expresberichtcommunicatie vast te leggen. Het maken van een entiteit verschilt van het maken van een niet-activiteitentiteit omdat u geen primair veld specificeert. Alle activitseitentiteiten hebben een **Primair veld** dat is ingesteld op **Onderwerp** en andere veelgebruikte velden die zijn gedefinieerd door de activiteitsentiteit. Hierdoor kunnen alle activiteittypen worden weergegeven in een weergave waarin u de algemene velden worden weergegeven.  

> [!NOTE]
> U kunt geen aangepaste activiteit maken via de PowerApps-portal. U moet de oplossingenverkenner openen via de knop **Geavanceerd**.
  
Als u een aangepaste activiteitsentiteit wilt maken, dan selecteert u **Stel in als activiteitenentiteit**. Als u dit hebt selecteert, dan zult u zien **Weergeven in activiteitenmenu's** is geselecteerd. Met deze instelling kunnen mensen dit activiteittype maken in de activiteitmenu's. Deze is niet geselecteerd voor activiteiten die gewoonlijk aan specifieke evenementen zijn gekoppeld en die zijn gemaakt door het gebruik van code of door een werkstroom. U kunt de instellingen niet wijzigen nadat u de entiteit hebt opgeslagen.  

### <a name="see-also"></a>Zie ook
[Entiteiten maken of bewerken](create-edit-entities.md)
