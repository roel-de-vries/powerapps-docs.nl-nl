---
title: Beperkte entiteiten waarvoor Dynamics 365-licenties vereist zijn| Microsoft Docs
description: Een lijst met beperkte entiteiten in Common Data Service (CDS) for Apps waarvoor Dynamics 365-licenties zijn vereist.
author: clwesene
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: reference
ms.date: 05/01/2018
ms.author: clwesene
ms.openlocfilehash: 79b6e386154b15ae6c625afbebbed18a8a86c420
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34167993"
---
# <a name="restricted-entities-requiring-dynamics-365-licenses"></a>Beperkte entiteiten waarvoor Dynamics 365-licenties vereist zijn
Makers van apps kunnen de meeste entiteiten die beschikbaar zijn in Common Data Service (CDS) voor apps gebruiken om apps en stromen te maken voor gebruikers die alleen beschikken over een licentie voor PowerApps-abonnement 1. Sommige entiteiten bevatten echter complexe bedrijfslogica waarvoor app-gebruikers moeten beschikken over een licentie voor PowerApps-abonnement 2 of voor Microsoft Flow-abonnement 2 (zie [Licentievereisten voor entiteiten](data-platform-entity-licenses.md) voor meer informatie). Voor een nog kleinere set entiteiten die is gekoppeld aan Dynamics 365-producten hebben gebruikers van canvas- en modelgestuurde apps een licentie nodig voor het bijbehorende Dynamics 365-product als ze records binnen de entiteiten willen maken, bijwerken of verwijderen. Deze worden aangeduid als *beperkte* entiteiten.

Entiteiten kunnen om de volgende redenen beperkt zijn tot een Dynamics 365-licentie:

* De entiteit wordt gebruikt voor het opslaan en onderhouden van productspecifieke configuratiegegevens die doorgaans niet buiten de toepassing worden gebruikt.
* De entiteit is voorzien van geavanceerde logica waarmee gegevens op een specifieke manier worden gemaakt en onderhouden bij gebruik binnen een Dynamics 365-product.

Als een app of stroom alleen informatie van een entiteit leest, is een Dynamics 365-licentie niet vereist en is alleen een juiste PowerApps- of Microsoft Flow-licentie nodig. 

## <a name="restricted-entities-for-create-update-and-delete-operations"></a>Beperkte entiteiten voor maak-, bijwerk- en verwijderbewerkingen
De volgende tabel bevat de beperkte entiteiten en de bijbehorende Dynamics 365-licentievereisten voor gebruikers van PowerApps- en Microsoft Flow-apps die gegevens die in de entiteiten zijn opgeslagen maken, bijwerken of verwijderen. 

