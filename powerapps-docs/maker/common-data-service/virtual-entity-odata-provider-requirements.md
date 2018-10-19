---
title: De OData v4-gegevensprovider voor virtuele entiteiten gebruiken met Common Data Service voor Apps | MicrosoftDocs
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
ms.assetid: null
caps.latest.revision: null
author: Mattp123
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="odata-v4-data-provider-configuration-requirements-and-best-practices"></a>De configuratie, vereisten en aanbevolen methoden van de OData v4-gegevensprovider

Dit onderwerp beschrijft hoe de OData v4-gegevensprovider kan worden geconfigureerd, en geeft de vereisten en aanbevolen methoden voor het gebruiken van de OData v4-gegevensprovider om verbinding te maken met een OData v4-webservice. 

## <a name="odata-v4-data-provider-best-practices"></a>Aanbevolen methoden OData v4-gegevensprovider

- Common Data Service voor Apps vereist dat alle entiteiten een id-kenmerk hebben. Dit is een unieke id en de waarde moet een guid zijn.  U kunt id-velden alleen toewijzen aan externe velden met het gegevenstype `Edm.Guid`.  U kunt een gegevenstype `Edm.Int32` niet toewijzen aan een veld van het gegevenstype Unieke id in CDS voor Apps.
-  OData-entiteiten met nullable eigenschappen moeten zodanig worden ingesteld dat zij overeenkomen met het toegewezen veld in de virtuele entiteit. Een OData-identiteiteigenschap met Nullable=False moet bijvoorbeeld een toegewezen veld hebben in CDS voor Apps en het kenmerk **Veldvereiste** moet zijn ingesteld op **Onderneming vereist**. 
- Voor het ophalen van meerdere queries, zoals bij het laden van gegevens naar een raster, beheert u de grootte van de dataset die terugkomt van de externe gegevensbron door gebruik te maken van de queryparameters selecteren en filteren.
- Als dit nog niet is ingeschakeld moeten systeembeheerders het traceren van plug-ins inschakelen. Zodra dit is ingeschakeld, worden alle fouten vanaf het OData-eindpunt geregistreerd in het traceerlogboek van de plug-in. Meer informatie: [Beheerdershandleiding: Dialoogvenster Systeeminstellingen - Tabblad Aanpassing](/dynamics365/customer-engagement/admin/system-settings-dialog-box-customization-tab) 

## <a name="data-type-mapping"></a>Gegevenstypetoewijzing

In de volgende tabel staan de gegevenstypetoewijzingen van het OData-entiteitsgegevensmodel (EDM) met gegevenstypen van CDS voor Apps. 

|Gegevenstype OData|Gegevenstype CDS voor Apps  |
|---------|---------|
|`Edm.Boolean`|Twee opties|
|`Edm.DateTime`|Datum en tijd|
|`Edm.DateTimeOffset`|Datum en tijd|
|`Edm.Decimal`|Decimaal of valuta|
|`Edm.Double`|Getal met drijvende komma|
|`Edm.Guid`|Unieke id|
|`Edm.Int32`|Geheel getal|
|`Edm.Int64`|Geheel getal|
|`Edm.String`|Enkele tekstregel of meerdere regels tekst|


### <a name="odata-edm-data-types-that-are-not-supported-for-mapping-with-virtual-entities"></a>OData EDM-gegevenstypen die niet worden ondersteund voor het toewijzen met virtuele entiteiten 

- `Edm.Binary `
- `Edm.Time` 
- `Edm.Float `
- `Edm.Single` 
- `Edm.Int16` 
- `Edm.Byte` 
- `Edm.SByte`

 
## <a name="add-a-data-source-using-the-odata-v4-data-provider"></a>Voeg een gegevensbron toe met de OData v4-gegevensprovider

In deze procedure ziet u hoe u de geïnstalleerde OData-gegevensprovider gebruikt als virtuele bron voor entiteitsgegevens.   
  
1. Ga naar **[Instellingen](../model-driven-apps/advanced-navigation.md#settings)** > **Beheer** > **Virtuele bronnen voor entiteitsgegevens**.  
1. Klik op de actiewerkbalk op **Nieuw**.  
1. Maak in het dialoogvenster **Gegevensprovider selecteren** een keuze uit de volgende gegevensbronnen en klik op **OK**.  
  
    - **OData v4-gegevensprovider**. CDS voor Apps bevat een Odata v4-serviceprovider die kan worden gebruikt voor een verbinding met gegevensbronnen die de open standaard van OData v4 ondersteunen.  
    - *Aangepaste gegevensprovider*. Als u een invoegtoepassing van een gegevensprovider hebt geïmporteerd, wordt de serviceprovider hier weergegeven. Meer informatie: [Documentatie voor ontwikkelaars: Aan de slag met virtuele entiteiten](/dynamics365/customer-engagement/developer/virtual-entities/get-started-ve)  
    
1. Vul op de eigenschappenpagina **Nieuwe gegevensbron** de volgende velden in en sla de record vervolgens op.  
  
    - **Name**. Typ een naam die de gegevensbron beschrijft.  
    - **Uri**. Als u de OData-gegevensprovider gebruikt, voert u de uri voor de OData-webservice in. Als u bijvoorbeeld de OData-provider gebruikt voor verbinding met een webservice die in Azure wordt gehost, kan de URI er als volgt uitzien: *`http://contosodataservice.azurewebsites.net/odata/`*.  
    - **Time-out in seconden**. Voer het aantal seconden in dat moet worden gewacht op een respons van de webservice alvorens een verzoek om time-out van gegevens wordt gedaan. Vul bijvoorbeeld 30 in om maximaal dertig seconden te wachten totdat een time-out plaatsvindt.  
    - **Pagineringsmodus**. Selecteer of u client-side of server-side paginering wilt gebruiken om te beheren hoe de queryresultaten worden gepagineerd. De standaardwaarde is client-side paginering. Bij server-side paginering beheert de server de manier waarop gepagineerd wordt door gebruik te maken van de parameter $skiptoken, die wordt toegevoegd aan de querytekenreeks. Meer informatie: [Systeemqueryoptie met token overslaan ($skiptoken)](https://msdn.microsoft.com/library/dd942121.aspx)  
        -  **Inline telling retourneren**. Retourneert het totaal aantal records in de resultatenset. Deze instelling wordt gebruikt om de functie volgende pagina in te schakelen als u gegevens retourneert naar een raster. Gebruik een waarde van false als uw OData-eindpunt de parameter $inclinecount van OData niet ondersteunt. De standaardwaarde is false.
    - **Aanvraagparameters**. U kunt desgewenst parameters toevoegen voor een aangepaste koptekst of een querytekenreeks voor de verbinding met de OData-webservice, zoals verificatieparameters naar de externe service. Klik op **Querytekenreeks** om te schakelen tussen de parameter en de waarde voor kolomkop en querytekenreeks. Er kunnen maximaal 10 kopteksten of querytekenreeksen worden toegevoegd. 
        > [!div class="mx-imgBorder"] 
        > ![Virtuele bron voor entiteitsgegevens](media/virtual-entity-data-source.png) 


## <a name="see-also"></a>Zie ook  

[Virtuele entiteiten maken en bewerken die gegevens uit een externe gegevensbron bevatten](create-edit-virtual-entities.md) <br/>
[TechNet Blog: Met behulp van de nieuwe, virtuele entiteiten werken met gegevens uit externe systemen](https://blogs.technet.microsoft.com/lystavlen/2017/09/08/virtual-entities/)
