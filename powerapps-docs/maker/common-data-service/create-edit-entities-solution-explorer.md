---
title: Entiteiten maken en bewerken met behulp van Solution Explorer | MicrosoftDocs
description: Meer informatie over het maken van een entiteit met behulp van Solution Explorer
ms.custom: ''
ms.date: 05/30/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
author: Mattp123
ms.author: matp
manager: kvivek
ms.openlocfilehash: 48025088da85bf0685ba1a46efa4f3a989a20a58
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39674108"
---
# <a name="create-and-edit-entities-using-solution-explorer"></a>Entiteiten maken en bewerken met behulp van Solution Explorer

Met de PowerApps-portal kunt u eenvoudig een entiteit maken voor de meest voorkomende situaties. Hierin zijn echter niet alle mogelijkheden geïmplementeerd. Wanneer u moet voldoen aan de vereisten die zijn beschreven in [Create and edit entities in Common Data Service for Apps](create-edit-entities.md) (Entiteiten maken en bewerken in Common Data Service for Apps), kunt u entiteiten met Solution Explorer maken of bewerken.

## <a name="open-solution-explorer"></a>Solution Explorer openen

Een deel van de naam van een entiteit die u maakt, is het aanpassingsvoorvoegsel. Dit is ingesteld op basis van de uitgever van de oplossing waarin u werkt. Als u het aanpassingsvoorvoegsel belangrijk vindt, moet u ervoor zorgen dat u in een niet-beheerde oplossing werkt waarbij het aanpassingsvoorvoegsel het voorvoegsel is dat u voor deze entiteit wilt gebruiken. Meer informatie: [Het voorvoegsel van de oplossingsuitgever wijzigen](change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

## <a name="view-entities"></a>Entiteiten weergeven

Selecteer in de node **Onderdelen** van Solution Explorer de node **Entiteiten**.

![Entiteiten weergeven in Solution Explorer](media/view-entities-solution-explorer.png)

## <a name="create-an-entity"></a>Een entiteit maken

Wanneer [entiteiten worden weergegeven](#view-entities), selecteert u **Nieuw** om het formulier voor nieuwe entiteiten te openen.

![Formulier voor nieuwe entiteiten Solution Explorer](media/new-entity-form-solution-explorer.png)

Het formulier voor nieuwe entiteiten heeft twee tabbladen. Op het tabblad **Algemeen** staan opties voor entiteiten. Op het tabblad **Primair veld** staan opties voor de speciale tekstveldregel die elke entiteit heeft en die aangeeft welke tekst wordt getoond wanneer er een koppeling is om de entiteit in een opzoekveld te openen.

Zie de volgende onderwerpen voor meer informatie over elke sectie:
- [Het primaire veld configureren](#configure-the-primary-field)
- [Vereiste velden configureren](#configure-required-fields)

> [!NOTE]
> U kunt van de entiteit ook een aangepaste activiteit maken. Als u dat doet, veranderen enkele standaardwaarden. Meer informatie: [Een aangepaste activiteitentiteit maken](#create-custom-activity-entity)

Nadat u de vereiste opties voor de entiteit hebt ingesteld, klikt u op de ![opdracht Opslaan](media/save-entity-icon-solution-explorer.png) om de aangepaste entiteit te maken.

### <a name="configure-the-primary-field"></a>Het primaire veld configureren

Op het tabblad **Primair veld** kunt u de standaardwaarden voor het primaire veld accepteren. U hebt de volgende opties:

|Veld   |Beschrijving  |
|---------|---------|
|**Weergavenaam**|Voer de lokaliseerbare label in die voor dit veld wordt weergegeven in formulieren en lijsten. De standaardwaarde is **Naam**.|
|**Naam**|Stel de naam in die voor dit veld in het systeem wordt gebruikt. De standaardwaarde is `<customization prefix>_name`|
|**Maximumlengte**|Voer de maximumlengte in voor de veldwaarden. De standaardwaarde is 100.|

> [!NOTE]
> Deze opties zijn niet van toepassing als de entiteit een activiteitenentiteit is. Meer informatie: [Een aangepaste activiteitentiteit maken](#create-custom-activity-entity)

### <a name="configure-required-fields"></a>Vereiste velden configureren

Enkele opties op het tabblad **Algemeen** zijn vereist voordat u de entiteit kunt opslaan.

|Veld   |Beschrijving  |
|---------|---------|
|**Weergavenaam**|Dit is de enkelvoudige naam voor de entiteit die in de app wordt weergegeven.<br />Deze kan later worden gewijzigd.|
|**Naam in meervoud**|Dit is de meervoudige naam voor de entiteit die in de app wordt weergegeven.<br />Deze kan later worden gewijzigd.|
|**Naam**|Dit veld wordt vooraf ingevuld op basis van de weergavenaam die u invoert. Het omvat het aanpassingsvoorvoegsel van de oplossingsuitgever.|
|**Eigendom**|U kunt eigendom van gebruiker of team of eigendom van organisatie kiezen. Meer informatie: [Eigendom van entiteit](types-of-entities.md#entity-ownership)|

## <a name="edit-an-entity"></a>Een entiteit bewerken

Wanneer [entiteiten worden weergeven](#view-entities), selecteert u de entiteit die u wilt bewerken of gaat u door met het bewerken van een nieuwe entiteit die u zojuist hebt opgeslagen.

> [!NOTE]
> Voor standaardentiteiten of aangepaste entiteiten die deel uitmaken een beheerde oplossing zijn de wijzigingen die u kunt toepassen mogelijk beperkt. Als de optie niet beschikbaar is of is uitgeschakeld, kunt u de wijziging niet uitvoeren.

#### <a name="set-once-options"></a>Eenmalig in te stellen opties

De volgende opties kunnen één keer worden ingesteld en naderhand niet worden gewijzigd. Stel deze opties alleen in wanneer u ze nodig hebt.

<!-- 
Same data is presented in edit-entities.md
Both should point to this include
 -->
[!INCLUDE [cc_entity-set-once-options-table](../../includes/cc_entity-set-once-options-table.md)]

#### <a name="options-that-you-can-change"></a>Opties die u kunt wijzigen

De volgende eigenschappen kunnen op elk moment worden gewijzigd.

<!-- 
Same data is presented in edit-entities.md
Both should point to this include
 -->
[!INCLUDE [cc_entity-changeable-options-table](../../includes/cc_entity-changeable-options-table.md)]

U kunt ook de volgende wijzigingen aanbrengen:
- [Velden maken en bewerken voor Common Data Service for Apps](create-edit-fields.md)
- [Relaties tussen entiteiten maken en bewerken](create-edit-entity-relationships.md)
- [Formulieren maken en ontwerpen](../model-driven-apps/create-design-forms.md)
- [Een zakelijke processtroom maken om processen te standaardiseren](/flow/create-business-process-flow)

## <a name="delete-an-entity"></a>Een entiteit verwijderen

Als iemand met de beveiligingsrol Systeembeheerder kunt u aangepaste entiteiten verwijderen die geen deel uitmaken van een beheerde oplossing.  
  
> [!IMPORTANT]
>  Wanneer u een aangepaste entiteit verwijdert, worden de databasetabellen met gegevens voor die entiteit verwijderd en gaan alle gegevens die ze bevatten verloren. Alle gekoppelde records met een bovenliggende relatie met de aangepaste entiteit worden ook verwijderd. Zie [Create and edit relationships between entities](create-edit-entity-relationships.md) (Relaties tussen entiteiten maken en bewerken) voor meer informatie over bovenliggende relaties.  
  
> [!NOTE]
> De enige manier om gegevens uit een verwijderde entiteit te herstellen, is door de database te herstellen naar een punt waarop de entiteit nog niet was verwijderd. Meer informatie: [Backup and restore instances](/dynamics365/customer-engagement/admin/backup-restore-instances) (Back-up maken van instances en deze herstellen)

Wanneer [entiteiten worden weergeven](#view-entities), klikt u op de ![opdracht Verwijderen](media/delete.gif) in de werkbalk.

Gebruik de opdracht Verwijderen in de menubalk tijdens het bekijken van een entiteit.

![opdracht Verwijderen](media/delete-custom-entity-solution-explorer.png)

> [!WARNING]
> Als u een entiteit verwijdert die gegevens bevat, wordt alle gegevens verwijderd. Deze gegevens kunnen alleen worden teruggehaald door de back-up van de database te herstellen.

> [!NOTE]
> Als er entiteitsafhankelijkheden zijn, wordt de fout **Het onderdeel kan niet worden verwijderd** weergegeven met de koppeling **Details** die u kunt gebruiken om informatie te bekijken waarin wordt uitgelegd waarom de entiteit niet kan worden verwijderd. In de meeste gevallen is de oorzaak een afhankelijkheid die moet worden verwijderd. 
>
> Mogelijk zijn er meer afhankelijkheden die de verwijdering van een entiteit blokkeren. In dit foutbericht wordt mogelijk alleen de eerste weergeven. Zie [Entiteitsafhankelijkheden identificeren](#identify-entity-dependencies) voor een andere manier voor het detecteren van afhankelijkheden.



### <a name="identify-entity-dependencies"></a>Entiteitsafhankelijkheden identificeren

U kunt afhankelijkheden die verhinderen dat een entiteit wordt verwijderd, identificeren voordat u de entiteit probeert te verwijderen. 

1. Klik in Solution Explorer, met de entiteit geselecteerd, op **Afhankelijkheden weergeven** in de opdrachtbalk.

![opdracht Afhankelijkheden weergeven](media/entity-show-dependencies.png)

2. Schuif in het dialoogvenster dat wordt geopend de lijst aan de rechterkant om de kolom **Afhankelijkheidstype** weer te geven.

![Type gepubliceerde afhankelijkheid](media/published-entity-dependency.png)

**Gepubliceerde** afhankelijkheden blokkeren het verwijderen van een entiteit. **Interne** afhankelijkheden moeten worden opgelost door het systeem.  

3. Verwijder de gepubliceerde afhankelijkheden. De entiteit moet nu kunnen worden verwijderd.

 > [!NOTE]
 > Een veelvoorkomende afhankelijkheid is dat een ander entiteitsformulier een opzoekveld bevat voor de entiteit die u wilt verwijderen. Als u het opzoekveld verwijdert uit het formulier, wordt de afhankelijkheid opgelost.

## <a name="create-custom-activity-entity"></a>Aangepaste activiteitenentiteit maken

Als u van de entiteit een activiteitenentiteit wilt maken, volgt u dezelfde stappen die in dit onderwerp worden beschreven, maar selecteert u **Definiëren als een activiteitenentiteit**.

![Definiëren als activiteitenentiteit](media/create-activity-entity-solution-explorer.png)

Een activiteitenentiteit is een speciaal soort entiteit waarmee acties worden bijgehouden waarvoor een vermelding kan worden gemaakt in een agenda. Meer informatie: [Activiteitenentiteiten](types-of-entities.md#activity-entities).

Sommige entiteitseigenschappen zijn niet compatibel wanneer u deze optie instelt. Een activiteitenentiteit moet voldoen aan standaardgedrag dat alle activiteitenentiteiten gebruiken.

Het primaire veld **Naam** en **Weergavenaam** worden ingesteld op **Onderwerp**. U kunt dit niet wijzigen.

De volgende opties zijn standaard ingesteld en kunnen niet worden gewijzigd:

 - **Feedback**
 - **Opmerkingen (inclusief bijlagen)**
 - **Verbindingen**
 - **Wachtrijen**
 - **Offlinefunctionaliteit voor Dynamics 365 voor Outlook**

De volgende opties kunnen niet worden ingesteld:

- **Gebieden waarin deze entiteit wordt weergeven**
- **Activiteiten**
- **E-mail verzenden**
- **Afdruk samenvoegen**
- **Controle van enkele record**
- **Controle van meerdere records**

## <a name="create-a-virtual-entity"></a>Een virtuele entiteit maken

Sommige opties worden alleen gebruikt bij het maken van een virtuele entiteit.

|Optie   |Beschrijving  |
|---------|---------|
|**Virtuele entiteit**|Dit geeft aan of de entiteit een virtuele entiteit is.|
|**Gegevensbron**|De gegevensbron voor de entiteit.|

Meer informatie: [Virtuele entiteiten maken en bewerken die gegevens van een externe gegevensbron bevatten](create-edit-virtual-entities.md)

### <a name="see-also"></a>Zie ook
[Entiteiten maken en bewerken in Common Data Service for Apps](create-edit-entities.md)<br />
[Zelfstudie: Een aangepaste entiteit met componenten in PowerApps maken](/powerapps/maker/common-data-service/create-custom-entity)<br />
[Een oplossing maken](create-solution.md)