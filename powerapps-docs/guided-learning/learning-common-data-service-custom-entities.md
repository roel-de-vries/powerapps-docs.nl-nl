---
title: Aangepaste entiteiten maken | Microsoft Docs
description: Het algemene gegevensmodel uitbreiden met aangepaste entiteiten
services: 
suite: powerapps
documentationcenter: na
author: mgblythe
manager: anneta
editor: 
tags: 
featuredvideoid: qg25q3MjFBo
courseduration: 6m
ms.service: powerapps
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/09/2016
ms.author: mblythe
ms.openlocfilehash: a28f64f1184e620430299ce4e8d32623172b3a08
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="create-custom-entities"></a>Aangepaste entiteiten maken
De Common Data Service is bedoeld voor al onze zakelijke klanten, van de kleinste bedrijfjes tot de grootste internationale ondernemingen. Het algemene gegevensmodel bevat een set standaardentiteiten die veel bedrijfsscenario’s ondersteunen. U hebt in het vorige onderwerp gezien dat u deze standaardentiteiten zo nodig kunt uitbreiden. Maar soms hebt u iets heel anders nodig voor het oplossen van problemen die specifiek zijn voor uw bedrijf. In dat geval hebt u een aangepaste entiteit nodig, en in dit onderwerp laten we zien hoe u er een kunt maken.

Er zijn twee manieren om een entiteit te maken:

* De entiteit helemaal vanaf nul maken. Dat gaan we in dit onderwerp doen.
* Een entiteit maken die gebaseerd is op een andere entiteit door de velden en instellingen van die entiteit, maar niet de gegevens ervan, te kopiëren.

## <a name="creating-an-entity-from-scratch"></a>Een identiteit maken vanaf nul
In dit voorbeeld maken we een aangepaste entiteit met de naam Product review, en dat doen we helemaal vanaf nul. Open om te beginnen het tabblad **Entiteiten** en klik of tik op **Nieuwe entiteit**. Voer een **naam voor de entiteit** in (geen spaties of speciale tekens), een gebruikersvriendelijke **weergavenaam** en een zinvolle **beschrijving**. Klik of tik op **Volgende**.

![Nieuwe entiteit](./media/learning-common-data-service-custom-entities/new-entity.png)

In het volgende scherm ziet u de vijf standaardvelden die allemaal standaard- en aangepaste entiteiten bevatten. Klik of tik op **Veld toevoegen** om uw eigen velden toe te voegen.

![Velden voor standaardentiteiten](./media/learning-common-data-service-custom-entities/default-fields.png)

In dit voorbeeld gaan we vier velden toevoegen:

* **Beoordelingsdatum**: een vereist datumveld.
* **Productwaardering**: een vereist veld voor gehele getallen. We zouden hier een selectielijst kunnen gebruiken om alleen bepaalde waarden op te geven (zoals 1-5), maar we houden het voorlopig eenvoudig.
* **Naam van revisor**: een niet-vereist tekstveld.
* **Reviewer Comment**: een eveneens niet-vereist tekstveld. 

Wanneer u tevreden bent over de entiteit, klikt of tikt u op **Maken**. Wanneer de entiteit is gemaakt, bevat deze nog geen gegevens. We laten in het volgende onderwerp zien hoe gegevens worden geïmporteerd.

![Aangepaste entiteitvelden](./media/learning-common-data-service-custom-entities/custom-fields.png)

## <a name="creating-a-relationship-between-two-entities"></a>Een relatie tussen twee entiteiten maken
Omdat we elke review willen koppelen aan een bepaald product, moeten we een relatie maken tussen de entiteit Product review en de entiteit Product. Open in de entiteit Product review het tabblad **Relaties** en klik of tik op **Nieuwe relatie**. Selecteer een **gerelateerde entiteit** en voer een **naam**, een **weergavenaam** en een **beschrijving** in. Klik of tik op **Opslaan** om de relatie te maken.

![Relaties tussen entiteiten maken](./media/learning-common-data-service-custom-entities/create-entity-relationship.png)

## <a name="connecting-to-a-custom-entity-in-powerapps-studio"></a>Verbinding maken met een aangepaste entiteit in PowerApps Studio
Verbinding maken met een aangepaste entiteit in PowerApps Studio gaat hetzelfde als verbinding maken met een standaardentiteit. Klik of tik op **Nieuw** en klik of tik onder **Common Data Service** op **Telefoonindeling**. Links ziet u beschikbare gegevensverbindingen en rechts ziet u de lijst met entiteiten.

![Verbinding maken met entiteit in PowerApps Studio](./media/learning-common-data-service-custom-entities/connect-to-custom-entity.png)

In het volgende onderwerp leert u hoe u gegevens beheert in de Common Data Service.