|Entiteit  |Logische naam  |Licentie vereist  |
|---------|---------|---------|
Werkelijk |msdyn_actual |Dynamics 365 for Field Service <br> **of** Dynamics 365 for Project Service Automation<br>**of** Dynamics 365 Customer Engagement-abonnement <br> **of** Dynamics 365-abonnement
Bedrijfsproces Overeenkomst |msdyn_bpf_baa0a411a239410cb8bded8b5fdd88e3 |Dynamics 365 for Field Service<br>**of** Dynamics 365 Customer Engagement-abonnement <br> **of** Dynamics 365-abonnement
Boekingenjournaal | msdyn_bookingjournal|Dynamics 365 for Field Service<br>**of** Dynamics 365 Customer Engagement-abonnement <br> **of** Dynamics 365-abonnement
Metagegevens voor het instellen van boekingen | msdyn_bookingsetupmetadata|Dynamics 365 for Field Service <br> **of** Dynamics 365 for Project Service Automation<br>**of** Dynamics 365 Customer Engagement-abonnement <br> **of** Dynamics 365-abonnement
Boekingstimestamp | msdyn_bookingtimestamp|Dynamics 365 for Field Service<br>**of** Dynamics 365 Customer Engagement-abonnement <br> **of** Dynamics 365-abonnement
Bedrijfsproces Aanvraag tot werkorder |msdyn_bpf_989e9b1857e24af18787d5143b67523b |Dynamics 365 for Field Service<br>**of** Dynamics 365 Customer Engagement-abonnement <br> **of** Dynamics 365-abonnement
Configuratie |msdyn_configuration |Dynamics 365 for Field Service <br> **of** Dynamics 365 for Project Service Automation<br>**of** Dynamics 365 Customer Engagement-abonnement <br> **of** Dynamics 365-abonnement
Recht | recht | Dynamics 365 for Customer Service, Enterprise edition <br>**of** Dynamics 365 Customer Engagement-abonnement <br> **of** Dynamics 365-abonnement
Schattingsregel|msdyn_estimateline|Dynamics 365 for Project Service Automation<br>**of** Dynamics 365 Customer Engagement-abonnement <br> **of** Dynamics 365-abonnement
Schatting|msdyn_estimate |Dynamics 365 for Project Service Automation<br>**of** Dynamics 365 Customer Engagement-abonnement <br> **of** Dynamics 365-abonnement
Feit|msdyn_fact |Dynamics 365 for Project Service Automation<br>**of** Dynamics 365 Customer Engagement-abonnement <br> **of** Dynamics 365-abonnement
Field Service-instelling |msdyn_fieldservicesetting |Dynamics 365 for Field Service<br>**of** Dynamics 365 Customer Engagement-abonnement <br> **of** Dynamics 365-abonnement
Field Service-systeemtaak |msdyn_fieldservicesystemjob |Dynamics 365 for Field Service<br>**of** Dynamics 365 Customer Engagement-abonnement <br> **of** Dynamics 365-abonnement
Doel | doel | Dynamics 365 for Sales Professional, <br>**of**Dynamics 365 for Sales, Enterprise Edition, <br>**of** Dynamics 365 Customer Engagement-abonnement <br> **of** Dynamics 365-abonnement
Incident | incident | Dynamics 365 for Customer Service, Enterprise edition <br>**of** Dynamics 365 Customer Engagement-abonnement <br> **of** Dynamics 365-abonnement
Voorraadjournaal |msdyn_inventoryjournal |Dynamics 365 for Field Service<br>**of** Dynamics 365 Customer Engagement-abonnement <br> **of** Dynamics 365-abonnement
Factuurproces |msdyn_bpf_d8f9dc7f099f44db9d641dd81fbd470d |Dynamics 365 for Project Service Automation<br>**of** Dynamics 365 Customer Engagement-abonnement <br> **of** Dynamics 365-abonnement
Reis | reis | Dynamics 365 for Marketing <br> **of** Dynamics 365 Customer Engagement-abonnement <br> **of** Dynamics 365-abonnement
Kennisartikel | kennisartikel | Dynamics 365 for Customer Service, Enterprise edition <br>**of** Dynamics 365 Customer Engagement-abonnement <br> **of** Dynamics 365-abonnement
Organisatie-eenheid |msdyn_organizationalunit |Dynamics 365 for Field Service <br> **of** Dynamics 365 for Project Service Automation<br>**of** Dynamics 365 Customer Engagement-abonnement <br> **of** Dynamics 365-abonnement
Productinventaris |msdyn_productinventory |Dynamics 365 for Field Service<br>**of** Dynamics 365 Customer Engagement-abonnement <br> **of** Dynamics 365-abonnement
Projectparameter|msdyn_projectparameter |Dynamics 365 for Project Service Automation<br>**of** Dynamics 365 Customer Engagement-abonnement <br> **of** Dynamics 365-abonnement
Projectfasen| msdyn_bpf_665e73aa18c247d886bfc50499c73b82|Dynamics 365 for Project Service Automation<br>**of** Dynamics 365 Customer Engagement-abonnement <br> **of** Dynamics 365-abonnement
Projecttaakafhankelijkheid|msdyn_projecttaskdependency |Dynamics 365 for Project Service Automation<br>**of** Dynamics 365 Customer Engagement-abonnement <br> **of** Dynamics 365-abonnement
Projecttaak|msdyn_projecttask |Dynamics 365 for Project Service Automation<br>**of** Dynamics 365 Customer Engagement-abonnement <br> **of** Dynamics 365-abonnement
Projectteamlid|msdyn_projecteam |Dynamics 365 for Project Service Automation<br>**of** Dynamics 365 Customer Engagement-abonnement <br> **of** Dynamics 365-abonnement
Bedrijfsproces Inkooporder | msdyn_bpf_2c5fe86acc8b414b8322ae571000c799|Dynamics 365 for Field Service<br>**of** Dynamics 365 Customer Engagement-abonnement <br> **of** Dynamics 365-abonnement
Detail van resourcetoewijzing (afgeschaft)|msdyn_resourceassignmentdetail |Dynamics 365 for Project Service Automation<br>**of** Dynamics 365 Customer Engagement-abonnement <br> **of** Dynamics 365-abonnement
Resourcetoewijzing|msdyn_resourceassignment |Dynamics 365 for Project Service Automation<br>**of** Dynamics 365 Customer Engagement-abonnement <br> **of** Dynamics 365-abonnement
Resourcebeperking (afgeschaft) |msdyn_workorderresourcerestriction | Dynamics 365 for Field Service<br>**of** Dynamics 365 Customer Engagement-abonnement <br> **of** Dynamics 365-abonnement
Regelset voor routering | routeringsregel | Dynamics 365 for Customer Service, Enterprise edition <br>**of** Dynamics 365 Customer Engagement-abonnement <br> **of** Dynamics 365-abonnement
Planbordinstelling |msdyn_scheduleboardsetting |Dynamics 365 for Field Service <br> **of** Dynamics 365 for Project Service Automation<br>**of** Dynamics 365 Customer Engagement-abonnement <br> **of** Dynamics 365-abonnement
Planningsparameter |msdyn_schedulingparameter |Dynamics 365 for Field Service <br> **of** Dynamics 365 for Project Service Automation<br>**of** Dynamics 365 Customer Engagement-abonnement <br> **of** Dynamics 365-abonnement
SLA| sla | Dynamics 365 for Customer Service, Enterprise edition <br>**of** Dynamics 365 Customer Engagement-abonnement <br> **of** Dynamics 365-abonnement
Planinstelling voor systeemgebruiker |msdyn_systemuserschedulersetting|Dynamics 365 for Field Service <br> **of** Dynamics 365 for Project Service Automation<br>**of** Dynamics 365 Customer Engagement-abonnement <br> **of** Dynamics 365-abonnement
Transactieverbinding|msdyn_transactionconnection |Dynamics 365 for Project Service Automation<br>**of** Dynamics 365 Customer Engagement-abonnement <br> **of** Dynamics 365-abonnement
Transactieoorsprong|msdyn_transactionorigin |Dynamics 365 for Project Service Automation<br>**of** Dynamics 365 Customer Engagement-abonnement <br> **of** Dynamics 365-abonnement
Transactietype|msdyn_transactiontype |Dynamics 365 for Project Service Automation<br>**of** Dynamics 365 Customer Engagement-abonnement <br> **of** Dynamics 365-abonnement
Uniek nummer|msdyn_uniquenumber |Dynamics 365 for Field Service<br>**of** Dynamics 365 Customer Engagement-abonnement <br> **of** Dynamics 365-abonnement
Bedrijfsproces Werkorder |msdyn_bpf_d3d97bac8c294105840e99e37a9d1c39 |Dynamics 365 for Field Service<br>**of** Dynamics 365 Customer Engagement-abonnement <br> **of** Dynamics 365-abonnement
Wachtrij voor het genereren van werkorderdetails (afgeschaft)|msdyn_workorderdetailsgenerationqueue |Dynamics 365 for Field Service<br>**of** Dynamics 365 Customer Engagement-abonnement <br> **of** Dynamics 365-abonnement

## <a name="licensing"></a>Licentieverlening
Zie de pagina [Licentieoverzicht](../../administrator/pricing-billing-skus.md) voor meer informatie over PowerApps- en Dynamics 365-licenties.

