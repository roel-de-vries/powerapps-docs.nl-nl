---
title: Modelgestuurde app-webresources maken of bewerken in PowerApps | MicrosoftDocs
description: Instructies voor het maken of bewerken van webresources
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
ms.openlocfilehash: 8d9414ba4c900f98ac26010e4e6d7240b336e2d7
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39679900"
---
# <a name="create-or-edit-model-driven-app-web-resources-to-extend-an-app"></a>Modelgestuurde app-webresources maken of bewerken om een app uit te breiden

Webresources worden doorgaans gebruikt door ontwikkelaars die een app willen uitbreiden met behulp van bestanden die voor webontwikkeling worden gebruikt. Het kan gebeuren dat app-gebruikers webresources moeten beheren die door een ontwikkelaar of designer zijn aangeleverd.  

> [!TIP]
> Raadpleeg [Documentatie voor ontwikkelaars: webresources voor Customer Engagement](/dynamics365/customer-engagement/developer/web-resources) voor een uitgebreide beschrijving van webresources.<br /> Raadpleeg [Documentatie voor ontwikkelaars: webresource-afhankelijkheden](/dynamics365/customer-engagement/developer/web-resources) voor informatie over webresource-afhankelijkheden die in PowerApps zijn toegevoegd.
   
<a name="BKMK_WhatAreWebResources"></a>

## <a name="what-are-web-resources"></a>Wat zijn webresources?  

Webresources zijn virtuele bestanden die in het systeem zijn opgeslagen. Elke webresource heeft een unieke naam die in een URL kan worden gebruikt om het bestand op te halen. Zie het als volgt: als u toegang hebt tot de daadwerkelijke webserver waarop de web-app wordt uitgevoerd, kunt u bestanden naar die website kopiëren. Met de meeste onlineservices is dit echter niet mogelijk.  In plaats daarvan kunt u webresources gebruiken om bestanden naar het systeem te uploaden en er vervolgens op naam naar verwijzen, net alsof u ze als bestanden naar de webserver had gekopieerd.  
  
Als u bijvoorbeeld een HTML-pagina als webresource maakt en deze de naam 'new_myWebResource.htm' geeft, kunt u die pagina in een browser openen met een URL zoals deze:  
 
`<base URL>/WebResources/new_myWebResource.htm   `
  
waarbij *\<base URL>* het deel van de URL is dat u gebruikt om apps weer te geven die eindigen op `dynamics.com`. Omdat webresource als gegevens in het systeem staan, hebben alleen gelicentieerde gebruikers voor uw organisatie op deze manier toegang tot deze webresources. Normaal gesproken wordt er niet rechtstreeks naar webresources verwezen, maar worden ze ingesloten in formulieren. Ze worden het meest gebruikt om JavaScript-bibliotheken voor formulierscripts te leveren.  
    
Omdat webresources gegevens in het systeem zijn en afhankelijk zijn van oplossingen, kunt u ze naar verschillende organisaties verplaatsen door ze als onderdeel van een oplossing te exporteren en de oplossing in een andere organisatie te importeren. U kunt de oplossingsverkenner gebruiken om met webresources te werken.
  
## <a name="open-solution-explorer"></a>Solution Explorer openen

