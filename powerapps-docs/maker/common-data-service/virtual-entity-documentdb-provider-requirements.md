---
title: 'Preview-functie: De gegevensprovider voor Azure Cosmos DB voor SQL-API gebruiken met Common Data Service voor Apps | MicrosoftDocs'
description: Lees hoe u de Azure Cosmos DB for SQL API-gegevensprovider kunt configureren voor gebruik met virtuele entiteiten.
keywords: SQL-API
ms.date: 06/27/2018
ms.service: crm-online
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.assetid: d0031ffc-8754-4a12-b8c1-e08edc49ff73
author: Mattp123
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
caps.latest.revision: null
topic-status: Drafting
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="preview-feature-azure-cosmos-db-sql-api-data-provider-requirements"></a>Preview-functie: vereisten voor Azure Cosmos DB for SQL API-gegevensprovider

In dit onderwerp worden de vereisten voor de gegevensprovider voor Azure Cosmos DB voor SQL-API beschreven en wordt aangegeven hoe u aanbevolen werkwijzen implementeert wanneer u de gegevensprovider voor Azure Cosmos DB voor SQL-API met virtuele entiteiten gebruikt. 

> [!IMPORTANT]
> - [!INCLUDE [cc-preview-features-definition](../../includes/cc-preview-features-definition.md)]
> - [!INCLUDE [cc-preview-features-definition](../../includes/cc-preview-features-expect-changes.md)]
> - [!INCLUDE [cc-preview-features-definition](../../includes/cc-preview-features-no-ms-support.md)]


## <a name="what-is-azure-cosmos-db"></a>Wat is Azure Cosmos DB?

