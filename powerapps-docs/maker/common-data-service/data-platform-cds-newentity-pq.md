---
title: Snelstartgids om gegevens aan een entiteit in Common Data Service toe te voegen met Power Query | Microsoft Docs
description: Snelstartgids met stapsgewijze instructies om met Power Query gegevens toe te voegen aan een nieuwe of bestaande entiteit in Common Data Service for Apps vanuit een andere gegevensbron.
documentationcenter: na
author: AFTOwen
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: cds
ms.date: 03/21/2018
ms.author: anneta
ms.openlocfilehash: e54553467714bad1f4bc17963f1011c0decc1963
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
---
# <a name="quickstart-add-data-to-an-entity-in-the-common-data-service-by-using-power-query"></a>Snelstartgids: Gegevens aan een entiteit in Common Data Service toevoegen met Power Query
In deze procedure maakt u een entiteit in de [Common Data Service for Apps](data-platform-intro.md) en vult u de entiteit met gegevens uit een OData-feed via Power Query. U kunt dezelfde technieken gebruiken om gegevens vanuit deze online en on-premises gegevensbronnen te integreren, waaronder:

* SQL Server
* Salesforce
* IBM DB2
* Access
* Excel
* Web-API’s
* OData-feeds
* Tekstbestanden

U kunt ook gegevens filteren, transformeren en samenvoegen voordat u deze in een nieuwe of bestaande entiteit laadt.

Als u geen licentie voor PowerApps hebt, kunt u zich [gratis registreren](../signup-for-powerapps.md).

## <a name="prerequisites"></a>Vereisten
Als u dit onderwerp wilt volgen, moet u overschakelen naar een [omgeving](../canvas-apps/working-with-environments.md) waarin u entiteiten kunt maken.

## <a name="specify-the-source-data"></a>De brongegevens opgeven

1. Meld u aan bij **PowerApps** en klik of tik vervolgens op de pijl omlaag op [Gegevens](https://web.powerapps.com) bij de linkerrand.

    ![PowerApps-startpagina](./media/data-platform-cds-newentity-pq/sign-in.png)

1. Tik of klik in de weergegeven lijst op **Gegevensintegratie** en klik of tik vervolgens op **Nieuw Project** bij de rechterbovenhoek van het venster.

1. Klik of tik in de lijst met gegevensbronnen op **OData**.

    ![De OAuth-connector kiezen](./media/data-platform-cds-newentity-pq/choose-odata.png)

1. Typ of plak deze URL onder **Verbindingsinstellingen** en selecteer vervolgens **Volgende**:<br>
`http://services.odata.org/V4/Northwind/Northwind.svc/`

1. Schakel in de lijst met tabellen het selectievakje **Klanten** in en klik of tik op **Volgende**.

    ![De tabel Klanten inschakelen selecteren](./media/data-platform-cds-newentity-pq/select-table.png)

1. (optioneel) Pas het schema naar behoefte aan door te kiezen welke kolommen u wilt opnemen, de tabel op een of andere manier te transformeren, een index of voorwaardelijke kolom toe te voegen of andere wijzigingen aan te brengen.

1. Klik of tik in de rechterbenedenhoek op **Volgende**.

## <a name="specify-the-target-entity"></a>De doelentiteit opgeven
1. Selecteer onder **Instellingen laden** de optie **Naar een nieuwe entiteit laden**.

    ![De naam van de nieuwe entiteit opgeven](./media/data-platform-cds-newentity-pq/new-entity-name.png)

    U kunt de nieuwe entiteit een andere naam of weergavenaam geven, maar laat de standaardwaarden ongewijzigd als u deze zelfstudie exact wilt volgen.

1. Klik of tik in de lijst **Primaire-naamveld** op **Naam contactpersoon** en klik of tik op **Volgende** in de rechterbenedenhoek.

    U kunt een ander veld voor de primaire naam opgeven of een andere kolom in de brontabel toewijzen aan elk veld in de entiteit die u maakt, of beide. Als u deze zelfstudie exact wilt volgen, laat u de standaardtoewijzing voor de kolom ongewijzigd.

1. Wanneer de **Laadstatus** is **voltooid**, selecteert u **Gereed** in de rechterbenedenhoek.

1. Selecteer onder **Gegevens** (in de buurt van de linkerrand) **Entiteiten** om de lijst met entiteiten in uw database weer te geven.

    De entiteit **Klanten** die u hebt gemaakt van een OData-feed wordt weergegeven als een aangepaste entiteit.

    ![Lijst met standaardentiteiten en aangepaste entiteiten](./media/data-platform-cds-newentity-pq/entity-list.png)

> [!WARNING]
> Als u met Power Query gegevens toevoegt aan een bestaande entiteit, worden alle gegevens in die entiteit overschreven.

Als u **Naar bestaande entiteit laden** selecteert, kunt u een entiteit opgeven waaraan u gegevens uit de tabel **Klanten** toevoegt. U kunt bijvoorbeeld de gegevens aan de entiteit **Account** toevoegen waarmee de Common Data Service wordt geleverd. Verder kunt u onder **Bronkolom** opgeven dat de gegevens in de kolom **Naam contactpersoon** uit de tabel **Klanten** moeten worden toegevoegd aan de kolom **Naam** in de entiteit **Accounts**.

![De naam van de nieuwe entiteit opgeven](./media/data-platform-cds-newentity-pq/existing-entity.png)

We zijn trots op deze functionaliteit en horen graag uw feedback. [Stuur ons vooral uw suggesties en feedback](https://powerusers.microsoft.com/t5/PowerApps-Community/ct-p/PowerApps1) over deze functie!

Als een [foutbericht over machtigingen](data-platform-cds-newentity-troubleshooting-mashup.md) wordt weergegeven, neemt u contact op met uw beheerder.