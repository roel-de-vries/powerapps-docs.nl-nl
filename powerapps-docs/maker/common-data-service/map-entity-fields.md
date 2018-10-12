---
title: Entiteitsvelden koppelen in PowerApps | Microsoft Docs
description: Meer informatie over het koppelen van entiteitsvelden
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
tags: ''
ms.openlocfilehash: 7e84e10a824ea218063cb2dccdc15ed7ae2340da
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39680620"
---
# <a name="map-entity-fields"></a>Entiteitsvelden koppelen
 
U kunt kenmerken koppelen tussen entiteiten waarvoor een entiteitsrelatie bestaat. Hiermee kunt u standaardwaarden instellen voor een record die wordt gemaakt in de context van een andere record. 

## <a name="easier-way-to-create-new-records-in-model-driven-apps"></a>Een eenvoudigere manier om nieuwe records te maken in modelgestuurde apps

Stel dat iemand een nieuwe contactpersonenrecord wil toevoegen voor een persoon een werknemer voor een specifiek account. Dit kan op twee verschillende manieren:  
  
### <a name="the-hard-way"></a>De moeilijke manier

Deze persoon kan in de app naar de gebruikelijke plek gaan om een volledig nieuwe contactpersonenrecord te maken. Maar in dit geval zullen het bovenliggende account en verschillende andere gegevens (zoals adres en telefoonnummer) moeten worden ingesteld, die waarschijnlijk hetzelfde zijn als het bovenliggende account. Dit kan veel tijd kosten en er kunnen fouten worden gemaakt.  
  
### <a name="the-easier-way"></a>De eenvoudigere manier

Het is eenvoudiger om te beginnen met de accountentiteit en vervolgens, met behulp van het subraster **Contactpersonen** in het formulier, **+** te selecteren om een contactpersoon toe te voegen. Hierbij wordt eerst gestimuleerd dat mensen bestaande gerelateerde contactpersonen zoeken, zodat ze niet per ongeluk een dubbele record maken. Als er geen bestaande record wordt gevonden, kan de gebruiker **Nieuw** selecteren en een nieuwe contactpersonenrecord maken. 

Het formulier voor de nieuwe contactpersonenrecord bevat dan eventuele toegewezen kenmerkwaarden van het account (zoals adres en telefoonnummer) als standaardwaarden. Gebruikers kunnen deze waarden bewerken voordat ze de record opslaan.

## <a name="how-this-works"></a>Hoe dit werkt

Wanneer u entiteitsvelden koppelt voor een 1:N-relatie tussen entiteiten worden bepaalde gegevensitems uit de primaire entiteitsrecord gekopieerd naar het formulier voor de nieuwe gerelateerde entiteit, waarmee standaardwaarden worden ingesteld die gebruikers kunnen bewerken voordat ze de record opslaan.
 
  
> [!NOTE]
> Deze toewijzingen kopiëren alleen standaardwaarden naar een record voordat deze wordt opgeslagen. Mensen kunnen de waarden bewerken voordat ze de record opslaan. De gegevens die worden verzonden zijn de gegevens zoals ze op dat moment zijn. Ze worden niet gesynchroniseerd als de brongegevens later worden gewijzigd.
>   
> Deze toewijzingen worden niet toegepast op gerelateerde records die worden gemaakt met behulp van een werkstroom of een dialoogproces. Ze worden niet automatisch toegepast op nieuwe records die worden gemaakt met behulp van code, hoewel ontwikkelaars een speciaal bericht kunnen gebruiken, `InitializeFrom` ([functie InitializeFrom](/dynamics365/customer-engagement/web-api/initializefrom?view=dynamics-ce-odata-9) of [klasse InitializeFromRequest](/dotnet/api/microsoft.crm.sdk.messages.initializefromrequest?view=dynamics-general-ce-9)), om een nieuwe record te maken met behulp van de beschikbare toewijzingen.  

## <a name="open-solution-explorer"></a>Solution Explorer openen

De enige manier om entiteitsvelden toe te wijzen is met behulp van Solution Explorer.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]
  