Azure Cosmos DB is het wereldwijd gedistribueerde multi-model databaseservice van Microsoft voor essentiële toepassingen. De service biedt uitgebreide en vertrouwde SQL-querymogelijkheden met consistent lage wachttijden voor JSON-gegevens zonder schema. Meer informatie: [Inleiding bij Azure Cosmos DB: SQL API](https://docs.microsoft.com/azure/cosmos-db/sql-api-introduction)

## <a name="requirements"></a>Vereisten

- Azure-abonnement met Azure Cosmos DB.
- Een Azure Cosmos DB SQL API-verzameling.
- Het Azure Cosmos DB-databasetype moet SQL zijn. 

## <a name="data-type-mapping"></a>Gegevenstypetoewijzing

Stel dat u een Azure Cosmos DB-document hebt in een verzameling *Orders* met de volgende JSON-structuur.

![Voorbeelddocument van JSON voor SQL API.](media/documentdbexample.png)

Deze tabel bevat de gegevenstypetoewijzingen voor het SQL API-document in de verzameling *Orders* met Common Data Service voor Apps.

|SQL API-gegevens|CDS voor Apps|
|--|--|
|`id`|Primaire sleutel|
|`name`|Eén tekstregel|
|`quantity`|Geheel getal|
|`orderid`|Enkele regel tekst|
|`ordertype`|Optieset|
|`amount`|Decimaal of valuta|
|`delivered`|Twee opties|
|`datetimeoffset`|Datum en tijd|

> [!NOTE]
> - Kenmerken met een onderstrepingsteken (_) als voorvoegsel zijn gegenereerd door de SQL API.
> - Kenmerken die als optioneel zijn geconfigureerd in het SQL API-document en in CDS voor Apps worden toegewezen als **Onderneming vereist** veroorzaken een fout tijdens het uitvoeren.
> - Kenmerkwaarden voor id moeten guids zijn.
> - Raadpleeg voor meer informatie over het gebruiken van datums in de SQL API [Werken met datums in Azure Cosmos DB](https://azure.microsoft.com/blog/working-with-dates-in-azure-documentdb-4/).

## <a name="supported-sql-query-filtering"></a>Ondersteunde filterfuncties voor SQL-query's

Filterfuncties voor SQL-query's ondersteunen de volgende operators. 

- Vergelijkingsoperators:`<`,`>`,`<=`, `>=`,`!=`
- Logische operators: `and`, `or` 
- Set-operators: `in`, `not in`
- Tekenreeksoperators: `like`, `contains`, b`egins with`, `ends with`

> [!NOTE]
> Het gebruik van zoals-operator wordt vertaald naar de equivalente operators `contains`/`begins with`/`ends with`. SQL API ondersteunt geen patroonargumenten zoals beschreven in het onderwerp [Like (Transact-SQL)](/sql/t-sql/language-elements/like-transact-sql). De gegevensprovider voor Azure Cosmos DB voor SQL-API kan het speciale geval `Like('[aA]%')` vertalen naar `BeginsWith('a')` OF `BeginsWith('A')`. Let op dat de tekenreeksvergelijking in SQL-API hoofdlettergevoelig is.

## <a name="add-a-data-source-using-the-azure-cosmos-db-for-sql-api-data-provider"></a>Een gegevensbron toevoegen met de Azure Cosmos DB for SQL API-gegevensprovider

1. Ga naar [AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.documentdb_data_provider?tab=Overview), selecteer **NU OPHALEN** en volg de aanwijzingen om de toepassing toe te voegen aan uw omgeving met v9x of een later exemplaar.
2. Als de oplossing is geïnstalleerd, meldt u zich aan bij de omgeving en gaat u naar **Instellingen** > **Beheer** > **Virtuele bronnen voor entiteitsgegevens**.
3. Selecteer op de werkbalk Acties de optie **NIEUW**, selecteer in het dialoogvenster **Gegevensprovider selecteren** de optie **Azure Cosmos DB for SQL API-gegevensprovider** en selecteer vervolgens **OK**.
![Selecteer de Azure Cosmos DB for SQL API-gegevensprovider.](media/createdatasource.png)
1. Vul de volgende informatie in en selecteer vervolgens **OPSLAAN EN SLUITEN**.

    |Veld|Beschrijving|
    |--|--|
    |**Name**|Typ een naam die de gegevensbron beschrijft.|
    |**Verzamelingsnaam**|De id van de Azure Cosmos DB-databaseverzameling met de gegevens die u wilt weergeven in een virtuele entiteit.  |
    |**Autorisatiesleutel**|De primaire of secundaire sleutel voor de Azure Cosmos DB-account. U vindt de sleutel van de Azure-beheerportal onder de instelling **Sleutels** in uw Azure Cosmos DB-account.|
    |**URI**|De URI van de resourcegroep waar de Azure Cosmos DB-verzameling zich bevindt. De URI wordt op vergelijkbare wijze gevormd als `https://contoso/documents.azure.com:443`. U vindt de URI van de Azure-beheerportal onder de instelling **Sleutels** voor de Azure Cosmos DB-account. |
    |**Time-out in seconden**|Voer het aantal seconden in dat moet worden gewacht op een respons van de Azure Cosmos DB-service alvorens een verzoek om time-out van gegevens wordt gedaan. Vul bijvoorbeeld 30 in om maximaal dertig seconden te wachten totdat een time-out plaatsvindt. De standaardwaarde is 120 seconden.|

    > [!div class="mx-imgBorder"] 
    > ![Maak de gegevensbron met de SQL API-gegevensprovider.](media/cosmosdb-datasource.png)

## <a name="best-practices-and-limitations"></a>Aanbevolen methoden en beperkingen

- Let op het volgende als u Azure Cosmos DB als gegevensbron gebruikt:
   - Elke Azure Cosmos DB-gegevensbron kan slechts aan één virtuele entiteit zijn gekoppeld.
   - U kunt meerdere gegevensbronnen verbinden met dezelfde verzameling in Azure Cosmos DB.
- U kunt de gegevens in een verzameling niet opdelen per entiteit.
- Azure Cosmos DB-databases vereisen geen schema, maar de gegevens in Azure Cosmos DB moeten zijn gestructureerd met een voorspelbaar schema. 
- Hoewel de gegevensprovider voor Azure Cosmos DB voor SQL-API de vertaling van query's met projectie-, filter- en sorteeroperators implementeert, worden koppelingsbewerkingen niet ondersteund.
- U kunt slechts op één kolom filteren met de SQL-API.

## <a name="see-also"></a>Zie ook

[Virtuele entiteiten maken en bewerken die gegevens uit een externe gegevensbron bevatten](create-edit-virtual-entities.md)
