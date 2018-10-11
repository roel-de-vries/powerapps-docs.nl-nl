---
title: Bedrijfslogica toepassen met code | Microsoft Docs
description: Meer informatie over hoe ontwikkelaars code kunnen gebruiken om bedrijfslogica toe te passen in Common Data Service for Apps.
services: ''
suite: powerapps
documentationcenter: na
author: JimDaly
manager: faisalmo
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/26/2018
ms.author: jdaly
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 9abcbf25d2376e28f83988ceb3797d3891ca53bc
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42843332"
---
# <a name="apply-business-logic-with-code"></a>Bedrijfslogica toepassen met code

Als het definiëren van bedrijfslogica vereist is in uw bedrijf, controleert u indien mogelijk eerst of u een van de declaratieve procesopties kunt toepassen. Zie [Aanpassingshandleiding voor Dynamics 365 Customer Engagement: Een aangepaste bedrijfslogica maken door middel van processen](/dynamics365/customer-engagement/customize/guide-staff-through-common-tasks-processes).

Wanneer een declaratief proces niet aan de vereisten voldoet, hebt u als ontwikkelaar verschillende mogelijkheden. In dit onderwerp vindt u algemene opties voor het schrijven van code.

## <a name="create-a-workflow-extension"></a>Een werkstroomextensie maken

U kunt een .NET-assembly schrijven om nieuwe opties te bieden in de ontwerpfunctie voor processen. Deze methode biedt een nieuwe optie voor personen die Workflow Designer gebruiken om een voorwaarde toe te passen of een nieuwe actie uit te voeren. Een werkstroomextensie kan vervolgens opnieuw worden gebruikt door niet-ontwikkelaars om de logica in uw code toe te passen.

Zie [Dynamics 365 Customer Engagement Developer Guide: Custom workflow activities (workflow assemblies)](/dynamics365/customer-engagement/developer/custom-workflow-activities-workflow-assemblies) (Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: Aangepaste werkstroomactiviteiten (werkstroomassembly's)) voor meer informatie.

## <a name="create-a-plug-in"></a>Een invoegtoepassing maken

U kunt een .NET-assembly schrijven die u als invoegtoepassing voor de gegevenstransactiestroom kunt gebruiken om de bedrijfslogica op de server toe te passen. Met Common Data Service voor Apps beschikt u over een framework waarmee u specifieke gebeurtenissen kunt registreren voor het uitvoeren van code die is gedefinieerd binnen klasse in een assembly. Deze klasse neemt een specifieke interface over waarmee een [Execute-methode](/dotnet/api/microsoft.xrm.sdk.iplugin.execute) beschikbaar wordt gemaakt. Wanneer de geregistreerde gebeurtenis plaatsvindt, wordt de `Execute`-methode voor de klasse aangeroepen en worden contextuele gegevens over de gebeurtenis doorgegeven.

U gebruikt het *registratieprogramma voor invoegtoepassingen* om uw assembly's te registreren.

Binnen de `Execute`-methode kunt u het objectmodel dat in de SDK-assembly's is gedefinieerd gebruiken om de gegevens over de contextuele gebeurtenis te evalueren en de toepasselijke acties uit te voeren om het volgende te doen:
- Bepalen of de bewerking moet worden geannuleerd door een fout te genereren
- Wijzigingen aanbrengen in de contextuele gegevens die worden doorgegeven aan de Execute-methode
- Aanvullende bewerkingen uitvoeren voor het automatiseren van processen met behulp van de organisatieservice

### <a name="synchronous-and-asynchronous-plug-ins"></a>Synchrone en asynchrone invoegtoepassingen
U kunt invoegtoepassingen zo registreren, dat ze synchroon worden uitgevoerd binnen de transactie of worden uitgesteld en naar een wachtrij worden verzonden, zodat de logica op een gunstiger moment kan worden toegepast met minder nadelige invloed op de server. Vanwege deze nadelige invloed op de server wordt u aangeraden asynchrone invoegtoepassingen te gebruiken.

Wanneer u de invoegtoepassing registreert voor synchrone uitvoering voor een gebeurtenis, kunt u aangeven wanneer de code moet worden uitgevoerd. Er zijn drie fasen:

|Gebeurtenis  |Beschrijving  |
|---------|---------|
|Voor validering|De code wordt uitgevoerd voordat de databasetransactie begint. Dit is een goed moment om bedrijfslogica toe te passen waarmee wordt bepaald of de bewerking moet worden geannuleerd voordat de transactie begint om te voorkomen dat de prestaties nadelig worden beïnvloed en de transactie wordt teruggedraaid.|
|Voor bewerking|De code wordt uitgevoerd nadat de databasetransactie is begonnen. Als u op dit moment een bewerking annuleert, moet de transactie worden teruggedraaid.|
|Na bewerking|De code wordt uitgevoerd tijdens de databasetransactie, nadat de belangrijkste gegevensbewerking is voltooid. Deze bewerking omvat wijzigingen die zijn toegepast tijdens eerdere gebeurtenissen, maar heeft nog grotere gevolgen wanneer de bewerking wordt geannuleerd.|

> [!NOTE]
> Voor synchrone invoegtoepassingen gelden beperkingen met betrekking tot de hoeveelheid systeembronnen die kan worden gebruikt. Als een invoegtoepassing de drempels overschrijdt of niet meer reageert, treedt een uitzondering op en wordt de bewerking geannuleerd.

Zie [Dynamics 365 Customer Engagement Developer Guide: Write plug-ins to extend business processes](/dynamics365/customer-engagement/developer/write-plugin-extend-business-processes) (Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: Invoegtoepassingen schrijven om bedrijfsprocessen uit te breiden) voor meer informatie.

### <a name="see-also"></a>Zie ook

[Overzicht van Common Data Service for Apps voor ontwikkelaars](overview.md)
