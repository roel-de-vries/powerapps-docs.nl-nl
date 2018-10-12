---
title: De Virtual Entity OData v4-gegevensprovider gebruiken met Common Data Service for Apps | Microsoft Docs
ms.custom: ''
ms.date: 06/04/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
ms.assetid: ''
caps.latest.revision: ''
author: Mattp123
ms.author: matp
manager: brycho
ms.openlocfilehash: 0bd2aed852b5d7eb9b354f30978725b1386a89aa
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39679212"
---
# <a name="odata-v4-data-provider-configuration-requirements-and-best-practices"></a>Configuratie, vereisten en aanbevolen procedures voor de OData v4-gegevensprovider

In dit onderwerp wordt beschreven hoe u de OData v4-gegevensprovider configureert en wat de vereisten en aanbevolen best practices zijn voor het gebruiken van de OData v4-gegevensprovider om verbinding te maken met een OData v4-webservice. 

## <a name="odata-v4-data-provider-best-practices"></a>Best practices voor de OData v4-gegevensprovider

- Common Data Service for Apps vereist dat alle entiteiten beschikken over een id-kenmerk. Deze id heet ook wel de 'unieke id' en de waarde moet een GUID zijn.  U kunt alleen id-velden aan externe velden toewijzen met het gegevenstype `Edm.Guid`.  U kunt het gegevenstype `Edm.Int32` in CDS for Apps niet toewijzen aan een veld voor unieke id's.
-  OData-entiteiten met eigenschappen die op null kunnen worden ingesteld, moeten zodanig worden ingesteld dat er een overeenkomst is met het toegewezen veld in de virtuele entiteit. Bij een OData-entiteiteigenschap met Nullable=False moet het toegewezen veld in het kenmerk **Veldvereiste** van CDS for Apps worden ingesteld op **Onderneming vereist**. 
- Als u meerdere query's uitvoert, bijvoorbeeld wanneer u gegevens in een raster laadt, controleert u de grootte van de gegevensset die door de externe gegevensbron wordt geretourneerd. Gebruik hiervoor de selecteer- en filterqueryparameters.
- Als tracering van plug-ins nog niet was ingeschakeld, moeten systeembeheerders dit inschakelen. Als dit is ingeschakeld, worden alle fouten van het OData-eindpunt vastgelegd in het traceringslogboek van de plug-in. Meer informatie: [Beheerdershandleiding: dialoogvenster Systeeminstellingen - tabblad Aanpassen](/dynamics365/customer-engagement/admin/system-settings-dialog-box-customization-tab) 

## <a name="data-type-mapping"></a>Toewijzing van gegevenstype

De volgende tabel bevat de OData Entity Data Model-toewijzingen van gegevenstypen (EDM) met CDS for Apps-gegevenstypen. 

|OData-gegevenstype|CDS for Apps-gegevenstype  |
|---------|---------|
|`Edm.Boolean`|Twee opties|
|`Edm.DateTime`|Datum en tijd|
|`Edm.DateTimeOffset`|Datum en tijd|
|`Edm.Decimal`|Decimaal getal of valuta|
|`Edm.Double`|Drijvendekommagetal|
|`Edm.Guid`|Unieke id|
|`Edm.Int32`|Geheel getal|
|`Edm.Int64`|Geheel getal|
|`Edm.String`|Eén regel tekst of meerdere regels tekst|


### <a name="odata-edm-data-types-that-are-not-supported-for-mapping-with-virtual-entities"></a>OData EDM-gegevenstypen die niet worden ondersteund voor toewijzing met virtuele entiteiten 

- `Edm.Binary `
- `Edm.Time` 
- `Edm.Float `
- `Edm.Single` 
- `Edm.Int16` 
- `Edm.Byte` 
- `Edm.SByte`

 
## <a name="add-a-data-source-using-the-odata-v4-data-provider"></a>Een gegevensbron toevoegen met de OData v4-gegevensprovider

