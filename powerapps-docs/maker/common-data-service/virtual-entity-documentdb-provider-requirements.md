---
title: 'Preview-functie: de Azure Cosmos DB voor SQL-API-gegevensprovider gebruiken met Common Data Service For Apps | MicrosoftDocs'
description: Informatie over hoe u de Azure Cosmos DB voor SQL-API-gegevensprovider configureert voor gebruik met virtuele entiteiten.
keywords: SQL-API
ms.date: 06/27/2018
ms.service: crm-online
ms.custom: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: d0031ffc-8754-4a12-b8c1-e08edc49ff73
author: Mattp123
ms.author: matp
manager: kvivek
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
caps.latest.revision: ''
topic-status: Drafting
ms.openlocfilehash: fa45376dff85205a0dfbf28334c678293528d00e
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39680516"
---
# <a name="preview-feature-azure-cosmos-db-sql-api-data-provider-requirements"></a>Preview-functie: vereisten voor Azure Cosmos DB SQL-API-gegevensprovider

In dit onderwerp worden de vereisten beschreven voor de Azure Cosmos DB voor SQL-API-gegevensprovider en hoe u aanbevolen procedures configureert wanneer u de Azure Cosmos DB voor SQL-API-gegevensprovider met virtuele entiteiten gebruikt. 

> [!IMPORTANT]
> - [!INCLUDE [cc-preview-features-definition](../../includes/cc-preview-features-definition.md)]
> - [!INCLUDE [cc-preview-features-definition](../../includes/cc-preview-features-expect-changes.md)]
> - [!INCLUDE [cc-preview-features-definition](../../includes/cc-preview-features-no-ms-support.md)]


## <a name="what-is-azure-cosmos-db"></a>Wat is Azure Cosmos DB?

