---
title: Opdrachten aanpassen met modelgestuurde apps | Microsoft Docs
description: Informatie over het aanpassen van opdrachten met modelgestuurde apps
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
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 4721ba49fe227d31f539eabd863b50842e7515b6
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42836249"
---
# <a name="customize-commands-with-model-driven-apps"></a>Opdrachten aanpassen met modelgestuurde apps 

De opdrachten die worden weergegeven in een formulier of op een opdrachtbalk kunnen worden aangepast. Opdrachten worden gebaseerd op de XML-schema's die worden gebruikt in Office-linten. De term *lint* wordt dus nog steeds gebruikt. Wanneer u een opdracht maakt, kunt u drie elementen definiëren:

- *Weergaveregels* worden geëvalueerd wanneer het formulier of de lijst wordt geladen om te bepalen of een opdracht of een groep opdrachten moet worden getoond.
- *Inschakelregels* worden gebruikt om te bepalen of een opdracht wordt ingeschakeld. Dit gebeurt op basis van verschillende factoren, zoals het op dat moment geselecteerde item in de gebruikersinterface.
- Een *actie* voor elke opdracht om aan te geven wat er moet gebeuren wanneer de optie wordt geselecteerd. Met een opdracht kan een URL worden geopend of een functie (gedefinieerd in een JavaScript-webresource) worden uitgevoerd.

Aangepaste opdrachten worden geplaatst op basis van mogelijke bestaande opdrachten. U moet een *aangepaste actie* opgeven op basis waarvan wordt gedefinieerd welke wijziging moet worden toegepast op de bestaande reeks opdrachten. 

Er is geen ontwerpfunctie beschikbaar voor opdrachten. De community biedt wel hulpprogramma's aan. Het [lint Workbench](http://www.develop1.net/public/rwb/ribbonworkbench.aspx) biedt een grafische interface en is het meest gebruikte hulpmiddel voor het aanpassen van opdrachten.

Zie [Dynamics 365 Customer Engagement Developer Guide: Customize commands and the ribbon](/dynamics365/customer-engagement/developer/customize-dev/customize-commands-ribbon) (Ontwikkelaarshandleiding voor Dynamics 365 klantcontacten: Opdrachten en het lint aanpassen) voor meer informatie.