In deze procedure ziet u hoe u de kant-en-klare OData-gegevensprovider gebruikt als gegevensbron voor virtuele entiteiten.   
  
1. Ga naar **[Instellingen](../model-driven-apps/advanced-navigation.md#settings)** > **Beheer** > **Gegevensbronnen voor virtuele entiteit**.  
1. Klik op **Nieuw** op de werkbalk.  
1. Selecteer een gegevensbron uit de volgende gegevensbronnen in het dialoogvenster **Gegevensprovider selecteren** en klik op **OK**.  
  
    - **OData v4-gegevensprovider**. CDS for Apps bevat een OData v4-gegevensprovider die kan worden gebruikt om verbinding te maken met gegevensbronnen die ondersteuning bieden voor de OData v4 open standaard.  
    - *Aangepaste gegevensprovider*. Als u een invoegtoepassing van een gegevensprovider hebt geïmporteerd, wordt de gegevensprovider hier weergegeven. Meer informatie: [Documentatie voor ontwikkelaars: aan de slag met virtuele entiteiten](/dynamics365/customer-engagement/developer/virtual-entities/get-started-ve)  
    
1. Op de eigenschappenpagina **Nieuwe gegevensbron** vult u de volgende velden in. Sla de record vervolgens op.  
  
    - **Naam**. Typ een naam die de gegevensbron beschrijft.  
    - **Uri**. Als u gebruikmaakt van de OData-gegevensprovider, voert u de URI van de OData-webservice in. Als u bijvoorbeeld gebruikmaakt van de OData-provider om verbinding te maken met een webservice die in Azure wordt gehost, kan de URI lijken op *`http://contosodataservice.azurewebsites.net/odata/`*.  
    - **Time-out in seconden**. Voer het aantal seconden in dat moet worden gewacht op een reactie van de webservice voordat een time-out optreedt van de aanvraag voor gegevens. Voer bijvoorbeeld 30 in om maximaal dertig seconden te wachten voordat een time-out optreedt.  
    - **Pagineringsmodus**. Selecteer of u paginering wilt laten plaatsvinden aan de clientzijde of aan de serverzijde - zo bepaalt u hoe de queryresultaten worden weergegeven. Standaard vindt paginering plaats aan de clientzijde. Als u voor paginering aan de serverzijde kiest, bepaalt de server hoe de resultaten worden weergegeven. Hiervoor wordt de parameter $skiptoken toegevoegd aan de querytekenreeks. Meer informatie: [Skip-tokensysteem voor query's ($skiptoken)](https://msdn.microsoft.com/library/dd942121.aspx)  
        -  **Inline aantal retourneren**. Hiermee wordt het totale aantal records in de resultatenset geretourneerd. Deze instelling wordt gebruikt om functionaliteit voor volgende pagina's in te schakelen wanneer u gegevens naar een raster retourneert. Gebruik de waarde false als uw OData-eindpunt geen ondersteuning biedt voor de OData-parameter $inclinecount. De standaardwaarde is false.
    - **Aanvraagparameters**. Optioneel kunt u aangepaste header- of querytekenreeksparameters, zoals verificatieparameters, toevoegen om de OData-webservice te verbinden met de externe service. Klik op **Querytekenreeks** om uit te schakelen tussen de header- en querytekenreeksparameter en -waarde. Er kunnen maximaal tien header- en querytekenreeksen worden toegevoegd. 
        ![Gegevensbronrecord van virtuele entiteit](media/virtual-entity-data-source.png) 


## <a name="see-also"></a>Zie ook  

[Virtuele entiteiten maken en bewerken die gegevens uit een externe gegevensbron bevatten](create-edit-virtual-entities.md) <br/>
[TechNet-blog: gegevens uit externe systemen gebruiken met de nieuwe virtuele entiteiten](https://blogs.technet.microsoft.com/lystavlen/2017/09/08/virtual-entities/)
