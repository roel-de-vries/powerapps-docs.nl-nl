---
title: Velden maken en bewerken voor Common Data Service voor Apps | MicrosoftDocs
ms.custom: ''
ms.date: 05/18/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
ms.assetid: d88677fa-2caf-47b0-aec6-10a25a7ec9c3
caps.latest.revision: 55
ms.author: matp
manager: brycho
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="how-to-create-and-edit-fields"></a>Velden maken en bewerken

Definieer in de velden van Common Data Service voor Apps de afzonderlijke gegevensitems die kunnen worden gebruikt om gegevens in een entiteit op te slaan. Velden worden soms *kenmerken* genoemd door ontwikkelaars. 
  
Evalueer voordat u een aangepast veld maakt of het gebruik van een bestaand veld aan uw vereisten zou voldoen. Meer informatie: [Nieuwe metagegevens maken of bestaande metagegevens gebruiken?](create-edit-metadata.md#create-new-metadata-or-use-existing-metadata)

Er zijn twee ontwerpers die u kunt gebruiken om velden te maken of te bewerken:

|Ontwerper| Beschrijving|
|--|--|
|[PowerApps-portal](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)|Biedt een eenvoudig gestroomlijnde ervaring, maar een aantal speciale instellingen is niet beschikbaar.<br />Meer informatie: [Velden maken en bewerken voor Common Data Service voor Apps met de PowerApps-portal](create-edit-field-portal.md)|
|Oplossingenverkenner|Deze ontwerper is niet zo eenvoudig, maar biedt meer flexibiliteit en heeft minder algemene vereisten.<br />Meer informatie: [Velden maken en bewerken voor Common Data Service voor Apps met de PowerApps-oplossingenverkenner](create-edit-field-solution-explorer.md) |

> [!NOTE]
> U kunt ook velden in uw omgeving maken met het volgende:
> - Selecteer in modelgestuurde apps **Nieuw veld** in de formuliereneditor.
> - Importeer een oplossing die de definitie van de velden bevat.
> - Gebruik Power Query om nieuwe entiteiten te maken en deze te vullen met gegevens.<br />Meer informatie: [Gegevens aan een entiteit toevoegen in Common Data Service voor Apps met behulp van Power Query](/powerapps/maker/common-data-service/data-platform-cds-newentity-pq).
> - Een ontwikkelaar kan [Metagegevensservices](/powerapps/developer/common-data-service/use-web-services#metadata-services) gebruiken om een programma te schrijven waarmee velden kunnen worden gemaakt en bijgewerkt.

De informatie in dit onderwerp kan u helpen bepalen welke ontwerper u kunt gebruiken. 

U moet de PowerApps-portal gebruiken om velden voor Common Data Service voor Apps te maken en te bewerken, tenzij u moet voldoen aan een van de volgende vereisten:

- Een opzoekveld Klant maken
- Een veld in een andere oplossing dan de CDS-standaardoplossing maken
- Overgangen van statusreden definiëren
- Meerdere velden in één keer bewerken
- Controleren inschakelen
- Beveiliging op veldniveau inschakelen
- Selecteren of het veld wordt weergegeven in het algemene filter in interactieve ervaring
- Selecteren of het veld sorteerbaar is in dashboards voor interactieve ervaring
- Een Veldvereiste-veld instellen als Onderneming aangeraden
- Beheerde eigenschappen voor een veld instellen

> [!NOTE]
> U kunt een opzoekveld in de PowerApps-portal of in de oplossingenverkenner maken door een één-op-veel-relatie in de entiteit te maken. Maar alleen de oplossingenverkenner bevat de optie om deze relatie te maken terwijl u een veld maakt.

## <a name="community-tools"></a>Community-hulpprogramma's

**[Attribute Manager](https://www.xrmtoolbox.com/plugins/DLaB.Xrm.AttributeManager/)** is een hulpprogramma dat de XrmToolbox-community heeft ontwikkeld voor CDS voor Apps. Raadpleeg het onderwerp [Ontwikkelaarhulpmiddelen](https://docs.microsoft.com/dynamics365/customer-engagement/developer/developer-tools) voor meer door de community ontwikkelde hulpprogramma's.

> [!NOTE]
> De community-hulpprogramma's zijn geen product van Microsoft en Microsoft biedt geen ondersteuning voor de community-hulpprogramma's. Als u vragen hebt over het hulpprogramma, raadpleegt u de uitgever hiervan. Meer informatie: [XrmToolBox](https://www.xrmtoolbox.com).

### <a name="see-also"></a>Zie ook  
[Velden maken en bewerken voor Common Data Service voor Apps met de PowerApps-portal](create-edit-field-portal.md)<br />
[Velden maken en bewerken voor Common Data Service voor Apps met de PowerApps-oplossingenverkenner | MicrosoftDocs](create-edit-field-solution-explorer.md)<br />
[Typen velden en veldgegevenstypen](types-of-fields.md)<br />
[Ontwikkelaarsdocumentatie: Werken met kenmerkmetagegevens](/dynamics365/customer-engagement/developer/org-service/work-attribute-metadata)
 
