---
title: Webresource-eigenschappen voor hoofdformulieren van modelgestuurde apps in PowerApps | MicrosoftDocs
description: Informatie over de webresource-eigenschappen voor hoofdformulieren
Keywords: Main form; Web resource properties; Dynamics 365
author: Mattp123
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.author: matp
manager: kvivek
ms.date: 06/27/2018
ms.service: crm-online
ms.topic: article
ms.assetid: 82cd41ea-95b0-4606-9e7d-43eb5ce9ecd6
ms.openlocfilehash: a08ca32b1d300d4302064940e65fd1d067c3ade6
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39679391"
---
# <a name="web-resource-properties-for-model-driven-app-forms"></a>Webresource-eigenschappen voor formulieren van modelgestuurde apps

U kunt webresources op een formulier toevoegen of bewerken om deze aantrekkelijker of nuttiger te maken voor app-gebruikers. Webresources met een formulier zijn installatiekopieën of besturingselementen voor HTML-bestanden.

> [!NOTE]
> Silverlight-webresources zijn afgeschaft en werken niet in de Unified Interface-client.

## <a name="access-web-resource-properties"></a>Webresource-eigenschappen openen

Tijdens het bekijken van een formulier:
- **Wanneer u een webresource toevoegt**: Selecteer het tabblad (bijvoorbeeld **Algemeen** of **Opmerkingen**) waar u de resource wilt invoegen, klik op het tabblad **Invoegen** en selecteer **Webresource**.<br />![Webresource invoegen](media/insert-web-resource.png)
- **Wanneer u een webresource bewerkt**: Selecteer een formuliertabblad en de webresource die u wilt bewerken, ga naar het tabblad **Start** en selecteer **Eigenschappen wijzigen**. <br />![Webresource-eigenschappen wijzigen](media/web-resource-change-properties.png)

Hiermee opent u het dialoogvenster **Webresource toevoegen** of **Webresource-eigenschappen**.

![Dialoogvenster Webresource toevoegen](media/add-web-resource-dialog.png)


## <a name="web-resource-properties"></a>Webresource-eigenschappen

 Het dialoogvenster **Webresource toevoegen** of **Webresource-eigenschappen** bevat twee, of soms drie tabbladen, afhankelijk van het type webresource.

### <a name="general-tab"></a>Tabblad Algemeen

Deze eigenschappen definiëren de webresource die moet worden gebruikt en hoe deze zich moet gedragen.

|Veld|Beschrijving|
|--|--|
|**Webresource**|*Vereist.* Zoek een bestaande webresource of maak een nieuwe. Gebruik de weergave **Webresource met formulier** om alleen HTML- en afbeeldingswebresources op te nemen die als visueel element aan een formulier kunnen worden toegevoegd.|
|**Naam**|*Vereist.* Geef een naam op voor het besturingselement voor webresources dat aan het formulier wordt toegevoegd. Deze waarde vormt een unieke aanduiding van het besturingselement in het formulier.|
|**Label**|*Vereist.* Automatisch gegenereerd op basis van de waarde in het veld **Naam**. Geef lokaliseerbare tekst op voor het besturingselement dat aan het formulier wordt toegevoegd. Selecteer **Label in het formulier weergeven** als u dit zichtbaar wilt maken.|
|**Standaard zichtbaar**|Als deze optie is ingeschakeld, wordt de webresource zichtbaar wanneer het formulier wordt geladen. Als u een bedrijfsregel hebt die, of een formulierscript dat de webresource naar behoefte weergeeft, deselecteert u dit veld. Meer informatie: [Formulierelementen weergeven of verbergen](visibility-options-legacy.md)|
|**Inschakelen voor mobiel**|Selecteer deze optie om ervoor te zorgen dat deze webresource zichtbaar is in mobiele apps.|

Stel, afhankelijk van het type webresource dat u selecteert, aanvullende eigenschappen in.

Voor HTML-webresources krijgt u deze te zien:

![Eigenschappen van HTML-webresources](media/web-resource-general-html-properties.png)

