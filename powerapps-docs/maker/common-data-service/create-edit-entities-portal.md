---
title: Entiteiten maken en bewerken met de PowerApps-portal | MicrosoftDocs
description: Meer informatie over het maken en bewerken van entiteiten met de PowerApps-portal
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
ms.assetid: fa04f99d-a5f9-48cb-8bfb-f0f50718ccee
caps.latest.revision: 41
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="create-and-edit-entities-using-powerapps-portal"></a>Entiteiten maken en bewerken met de PowerApps-portal

De [PowerApps-portal](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) biedt een eenvoudige manier om entiteiten te maken en te bewerken voor Common Data Service voor Apps.

Met de portal wordt de configuratie van de meest gebruikte opties ingeschakeld, maar bepaalde opties kunnen alleen worden ingesteld met oplossingenverkenner. Zie voor meer informatie: 
- [Entiteiten maken en bewerken in Common Data Service voor Apps](create-edit-entities.md)
- [Entiteiten maken met de oplossingenverkenner](create-edit-entities-solution-explorer.md)

## <a name="view-entities"></a>Entiteiten weergeven

1. Selecteer via de [PowerApps-portal](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) de ontwerpmodus **Modelgestuurd** of **Canvas**.
2. Selecteer **Gegevens** > **Entiteiten**

![Entiteiten weergeven](media/view-entities-portal.png)

U kunt de entiteiten die u ziet filteren met de volgende weergaven in een lijst: 

![Entiteitsweergaven](media/entity-views-portal.png)

 |weergave|Beschrijving|
 |--|--|
 |**Alle**| Hiermee worden alle entiteiten weergegeven|
 |**Aangepast**|Hiermee worden alleen aangepaste entiteiten weergegeven|
 |**Standaard**|Hiermee worden alleen de standaardentiteiten weergegeven |

U kunt ook **Groeperen** selecteren om entiteiten te groeperen door de erop toegepaste **Codes**.

## <a name="create-an-entity"></a>Een entiteit maken

Selecteer tijdens het [weergeven van entiteiten](#view-entities) op de menubalk op **Nieuwe entiteit**. Hiermee wordt het deelvenster Nieuwe entiteit geopend.

![Deelvenster Nieuwe entiteit](media/new-entity-panel.png)

Voer gegevens voor de volgende velden in

|Veld|Beschrijving|
|--|--|
|**Weergavenaam**|Dit is de enkelvoudige naam voor de entiteit die in de app wordt weergegeven. Dit kan later worden gewijzigd.|
|**Meervoudsweergavenaam**|Dit is de meervoudige naam voor de entiteit die in de app wordt weergegeven. Dit kan later worden gewijzigd.|
|**Name**|Dit veld wordt vooraf ingevuld op basis van de **Weergavenaam** die u invoert. Het bevat het aanpassingsvoorvoegsel voor de CDS-oplossingsuitgever. U kunt dit niet wijzigen nadat de entiteit is opgeslagen.|
|**Beschrijving**|Geef een begrijpelijke beschrijving van de doelstelling van de entiteit op.|

Selecteer **Volgende** om door te gaan. Hiermee wordt het deelvenster **Nieuwe entiteit** gesloten en wordt de lijst met velden weergegeven.

Het veld **Primaire naam** is het enige veld dat op dit punt zichtbaar is. Selecteer het veld **Primaire naam** om te bewerken als u de **Weergavenaam** of **Naam** van het veld wilt wijzigen. De standaardwaarden worden hieronder weergegeven:

![Deelvenster Primaire naam](media/primary-name-panel.png)

Selecteer **Entiteit opslaan** om de entiteit te maken of door te gaan met bewerken van de entiteit.

![Entiteit opslaan](media/save-entity-portal.png)

## <a name="edit-an-entity"></a>Een entiteit bewerken

Selecteer tijdens het [weergeven van entiteiten](#view-entities) de entiteit die u wilt bewerken.

Selecteer Instellingen in het menu als u de **Weergavenaam**, **Meervoudsweergavenaam** of **Beschrijving** voor de entiteit wilt bewerken.

![Entiteitsinstellingen](media/entity-settings-portal.png)

Maak een selectie voor andere items uit de tabbladen.

### <a name="fields"></a>Velden

Zie [Velden maken en bewerken](create-edit-fields.md)

### <a name="relationships"></a>Relaties

Zie [Relaties tussen entiteiten maken en bewerken](create-edit-entity-relationships.md)

### <a name="business-rules"></a>Bedrijfsregels

Zie [Bedrijfsregels en aanbevelingen maken om logica in een formulier toe te passen](../model-driven-apps/create-business-rules-recommendations-apply-logic-form.md)

### <a name="views"></a>Weergaven

Zie [Een weergave maken of bewerken](../model-driven-apps/create-edit-views.md)

### <a name="forms"></a>Formulieren

Zie [Formulieren maken en ontwerpen](../model-driven-apps/create-design-forms.md)

### <a name="dashboards"></a>Dashboards

Zie [Dashboards maken of bewerken](../model-driven-apps/create-edit-dashboards.md)

### <a name="charts"></a>Grafieken

Zie [Een systeemgrafiek maken](../model-driven-apps/create-edit-system-chart.md)

### <a name="keys"></a>Sleutels

Zie [Alternatieve sleutels definiëren om te verwijzen naar records](define-alternate-keys-reference-records.md)

### <a name="data"></a>Gegevens

Geef de gegevens in de entiteit weer.
Gebruik het menu **Weergave selecteren** om een keuze te maken uit beschikbare weergaven voor de entiteit of alle velden weer te geven.

![Weergave selecteren](media/entity-data-select-view.png)

Gebruik de opdrachten **Volgende pagina** en **Vorige pagina** onder aan het formulier om meer gegevens te bekijken.

## <a name="delete-an-entity"></a>Een entiteit verwijderen

Als iemand met de beveiligingsrol systeembeheerder kunt u aangepaste entiteiten verwijderen die geen onderdeel van een beheerde oplossing.  
  
> [!IMPORTANT]
>  Als u een aangepaste entiteit verwijdert, dan worden de databasetabellen die gegevens voor deze entiteit opslaan verwijderd en alle gegevens die ze bevatten zullen verdwijnen. Gekoppelde records die een bovenliggende relatie hebben met de aangepaste entiteit worden ook verwijderd. Zie voor meer informatie over bovenliggende relaties raadpleegt u [Relaties tussen entiteiten maken en bewerken](create-edit-entity-relationships.md).  
  
> [!NOTE]
> De enige wijze om gegevens te herstellen uit een entiteit die is verwijderd, is het herstellen database vanuit een punt voordat de entiteit werd verwijderd. Meer informatie: [Back-up van exemplaren maken en deze terugzetten](/dynamics365/customer-engagement/admin/backup-restore-instances)

Selecteer tijdens het [weergeven van entiteiten](#view-entities) de entiteit en selecteer **Entiteit verwijderen** in het menu of het contextmenu.

![Een entiteit verwijderen met de PowerApps-portal](media/delete-entity-powerapps-portal.png)

Als de entiteit afhankelijkheden die het verwijderen verhinderen, ziet u een foutbericht. Als u alle afhankelijkheden wilt identificeren en verwijderen, moet u de oplossingenverkenner gebruiken. Meer informatie [Entiteitafhankelijkheden identificeren](create-edit-entities-solution-explorer.md#identify-entity-dependencies)

### <a name="see-also"></a>Zie ook

[Entiteiten maken en bewerken in Common Data Service voor Apps](create-edit-entities.md)<br />
[Entiteiten maken met de oplossingenverkenner](create-edit-entities-solution-explorer.md)


