---
title: Entiteitsvelden toewijzen in PowerApps | MicrosoftDocs
description: Lees hoe u entiteitsvelden kunt toewijzen
ms.custom: ''
ms.date: 05/29/2018
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
ms.assetid: 7c5aa1c3-bde9-43f1-a369-fdcdbf14dec0
caps.latest.revision: 33
ms.author: matp
manager: kvivek
tags: null
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="map-entity-fields"></a>Entiteitsvelden toewijzen
 
U kunt kenmerken toewijzen tussen entiteiten met een entiteitsrelatie. Hiermee kunt u standaardwaarden instellen voor een record die is gemaakt in de context van een andere record. 

## <a name="easier-way-to-create-new-records-in-model-driven-apps"></a>Eenvoudigere manier om nieuwe records te maken in modelgestuurde apps

Stel dat mensen een nieuwe contactpersoonrecord willen toevoegen voor een persoon die een werknemer voor een bepaalde account is. Dit kan op twee verschillende manieren:  
  
### <a name="the-hard-way"></a>De moeilijke manier

Mensen kunnen navigeren in de app om een nieuwe contactpersoonrecord te maken. Maar daarna moeten ze de bovenliggende account instellen en meerdere gegevensitems selecteren (zoals adres- en telefoongegevens) die waarschijnlijk overeenkomen met die van de bovenliggende account. Dit kan tijdrovend zijn en verhoogt het risico op fouten.  
  
### <a name="the-easier-way"></a>De eenvoudigere manier

Een eenvoudigere manier is met de accountentiteit te beginnen en, met behulp van het subraster **Contactpersonen** op het formulier, **+** te selecteren om een contactpersoon toe te voegen. Mensen worden dan eerst verzocht om reeds bestaande verwante contactpersonen op te zoeken zodat ze niet per ongeluk een dubbele record maken. Als ze geen bestaande record vinden, kunnen ze **Nieuw** selecteren en een nieuwe contactpersoonrecord maken. 

Het formulier met de nieuwe contactpersoonrecord bevat alle toegewezen kenmerkwaarden uit de account (zoals adres- en telefoongegevens) als standaardwaarden. Deze waarden kunnen worden bewerkt voordat de record wordt opgeslagen.

## <a name="how-this-works"></a>Hoe dit werkt

Als u entiteitsvelden voor een 1:N-entiteitsrelatie toewijst, worden bepaalde gegevensitems uit de record van de primaire entiteit naar het formulier voor de nieuwe gerelateerde entiteit gekopieerd om standaardwaarden in te stellen die mensen kunnen bewerken voordat ze opslaan.
 
  
> [!NOTE]
> Met deze toewijzingen worden alleen standaardwaarden op een record ingesteld voordat de record wordt opgeslagen. Mensen kunnen de waarden wijzigen alvorens ze op te slaan. De gegevens die worden overgebracht zijn de gegevens op dat moment. Deze worden niet gesynchroniseerd als de brongegevens later worden gewijzigd.
>   
> Deze toewijzingen worden niet toegepast op de verwante records die zijn gemaakt met een werkstroom of dialoogvensterproces. Ze worden niet automatisch toegepast op nieuwe records die gemaakt zijn met code, maar ontwikkelaars kunnen een speciaal bericht gebruiken dat `InitializeFrom` ([InitializeFrom Function](/dynamics365/customer-engagement/web-api/initializefrom?view=dynamics-ce-odata-9) of [InitializeFromRequest Class](/dotnet/api/microsoft.crm.sdk.messages.initializefromrequest?view=dynamics-general-ce-9)) heet om een nieuwe record te maken met behulp van beschikbare toewijzingen.  

## <a name="open-solution-explorer"></a>Open de oplossingenverkenner.

U kunt entiteitsvelden alleen toewijzen met de oplossingenverkenner.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]
  
