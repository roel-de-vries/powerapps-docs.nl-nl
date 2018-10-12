---
title: Virtuele entiteiten maken en bewerken met Common Data Service voor Apps | MicrosoftDocs
description: Informatie over het maken van virtuele entiteiten
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
ms.openlocfilehash: 675c0ac5763698c82a7d13bfc75f8b7357d6cf0b
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39674871"
---
# <a name="create-and-edit-virtual-entities-that-contain-data-from-an-external-data-source"></a>Virtuele entiteiten maken en bewerken die gegevens van een externe gegevensbron bevatten

Een virtuele entiteit is een aangepaste entiteit in Common Data Service voor Apps die velden heeft met gegevens van een externe gegevensbron. Virtuele entiteiten worden in uw app aan gebruikers weergeven als normale entiteitsrecords, maar bevatten gegevens die afkomstig zijn uit een externe database, zoals een Azure SQL Database. Records op basis van virtuele entiteiten zijn beschikbaar in alle clients, inclusief aangepaste clients die zijn ontwikkeld met behulp van CDS voor App-webservices.  
  
In het verleden moest u om de verschillende gegevensbronnen te integreren, een connector maken die gegevens kon verplaatsen of een aangepaste invoegtoepassing aan de client- of serverzijde. Met virtuele entiteiten kunt u echter rechtstreeks verbinding maken met een externe gegevensbron in runtime, zodat specifieke gegevens van een externe gegevensbron beschikbaar zijn in een omgeving, zonder dat gegevensreplicatie noodzakelijk is.  

Virtuele entiteiten bestaan uit drie belangrijke onderdelen, een *gegevensprovider*, een *gegevensbron* en een *virtuele entiteit*. De gegevensprovider bestaat uit invoegtoepassingen en een gegevensbron-entiteit. De gegevensbron is een entiteitsrecord in CDS voor Apps, met metagegevens die het schema van de verbindingsparameters voorstellen. Elke virtuele entiteit refereert aan een gegevensbron in de entiteitsdefinitie.  
  
CDS voor Apps omvat een OData-gegevensprovider die u kunt gebruiken om verbinding te maken met een OData v4-webservice die toegang heeft tot de externe gegevens. 
  
Ontwikkelaars kunnen ook hun eigen gegevensproviders bouwen. Gegevensproviders worden in een omgeving als oplossing geïnstalleerd. Meer informatie: [Documentatie voor ontwikkelaars: aan de slag met virtuele entiteiten](/dynamics365/customer-engagement/developer/virtual-entities/get-started-ve)
  
 ![Virtueel entiteitsdiagram](media/virtual-entity-diagram.png "Virtueel entiteitsdiagram")  
  
<a name="benefits"></a> 
  
## <a name="virtual-entity-benefits"></a>Voordelen van een virtuele entiteit  
  
- Ontwikkelaars kunnen invoegtoepassingen implementeren om externe gegevens te lezen met de CDS voor Apps-webservices en het Plug-in-registratiehulpmiddel.  
- Systeemaanpassers gebruiken PowerApps Solution Explorer om het gegevensbronrecord te configureren en virtuele entiteiten te maken die worden gebruikt voor toegang tot externe gegevens, zonder code te hoeven schrijven.  
- Eindgebruikers werken met de records die zijn gemaakt door de virtuele entiteit om gegevens in velden, rasters, zoekresultaten, rapporten op basis van FetchXML en dashboards te bekijken.  
  
<a name="AddDataSource"></a> 
  
## <a name="add-a-data-source-to-use-for-virtual-entities"></a>Een gegevensbron toevoegen voor virtuele entiteiten 
 
 Ontwikkelaars maken een aangepaste invoegtoepassing die kan worden gebruikt als gegevensprovider voor een virtuele entiteit. U kunt ook de aangeboden OData v4-gegevensprovider gebruiken. Meer informatie: [Configuratie, vereisten en aanbevolen procedures voor OData v4-gegevensprovider](virtual-entity-odata-provider-requirements.md)  
  
