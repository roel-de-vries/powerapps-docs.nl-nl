---
title: Webresources voor modelgestuurde apps maken of bewerken in PowerApps | MicrosoftDocs
description: Informatie over het maken of bewerken van een webresource
ms.custom: ''
ms.date: 06/02/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: ef4ba8df-9ba9-4066-b40d-def9761c7de2
caps.latest.revision: 21
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-or-edit-model-driven-app-web-resources-to-extend-an-app"></a>Webresources voor modelgestuurde apps maken of bewerken om een app uit te breiden

Webresources worden doorgaans gebruikt door ontwikkelaars om een app uit te breiden met bestanden die in webontwikkeling worden gebruikt. Appgebruikers moeten mogelijk webresources beheren die door een ontwikkelaar of ontwerper worden geleverd.  

> [!TIP]
> Voor een grondige bespreking van webresources raadpleegt u [Documentatie voor ontwikkelaars: Webresources voor Customer Engagement](/dynamics365/customer-engagement/developer/web-resources).<br /> Voor informatie over webresourceafhankelijkheden die zijn toegevoegd in PowerApps raadpleegt u [Documentatie voor ontwikkelaars: Webresourceafhankelijkheden](/dynamics365/customer-engagement/developer/web-resources).
   
<a name="BKMK_WhatAreWebResources"></a>

## <a name="what-are-web-resources"></a>Wat zijn webresources?  

Webresources zijn virtuele bestanden die in het systeem worden opgeslagen. Elke webresource heeft een unieke naam die in een URL kan worden gebruikt om het bestand op te halen. Zie het zo: als u toegang had tot de werkelijke webserver die de webapp uitvoert, zou u bestanden naar deze website kunnen kopiëren. Maar met de meeste onlineservices is dit niet mogelijk.  In plaats daarvan kunt u webresources gebruiken om bestanden te uploaden naar het systeem en er vervolgens bij naam naar verwijzen alsof u ze als bestanden naar de webserver hebt gekopieerd.  
  
Als u bijvoorbeeld een html-pagina als webresource met de naam "new_myWebResource.htm" maakt, kunt u deze pagina in een browser openen met een URL die er zo uitziet:  
 
`<base URL>/WebResources/new_myWebResource.htm   `
  
waarbij *\<base URL>* het deel van de URL is dat u kunt gebruiken om apps weer te geven die eindigen op `dynamics.com`. Omdat de webresource bestaat uit gegevens in het systeem, kunnen alleen gebruikers met gebruiksrecht voor uw organisatie er op deze manier toegang toe krijgen. Normaal gesproken worden webresources opgenomen in formulieren in plaats van dat er direct naar wordt verwezen. Het meest voorkomende gebruik is JavaScript-bibliotheken te bieden voor formulierscripts.  
    
Aangezien webresources gegevens in het systeem zijn en oplossingsbewust zijn, kunt u ze naar verschillende organisaties verplaatsen door ze te exporteren als onderdeel van een oplossing en ze in een andere organisatie in de oplossing importeren. U moet de oplossingenverkenner gebruiken om te werken met webresources.
  
## <a name="open-solution-explorer"></a>Open de oplossingenverkenner.