De toewijzing van velden wordt gedaan in de context van 1:N- of N:1-entiteitsrelatie, dus eerst moet u [1:N- of N:1-entiteitsrelaties weergeven](create-edit-1n-relationships-solution-explorer.md#view-entity-relationships).

## <a name="view-mappable-fields"></a>Toewijsbare velden weergeven

Veldtoewijzingen worden niet daadwerkelijk gedefinieerd in de entiteitsrelaties, maar ze zijn beschikbaar in de relatiegebruikersinterface. Niet elke 1:N-entiteitsrelatie heeft ze. Als u een lijst met 1:N (or N:1)-entiteitsrelaties voor een entiteit weergeeft, kunt u de weergegeven relaties op type filteren. U kunt **Alle**, **Aangepast**, **Aanpasbaar** of **Kan worden toegewezen** selecteren. Entiteitsrelaties die kunnen worden toegewezen, bieden de mogelijkheid om entiteitsvelden toe te wijzen. 

![Toewijsbare entiteitsrelaties weergeven](media/mappable-entity-relationships.png) 

Wanneer u een toewijsbare entiteitsrelatie wilt openen, selecteert u **Toewijzingen** in de linkernavigatie.

![Toewijzingen selecteren voor de entiteitsrelatie](media/map-entity-fields-ui-solution-explorer.png)

## <a name="delete-mappings"></a>Toewijzingen verwijderen

Als er toewijzingen zijn die u niet wilt toepassen, kunt u deze selecteren en klikken op het ![pictogram Verwijderen](media/delete.gif) .

## <a name="add-new-mappings"></a>Nieuwe toewijzingen toevoegen

Als u een nieuwe toewijzing wilt maken, klikt u op de werkbalk op **Nieuw**. Het dialoogvenster **Veldtoewijzing maken** wordt geopend.

![Dialoogvenster Veldtoewijzing maken](media/create-field-mapping-dialog.png)

Selecteer een bronentiteitsveld en een doelentiteitsveld met waarden die u wilt toewijzen. 

![Veldtoewijzing configureren](media/configure-field-mapping.png)

Selecteer **OK** om het dialoogvenster te sluiten.

In de volgende regels ziet u welke soorten gegevens kunnen worden toegewezen.  
  
- Beide velden moeten van hetzelfde type zijn en dezelfde opmaak hebben.  
- De lengte van het doelveld moet gelijk zijn aan of groter zijn dan de lengte van het bronveld.  
- Het doelveld mag nog niet aan een ander veld zijn toegewezen.  
- Het bronveld moet zichtbaar zijn op het formulier.  
- Het doelveld moet een veld zijn waarin de gebruiker gegevens kan invoeren.  
- Adres-id-waarden kunnen niet worden toegewezen.
- Als u toewijst vanuit of naar een veld dat niet in een formulier wordt weergegeven, wordt de toewijzing pas uitgevoerd wanneer het veld aan een formulier is toegevoegd.
- Als de velden optiesets zijn, moet de geheel-getalwaarde voor alle opties identiek zijn.  
  
> [!NOTE]
>  Als u optiesetvelden moet toewijzen, raden we u aan beide velden te configureren zodat ze dezelfde algemene optieset. Anders is het wellicht moeilijk om twee verschillende optiesets handmatig te gesynchroniseren. Als de waarden met gehele getallen voor elke optie niet correct zijn toegewezen, kunnen zich problemen in uw gegevens voordoen. Meer informatie: [Algemene optiesets maken en bewerken voor Common Data Service voor Apps (selectielijsten)](create-edit-global-option-sets.md)  
  
## <a name="automatically-generate-field-mappings"></a>Veldtoewijzingen automatisch genereren  

U kunt toewijzingen ook automatisch genereren door **Toewijz. genereren** te selecteren in het menu **Meer acties**.

Ga zorgvuldig te werk wanneer u dit doet met systeementiteiten. Gebruik dit als u aangepaste entiteiten maakt en toewijzingen wilt instellen. 

> [!WARNING]
> Hiermee worden alle bestaande toewijzingen verwijderd en vervangen door voorgestelde toewijzingen die zijn gebaseerd op de velden met vergelijkbare namen en gegevenstypen. Als u dit op een systeementiteit gebruikt, kan het dat een aantal verwachte toewijzingen verloren gaan. Voor aangepaste entiteiten bespaart het tijd omdat u toewijzingen die u niet wilt makkelijker kunt verwijderen en andere kunt toevoegen die de actie Toewijzingen genereren niet heeft gemaakt.  


## <a name="publish-customizations"></a>Aanpassingen publiceren 

Aangezien veldtoewijzingen geen metagegevens zijn, moet u deze publiceren voordat de wijzigingen van kracht worden. 
<!-- TODO Need a general topic about publishing to link to in situations like this -->

### <a name="see-also"></a>Zie ook
[1:N- (één-op-veel) of N:1-entiteitsrelaties (veel-op-één) maken en bewerken met de oplossingenverkenner](create-edit-1n-relationships-solution-explorer.md)<br />
[Documentatie voor ontwikkelaars: Entiteits- en kenmerktoewijzingen aanpassen](/dynamics365/customer-engagement/developer/customize-entity-attribute-mappings)<br />
[Documentatie voor ontwikkelaars: Een nieuwe entiteit maken op basis van een andere entiteit](/dynamics365/customer-engagement/developer/webapi/create-entity-web-api#create-a-new-entity-from-another-entity)