1. Ga naar **[Instellingen](../model-driven-apps/advanced-navigation.md#settings)** > **Beheer** > **Gegevensbronnen voor virtuele entiteit**.  
1. Selecteer **Nieuw** op de werkbalk.  
1. Selecteer een gegevensbron uit de volgende gegevensbronnen in het dialoogvenster **Gegevensprovider selecteren** en selecteer dan **OK**.
 
    |Gegevensprovider|Beschrijving|
    |--|--|
    |*Aangepaste gegevensprovider*|Als u een invoegtoepassing van een gegevensprovider hebt geïmporteerd, wordt de gegevensprovider hier weergegeven. Meer informatie: [Documentatie voor ontwikkelaars: aan de slag met virtuele entiteiten](/dynamics365/customer-engagement/developer/virtual-entities/get-started-ve)|
    |**OData v4 Data Provider**|CDS voor App omvat een OData-gegevensprovider die kan worden gebruikt met OData v4-webservices. Meer informatie: [Configuratie, vereisten en aanbevolen procedures voor OData v4-gegevensprovider](virtual-entity-odata-provider-requirements.md)|

  
### <a name="add-a-secured-field-to-a-data-source"></a>Een beveiligd veld toevoegen aan een gegevensbron

Velden voor een gegevensbron worden op dezelfde manier gemaakt als elke andere entiteit. Schakel voor gegevens die versleuteld of gevoelig zijn het kenmerk Gegevensbron geheim in op het aangepaste veld van de gegevensbron. Om bijvoorbeeld een veld te beveiligen dat een databaseverbindingsreeks bevat. 

> [!NOTE]
> Het kenmerk Gegevensbron geheim is alleen beschikbaar bij velden die zijn toegevoegd aan een Gegevensbronformulier.

![Kenmerk Gegevensbron geheim](media/datasourcesecret.png)
  
<a name="createVirtualEntity"></a> 
  
## <a name="create-a-virtual-entity"></a>Een virtuele entiteit maken
  
U maakt een virtuele entiteit net als elke andere entiteit in CDS voor Apps met de toevoeging van een paar extra kenmerken die hier worden beschreven. Virtuele entiteiten moeten worden gemaakt met de Solution Explorer.

> [!NOTE]
>  Hoewel u een virtuele entiteit kunt maken door **Geen** te selecteren als de databron, heeft een virtuele entiteit voor het verkrijgen van gegevens een gegevensbron nodig. Meer informatie: [Een gegevensbron toevoegen voor virtuele entiteiten](#AddDataSource)

### <a name="open-solution-explorer"></a>Solution Explorer openen

Een deel van de naam van elke virtuele entiteit die u maakt, is het aanpassingsvoorvoegsel. Dit is ingesteld op basis van de uitgever van de oplossing waarin u werkt. Als u geïnteresseerd bent in het aanpassingsvoorvoegsel, moet u ervoor zorgen dat u in een niet-beheerde oplossing werkt waarbij het aanpassingsvoorvoegsel het voorvoegsel is dat u voor deze virtuele entiteit wilt gebruiken. Meer informatie: [Het publicatievoorvoegsel van de oplossing wijzigen](change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

### <a name="create-a-virtual-entity"></a>Een virtuele entiteit maken
  
1. Maak in Solution Explorer een nieuwe entiteit. Selecteer hiervoor in het linkernavigatiedeelvenster **Entiteiten** en selecteer vervolgens**Nieuw**.  
2. Selecteer **Virtuele entiteit** in het tabblad **Algemeen** van de **Entiteitsdefinitie** en selecteer vervolgens in de vervolgkeuzelijst **Gegevensbron** de gewenste gegevensbron.  
  
    ![Optie Virtuele entiteit in entiteitsdefinitie](media/virtual-entity-click-option.png)  
  
1. Vul de volgende verplichte velden in de entiteitsdefinitie in.
  
    |Veld|Beschrijving|
    |--|--|
    |**Externe naam**|Voer de tabelnaam in de externe gegevensbron in waar deze entiteit naar verwijst.|
    |**Naam van externe verzameling**|Voer de meervoudstabelnaam in de externe gegevensbron in waar deze entiteit naar verwijst.|
      
    Hier volgt een voorbeeld van een entiteit genaamd *Film* die een Azure Cosmos DB-gegevensprovider gebruikt om documentatie te openen.  
      
    ![Virtuele-entiteitsdefinitie die Azure Cosmos DB-gegevensprovider gebruikt](media/virtual-entity-definition.PNG)  
      
    > [!IMPORTANT]
    > Verschillende opties, zoals Toegangsteams, Wachtrijen en Snel maken, zijn niet beschikbaar bij virtuele entiteiten. Meer informatie: [Overwegingen bij het gebruik van virtuele entiteiten](#considerations)  
      
    Voltooi, voor zover nodig, de overige vereiste en optionele eigenschappen, zoals weergave en meervoudsnamen. Zie [Entiteiten maken en bewerken](create-edit-entities.md) voor meer informatie over deze eigenschappen.  
  
1. Maak en voeg een of meer velden toe voor de virtuele entiteit. Naast de standaardveldeigenschappen die vereist zijn om een aangepast veld te maken, zijn deze optionele eigenschappen beschikbaar voor elk aangepast veld dat u maakt voor een virtuele entiteit.

    |Veld|Beschrijving|
    |--|--|
    |**Externe naam**|Dit is meestal de unieke naam om gegevens te identificeren die u wilt weergeven in een veld.|
    |**Externe typenaam**|Als het veldtype dat u maakt OptieSet is: deze eigenschap verwijst naar de externe naam van de set met waarden in de externe service voor de optieset.  Normaal gesproken kan dit een enum of de naam van de klasse van een tekenreekswaarde zijn. De Externe typenaam kan worden gebruikt als een volledige gekwalificeerde naam is vereist.  Als bijvoorbeeld de *Typenaam* in OData, waar parameters in een query de volledige gekwalificeerde naam nodig hebben, zoals [*Typenaam*].[*Waarde*].|
    |**Externe waarde**|Als het veldtype dat u maakt OptieSet is: deze eigenschap verwijst naar de gerelateerde waarde in de externe gegevensbron voor het optie-item.  Deze ingevoerde waarde wordt gebruikt om vast te stellen welk optieset-item wordt weergegeven in de app.  |

    Voltooi de aanvullende eigenschappen indien nodig. Zie [Velden maken en bewerken](create-edit-fields.md) voor meer informatie over deze eigenschappen.  
  
1. Selecteer op de eigenschappenpagina **Veld** **Opslaan en sluiten**.  
1. Selecteer **Opslaan** op de werkbalk van Solution Explorer.  
1. Selecteer **Publiceren** op de werkbalk van Solution Explorer.  
1. Sluit Solution Explorer.  

<a name="considerations"></a>
   
## <a name="considerations-when-you-use-virtual-entities"></a>Overwegingen bij het gebruik van virtuele entiteiten  

Virtuele entiteiten hebben de volgende beperkingen.  
  
- Alle virtuele entiteiten zijn alleen-lezen.  
- Bestaande entiteiten kunnen niet worden geconverteerd naar virtuele entiteiten.  
- Standaard bevatten virtuele entiteiten alleen een Naam- en ID-veld.  Andere door het systeem beheerde velden, zoals Status of Gemaakt op/Gewijzigd op worden niet ondersteund.
- Virtuele entiteiten ondersteunen geen aangepaste velden van de gegevenstypen Valuta, Afbeelding of Klant.
- Virtuele entiteiten ondersteunen geen controle.  
- Virtuele entiteitsvelden kunnen niet worden gebruikt in getotaliseerde of berekende velden.
- Een virtuele entiteit mag geen activiteitstype van een entiteit zijn.  
- Veel functies die van invloed zijn op tabelrijen van entiteiten kunnen niet worden ingeschakeld bij virtuele entiteiten.  Voorbeelden hiervan zijn wachtrijen, kennisbeheer, SLA’s, duplicaatdetectie, wijzigingstracering, mobiele offlinefunctionaliteit, veldbeveiliging, relevantiezoekacties, portals voor Dynamics 365-webportaloplossingen en N:N-verhoudingen tussen virtuele entiteiten.  
- Virtuele entiteiten zijn bedrijfseigendom en bieden geen ondersteuning voor de Common Data Service voor Apps-beveiligingsconcepten op rijniveau. Het is raadzaam dat u uw eigen beveiligingsmodel implementeert voor de externe gegevensbron.  
- Het is raadzaam dat u zich richt op een enkele gegevensbron als u gebruikmaakt van virtuele entiteiten in Geavanceerd zoeken. Een Geavanceerde zoekactie maken die uiteindelijk een verbinding maakt tussen de systeemeigen gegevens van Common Data Service voor Apps en de externe gegevens van de virtuele entiteit wordt bijvoorbeeld niet ondersteund.  
- Eigenschappen van metagegevens van velden die gevalideerd worden bij een update zijn niet van toepassing op virtuele entiteiten. Een veld Geheel getal op een veld van een virtuele entiteit kan bijvoorbeeld worden ingesteld op een minimale waarde van nul. Maar, aangezien de waarde afkomstig is uit een externe gegevensbron, zal een query waarden kleiner dan nul retourneren wanneer ze komen van een virtuele entiteit.  De eigenschap Minimale waarde wordt niet geïmpliceerd in de query.  U moet nog steeds de waarden groter dan nul filteren als u dat wilt.
- Virtuele entiteiten ondersteunen geen wijzigingstracering en kunnen niet worden gesynchroniseerd met een CDS voor Apps-functie, zoals de Data Export Service.
  
### <a name="see-also"></a>Zie ook  

[Vereisten en aanbevolen procedures voor OData v4-gegevensprovider](virtual-entity-odata-provider-requirements.md)</br> 
[Entiteiten maken en bewerken](create-edit-entities.md)</br>
[Velden maken en bewerken](create-edit-fields.md)
