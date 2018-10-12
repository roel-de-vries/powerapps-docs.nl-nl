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
ms.openlocfilehash: 60e16ff8cb5c40a37cf0a5243b420f77c4a695bb
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39681623"
---
# <a name="types-of-entities"></a>Typen entiteiten

Voordat u entiteiten in Common Data Service for Apps gaat maken, moet u weten dat er verschillende typen entiteiten zijn. Zodra een aangepaste entiteit is gemaakt, kunnen deze typen niet worden gewijzigd. De twee belangrijkste verschillen zijn gebaseerd op het eigendom van entiteit en of de entiteiten activiteitsentiteiten zijn.  
  
<a name="BKMK_EntityOwnership"></a>

## <a name="entity-ownership"></a>Eigendom van entiteit  

Er zijn vier typen eigendom van entiteit. Bij het maken van een aangepaste entiteit zijn de enige opties **eigendom van gebruiker of team** of **eigendom van organisatie**, maar houd er rekening mee dat andere entiteiten andere eigendomstypen hebben.  
  
|Eigendom|Beschrijving|  
|---------------|-----------------|  
|**Eigendom van bedrijf**|De gegevens in deze entiteiten horen bij het bedrijfsonderdeel. Toegang tot de gegevens kan worden beheerd op het niveau van het bedrijfsonderdeel.|  
|**Geen**|De gegevens zijn geen eigendom van een andere entiteit.|  
|**Eigendom van organisatie**|De gegevens horen bij de organisatie. Toegang tot de gegevens wordt beheerd op het niveau van de organisatie.|  
|**Eigendom van gebruiker of team**|De gegevens horen bij een gebruiker of een team. Acties die kunnen worden uitgevoerd voor deze records, kunnen worden beheerd op het niveau van een gebruiker.|  
  
  
> [!IMPORTANT]
>  Nadat een entiteit is gemaakt, kunt u het eigendom niet wijzigen. Voordat u een entiteit maakt, moet u controleren of u het juiste eigendomstype hebt gekozen. Als u later besluit dat uw aangepaste entiteit van een ander type zijn moet, moet u de entiteit verwijderen en een nieuwe maken.
  
<a name="BKMK_ActivityEntities"></a>

## <a name="activity-entities"></a>Activiteitsentiteiten

Een activiteit kan worden gezien als een actie waarvoor een item in een agenda kan worden gemaakt. Een activiteit heeft tijddimensies (begintijd, eindtijd, vervaldatum en duur) die helpen bepalen wanneer de actie is of wordt uitgevoerd. Activiteiten bevatten ook gegevens die u kunnen helpen bepalen welke actie die activiteit vertegenwoordigt, bijvoorbeeld het onderwerp en de beschrijving. Een activiteit kan worden geopend, geannuleerd of voltooid. De voltooide status van een activiteit heeft verschillende gekoppelde substatuswaarden ter verduidelijking van de manier waarop de activiteit is voltooid.  
  
Activiteitsentiteiten kunnen alleen eigendom zijn van een gebruiker of team, ze kunnen geen eigendom zijn van een organisatie.  
  
In de volgende tabel ziet u de activiteitsentiteiten die beschikbaar zijn in een standaard CDS for Apps-omgeving.
  
|Naam|Beschrijving|In activiteitenmenu's weergeven|Referentie|
|----------|-----------------|----------------|---------------|  
|**Appointment**|Verplichting waarmee een tijdsinterval met een begin- en eindtijd en een duur wordt aangegeven.|Ja|[Appointment](/powerapps/developer/common-data-service/reference/entities/appointment)|
|**E-mail**|Activiteit die wordt geleverd met behulp van e-mailprotocollen.|Ja|[E-mail](/powerapps/developer/common-data-service/reference/entities/email)|
|**Fax**|Activiteit waarmee het resultaat van gesprekken en het aantal faxpagina's wordt bijgehouden. Optioneel kan een elektronisch exemplaar van het document worden opgeslagen.|Ja|[Fax](/powerapps/developer/common-data-service/reference/entities/fax)|
|**Letter**|Activiteit waarmee de bezorging van een brief wordt bijgehouden. De activiteit kan het elektronische exemplaar van de brief bevatten.|Ja|[Letter](/powerapps/developer/common-data-service/reference/entities/letter)|
|**Telefoongesprek**|Activiteit waarmee een telefoongesprek wordt bijgehouden.|Ja|[Telefoongesprek ](/powerapps/developer/common-data-service/reference/entities/phonecall)|
|**Terugkerende afspraak**|De hoofdafspraak van een reeks terugkerende afspraken.|Ja|[RecurringAppointmentMaster](/powerapps/developer/common-data-service/reference/entities/recurringappointmentmaster)|
|**Task**|Algemene activiteit waarmee het werk wordt aangegeven dat moet worden uitgevoerd.|Ja|[Task](/powerapps/developer/common-data-service/reference/entities/task)|
  
U kunt nieuwe aangepaste activiteitsentiteiten maken. U kunt bijvoorbeeld een aangepaste activiteitsentiteit maken om communicatie via chatberichten vast te leggen. Het maken van een activiteitsentiteit verschilt van het maken van een niet-activiteitsentiteit omdat u niet een primair veld opgeeft. Alle activiteitsentiteiten hebben een **Primair veld** ingesteld op **Onderwerp** en andere algemene velden die zijn gedefinieerd door de activiteitsentiteit. Hierdoor kunnen alle soorten activiteiten in een weergave worden getoond waarin alleen de algemene velden worden weergegeven.  

> [!NOTE]
> U kunt geen aangepaste activiteit maken met behulp van de PowerApps-portal. U moet de Slution Explorer openen met behulp van de knop **Geavanceerd**.
  
Wanneer u een aangepaste activiteitsentiteit wilt maken, selecteert u **Definiëren als een activiteitsentiteit**. Nadat u deze optie hebt geselecteerd, ziet u dat **Weergeven in activiteitenmenu's** is geselecteerd. Deze instelling biedt mensen de mogelijkheid dit type activiteit te maken in activiteitenmenu’s. Dit is niet geselecteerd voor activiteiten die gewoonlijk zijn gekoppeld aan specifieke gebeurtenissen en op de achtergrond worden gemaakt met behulp van code of door een werkstroom. U kunt deze instellingen niet meer wijzigen nadat u de entiteit hebt opgeslagen.  

### <a name="see-also"></a>Zie ook
[Entiteiten maken of bewerken](create-edit-entities.md)
