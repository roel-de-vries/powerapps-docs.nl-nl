---
title: Nieuwe entiteiten maken in de Common Data Service (CDS) met behulp van Power Query | Microsoft Docs
description: Stapsgewijze instructies voor het maken van een nieuwe entiteit in de CDS met behulp van Power Query.
services: 
suite: powerapps
documentationcenter: na
author: mllopis
manager: kfend
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/18/2017
ms.author: millopis
ms.openlocfilehash: 834e05a89fff2142bc38b359ea5b6bccc08894aa
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="create-new-entities-in-the-common-data-service-cds-using-power-query"></a>Nieuwe entiteiten in de Common Data Service (CDS) maken met behulp van Power Query
Met de integratie van **Power Query**, kunnen ontwikkelaars van business-apps nieuwe entiteiten in de Common Data Service (CDS) maken, op basis van een verscheidenheid aan gegevensbronnen.

Met de **Common Data Service** kunnen gebruikers gegevens veilig opslaan en beheren in een set aangepaste en standaardentiteiten. Een *entiteit* is een set velden waarin gegevens worden opgeslagen, vergelijkbaar met een tabel in een database. Zodra de gegevens zijn opgeslagen in de Common Data Service, kunt u met **Microsoft PowerApps** uitgebreide toepassingen bouwen die gebruikmaken van de opgeslagen gegevens.

Door de integratie van **Power Query** kunnen ontwikkelaars van zakelijke apps PowerApps gebruiken om nieuwe entiteiten te maken in de **Common Data Service** op basis van gegevens uit externe gegevensbronnen, zoals on-premises gegevensbronnen als relationele databases (SQL Server, IBM DB2, etc.), Excel-, Acces- en tekstbestanden en online diensten als Salesforce, Azure SQL Database en Data Warehouse, Web API’s, OData-feeds en nog veel meer. Naast de mogelijkheid verbinding te maken met tal van verschillende gegevensbronnen, biedt het gebruik van **Power Query** ook de mogelijkheid gegevens te filteren, transformeren en combineren, voordat u deze in de Common Data Service laadt.

![Nieuwe entiteit op basis van gegevens](media/data-platform-cds-newentity-pq/data-platform-cds-pq-01.jpg)

## <a name="enabling-the-cds-new-entities-from-power-query-feature"></a>De CDS-functie Nieuwe entiteiten op basis van Power Query inschakelen
Deze functie is beschikbaar in uw PowerApps-tenant, maar is niet standaard ingeschakeld. U kunt deze inschakelen in [web.powerapps.com](https://aka.ms/pqocds).

**Opmerking:** u kunt alleen nieuwe aangepaste entiteiten maken in databases die u hebt gemaakt.

Volg in de PowerApps-portal de volgende stappen om deze functie in te schakelen:

1. Blader naar het tabblad **Common Data Service > Entiteiten**, in het navigatiedeelvenster aan de linkerzijde.
2. Selecteer uit het vervolgkeuzemenu voor **Entiteiten** de optie **Nieuwe entiteit**.
3. Selecteer in het vervolgkeuzemenu dat vervolgens wordt weergegeven **Nieuwe entiteit op basis van gegevens (Technical Preview)**, zoals weergegeven in de volgende afbeelding.
   
    ![Nieuwe entiteit op basis van gegevens](media/data-platform-cds-newentity-pq/data-platform-cds-pq-02.jpg)
4. Wanneer u in het menu **Nieuwe entiteit op basis van gegevens (Technical Preview)** selecteert, wordt in deze Technical Preview een lijst met beschikbare connectors weergegeven, zoals wordt weergegeven in de volgende afbeelding.
   
   ![Beschikbare connectors](media/data-platform-cds-newentity-pq/data-platform-cds-pq-03.jpg)
5. Wanneer u de connector die u wilt gebruiken hebt geselecteerd, kunt u doorgaan met de volgende stappen om de details en referenties van de gegevensbronverbinding op te geven, tabellen te selecteren om te importeren, enzovoort. Het is mogelijk dat u ook toegang heeft tot de **Query Editor** (met behulp van de knop **Bewerken** in de **Navigator**-weergave) en die kunt gebruiken om filters toe te passen of stappen voor gegevenstransformatie in te stellen voordat u gegevens naar de CDS importeert.
   
    ![](media/data-platform-cds-newentity-pq/data-platform-cds-pq-04.jpg)

## <a name="adjust-load-settings-and-other-behavior"></a>Instellingen voor laden en ander gedrag aanpassen
Nadat u de stappen in de vorige sectie hebt gevolgd en u over een gegevensbron beschikt om met behulp van **Power Query** nieuwe entiteiten in de CDS te maken, kunt u aanvullende instellingen voor laden instellen, zoals verversingsgedrag en entiteitspecifieke instellingen (zoals weergavenaam, primaire sleutels, etc.).

![](media/data-platform-cds-newentity-pq/data-platform-cds-pq-05.jpg)

Zodra u deze stappen hebt uitgevoerd en **Laden** hebt geselecteerd, hebt u nieuwe aangepaste entiteiten gemaakt in de CDS. U kunt query's ook na het laden bewerken, aan de hand van het menu **Entiteit** voor een specifieke entiteit.

We zijn erg trots op deze functionaliteit en horen graag uw feedback. [Stuur ons vooral uw suggesties en feedback](https://powerusers.microsoft.com/t5/PowerApps-Community/ct-p/PowerApps1) over deze functie!

