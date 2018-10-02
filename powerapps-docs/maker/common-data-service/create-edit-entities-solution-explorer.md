---
title: Entiteiten maken en bewerken met de oplossingenverkenner | MicrosoftDocs
description: Meer informatie over het maken van een entiteit met de oplossingenverkenner
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="create-and-edit-entities-using-solution-explorer"></a>Entiteiten maken met de oplossingenverkenner

U kunt een entiteit eenvoudig maken met de PowerApps-portal voor de meest voorkomende situaties, maar niet alle mogelijkheden worden hier geïmplementeerd. Als u moet voldoen aan de vereisten die worden beschreven in [Entiteiten maken en bewerken in Common Data Service voor Apps](create-edit-entities.md), kunt u dat bereiken door entiteiten te maken of te bewerken met de oplossingenverkenner.

## <a name="open-solution-explorer"></a>Open de oplossingenverkenner.

Een deel van de naam van een entiteit die u maakt, is het aanpassingsvoorvoegsel. Dit is ingesteld op basis van de oplossingsuitgever voor de oplossing waarin u werkt. Als het aanpassingsvoorvoegsel voor u van belang is, zorg er dan voor dat u werkt in een onbeheerde oplossing waarvoor het aanpassingsvoorvoegsel is wat u voor deze entiteit wilt. Meer informatie: [Het voorvoegsel voor de oplossingsuitgever wijzigen](change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

## <a name="view-entities"></a>Entiteiten weergeven

Selecteer in het knooppunt **Onderdelen** van de oplossingenverkenner het knooppunt **Entiteiten**.

![Entiteiten weergeven in oplossingenverkenner](media/view-entities-solution-explorer.png)

## <a name="create-an-entity"></a>Een entiteit maken

Selecteer tijdens het [weergeven van entiteiten](#view-entities) **Nieuw** om het nieuwe entiteitsformulier te openen.

![Nieuw entiteitsformulier in oplossingenverkenner](media/new-entity-form-solution-explorer.png)

Het nieuwe entiteitsformulier heeft twee tabbladen. Het tabblad **Algemeen** is voor entiteitsopties. Het tabblad **Primair veld** is voor opties over het speciale tekstveld met één regel dat elke entiteit heeft waarmee de tekst wordt gedefinieerd die wordt weergegeven wanneer er een koppeling is om de entiteit in een opzoekveld te openen.

Zie voor informatie over elke sectie het volgende:
- [Het primaire veld configureren](#configure-the-primary-field)
- [Vereiste velden configureren](#configure-required-fields)

> [!NOTE]
> U kunt van de entiteit ook een aangepaste activiteit maken. Met deze keuze wordt een aantal standaardoptiewaarden gewijzigd. Meer informatie: [Een aangepaste entiteit voor een activiteit maken](#create-custom-activity-entity)

Nadat u de vereiste opties voor de entiteit hebt ingesteld, klikt u op ![De opdracht Opslaan](media/save-entity-icon-solution-explorer.png) om de aangepaste entiteit te maken.

### <a name="configure-the-primary-field"></a>Het primaire veld configureren

Typ op het tabblad **Primair veld** kunt u gewoonlijk de standaardwaarden voor het primaire veld accepteren, maar u hebt de volgende opties:

|Veld   |Beschrijving  |
|---------|---------|
|**Weergavenaam**|Voer het lokaliseerbare label in dat voor dit veld in formulieren en lijsten wordt weergegeven. De standaardwaarde is **Naam**.|
|**Name**|Stel de naam in die in het systeem wordt gebruikt voor dit veld. De standaardwaarde is `<customization prefix>_name`.|
|**Maximale lengte**|Voer de maximale lengte voor de veldwaarden in. De standaard is 100.|

> [!NOTE]
> Deze opties gelden niet als de entiteit een activiteitsentiteit is. Meer informatie:  [Een aangepaste entiteit voor een activiteit maken](#create-custom-activity-entity)

### <a name="configure-required-fields"></a>Vereiste velden configureren

Op het tabblad **Algemeen** zijn enkele opties vereist voordat u de entiteit kunt opslaan.

|Veld   |Beschrijving  |
|---------|---------|
|**Weergavenaam**|Dit is de enkelvoudige naam voor de entiteit die in de app wordt weergegeven.<br />Dit kan later worden gewijzigd.|
|**Meervoudsnaam**|Dit is de meervoudige naam voor de entiteit die in de app wordt weergegeven.<br />Dit kan later worden gewijzigd.|
|**Name**|Dit veld wordt vooringevuld op basis van de weergavenaam die u invoert. Het bevat het aanpassingsvoorvoegsel van de oplossingsuitgever.|
|**Eigendom**|U kunt kiezen tussen enerzijds eigendom van een gebruiker of een team, of anderzijds eigendom van de organisatie. Meer informatie: [Eigendom van entiteit](types-of-entities.md#entity-ownership)|

## <a name="edit-an-entity"></a>Een entiteit bewerken

Selecteer tijdens het [weergeven van entiteiten](#view-entities) de entiteit die u wilt bewerken of ga verder met het bewerken van een nieuwe entiteit die u net hebt opgeslagen.

> [!NOTE]
> Standaardentiteiten of aangepaste entiteiten die deel uitmaken van een beheerde oplossing kunnen beperkingen hebben voor wijzigingen die u kunt toepassen. Als de optie niet beschikbaar is of is uitgeschakeld, mag u de wijziging niet aanbrengen.

#### <a name="set-once-options"></a>Opties eenmaal instellen

De volgende opties kunnen één keer worden ingesteld en kunnen niet worden gewijzigd nadat u deze hebt ingesteld. Stel deze opties alleen in wanneer u ze nodig hebt.

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
- [Velden maken en bewerken voor Common Data Service voor Apps](create-edit-fields.md)
- [Relaties tussen entiteiten maken en bewerken](create-edit-entity-relationships.md)
- [Formulieren maken en ontwerpen](../model-driven-apps/create-design-forms.md)
- [Een bedrijfsprocesstroom maken om processen te standaardiseren](/flow/create-business-process-flow)

## <a name="delete-an-entity"></a>Een entiteit verwijderen

Als iemand met de beveiligingsrol systeembeheerder kunt u aangepaste entiteiten verwijderen die geen onderdeel van een beheerde oplossing.  
  
> [!IMPORTANT]
>  Als u een aangepaste entiteit verwijdert, dan worden de databasetabellen die gegevens voor deze entiteit opslaan verwijderd en alle gegevens die ze bevatten zullen verdwijnen. Gekoppelde records die een bovenliggende relatie hebben met de aangepaste entiteit worden ook verwijderd. Zie voor meer informatie over bovenliggende relaties raadpleegt u [Relaties tussen entiteiten maken en bewerken](create-edit-entity-relationships.md).  
  
> [!NOTE]
> De enige wijze om gegevens te herstellen uit een entiteit die is verwijderd, is het herstellen database vanuit een punt voordat de entiteit werd verwijderd. Meer informatie: [Back-up van exemplaren maken en deze terugzetten](/dynamics365/customer-engagement/admin/backup-restore-instances)

Klik tijdens het [weergeven van entiteiten](#view-entities) op de opdracht ![Verwijderen](media/delete.gif) op de werkbalk.

Gebruik tijdens het weergeven van een entiteit de opdracht Verwijderen op de menubalk.

![Opdracht Verwijderen](media/delete-custom-entity-solution-explorer.png)

> [!WARNING]
> Als een entiteit met gegevens wordt verwijderd, worden alle gegevens verwijderd. Deze gegevens kunnen alleen door de back-up van de database worden opgehaald.

> [!NOTE]
> Als er entiteitafhankelijkheden zijn, ontvangt u een **Het onderdeel kan niet worden verwijderd**-foutbericht met de koppeling **Details** die u kunt gebruiken om informatie te verkrijgen over de reden waarom de entiteit niet kan worden verwijderd. In de meeste gevallen wordt dit veroorzaakt door een afhankelijkheid die moet worden verwijderd. 
>
> Er kunnen meerdere afhankelijkheden zijn die de verwijdering van een entiteit blokkeren. Met dit foutbericht wordt mogelijk alleen de eerste weergegeven. Zie voor een alternatieve manier om afhankelijkheden te detecteren [Entiteitafhankelijkheden identificeren](#identify-entity-dependencies)



### <a name="identify-entity-dependencies"></a>Entiteitafhankelijkheden identificeren

U kunt afhankelijkheden identificeren die voorkomen dat een entiteit wordt verwijderd voordat u deze probeert te verwijderen. 

1. Klik in de oplossingenverkenner terwijl de entiteit is geselecteerd op **Afhankelijkheden weergeven** op de opdrachtbalk.

![Opdracht Afhankelijkheden weergeven](media/entity-show-dependencies.png)

2. Schuif in het dialoogvenstervenster dat wordt geopend in de lijst naar rechts om de kolom **Afhankelijkheidstype** weer te geven.

![Gepubliceerd afhankelijkheidstype](media/published-entity-dependency.png)

**Gepubliceerd**e afhankelijkheden zorgen ervoor dat een entiteit niet wordt verwijderd. **Intern**e afhankelijkheden moeten door het systeem worden opgelost.  

3. Verwijder deze gepubliceerde afhankelijkheden. U moet de entiteit kan kunnen verwijderen.

 > [!NOTE]
 > Een zeer vaak voorkomende afhankelijkheid is dat een ander entiteitsformulier een opzoekveld heeft voor de entiteit die u verwijdert. Als u het opzoekveld uit het formulier verwijdert, wordt de afhankelijkheid opgelost.

## <a name="create-custom-activity-entity"></a>Een aangepaste entiteit voor een activiteit maken

Als u de entiteit als een activiteitsentiteit wilt maken, gebruikt u de stappen die in dit onderwerp zijn beschreven, maar selecteer **Definiëren als een activiteitsentiteit**.

![Definiëren als activiteitenentiteit](media/create-activity-entity-solution-explorer.png)

Een activiteitsentiteit is een speciaal type entiteit waarmee acties worden bijgehouden waarvoor een vermelding in een agenda kan worden gemaakt. Meer informatie: [Activiteitsentiteiten](types-of-entities.md#activity-entities).

Als u deze optie instelt, zijn sommige entiteitseigenschappen niet compatibel. Een activiteitsentiteit moet voldoen aan standaardgedragingen die alle activiteitsentiteiten gebruiken.

**Naam** en **Weergavenaam** van het primaire veld worden ingesteld op **Onderwerp** en kunt u dit niet wijzigen.

De volgende opties zijn standaard ingesteld en kunnen niet worden gewijzigd:

 - **Feedback**
 - **Notities (inclusief bijlagen)**
 - **Verbindingen**
 - **Wachtrijen**
 - **Offlinemogelijkheid voor Dynamics 365 voor Outlook**

De volgende opties kunnen niet worden ingesteld:

- **Gebieden waarin deze entiteit wordt weergegeven**
- **Activiteiten**
- **E-mail verzenden**
- **Afdruk samenvoegen**
- **Controle van één record**
- **Controle van meerdere records**

## <a name="create-a-virtual-entity"></a>Een virtuele entiteit maken

Sommige opties worden alleen gebruikt bij het maken van een virtuele entiteit.

|Optie   |Beschrijving  |
|---------|---------|
|**Virtuele entiteit**|Of de entiteit een virtuele entiteit is.|
|**Gegevensbron**|De gegevensbron voor de entiteit.|

Meer informatie: [Virtuele entiteiten maken en bewerken die gegevens uit een externe gegevensbron bevatten](create-edit-virtual-entities.md)

### <a name="see-also"></a>Zie ook
[Entiteiten maken en bewerken in Common Data Service voor Apps](create-edit-entities.md)<br />
[Zelfstudie: een aangepaste entiteit maken die onderdelen heeft in PowerApps](/powerapps/maker/common-data-service/create-custom-entity)<br />
[Een oplossing maken](create-solution.md)
