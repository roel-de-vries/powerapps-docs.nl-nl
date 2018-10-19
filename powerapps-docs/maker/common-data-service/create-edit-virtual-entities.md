---
title: Virtuele entiteiten maken en bewerken met Common Data Service voor Apps | MicrosoftDocs
description: Lees hoe u virtuele entiteiten kunt maken
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.assetid: 44834893-0bf6-4a64-8f06-7583fe08330d
caps.latest.revision: 11
author: Mattp123
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-and-edit-virtual-entities-that-contain-data-from-an-external-data-source"></a>Virtuele entiteiten maken en bewerken die gegevens uit een externe gegevensbron bevatten

Een virtuele entiteit is een aangepaste entiteit in Common Data Service voor Apps die velden bevat met gegevens uit een externe gegevensbron. Virtuele entiteiten worden in uw app aan gebruikers getoond als normale entiteitsrecords, maar bevatten gegevens die afkomstig zijn uit een externe database, zoals een Azure SQL-database. Records die op virtuele entiteiten zijn gebaseerd, zijn beschikbaar in alle clients, inclusief aangepaste clients die zijn ontwikkeld met de CDS voor Apps-webservices.  
  
In het verleden moest u, om de ongelijksoortige gegevensbronnen te integreren, een connector maken om gegevens te verplaatsen of een aangepaste toepassing te ontwikkelen, aan de server- of clientzijde. Met virtuele entiteiten kunt u echter rechtstreeks verbinding maken met een externe gegevensbron tijdens runtime zodat de bepaalde gegevens uit de externe gegevensbron in een omgeving beschikbaar zijn zonder de noodzaak van gegevensreplicatie.  

Virtuele entiteiten zijn samengesteld uit drie hoofdonderdelen, een *gegevensprovider*, een *gegevensbron*-record en een *virtuele entiteit*. De gegevensprovider bestaat uit en invoegtoepassingen een gegevensbronentiteit. De gegevensbron is een entiteitsrecord in CDS voor Apps, die metagegevens bevat waarmee het schema van de verbindingparameters wordt vertegenwoordigd. Elk virtuele entiteit verwijst naar een gegevensbron in de entiteitdefinitie.  
  
CDS voor Apps bevat een OData-gegevensprovider waarmee u verbinding kunt maken met een OData v4-webservice die toegang heeft tot de externe gegevens. 
  
Ook kunnen ontwikkelaars hun eigen gegevensproviders bouwen. De gegevensproviders worden in een omgeving geïnstalleerd als oplossing. Meer informatie: [Ontwikkelaarsdocumentatie: Aan de slag met virtuele entiteiten](/dynamics365/customer-engagement/developer/virtual-entities/get-started-ve)
  
 ![Diagram virtuele entiteit](media/virtual-entity-diagram.png "Diagram virtuele entiteit")  
  
<a name="benefits"></a> 
  
## <a name="virtual-entity-benefits"></a>Voordelen van virtuele entiteiten  
  
- Ontwikkelaars kunnen invoegtoepassingen implementeren om externe gegevens te lezen met behulp van de CDS voor Apps-webservies en het hulpmiddel voor registratie van invoegtoepassingen.  
- Systeemaanpassers gebruiken de PowerApps-oplossingenverkenner om de gegevensbronrecord te configureren en virtuele entiteiten te maken die worden gebruikt voor toegang tot externe gegevens zonder code te schrijven.  
- Eindgebruikers werken met de records die door de virtuele entiteit zijn gemaakt om de gegevens weer te geven in velden, rasters, zoekresultaten en op Fetch XML gebaseerde rapporten en dashboards.  
  
<a name="AddDataSource"></a> 
  
## <a name="add-a-data-source-to-use-for-virtual-entities"></a>Een gegevensbron toevoegen om virtuele entiteiten te gebruiken 
 
 Ontwikkelaars kunnen een aangepaste invoegtoepassing maken om als gegevensprovider voor een virtuele entiteit te gebruiken. U kunt ook gebruikmaken van de opgegeven OData v4-gegevensprovider. Meer informatie: [De configuratie, vereisten en aanbevolen methoden van de OData v4-gegevensprovider](virtual-entity-odata-provider-requirements.md)  
  