Een deel van de naam van elke webresource die u maakt is het aanpassingsvoorvoegsel. Dit is ingesteld op basis van de oplossingsuitgever voor de oplossing waarin u werkt. Als het aanpassingsvoorvoegsel voor u van belang is, zorg er dan voor dat u werkt in een onbeheerde oplossing waarvoor het aanpassingsvoorvoegsel overeenkomt met wat u voor deze webresource wilt. Meer informatie: [Het voorvoegsel voor de oplossingsuitgever wijzigen](../common-data-service/change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

## <a name="view-web-resources"></a>Webresources weergeven

Selecteer terwijl de oplossingenverkenner is geopend onder **Onderdelen** de optie **Webresources**.

![Webresources weergeven](media/view-web-resources-solution-explorer.png)

<a name="BKMK_CreateAndEditWebResources"></a>

## <a name="create-or-edit-web-resources"></a>Webresources maken of bewerken  

Selecteer terwijl [webresources worden weergegeven](#view-web-resources) de optie **Nieuw** om een nieuwe webresource te maken of dubbelklik op een bestaande webresource om deze te bewerken.

![Formulier voor nieuwe webresource](media/new-web-resource-form.png)

Vul het formulier in om de webresource te maken of te bewerken:
  
|Veld|Beschrijving|  
|-----------|-----------------|  
|**Name**|*Vereist*. Dit is de unieke naam voor deze webresource. U kunt deze niet wijzigen nadat u de webresource hebt opgeslagen.<br />&bull; Deze naam kan alleen letters, cijfers, punten en niet-opeenvolgende voorwaartse slashes ("/") bevatten.<br /> &bull; Het prefix van de oplossingsuitgeveraanpassing wordt vóór aan de naam van de webresource toegevoegd.|  
|**Weergavenaam**|De naam die wordt weergegeven als u een lijst met webresources bekijkt.|  
|**Beschrijving**|Een beschrijving van de webresource.|  
|**Type**|*Vereist*. Dit is het type van de webresource. U kunt deze niet wijzigen nadat u de webresource hebt opgeslagen.|  
|**Teksteditor**|Als het type webresource een soort tekstbestand vertegenwoordigt, selecteert u deze knop om een pagina te openen en de inhoud te bewerken met de teksteditor.<br />Meer informatie: [De teksteditor gebruiken](#use-the-text-editor-appropriately)| 
|**Taal**|Hiermee kunt u een taal selecteren. Deze optie markeert slechts de record waarin de webresourcegegevens zijn opgeslagen. Het gedrag van de webresource verandert niet.|  
|**Bestand uploaden**|Selecteer **Bladeren** om een bestand te kiezen om als webresource te uploaden.<br />&bull; U kunt een bestand uploaden wanneer u een nieuwe webresource maakt of om een bestaande webresource te overschrijven.<br />&bull; De naamextensie van het bestand moet overeenkomen met toegestane bestandsextensies.<br />&bull;De maximumbestandsgrootte voor uploaden van een bestand als webresource is standaard 5 MB. Deze waarde kan worden gewijzigd in Dynamics 365 Customer Engagement via **Systeeminstellingen** > **tabblad E-mail** > **Maximale bestandsgrootte instellen voor bijlagen**. Meer informatie: [Dialoogvenster Systeeminstellingen - Tabblad E-mail](https://docs.microsoft.com/dynamics365/customer-engagement/admin/system-settings-dialog-box-email-tab) |  
|**URL**|Zodra u de webresource hebt opgeslagen, wordt hier de URL naar de webresource weergegeven. Selecteer deze koppeling om de webresource in uw browser weer te geven.|  
  
Nadat u uw wijzigingen hebt toegevoegd, kiest u **Opslaan** en vervolgens **Publiceren**.  

> [!NOTE]
> Wijzigingen in een webresource worden pas weergegeven in de toepassing als u deze publiceert.
  
<a name="BKMK_UsingTextEditor"></a>
   
### <a name="use-the-text-editor-appropriately"></a>De teksteditor gebruiken

De teksteditor uit de toepassing voor webresources moet alleen worden gebruikt voor eenvoudige bewerkingen van tekstbestanden. U kunt deze gebruiken voor het maken en bewerken van HTML-webresources, maar u moet alleen HTML-webresources bewerken die met de teksteditor zijn gemaakt. De teksteditor is ontworpen voor zeer eenvoudige HTML-inhoud. 

> [!IMPORTANT]
> Als de inhoud van een HTML-webresource niet met de teksteditor is gemaakt, gebruikt u niet de teksteditor om deze te bewerken.  
> De teksteditor gebruikt een besturingselement waarmee de HTML-bron zo wordt gewijzigd dat deze kan worden bewerkt. Deze wijzigingen kunnen de pagina anders laten werken in de browser en kunnen ertoe leiden dat geavanceerde code niet meer werkt. Het openen en opslaan van een HTML-resource zonder wijzigingen aan te brengen kan bepaalde HTML-webresources beschadigen.  Meer informatie: [Documentatie voor ontwikkelaars: De teksteditor gebruiken voor HTML-webresources](/dynamics365/customer-engagement/developer/webpage-html-web-resources#use-the-text-editor-for-html-web-resources)
  
We raden u aan een externe toepassing te gebruiken om tekstbestanden te bewerken en ze vervolgens lokaal op te slaan voordat u ze uploadt met de knop **Bestand uploaden**. Zo kunt u een kopie van de webresource behouden als u naar een eerdere versie moet terugkeren. U kunt een eenvoudige editor zoals Kladblok gebruiken, maar een teksteditor met meer geavanceerde mogelijkheden wordt sterk aanbevolen. [Visual Studio Community](https://www.visualstudio.com/vs/community/) en [Visual Studio Code](https://code.visualstudio.com/) zijn gratis en bieden krachtige mogelijkheden voor het bewerken van de tekstbestanden die worden gebruikt door webresources.  

<a name="BKMK_CreateAndEditFormWebResources"></a>
 
## <a name="create-and-edit-a-web-resource-on-a-form"></a>Een webresource maken en bewerken in een formulier

U kunt webresources toevoegen aan of bewerken in een formulier om het aantrekkelijker en bruikbaarder te maken voor gebruikers. 

> [!NOTE]
> U kunt een webresource niet opnemen in een formulierkoptekst of -voettekst.  

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

### <a name="navigate-to-a-form"></a>Navigeren naar een formulier
In de geopende oplossingenverkenner vouwt u onder **Onderdelen** achtereenvolgens **Entiteiten** en de entiteit waarmee u wilt werken uit.

Kies **Formulieren**, zoek in de lijst een formulier van het type Hoofd en dubbelklik of tik vervolgens op het item om het formulier te openen en te bewerken.

### <a name="add-or-edit-web-resource-in-a-form"></a>Een webresource in een formulier toevoegen of bewerken

Zie [Eigenschappen van webresource](web-resource-properties-legacy.md) voor informatie over de eigenschappen die u kunt instellen voor webresources in een formulier.

### <a name="preview"></a>Voorbeeld weergeven

U kunt als volgt vooraf bekijken hoe het hoofdformulier wordt weergegeven en hoe gebeurtenissen werken:
- Selecteer op het tabblad **Start** de optie **Voorbeeld** en selecteer vervolgens **Formulier maken**, **Formulier bijwerken** of **Alleen-lezen formulier**.
- Als u het formulier Voorbeeld wilt sluiten, selecteert u **Sluiten** in het menu **Bestand**.

### <a name="save"></a>Opslaan

Als u klaar bent met het bewerken van het formulier, selecteert u op het tabblad **Start** de optie **Opslaan en sluiten** om het formulier te sluiten. 

### <a name="publish"></a>Publiceren

Als de aanpassingen zijn voltooid, publiceert u deze:
- Als u alleen aanpassingen wilt publiceren voor het onderdeel dat u momenteel bewerkt, selecteert u in het navigatiedeelvenster de entiteit waaraan u hebt gewerkt en vervolgens **Publiceren**.
- Als u aanpassingen wilt publiceren voor alle niet-gepubliceerde onderdelen tegelijk, selecteert u **Entiteiten** in het navigatiedeelvenster en **Alle aanpassingen publiceren** op de werkbalk **Acties**.
   
  
### <a name="see-also"></a>Zie ook  

[Webresource-eigenschappen](web-resource-properties-legacy.md) <br /> 
[Formulieren maken en ontwerpen](create-design-forms.md) <br />
[Inzicht krijgen in onderdelen van modelgestuurde apps](model-driven-app-components.md) <br /> 
[Documentatie voor ontwikkelaars: Webresources voor Customer Engagement](/dynamics365/customer-engagement/developer/web-resources)
