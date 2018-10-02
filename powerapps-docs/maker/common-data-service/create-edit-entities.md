---
title: Entiteiten maken en bewerken in Common Data Service voor Apps | MicrosoftDocs
description: Meer informatie over het maken en bewerken van entiteiten
ms.custom: ''
ms.date: 05/11/2018
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
# <a name="create-and-edit-entities-in-common-data-service-for-apps"></a>Entiteiten maken en bewerken in Common Data Service voor Apps

Evalueer voordat u een aangepaste entiteit maakt of het gebruik van een bestaande entiteit aan uw vereisten zal voldoen. Meer informatie: [Nieuwe metagegevens maken of bestaande metagegevens gebruiken?](create-edit-metadata.md#create-new-metadata-or-use-existing-metadata)

Er zijn twee ontwerpers u kunt gebruiken om een entiteit te maken:

|Ontwerper| Beschrijving|
|--|--|
|[PowerApps-portal](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)|Biedt een eenvoudig gestroomlijnde ervaring, maar een aantal speciale instellingen is niet beschikbaar.<br />Zie voor meer informatie: <br />[Zelfstudie: een aangepaste entiteit maken die onderdelen heeft in PowerApps](/powerapps/maker/common-data-service/create-custom-entity)<br />[Entiteiten maken en bewerken met de PowerApps-portal](create-edit-entities-portal.md)|
|Oplossingenverkenner|Deze ontwerper is niet zo eenvoudig, maar biedt meer flexibiliteit en heeft minder algemene vereisten. <br />Meer informatie [Entiteiten maken en bewerken met de oplossingenverkenner](create-edit-entities-solution-explorer.md)|

> [!NOTE]
> U kunt ook entiteiten in uw omgeving maken met het volgende:
> - Importeer een oplossing die de definitie van de entiteit bevat.
> - Gebruik Power Query om nieuwe entiteiten te maken en deze te vullen met gegevens. Meer informatie: [Gegevens aan een entiteit toevoegen in Common Data Service voor Apps met behulp van Power Query](/powerapps/maker/common-data-service/data-platform-cds-newentity-pq).
> - Een ontwikkelaar kan [Metagegevensservices](/powerapps/developer/common-data-service/use-web-services#metadata-services) gebruiken om een programma te schrijven.


## <a name="entity-options-not-available-in-the-powerapps-portal"></a>Entiteitsopties niet beschikbaar in de PowerApps-portal

De informatie in dit onderwerp kan u helpen bepalen welke ontwerper u kunt gebruiken. U kunt de PowerApps-portal gebruiken om de entiteit te maken tenzij u moet voldoen aan de volgende vereisten.

- Het aanpassingsvoorvoegsel bepalen

  Een deel van de naam van een aangepaste entiteit die u maakt is het aanpassingsvoorvoegsel. Dit is ingesteld op basis van de oplossingsuitgever voor de oplossing waarin u werkt. Als het aanpassingsvoorvoegsel voor u van belang is, zorg er dan voor dat u werkt in een onbeheerde oplossing waarvoor het aanpassingsvoorvoegsel is wat u voor deze entiteit wilt. Meer informatie [Het voorvoegsel voor de oplossingsuitgever wijzigen](change-solution-publisher-prefix.md).

- Entiteit in eigendom van organisatie maken

  Met de PowerApps-portal worden standaard entiteiten die in eigendom zijn van **Gebruiker of team** gemaakt. Gebruik de oplossingenverkenner om het eigendom in te stellen op **Organisatie**. Meer informatie: [Eigendom van entiteit](types-of-entities.md#entity-ownership)

- Een activiteitsentiteit maken

  Een activiteitsentiteit is een speciaal type entiteit waarmee acties worden bijgehouden waarvoor een vermelding in een agenda kan worden gemaakt. Meer informatie: [Activiteitsentiteiten](types-of-entities.md#activity-entities).

- De pictogrammen voor een aangepaste entiteit wijzigen

  Standaard hebben alle aangepaste entiteiten in de modelgestuurde apps dezelfde pictogrammen. U kunt afbeeldingswebresources maken voor de pictogrammen die u voor uw aangepaste entiteiten wilt. Meer informatie:  [Pictogrammen wijzigen voor aangepaste entiteiten](../model-driven-apps/change-custom-entity-icons.md). 

- Wijzig desgewenst de volgende eigenschappen die alleen kunnen worden ingeschakeld:

  [!INCLUDE [cc_entity-set-once-options-table](../../includes/cc_entity-set-once-options-table.md)]

- Wijzig desgewenst de volgende eigenschappen:

  <!-- Based on ../../includes/cc_entity-changeable-options-table.md 
Removed these:

  /|**Description**/|Provide a meaningful description of the purpose of the entity./|

  /|**Primary Image**/|System entities that support images will already have an **Image** field. You can choose whether to display data in this field as the image for the record by setting this field to **[None]** or **Default Image**.<br /><br /> For custom entities you must first create an image field. Each entity can have only one image field. After you create one, you can change this setting to set the primary image. More information: [Image fields](../maker/common-data-service/types-of-fields.md#image-fields) /|-->

  |Optie   |Beschrijving  |
  |---------|---------|
  |**Toegangsteams**|Maak teamsjablonen voor deze entiteit. |
  |**Snelle invoer toestaan**|Nadat u een **Formulier voor snelle invoer** hebt gemaakt en gepubliceerd voor deze entiteit, heeft men de mogelijkheid om een nieuwe record te maken met de knop **Maken** in het navigatiedeelvenster. Meer informatie: [Formulieren maken en ontwerpen](../model-driven-apps/create-design-forms.md)<br /><br /> Als dit voor een aangepaste activiteitsentiteit is ingeschakeld, dan wordt de aangepaste activiteit in de groep activiteitsentiteiten zichtbaar wanneer gebruikers de knop **Maken** in het navigatiedeelvenster gebruiken. Omdat activiteiten echter geen formulieren voor snelle invoer ondersteunen, wordt het hoofdformulier gebruikt wanneer op het aangepaste entiteitspictogram wordt geklikt.|
  |**Gebieden waarin deze entiteit wordt weergegeven**|Kies in de webtoepassing een van de beschikbare siteoverzichtgebieden om deze entiteit weer te geven. Dit is niet van toepassing op modelgestuurde apps.|
  |**Controle**|Als controle is ingeschakeld voor uw organisatie, dan kunnen wijzigingen in entiteitsrecords door de tijd heen worden vastgelegd. Als u de controle voor een entiteit inschakelt, dan wordt de controle ook ingeschakeld voor alle velden ervan. U kunt velden selecteren of wissen waarvoor u de controle wilt inschakelen.|
  |**Bijhouden van wijzigingen**|Hiermee is gegevenssynchronisatie op een efficiënte manier mogelijk door te detecteren welke gegevens zijn gewijzigd sinds de gegevens oorspronkelijk zijn geëxtraheerd of voor het laatst zijn gesynchroniseerd.  |
  |**Color (Kleur)**|Stel een kleur in die voor de entiteit in modelgestuurde apps moet worden gebruikt.|
  |**Documentbeheer**|Nadat andere taken zijn uitgevoerd om documentbeheer voor uw organisatie in te schakelen, kan door activering van deze functie deze entiteit deelnemen aan integratie met SharePoint. |
  |**Duplicaatdetectie**|Als duplicaatdetectie is ingeschakeld voor uw organisatie, dan kunt u door het inschakelen hiervan duplicaatdetectieregels voor deze entiteit maken.|
  |**Inschakelen voor mobiel**|Maak deze entiteit beschikbaar voor de apps Dynamics 365 voor telefoons en Dynamics 365 voor tablets. U hebt ook de mogelijkheid om deze entiteit **Alleen-lezen in mobiel** te maken.<br /><br /> Als de formulieren voor een entiteit een extensie vereisen die niet in de apps Dynamics 365 for phones en Dynamics 365 for tablets wordt ondersteund, dan gebruikt u deze instelling om ervoor te zorgen dat gebruikers van mobiele apps de gegevens voor deze entiteiten niet kunnen bewerken.|
  |**Inschakelen voor telefoonexpres**|Maak deze entiteit beschikbaar voor de app Dynamics 365 for phones.|
  |**Afdruk samenvoegen**|Mensen kunnen deze entiteit met afdruk samenvoegen gebruiken.|
  |**Offlinemogelijkheid voor Dynamics 365 voor Outlook**|Of de gegevens in deze entiteit beschikbaar zijn terwijl de toepassing Dynamics 365 for Outlook niet met het netwerk is verbonden.|
  |**Leesvenster in Dynamics 365 voor Outlook**|Of de entiteit in het leesvenster voor de app Dynamics 365 for Outlook zichtbaar is.|
  |**Aangepaste Help gebruiken**|Als deze optie is ingeschakeld, stelt u een Help-URL in om te bepalen welke pagina gebruikers zien wanneer zij op de knop Help in de toepassing klikken. Gebruik dit om specifieke aanwijzingen voor uw bedrijfprocessen voor de entiteit te verschaffen.|


### <a name="see-also"></a>Zie ook

[Entiteiten maken met de oplossingenverkenner](create-edit-entities-solution-explorer.md)<br />
[Zelfstudie: een aangepaste entiteit maken die onderdelen heeft in PowerApps](/powerapps/maker/common-data-service/create-custom-entity)<br />
[Een entiteit bewerken](edit-entities.md)<br />
[Ontwikkelaarsdocumentatie: Een aangepaste entiteit maken](/dynamics365/customer-engagement/developer/org-service/create-custom-entity)
