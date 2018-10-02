---
title: Webresource-eigenschappen voor hoofdformulieren voor modelgestuurde apps in PowerApps | MicrosoftDocs
description: Verkrijg inzicht in de eigenschappen van webresources voor hoofdformulieren
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="web-resource-properties-for-model-driven-app-forms"></a>Webresource-eigenschappen voor formulieren voor modelgestuurde apps

U kunt webresources toevoegen aan of bewerken in een formulier om het aantrekkelijker en bruikbaarder te maken voor app-gebruikers. Webresources met formulieren zijn besturingselementen voor afbeeldingen of HTML-bestanden.

> [!NOTE]
> Silverlight-webresources zijn afgeschaft en werken niet in de Unified Interface-client.

## <a name="access-web-resource-properties"></a>Webresource-eigenschappen openen

Als u een formulier weergeeft:
- **Als u een webresource wilt toevoegen:**: selecteer het tabblad (bijvoorbeeld **Algemeen** of **Notities**) waarop u de resource wilt toevoegen en selecteer op het tabblad **Invoegen** de optie **Webresource**.<br />![Webresource invoegen](media/insert-web-resource.png)
- **Als u een webresource wilt bewerken**: selecteer een formuliertabblad en de webresource die u wilt bewerken. Vervolgens selecteert u op het tabblad **Start** de optie **Eigenschappen wijzigen**. <br />![Webresource-eigenschappen wijzigen](media/web-resource-change-properties.png)

Het dialoogvenster **Webresource toevoegen** of **Eigenschappen van webresource** wordt geopend.

![Dialoogvenster Webresource toevoegen](media/add-web-resource-dialog.png)


## <a name="web-resource-properties"></a>Webresource-eigenschappen

 Het dialoogvenster **Webresource toevoegen** of **Eigenschappen van webresource** bevat meestal twee en in sommige gevallen drie tabbladen, afhankelijk van het type webresource.

### <a name="general-tab"></a>Tabblad Algemeen

Deze eigenschappen definiëren welke webresource moet worden gebruikt en hoe deze zich moet gedragen.

|Veld|Beschrijving|
|--|--|
|**Webresource**|*Vereist.* Zoek een bestaande webresource op of maak een nieuwe. Gebruik de weergave **Webresource met formulier** om alleen HTML- en afbeeldingswebresources op te nemen die als visuele elementen aan een formulier kunnen worden toegevoegd.|
|**Name**|*Vereist.* Geef een naam op voor het webresourcebesturingselement dat aan het formulier wordt toegevoegd. Met deze waarde wordt het besturingselement in het formulier uniek geïdentificeerd.|
|**Label**|*Vereist.* Automatisch gegenereerd op basis van de waarde van het veld **Naam**. Geef lokaliseerbare tekst op voor het webresourcebesturingselement dat aan het formulier wordt toegevoegd. Selecteer **Label in het formulier weergeven** als u dit zichtbaar wilt maken.|
|**Standaard zichtbaar**|Als dit is ingeschakeld, is de webresource zichtbaar wanneer het formulier wordt geladen. Voor een bedrijfsregel of formulierscript waarvoor de webresource als noodzakelijk wordt weergegeven, schakelt u dit veld uit. Meer informatie: [Formulierelementen weergeven of verbergen](visibility-options-legacy.md)|
|**Inschakelen voor mobiel**|Selecteer deze optie als deze webresource zichtbaar moet zijn in mobiele apps.|

Afhankelijk van het geselecteerde type webresource, kunt u aanvullende eigenschappen instellen.

Voor HTML-webresources krijgt u het volgende te zien:

![Eigenschappen van webresources](media/web-resource-general-html-properties.png)

