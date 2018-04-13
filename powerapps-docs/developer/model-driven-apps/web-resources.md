---
title: Webresources gebruiken | Microsoft Docs
description: Ontdek hoe ontwikkelaars webresources gebruiken in modelgestuurde apps.
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
ms.date: 03/17/2018
ms.author: jdaly
ms.openlocfilehash: 56e994929036cc713e7bf7dfc04f46bf991a3530
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2018
---
# <a name="use-web-resources"></a>Webresources gebruiken

Er is een virtuele map met de naam `webresources` beschikbaar in elk Common Data Service for Apps-exemplaar. Hier kunt u HTML, JS, CSS, afbeeldingen en andere bestanden op naam aanvragen en ze openen in uw browser. U kunt deze bestanden met de toepassing uploaden of ze via programmacode toevoegen als [WebResource Entity](../common-data-service/reference/entities/webresource.md)-records. [XrmToolBox WebResources Manager](https://www.xrmtoolbox.com/plugins/MsCrmTools.WebResourcesManager/) is een communityhulpprogramma dat u kunt gebruiken om met deze records te werken.

De records kunnen naar elkaar verwijzen met behulp van aan elkaar gerelateerde padnamen in de inhoud. Dankzij deze mogelijkheid om bestanden te uploaden en ze op naam op te vragen, beschikt u over alle bouwstenen die u nodig hebt om webtoepassingen te maken met bestanden die worden verwerkt binnen de geverifieerde sessie van uw browser. Door alleen clientcode te gebruiken met AJAX-technieken kunt u uitgebreide toepassingen maken voor uitvoering in een browservenster of in een IFrame in een formulier of dashboard. 

Over het algemeen zult u JavaScript-webresources gebruiken om gebeurtenis-handlerfuncties toe te voegen aan formulieren en opdrachten.

Meer informatie:
- [Clientscripts met modelgestuurde apps](client-scripting.md)
- [Dynamics 365 Customer Engagement Developer Guide: Web resources](/dynamics365/customer-engagement/developer/web-resources) (Ontwikkelaarshandleiding voor Dynamics 365 klantcontacten: webresources)
