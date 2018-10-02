---
title: Gegevens aan een entiteit toevoegen in Common Data Service voor Apps met behulp van Power Query | Microsoft Docs
description: Stapsgewijze instructies voor het gebruik van Power Query om gegevens aan een nieuwe of bestaande entiteit toe te voegen in Common Data Service (CDS) voor Apps vanuit een andere gegevensbron.
author: AFTOwen
manager: kfile
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: cds
ms.date: 03/21/2018
ms.author: anneta
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="add-data-to-an-entity-in-common-data-service-for-apps-by-using-power-query"></a>Gegevens aan een entiteit toevoegen in Common Data Service voor Apps met behulp van Power Query
In deze procedure maakt u een entiteit n [Common Data Service (CDS) voor Apps](data-platform-intro.md) en vult u die entiteit met gegevens vanuit een OData-feed door Power Query te gebruiken. U kunt dezelfde methoden gebruiken om gegevens vanuit deze online en on-premises bronnen te integreren, onder andere:

* SQL Server
* Salesforce
* IBM DB2
* Toegang
* Excel
* Web-API´s
* OData-feeds
* Tekstbestanden

U kunt gegevens ook filteren, transformeren en combineren voordat u ze in een nieuwe of bestaande entiteit laadt.

Als u geen licentie voor PowerApps hebt, kunt u zich [gratis registreren](../signup-for-powerapps.md).

## <a name="prerequisites"></a>Vereisten
Als u dit onderwerp wilt volgen, moet u overschakelen naar een [omgeving](../canvas-apps/working-with-environments.md) waarin u entiteiten kunt maken.

## <a name="specify-the-source-data"></a>De brongegevens opgeven

1. Meld u aan bij [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) en klik of tik vervolgens op de pijl-omlaag voor **Gegevens** nabij de linkerrand.

    ![PowerApps-startpagina](./media/data-platform-cds-newentity-pq/sign-in.png)

1. Klik of tik in de lijst die verschijnt op **Gegevensintegratie** en klik of tik vervolgens op **Nieuw project** in de rechterbovenhoek van het venster.

1. Klik of tik in de lijst met gegevensbronnen op **OData**.

    ![De OAuth-connector kiezen](./media/data-platform-cds-newentity-pq/choose-odata.png)

1. Typ of plak onder **Verbindinginstellingen** deze URL en selecteer vervolgens **Volgende**:<br>
`http://services.odata.org/V4/Northwind/Northwind.svc/`

1. Schakel in de lijst met tabellen het selectievakje **Klanten** in en klik of tik vervolgens op **Volgende**.

    ![De tabel Klanten selecteren](./media/data-platform-cds-newentity-pq/select-table.png)

1. (optioneel) Pas het schema aan uw behoeften aan door te kiezen welke kolommen moeten worden opgenomen, de tabel op een of meer manieren te transformeren, een index of een voorwaardelijke kolom toe te voegen of andere wijzigingen aan te brengen.

1. Klik of tik in de rechterbenedenhoek op **Volgende**.

## <a name="specify-the-target-entity"></a>De doelentiteit opgeven
1. Selecteer onder **Instellingen laden** **De nieuwe entiteit laden**.

    ![Geef de naam van de nieuwe entiteit op.](./media/data-platform-cds-newentity-pq/new-entity-name.png)

    U kunt de nieuwe entiteit een andere naam of een weergavenaam geven, maar laat de standaardwaarden staan en volg deze zelfstudie precies.

1. Klik of tik in de lijst **Veld primaire naam** op **ContactName** en klik of tik vervolgens op **Volgende** in de rechterbenedenhoek.

    U kunt een ander veld voor primaire naam opgeven, een andere kolom in de brontabel toewijzen aan elk veld in de entiteit die u maakt, of beide. Als u deze zelfstudie exact wilt volgen, neemt u de standaardkolomtoewijzing over.

1. Als de **Laadstatus** **Voltooid** is, selecteert u **Gereed** in de rechterbenedenhoek.

1. Selecteer onder **Gegevens** (bij de linkerrand) **Entiteiten** om de lijst met entiteiten in uw database weer te geven.

    De entiteit **Klanten** die u op basis van een OData-feed hebt gemaakt, wordt weergegeven als een aangepaste entiteit.

    ![Lijst met standaardentiteiten en aangepaste entiteiten](./media/data-platform-cds-newentity-pq/entity-list.png)

> [!WARNING]
> Als u Power Query gebruikt om gegevens aan een bestaande entiteit toe te voegen, worden alle gegevens in die entiteit overschreven.

Als u **Laden naar bestaande entiteit** selecteert, kunt u een entiteit opgeven waarin u gegevens van de tabel **Klanten** toevoegt. U kunt bijvoorbeeld de gegevens toevoegen aan de entiteit **Account** waarmee Common Data Service wordt geleverd. Onder **Bronkolom** kunt u nader specificeren dat gegevens in de kolom **ContactName** van de tabel **Klanten** aan de kolom **Naam** in de entiteit **Accounts** moeten worden toegevoegd.

![Geef de naam van de nieuwe entiteit op.](./media/data-platform-cds-newentity-pq/existing-entity.png)

Wij zijn enthousiast over deze functionaliteit en zien uw feedback graag tegemoet. [Stuur ons uw suggesties en feedback](https://powerusers.microsoft.com/t5/PowerApps-Community/ct-p/PowerApps1) over deze functie.

Als er een [foutbericht over machtigingen](data-platform-cds-newentity-troubleshooting-mashup.md) wordt weergegeven, bespreek dit dan met uw beheerder.
