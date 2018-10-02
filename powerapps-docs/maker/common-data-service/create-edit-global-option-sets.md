---
title: Overzicht van het maken en bewerken van algemene optiesets (selectielijsten) voor Common Data Service voor Apps | MicrosoftDocs
ms.custom: ''
ms.date: 05/26/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
ms.assetid: f06b8941-8dca-4601-b965-341cfb6fc3b2
caps.latest.revision: 11
ms.author: matp
manager: brycho
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-and-edit-global-option-sets-overview"></a>Overzicht van het maken en bewerken van algemene optiesets 

Een optieset (selectielijst) is een veldtype dat in een entiteit kan worden opgenomen. Het definieert een verzameling opties. Wanneer een optieset wordt weergegeven in een formulier, ziet u een vervolgkeuzelijstbesturingselement. Wanneer de optieset wordt weergegeven in **Geavanceerd zoeken**, gebruikt deze een *selectielijstbesturingselement*. Soms worden optiesets door ontwikkelaars selectielijsten genoemd.  
  
U kunt een optieset definiëren door een verzameling opties te gebruiken die binnen zichzelf zijn gedefinieerd (lokaal) of de optieset kan een verzameling opties gebruiken (algemeen) die door andere optiesetvelden kan worden gebruikt. 

Algemene optiesets zijn handig wanneer u een standaardset van categorieën hebt die op meerdere velden kan worden toegepast. Het onderhouden van twee aparte optiesets met dezelfde waarden is moeilijk en als ze niet gesynchroniseerd worden, kunt u de fouten krijgen, voornamelijk als u entiteitsvelden aan een een-te-veel-entiteitsrelatie toewijst. Meer informatie:  [Entiteitsvelden toewijzen](map-entity-fields.md).

> [!NOTE]
> Als u elke optieset als een algemene optieset definieert, wordt uw lijst met algemene optiesets steeds groter en kan deze lastig te beheren zijn. Als u weet dat de set met opties slechts op één plaats wordt gebruikt, gebruikt u een lokale optieset.

Er zijn twee ontwerpers die u kunt gebruiken om algemene optiesets te maken of te bewerken:

|Ontwerper| Beschrijving|
|--|--|
|[PowerApps-portal](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)|Biedt een eenvoudig gestroomlijnde ervaring, maar een aantal speciale instellingen is niet beschikbaar.<br />Meer informatie: [Een optieset maken](custom-picklists.md) |
|Oplossingenverkenner|Deze ontwerper is niet zo eenvoudig, maar biedt meer flexibiliteit en heeft minder algemene vereisten. <br />Meer informatie: [Algemene optiesets maken en bewerken voor Common Data Service voor Apps met de oplossingenverkenner](create-edit-global-option-sets-solution-explorer.md) |

> [!NOTE]
> U kunt ook algemene optiesets in uw omgeving maken met het volgende:
> - Importeer een oplossing die de definitie van de algemene optiesets bevat.
> - Een ontwikkelaar kan een programma schrijven om deze te maken. <br />Meer informatie: [Ontwikkelaarsdocumentatie: Algemene optiesets aanpassen](/dynamics365/customer-engagement/developer/org-service/customize-global-option-sets).

De informatie in dit onderwerp kan u helpen bepalen welke ontwerper u kunt gebruiken. 

U kunt de [PowerApps-portal](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) gebruiken om te werken met algemene optiesets tenzij u moet voldoen aan de volgende vereisten:

- Kleuren aan opties toewijzen
- De volgorde van opties wijzigen
- Een algemene optieset maken in een andere oplossing dan de CDS-standaardoplossing
- Beheerde eigenschappen instellen
- Eigenschappen instellen die voor virtuele entiteiten worden gebruikt
- Afhankelijkheden weergeven

## <a name="see-also"></a>Zie ook

[Een optieset maken](custom-picklists.md)<br />
[Algemene optiesets maken en bewerken voor Common Data Service voor Apps met de oplossingenverkenner](create-edit-global-option-sets-solution-explorer.md)<br />
[Ontwikkelaarsdocumentatie: Algemene optiesets aanpassen](/dynamics365/customer-engagement/developer/org-service/customize-global-option-sets)
  

 