Azure Cosmos DB is de wereldwijd gedistribueerde, multimodeldatabaseservice van Microsoft voor bedrijfskritische apps. Het biedt rijke en vertrouwde SQL-querymogelijkheden met consistente lage latenties voor JSON-gegevens zonder schema. Meer informatie [Inleiding tot Azure Cosmos DB: SQL-API](https://docs.microsoft.com/azure/cosmos-db/sql-api-introduction)

## <a name="requirements"></a>Vereisten

- Azure-abonnement met Azure Cosmos DB.
- Een Azure Cosmos DB SQL-API-verzameling.
- Het Azure Cosmos DB-databasetype moet SQL zijn. 

## <a name="data-type-mapping"></a>Toewijzing van gegevenstype

Stel dat u een Azure Cosmos DB-document hebt in een verzameling met de naam *Bestellingen* die de volgende JSON-structuur heeft.

![Voorbeeld van JSON voor SQL-API-document.](media/documentdbexample.png)

Deze tabel geeft de gegevenstypetoewijzingen aan voor het SQL-API-document in de verzameling *Bestellingen* met Common Data Service for Apps.

|SQL-API|CDS for Apps|
|--|--|
|`id`|Primaire sleutel|
|`name`|Eén tekstregel|
|`quantity`|Geheel getal|
|`orderid`|Eén tekstregel|
|`ordertype`|Optieset|
|`amount`|Decimaal getal of valuta|
|`delivered`|Twee opties|
|`datetimeoffset`|Datum en tijd|

> [!NOTE]
> - Kenmerken met het voorvoegsel onderstrepingsteken (_) worden gegenereerd door de SQL-API.
> - Kenmerken die zijn geconfigureerd als optioneel in het SQL-API-document en zijn toegewezen in CDS voor apps als **Onderneming vereist** veroorzaken een runtime-fout.
> - ID-kenmerkwaarden moeten GUID's zijn.
> - Zie voor meer informatie over het gebruik van datums in de SQL-API [Werken met datums in Azure Cosmos DB](https://azure.microsoft.com/blog/working-with-dates-in-azure-documentdb-4/).

## <a name="supported-sql-query-filtering"></a>Ondersteunde SQL-queryfilters

SQL-queryfilters ondersteunen de volgende operators. 

- Vergelijkingsoperators:`<`,`>`,`<=`, `>=`,`!=`
- Logische operators: `and`, `or` 
- Set-operators: `in`, `not in`
- Tekenreeksoperators: `like`, `contains`, b`egins with`, `ends with`

> [!NOTE]
> Gebruik van de like-operator wordt vertaald naar de gelijkwaardige `contains`/`begins with`/`ends with` operators. De SQL-API biedt geen ondersteuning voor patroonargumenten zoals beschreven in het onderwerp [Like(Transact-SQL)](/sql/t-sql/language-elements/like-transact-sql). De Azure Cosmos DB voor SQL-API-gegevensprovider kan de enkele bijzondere bewerking `Like('[aA]%')` vertalen naar `BeginsWith('a')` OR `BeginsWith('A')`. Merk op dat de tekenreeksvergelijking in de SQL-API hoofdlettergevoelig is.

## <a name="add-a-data-source-using-the-azure-cosmos-db-for-sql-api-data-provider"></a>Een gegevensbron toevoegen met behulp van de Azure Cosmos DB voor SQL-API-gegevensprovider

1. Ga naar [AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.documentdb_data_provider?tab=Overview), selecteer **NU DOWNLOADEN** en volg de instructies om de app toe te voegen aan uw omgeving met behulp van v9x of hoger.
2. Nadat de oplossing is geïnstalleerd, meldt u zich aan bij de omgeving en gaat u naar **Instellingen** > **Beheer** > **Gegevensbronnen voor virtuele entiteit**.
3. Selecteer **NIEUW** op de werkbalk Acties en klik in het dialoogvenster **Gegevensprovider selecteren** op de optie **Azure Cosmos DB voor SQL-API-gegevensprovider** en selecteer vervolgens **OK** .
![Selecteer de Azure Cosmos DB voor SQL-API-gegevensprovider.](media/createdatasource.png)
1. Voer de volgende gegevens in en selecteer vervolgens **OPSLAAN EN SLUITEN**.

    |Veld|Beschrijving|
    |--|--|
    |**Naam**|Typ een naam die de gegevensbron beschrijft.|
    |**Verzamelingnaam**|De id van de Azure Cosmos DB-databaseverzameling met de gegevens die boven moeten komen in een virtuele entiteit.  |
    |**Autorisatiesleutel**|De primaire of secundaire sleutel voor het Azure Cosmos DB-account. U vindt de sleutel van de Azure-beheerportal onder de instelling **Sleutels** onder uw Azure Cosmos DB-account.|
    |**Uri**|De URI van de resourcegroep waar de Azure Cosmos DB-verzameling zich bevindt. De URI heeft een indeling die vergelijkbaar is met `https://contoso/documents.azure.com:443`. U vindt de URI van de Azure-beheerportal onder de instelling **Sleutels** voor uw Azure Cosmos DB-account. |
    |**Time-out in seconden**|Voer het aantal seconden in dat moet worden gewacht op een reactie van de Azure Cosmos DB-service voordat een time-out optreedt voor de aanvraag voor gegevens. Voer bijvoorbeeld 30 in om maximaal dertig seconden te wachten voordat een time-out optreedt. De standaardtime-out is 120 seconden.|

    ![Maak de gegevensbron met behulp van de SQL-API-gegevensprovider.](media/cosmosdb-datasource.png)

## <a name="best-practices-and-limitations"></a>Aanbevolen procedures en beperkingen

- Let op het volgende wanneer u Azure Cosmos DB als gegevensbron gebruikt:
   - Elke Azure Cosmos DB-gegevensbron kan alleen worden gekoppeld aan één enkele virtuele entiteit.
   - U kunt meerdere gegevensbronnen verbinden aan dezelfde verzameling in de Azure Cosmos DB.
- U kunt de gegevens in een verzameling niet segmenteren op entiteit.
- Voor Azure Cosmos DB-databases is geen schema vereist, maar de gegevens in de Azure Cosmos DB moeten wel worden opgebouwd met behulp van een voorspelbaar schema. 
- Hoewel de Azure Cosmos DB voor SQL-API-gegevensprovider query-vertaling van operators voor projectie, filteren en sorteren implementeert, ondersteunt deze geen join-bewerkingen.
- Met SQL-API kunt u alleen filteren op één kolom.

## <a name="see-also"></a>Zie ook

[Virtuele entiteiten die gegevens uit een externe gegevensbron bevatten, maken en bewerken](create-edit-virtual-entities.md)