Een deel van de naam van webresources die u maakt, bestaat uit het aanpassingsvoorvoegsel. Dit wordt ingesteld op basis van het publicatieprogramma voor de oplossing waarin u werkt. Als u geïnteresseerd bent in het aanpassingsvoorvoegsel, moet u ervoor zorgen dat u in een niet-beheerde oplossing werkt waarbij het aanpassingsvoorvoegsel het voorvoegsel is dat u voor webresource wilt gebruiken. Meer informatie: [Het publicatievoorvoegsel van de oplossing wijzigen](../common-data-service/change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

## <a name="view-web-resources"></a>Webresources weergeven

Zorg ervoor dat de oplossingsverkenner is geopend en selecteer **Webresources** onder **Onderdelen**.

![Webresources weergeven](media/view-web-resources-solution-explorer.png)

<a name="BKMK_CreateAndEditWebResources"></a>

## <a name="create-or-edit-web-resources"></a>Webresources maken of bewerken  

Terwijl u [webresources bekijkt](#view-web-resources), selecteert u **Nieuw** om een nieuwe webresource te maken, of dubbelklikt u op een bestaande webresource om deze te bewerken.

![Nieuw webresourceformulier](media/new-web-resource-form.png)

Vul het formulier in om de webresource te maken of te bewerken:
  
|Veld|Beschrijving|  
|-----------|-----------------|  
|**Naam**|*Vereist*. Dit is de unieke naam voor deze webresource. U kunt dit niet meer wijzigen zodra de webresource is opgeslagen.<br />&bull; Deze naam mag alleen letters, cijfers, punten en niet-opeenvolgende schuine strepen (/) bevatten.<br /> &bull; Het aanpassingsvoorvoegsel voor publicatie van de oplossing wordt aan het begin van de naam van de webresource toegevoegd.|  
|**Weergavenaam**|De naam die wordt weergegeven als u een lijst met webresources bekijkt.|  
|**Description**|Een beschrijving van de webresource.|  
|**Type**|*Vereist*. Dit is het type webresource. U kunt dit niet meer wijzigen zodra de webresource is opgeslagen.|  
|**Teksteditor**|Wanneer het type webresource een soort tekstbestand is, selecteert u deze knop om een pagina te openen zodat u de inhoud met behulp van een teksteditor kunt bewerken.<br />Meer informatie: [De teksteditor goed gebruiken](#use-the-text-editor-appropriately)| 
|**Taal**|Hiermee kunt u een taal selecteren. Met deze optie wordt alleen een tag aan de record toegevoegd waarin de webresourcegegevens zijn opgeslagen. Het gedrag van de webresource wordt niet veranderd.|  
|**Bestand uploaden**|Selecteer de knop **Bladeren...** om een bestand te selecteren dat u als webresource wilt uploaden.<br />&bull; U kunt een bestand uploaden wanneer u een nieuwe webresource maakt of om een bestaande webresource te overschrijven.<br />&bull; De bestandsnaamextensie van het bestand moet overeenkomen met de toegestane extensies.<br />&bull; Standaard mag een bestand dat als webresource kan worden geüpload maximaal 5 MB groot zijn. Deze waarde kan worden aangepast in Dynamics 365 Customer Engagement met behulp van de instelling **Systeeminstellingen** > **E-mail**-tabblad > **Limiet bestandsgrootte voor bijlagen instellen**. Meer informatie: [Het dialoogvenster Systeeminstellingen - het tabblad E-mail](https://docs.microsoft.com/dynamics365/customer-engagement/admin/system-settings-dialog-box-email-tab) |  
|**URL**|Nadat u de webresource hebt opgeslagen, wordt de URL naar de webresource hier weergegeven. Selecteer deze koppeling om de webresource in uw browser weer te geven.|  
  
Nadat u uw wijzigingen hebt toegevoegd, kiest u **Opslaan** en vervolgens **Publiceren**.  

> [!NOTE]
> Wijzigingen in een webresource zijn pas zichtbaar in de toepassing wanneer u deze publiceert.
  
<a name="BKMK_UsingTextEditor"></a>
   
### <a name="use-the-text-editor-appropriately"></a>De teksteditor goed gebruiken

De teksteditor die in de toepassing voor webresources wordt aangeboden, mag alleen worden gebruikt voor eenvoudige bewerkingen van tekstbestanden. U kunt de editor gebruiken om HTML-webresources te maken en te bewerken, maar u mag alleen HTML-webresources bewerken die met de teksteditor zijn gemaakt. De teksteditor is alleen ontworpen voor heel eenvoudige HTML-inhoud. 

> [!IMPORTANT]
> Als de inhoud of een HTML-webresource niet met de teksteditor is gemaakt, kunt u de teksteditor niet gebruiken om dit te bewerken.  
> De teksteditor gebruikt een besturingselement waarmee de HTML-bron zodanig wordt aangepast dat u deze kunt bewerken. Door deze wijzigingen kan de pagina zich in de browser anders gedragen en ervoor zorgen dat geavanceerdere code niet meer werkt. Wanneer u een HTML-webresource met de teksteditor opent en opslaat zonder wijzigingen aan te brengen, kunnen sommige HTML-webresources worden afgebroken.  Meer informatie: [Documentatie voor ontwikkelaars: De teksteditor voor HTML-webresources gebruiken](/dynamics365/customer-engagement/developer/webpage-html-web-resources#use-the-text-editor-for-html-web-resources)
  
Het wordt aanbevolen een externe editor te gebruiken om tekstbestanden te bewerken en ze vervolgens lokaal op te slaan voordat u ze met de knop **Bestand uploaden** gaat uploaden. Op deze manier kunt u een kopie van de webresource behouden als u naar een eerdere versie wilt terugkeren. U kunt een eenvoudige editor zoals Notepad gebruiken, maar een teksteditor met geavanceerdere mogelijkheden wordt ten zeerste aangeraden. [Visual Studio Community](https://www.visualstudio.com/vs/community/) en [Visual Studio Code](https://code.visualstudio.com/) zijn gratis en bieden krachtige mogelijkheden om de op tekst gebaseerde bestanden die door webresources worden gebruikt te bewerken.  

<a name="BKMK_CreateAndEditFormWebResources"></a>
 
## <a name="create-and-edit-a-web-resource-on-a-form"></a>Een webresource op een formulier maken en bewerken

U kunt webresources op een formulier toevoegen of bewerken om deze aantrekkelijker of nuttiger te maken voor gebruikers. 

> [!NOTE]
> U kunt geen webresource in de voet- of koptekst van een formulier invoegen.  

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

### <a name="navigate-to-a-form"></a>Naar een formulier navigeren
Zorg ervoor dat de oplossingsverkenner is geopend en vouw onder **Onderdelen** de optie **Entiteiten** uit. Vouw daarna de entiteit uit waarmee u wilt werken.

Kies **Formulieren**, zoek in de lijst naar een formulier van het type Hoofd en dubbelklik of tik vervolgens op de vermelding om het formulier te openen en te bewerken.

### <a name="add-or-edit-web-resource-in-a-form"></a>Webresources in een formulier toevoegen of bewerken

Zie [Eigenschappen webresource](web-resource-properties-legacy.md) voor informatie over de eigenschappen die u kunt instellen voor webresources in een formulier.

### <a name="preview"></a>Preview

U kunt als volgt een voorbeeld bekijken van de weergave van het hoofdformulier en hoe gebeurtenissen werken:
- Ga naar het tabblad **Home** en selecteer **Preview**. Selecteer vervolgens **Formulier maken**, **Formulier bijwerken** of **Alleen-lezen formulier**.
- Als u het Preview-formulier wilt sluiten, gaat u naar het menu **Bestand** en selecteert u **Sluiten**.

### <a name="save"></a>Opslaan

Wanneer u klaar bent met het bewerken van het formulier, selecteert u **Opslaan en sluiten** op het tabblad **Home** om het formulier te sluiten. 

### <a name="publish"></a>Publiceren

Wanneer uw aanpassingen zijn voltooid, gaat u ze publiceren:
- Als u aanpassingen voor alleen het momenteel bewerkte component wilt publiceren, selecteert u de entiteit waaraan u hebt gewerkt in het navigatiedeelvenster en selecteert u vervolgens **Publiceren**.
- Als u aanpassingen voor alle niet-gepubliceerde onderdelen in één keer wilt publiceren, selecteert u **Entiteiten** in het navigatiedeelvenster en vervolgens **Alle aanpassingen publiceren** op de werkbalk **Acties**.
   
  
### <a name="see-also"></a>Zie ook  

[Eigenschappen webresource](web-resource-properties-legacy.md) <br /> 
[Formulieren maken en ontwerpen](create-design-forms.md) <br />
[Aan de slag met aanpassen](getting-started-customization.md) <br /> 
[Documentatie voor ontwikkelaars: webresources voor Customer Engagement](/dynamics365/customer-engagement/developer/web-resources)