|Veld|Beschrijving|
|--|--|
|**Aangepaste parameter(gegevens)**|Meestal configuratiegegevens die aan de HTML-webresource worden doorgegeven als tekenreeksparameter `data` van de query. Scripts die aan de HTML-pagina zijn gekoppeld hebben toegang tot deze gegevens en gebruiken die om het gedrag van de pagina te wijzigen.|
|**Het uitvoeren van scripts tussen frames beperken indien ondersteund**|Gebruik deze optie als u de inhoud in de HTML-webresource niet volledig vertrouwt. Meer informatie: [Documentatie voor ontwikkelaars: Geef aan of u het uitvoeren van scripts tussen frames wilt beperken](/dynamics365/customer-engagement/developer/use-iframe-and-web-resource-controls-on-a-form#select-whether-to-restrict-cross-frame-scripting)|
|**De typecode van het recordobject en de unieke id doorgeven als parameters**|De gegevens over de huidige record die zichtbaar zijn in het formulier, kunnen aan de pagina van de HTML-webresource worden doorgegeven, zodat het script dat op de pagina wordt uitgevoerd, toegang heeft tot gegevens over de record. Meer informatie: <br />[Parameters doorgeven aan webresources](#pass-parameters-to-web-resources)<br />[Documentatie voor ontwikkelaars: Contextuele informatie over de record doorgeven](/dynamics365/customer-engagement/developer/use-iframe-and-web-resource-controls-on-a-form#pass-contextual-information-about-the-record)|

Voor afbeeldingswebresources hebt u de mogelijkheid om **alternatieve tekst** op te geven die belangrijk is voor ondersteunende technologieën die ervoor zorgen dat iedereen toegang heeft tot de pagina.

<!-- TODO: Why are Custom Parameters available to pass to image web resources? -->

### <a name="formatting-tab"></a>Tabblad Opmaak

Op het tabblad **Opmaak** variëren de weergegeven opties op basis van het type webresource dat is ingevoerd en van de context waarin het is ingevoerd. Onder deze opties vallen bijvoorbeeld de mogelijkheid om op te geven hoeveel kolommen en rijen moeten worden weergegeven en of een rand moet worden weergegeven, en om het schuifgedrag te bepalen.

![Opmaakeigenschappen van webresources](media/web-resource-formatting-properties.png)

|Eigenschap|Beschrijving|  
|--------------|-----------------|
|**Selecteer het aantal kolommen dat het besturingselement in beslag neemt**|Als de sectie die de webresource bevat, uit meer dan één kolom bestaat, kunt u het veld zo instellen dat het evenveel kolommen in beslag neemt als de sectie.|  
|**Selecteer het aantal rijen dat het besturingselement in beslag neemt**|U kunt de hoogte van de webresource beheren door een aantal rijen op te geven of door **Automatisch uitvouwen om de beschikbare ruimte te gebruiken** te selecteren. Zo zorgt u ervoor dat de hoogte van de webresource wordt uitgevouwen naar de beschikbare ruimte.|  
|**Selecteer het schuiftype voor het IFRAME**|Er wordt een HTML-webresource aan het formulier toegevoegd met behulp van een IFRAME.<br /><br /> - **Zo nodig**: Schuifbalken weergeven wanneer de grootte van de webresource groter is dan de beschikbare ruimte.<br />- **Altijd**: Schuifbalken altijd weergegeven.<br />- **Nooit**: Schuifbalken nooit weergeven.|  
|**Rand weergeven**|Een rand weergeven rondom de webresource.|  


### <a name="dependencies-tab"></a>Tabblad Afhankelijkheden

Met behulp van een script kan een webresource communiceren met de velden in het formulier. Als een veld uit het formulier wordt verwijderd, wordt het script in de webresource mogelijk onderbroken. Voeg alle velden waar de scripts in de webresource naar verwijzen, toe aan de **Afhankelijke velden**, zodat deze niet per ongeluk kunnen worden verwijderd.

![Afhankelijkheidseigenschappen van webresources](media/web-resource-dependency-properties.png)
  
<a name="BKMK_PassingParametersToWebResource"></a> 
 
## <a name="pass-parameters-to-web-resources"></a>Parameters doorgeven aan webresources 

Een HTML-webresource kan ermee akkoord gaan dat parameters worden doorgegeven als tekenreeksparameter van een query.  
  
Als u de optie **De typecode van het recordobject en de unieke id doorgeven als parameters** inschakelt, kan informatie over de record worden doorgegeven. Als er informatie in het veld **Aangepaste parameter(gegevens)** wordt getypt, wordt die doorgegeven met behulp van de parameter data. De waarden die worden doorgegeven, zijn:  
  
|Parameter|Beschrijving|  
|---------------|-----------------|  
|`data`|Deze parameter wordt alleen doorgegeven als er tekst is opgegeven voor **Aangepaste parameter(gegevens)**.|  
|`orglcid`|De LCID van de standaardtaal van de organisatie.|  
|`orgname`|De naam van de organisatie.|  
|`userlcid`|De LCID van de voorkeurstaal van de gebruiker|  
|`type`|**Niet gebruiken.** De code van het entiteitstype. Deze numerieke waarde kan afwijken voor aangepaste entiteiten in verschillende organisaties. Gebruik in plaats daarvan de naam van het entiteitstype.|  
|`typename`|De naam van het entiteitstype.|  
|`id`|De id-waarde van de record. Deze parameter heeft geen waarde totdat de entiteitsrecord wordt opgeslagen.|  
  
Andere parameters zijn niet toegestaan en de webresource kan niet worden geopend als er andere parameters worden gebruikt. Als u meerdere waarden wilt doorgeven, kunt u de parameter data overbelasten, zodat er meer parameters in kunnen worden opgenomen.

Meer informatie: [Documentatie voor ontwikkelaars: Contextuele informatie over de record doorgeven](/dynamics365/customer-engagement/developer/use-iframe-and-web-resource-controls-on-a-form#pass-contextual-information-about-the-record)

### <a name="see-also"></a>Zie ook

[Webresources maken of bewerken om een app uit te breiden](create-edit-web-resources.md)<br />
[Het hoofdformulier en de bijbehorende onderdelen gebruiken](use-main-form-and-components.md)