Het toewijzen van velden vindt plaats in de context van een 1:N- of N:1-entiteitsrelatie, dus u moet eerst de [1:N- of N:1-entiteitsrelaties weergeven](create-edit-1n-relationships-solution-explorer.md#view-entity-relationships).

## <a name="view-mappable-fields"></a>Toewijsbare velden weergeven

Veldtoewijzingen worden in feite niet gedefinieerd binnen de entiteitsrelaties, maar deze worden inzichtelijk gemaakt in de gebruikersinterface van de relatie. Niet elke 1:N-entiteitsrelatie heeft ze. Wanneer u een lijst met 1:N (of N:1)-entiteitsrelaties voor een entiteit bekijkt, kunt u de weergegeven relaties filteren op type. U kunt hiervoor kiezen uit **Alle**, **Aangepast**, **Aanpasbaar** of **Toewijsbaar**. Toewijsbare entiteitsrelaties bieden toegang om entiteitsvelden toe te wijzen. 

![Toewijsbare entiteitsrelaties bekijken](media/mappable-entity-relationships.png) 

Wanneer u een toewijsbare entiteitsrelatie opent, selecteert u **Toewijzingen** in het linkernavigatievenster.

![Toewijzingen voor de entiteitsrelatie selecteren](media/map-entity-fields-ui-solution-explorer.png)

## <a name="delete-mappings"></a>Toewijzingen verwijderen

Als er toewijzingen zijn die u niet wilt toepassen, kunt u deze selecteren en klikken op het pictogram ![Pictogram voor verwijderen](media/delete.gif) .

## <a name="add-new-mappings"></a>Nieuwe toewijzingen toevoegen

Klik in de werkbalk op **Nieuw** om een nieuwe toewijzing te maken. Hiermee opent u het dialoogvenster **Veldtoewijzing maken**.

![Dialoogvenster Veldtoewijzing maken](media/create-field-mapping-dialog.png)

Selecteer een bronentiteitsveld en een doelentiteitsvelden met waarden die u wilt koppelen. 

![Veldtoewijzing configureren](media/configure-field-mapping.png)

Selecteer vervolgens **OK** om het dialoogvenster te sluiten.

De volgende regels laten zien welke soorten gegevens kunnen worden gekoppeld.  
  
- Beide velden moeten hetzelfde type en in de dezelfde indeling zijn.  
- De lengte van het doelveld moet gelijk aan of groter dan de lengte van het bronveld zijn.  
- Het doelveld mag nog niet aan een ander veld zijn gekoppeld.  
- Het bronveld moet worden weergegeven op het formulier.  
- Het doelveld moet een veld zijn waarin een gebruiker gegevens kan invoeren.  
- Id-waarden voor adressen kunnen niet worden toegewezen.
- Als u een toewijzing maakt naar of van een veld dat niet wordt weergegeven op een formulier, wordt de toewijzing niet uitgevoerd totdat het veld wordt toegevoegd aan een formulier.
- Als de velden Optiesets zijn, moeten de waarden (in gehele getallen) voor elke optie identiek zijn.  
  
> [!NOTE]
>  Als u velden voor optiesets moet toewijzen, raden wij aan dat u beide velden zo configureert dat ze dezelfde algemene optieset gebruiken. Anders kan het lastig zijn om twee verschillende sets met opties handmatig gesynchroniseerd te houden. Als de waarden voor elke optie (in gehele getallen) niet correct worden toegewezen, kunt u problemen in uw gegevens veroorzaken. Meer informatie: [Globale optiesets maken en bewerken voor Common Data Service voor apps (selectielijsten)](create-edit-global-option-sets.md)  
  
## <a name="automatically-generate-field-mappings"></a>Automatisch veldtoewijzingen genereren  

U kunt ook automatisch toewijzingen genereren door **Toewijzingen genereren** te selecteren in het menu **Meer acties**.

Wees voorzichtig wanneer u dit doet met systeementiteiten. Gebruik deze instelling als u aangepaste entiteiten wilt maken en hiervoor toewijzingen wilt gebruiken. 

> [!WARNING]
> Hiermee verwijdert u alle bestaande toewijzingen en vervangt u deze door voorgestelde toewijzingen die alleen zijn gebaseerd op de velden met vergelijkbare namen en gegevenstypen. Als u dit op een systeementiteit gebruikt, is het mogelijk dat enkele verwachte toewijzingen verloren gaan. Voor aangepaste entiteiten kunt u zo tijd besparen omdat u makkelijker eventuele toewijzingen die u niet wilt kunt verwijderen en andere kunt toevoegen die niet werden gemaakt bij het genereren van de toewijzingen.  


## <a name="publish-customizations"></a>Aanpassingen publiceren 

Omdat veldtoewijzingen geen metagegevens zijn, moet u ze publiceren voordat wijzigingen van kracht worden. 
<!-- TODO Need a general topic about publishing to link to in situations like this -->

### <a name="see-also"></a>Zie ook
[1:N (een-op-veel)- of N:1 (veel-op-een)-relaties maken of bewerken met behulp van Solution Explorer](create-edit-1n-relationships-solution-explorer.md)<br />
[Documentatie voor ontwikkelaars: Entiteiten en kenmerktoewijzingen aanpassen](/dynamics365/customer-engagement/developer/customize-entity-attribute-mappings)<br />
[Documentatie voor ontwikkelaars: Web-API - Een nieuwe entiteit maken op basis van een andere entiteit](/dynamics365/customer-engagement/developer/webapi/create-entity-web-api#create-a-new-entity-from-another-entity)