1. Ga naar **[Instellingen](../model-driven-apps/advanced-navigation.md#settings)** > **Beheer** > **Virtuele bronnen voor entiteitsgegevens**.  
1. Selecteer op de werkbalk Acties de optie **Nieuw**.  
1. Maak in het dialoogvenster **Gegevensprovider selecteren** een keuze uit de volgende gegevensbronnen en selecteer vervolgens **OK**.
 
    |Gegevensprovider|Beschrijving|
    |--|--|
    |*Aangepaste gegevensprovider*|Als u een invoegtoepassing van een gegevensprovider hebt geïmporteerd, wordt de serviceprovider hier weergegeven. Meer informatie [Ontwikkelaarsdocumentatie: Aan de slag met virtuele entiteiten](/dynamics365/customer-engagement/developer/virtual-entities/get-started-ve)|
    |**OData v4-gegevensprovider**|CDS voor Apps bevat een OData-gegevensprovider die bij de OData v4-webservices kan worden gebruikt. Meer informatie [De configuratie, vereisten en aanbevolen methoden van de OData v4-gegevensprovider](virtual-entity-odata-provider-requirements.md)|

  
### <a name="add-a-secured-field-to-a-data-source"></a>Een beveiligd veld toevoegen aan een gegevensbron

U kunt velden maken voor een gegevensbron zoals u ze ook voor andere entiteiten zou maken. Voor gecodeerde of gevoelige gegevens kunt u het kenmerk Geheim voor gegevensbron in het aangepaste veld van de gegevensbron inschakelen. U doet dit bijvoorbeeld om een veld met een verbindingstekenreeks voor de database te beveiligen. 

> [!NOTE]
> Het kenmerk Geheim voor gegevensbron is alleen beschikbaar voor velden die aan een gegevensbronformulier zijn toegevoegd.

> [!div class="mx-imgBorder"] 
> ![Geheim kenmerk voor gegevensbron](media/datasourcesecret.png)
  
<a name="createVirtualEntity"></a> 
  
## <a name="create-a-virtual-entity"></a>Een virtuele entiteit maken
  
U maakt een virtuele entiteit zoals u ook andere entiteiten maakt in CDS voor Apps, alleen voegt u nu een aantal extra kenmerken toe die hier worden beschreven. Virtuele entiteiten moeten worden gemaakt met de oplossingenverkenner.

> [!NOTE]
>  Hoewel u een virtuele entiteit kunt maken door **Geen** als gegevensbron te selecteren, heeft een virtuele entiteit wel een gegevensbron nodig om gegevens te kunnen ophalen. Meer informatie [Een gegevensbron toevoegen om virtuele entiteiten te gebruiken](#AddDataSource)

### <a name="open-solution-explorer"></a>Open de oplossingenverkenner.

Een deel van de naam van een virtuele entiteit die u maakt is het aanpassingsvoorvoegsel. Dit is ingesteld op basis van de oplossingsuitgever voor de oplossing waarin u werkt. Als het aanpassingsvoorvoegsel voor u van belang is, zorg er dan voor dat u werkt in een onbeheerde oplossing waarvoor het aanpassingsvoorvoegsel is wat u voor deze virtuele entiteit wilt. Meer informatie: [Het voorvoegsel voor de oplossingsuitgever wijzigen](change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

### <a name="create-a-virtual-entity"></a>Een virtuele entiteit maken
  
1. Maak een nieuwe entiteit in de oplossingenverkenner. Hiervoor selecteert u in het navigatiedeelvenster aan de linkerkant de optie **Entiteiten** en selecteert u vervolgens **Nieuw**.  
2. Selecteer op het tabblad **Algemeen** van de **Entiteitsdefinitie** de optie **Virtuele entiteit** en vervolgens in de vervolgkeuzelijst **Gegevensbron** de gewenste gegevensbron.  

    > [!div class="mx-imgBorder"] 
    > ![Optie Virtuele entiteit in entiteitsdefinitie](media/virtual-entity-click-option.png)  
  
1. Vul voor de Entiteitdefinitie u de volgende vereiste velden.
  
    |Veld|Beschrijving|
    |--|--|
    |**Externe naam**|Voer de naam van de tabel in de externe gegevensbron in waaraan deze entiteit is toegewezen.|
    |**Naam van externe verzameling**|Voer de meervoudige naam van de tabel in de externe gegevensbron in waaraan deze entiteit is toegewezen.|
      
    Hier volgt een voorbeeld van een virtuele entiteit met de naam *Film* die een Azure Cosmos DB-gegevensprovider gebruikt om de documentbestanden te openen.  
      
    > [!div class="mx-imgBorder"] 
    > ![Virtuele entiteitsdefinitie met de Azure Cosmos DB-gegevensprovider](media/virtual-entity-definition.PNG)  
      
    > [!IMPORTANT]
    > Opties zoals Toegangteams, wachtrijen en Snel maken zijn niet beschikbaar voor virtuele entiteiten. Meer informatie [Overwegingen als u virtuele entiteiten gebruikt](#considerations)  
      
    Vul indien nodig de overige vereiste en optionele eigenschappen in, zoals weergave en meervoudsnamen. Voor meer informatie over deze eigenschappen raadpleegt u [Entiteiten maken en bewerken](create-edit-entities.md).  
  
1. Maak een of meer velden voor de virtuele entiteit en en voeg ze toe. Naast de standaarddveldeigenschappen die vereist zijn voor het maken van een aangepast veld, zijn deze optionele eigenschappen beschikbaar voor elk aangepast veld dat u maakt voor een virtuele entiteit.

    |Veld|Beschrijving|
    |--|--|
    |**Externe naam**|Dit is doorgaans de unieke naam waarmee u de gegevens aanduidt die u in het veld wilt weergeven.|
    |**Externe typenaam**|Als het veldtype dat u maakt OptionSet is: deze eigenschap verwijst naar de externe naam van de set waarden in de externe service voor de optieset.  Normaal gesproken kan dit een opsomming zijn of een naam van een klasse met tekenreekswaarden. De externe typenaam kan worden gebruikt als een volledig gekwalificeerde naam is vereist.  Als bijvoorbeeld *Typenaam* met OData als parameters in een query de volledig gekwalificeerde naam vereisen, zoals [*Typenaam*].[*Waarde*].|
    |**Externe waarde**|Als het veldtype dat u maakt OptionSet is: deze eigenschap verwijst naar de corresponderende waarde in de externe gegevensbron voor het optiesetitem.  De ingevoerde waarde wordt gebruikt om te bepalen welk optiesetitem wordt weergegeven in de app.  |

    Vul desgewenst extra eigenschappen in. Voor meer informatie over deze eienschappen raadpleegt u [Velden maken en bewerken](create-edit-fields.md).  
  
1. Selecteer **Opslaan en sluiten** op de eigenschappenpagina **Veld**.  
1. Selecteer **Opslaan** op de werkbalk van de oplossingsverkenner.  
1. Selecteer **Publiceren** op de werkbalk van de oplossingsverkenner.  
1. Sluit de oplossingenverkenner.  

<a name="considerations"></a>
   
## <a name="considerations-when-you-use-virtual-entities"></a>Overwegingen als u virtuele entiteiten gebruikt  

Virtuele entiteiten hebben deze beperkingen.  
  
- Alle virtuele entiteiten zijn alleen-lezen.  
- Bestaande entiteiten kunnen niet naar virtuele entiteiten worden geconverteerd.  
- Standaard bevatten virtuele entiteiten alleen een naam- en identiteitsveld.  Andere door het systeem beheerde velden, zoals Status of Gemaakt op/Gewijzigd op, worden niet ondersteund.
- Virtuele entiteiten ondersteunen aangepaste velden van het type Valuta, Afbeelding of Klantgegevens niet.
- Virtuele entiteiten ondersteunen geen controle.  
- Virtuele entiteitsvelden kunnen niet in rollups of berekende velden worden gebruikt.
- Een virtuele entiteit kan geen entiteit van het type activiteit zijn.  
- Veel functies die de rijen in de entiteitstabel beïnvloeden, kunnen niet met virtuele entiteiten worden ingeschakeld.  Voorbeelden zijn wachtrijen, kennisbeheer, SLA's, duplicaatdetectie, het bijhouden van wijzigingen, Mobile offline-mogelijkheid, veldbeveiliging, zoeken op relevantie, portals voor webportaloplossingen van Dynamics 365 en N:N-relaties tussen virtuele entiteiten.  
- Virtuele entiteiten zijn eigendom van de organisatie en bieden geen ondersteuning voor beveiligingsconcepten van Commond Data Service for Apps op rijniveau. We adviseren u om uw eigen beveiligingsmodel voor de externe gegevensbron te implementeren.  
- We adviseren u om één gegevensbron als bestemming te gebruiken als u virtuele entiteiten in Geavanceerd zoeken gebruikt. Het maken van een geavanceerde zoekopdracht die uiteindelijk in een koppeling tussen systeemeigen gegevens van Common Data Service for Apps en de virtuele externe entiteitsgegevens resulteert, wordt bijvoorbeeld niet ondersteund.  
- Eigenschappen van veldmetagegevens die tijdens een update worden gevalideerd, zijn niet van toepassing op virtuele entiteiten. Het veld Geheel getal kan in een veld van een virtuele entiteit bijvoorbeeld worden ingesteld op een minimale waarde van nul. Omdat de waarde echter afkomstig is van een externe gegevensbron, geeft een query waarden terug die lager zijn dan nul wanneer deze van een virtuele entiteit zijn opgehaald.  De eigenschap voor de minimumwaarde wordt niet bij de query betrokken.  U moet nog wel steeds desgewenst de waarden filteren die groter zijn dan 0.
- Virtuele entiteiten bieden geen ondersteuning voor het bijhouden van wijzigingen en kunnen niet worden gesynchroniseerd met een CDS voor Apps-functie zoals de gegevensexportservice.
  
### <a name="see-also"></a>Zie ook  

[De vereisten en aanbevolen methoden van de OData v4-gegevensprovider](virtual-entity-odata-provider-requirements.md)</br> 
[Entiteiten maken en bewerken](create-edit-entities.md)</br>
[Velden maken en bewerken](create-edit-fields.md)