|Veld|Beschrijving|
|--|--|
|**Aangepaste parameter(gegevens)**|Doorgaans configuratiegegevens die aan de HTML-webresource worden doorgegeven als querytekenreeksparameter `data`. Scripts die zijn gekoppeld aan de HTML-pagina hebben toegang tot deze gegevens en gebruiken deze om het gedrag van de pagina te wijzigen.|
|**Het uitvoeren van scripts tussen frames beperken, indien ondersteund**|Gebruik deze optie als u de inhoud in de HTML-webresource niet volledig vertrouwt. Meer informatie: [Documentatie voor ontwikkelaars: Selecteren of het uitvoeren van scripts tussen frames moet worden beperkt](/dynamics365/customer-engagement/developer/use-iframe-and-web-resource-controls-on-a-form#select-whether-to-restrict-cross-frame-scripting)|
|**Geef de recordobject-typecode en de unieke id als parameters door**|Gegevens over de huidige record die zichtbaar is in het formulier kunnen aan de HTML-webresourcepagina worden doorgegeven zodat het script dat op de pagina wordt uitgevoerd toegang tot gegevens over de record heeft. Zie voor meer informatie: <br />[Geef parameters door aan webresources](#pass-parameters-to-web-resources)<br />[Documentatie voor ontwikkelaars: Contextinformatie doorgeven over de huidige record](/dynamics365/customer-engagement/developer/use-iframe-and-web-resource-controls-on-a-form#pass-contextual-information-about-the-record)|

Voor afbeeldingswebresources kunt u de optie **Alternatieve tekst** gebruiken. Deze optie is belangrijk voor ondersteunende technologieën die de pagina voor iedereen toegankelijk maken.

<!-- TODO: Why are Custom Parameters available to pass to image web resources? -->

### <a name="formatting-tab"></a>Tabblad Opmaak

Op het tabblad **Opmaak** verschillen de opties die worden weergegeven op basis van het type webresource dat wordt ingevoegd en de context. Deze opties omvatten onder andere het opgeven van het aantal kolommen en rijen dat wordt weergegeven, of er een rand wordt weergegeven en het schuifgedrag.

![Eigenschappen voor indeling van webresource](media/web-resource-formatting-properties.png)

|Eigenschap|Beschrijving|  
|--------------|-----------------|
|**Selecteer het aantal kolommen dat het besturingselement in beslag neemt**|Als de sectie die de webresource bevat meer dan één kolom heeft, kunt u het veld zo instellen dat het evenveel kolommen bezet als sectie.|  
|**Selecteer het aantal rijen dat het besturingselement in beslag neemt**|U kunt de hoogte van de webresource bepalen door een aantal rijen op te geven of **Vouw automatisch uit om de beschikbare ruimte te gebruiken** te selecteren om de webresourcehoogte te baseren op de beschikbare ruimte.|  
|**Selecteer het schuiftype voor de IFrame**|Een HTML-webresource wordt toegevoegd aan het formulier via een IFrame.<br /><br /> - **Zo nodig**: Schuifbalken weergeven als de omvang van de webresource groter is dan beschikbaar.<br />- **Altijd**: Altijd schuifbalken weergeven.<br />- **Nooit**: Nooit schuifbalken weergeven.|  
|**Rand weergeven**|Geef een rand om de webresource weer.|  


### <a name="dependencies-tab"></a>Tabblad Afhankelijkheden

Er kan interactie bestaan tussen een webresource en velden in het formulier dat script gebruikt. Als een veld wordt verwijderd uit het formulier, dan kan het script in de websource worden onderbroken. Voeg velden toe waaraan door scripts gerefereerd wordt in de webresource aan de **Afhankelijke velden** zodat ze niet per ongeluk kunnen worden verwijderd.

![Eigenschappen voor afhankelijkheden van webresource](media/web-resource-dependency-properties.png)
  
<a name="BKMK_PassingParametersToWebResource"></a> 
 
## <a name="pass-parameters-to-web-resources"></a>Geef parameters door aan webresources 

Een HTML-webresource kan parameters accepteren die worden doorgegeven als queryreeksparameters.  
  
De gegevens over de record kunnen worden doorgegeven door de optie **Geef de typecode van het recordobject en de unieke id's als parameters door** in te schakelen. Als gegevens in het veld **Aangepaste parameter(gegevens)** worden ingevoerd, worden ze doorgegeven met behulp van de gegevensparameter. De doorgegeven waarden zijn:  
  
|Parameter|Beschrijving|  
|---------------|-----------------|  
|`data`|Deze parameter wordt alleen doorgegeven als er tekst voor **Aangepaste parameter(gegevens)** wordt geleverd.|  
|`orglcid`|De standaardtaal-LCID van de Organisatie.|  
|`orgname`|De naam van de organisatie.|  
|`userlcid`|De voorkeurstaal-LCID van de gebruiker|  
|`type`|**Gebruik dit niet.** De code van het entiteittype. Deze numerieke waarde kan voor aangepaste entiteiten in andere organisaties verschillend zijn. Gebruik in plaats daarvan de naam van het identiteittype.|  
|`typename`|De naam van het entiteittype.|  
|`id`|De id-waarde van de record. Deze parameter heeft geen waarde totdat de entiteitsrecord wordt opgeslagen.|  
  
Andere parameters zijn niet toegestaan en de webresource wordt niet geopend als andere parameters worden gebruikt. Als u meerdere waarden moet doorgeven, kan de gegevensparameter worden overbelast om er meer parameters in op te nemen.

Meer informatie: [Documentatie voor ontwikkelaars: Contextinformatie doorgeven over de huidige record](/dynamics365/customer-engagement/developer/use-iframe-and-web-resource-controls-on-a-form#pass-contextual-information-about-the-record)

### <a name="see-also"></a>Zie ook

[Webresources maken of bewerken om een app uit te breiden](create-edit-web-resources.md)<br />
[Het hoofdformulier en de onderdelen ervan gebruiken](use-main-form-and-components.md)
