---
title: Entiteiten en metagegevens in Common Data Service voor Apps | MicrosoftDocs
description: Meer informatie over entiteiten en metagegevens in Common Data Service voor Apps
ms.custom: ''
ms.date: 05/30/2018
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
ms.assetid: 88b18946-474c-4c94-8e4c-27532f930757
caps.latest.revision: 28
ms.author: matp
manager: kvivek
ms.openlocfilehash: ef2f92865205fa7c97ada356edc70ac69a637e0f
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39681655"
---
# <a name="entities-and-metadata-in-common-data-service-for-apps"></a>Entiteiten en metagegevens in Common Data Service voor Apps

Common Data Service voor Apps is zo ontworpen dat u snel en eenvoudig een gegevensmodel voor uw toepassing kunt maken. Normaal gesproken zou u zich niet moeten hoeven bezighouden met sommige van de details over metagegevens die in dit onderwerp worden geïntroduceerd. Maar als u een beter begrip wilt krijgen in de manier waarop apps die CDS voor Apps gebruiken werken, of wanneer u wilt weten wat er mogelijk is, kan het begrijpen van de metagegevens die door CDS voor Apps worden gebruikt inzicht opleveren.

*Metagegevens* zijn gegevens over gegevens. CDS voor Apps biedt een flexibel platform voor u, omdat het relatief eenvoudig is om de definities van de gegevens die de omgeving gebruikt, te bewerken. In CDS voor Apps zijn de metagegevens een verzameling entiteiten. Entiteiten beschrijven de soorten gegevens die in de database zijn opgeslagen.  Elke entiteit komt overeen met een databasetabel en elk veld (ook bekend als kenmerk) binnen een entiteit vertegenwoordigt een kolom in die tabel. Entiteitmetagegevens bepalen welke soorten records u kunt maken en wat voor soort acties daarop kunnen worden uitgevoerd. Wanneer u de aanpassingshulpmiddelen gebruikt om entiteiten, velden en entiteitsrelaties te maken of te bewerken, bewerkt u deze metagegevens. 
  
Verschillende clients die mensen gebruiken om te werken met de gegevens in uw omgeving, zijn afhankelijk van de entiteitmetagegevens en passen zich aan wanneer u de metadata aanpast. Maar deze clients zijn ook afhankelijk van andere gegevens om te bepalen welke visuele elementen moeten worden weergegeven, welke aangepaste logica eventueel moet worden toegepast en hoe de beveiliging moet worden toegepast. Deze systeemgegevens worden ook opgeslagen binnen entiteiten, maar de entiteiten zelf zijn niet beschikbaar voor aanpassing.

In de [Entity Reference](/powerapps/developer/common-data-service/reference/about-entity-reference) kunt u meer informatie vinden over standaardentiteiten, kenmerken en entiteitsrelaties die standaard in CDS voor Apps zijn opgenomen.

> [!TIP]
> In de ontwerpfuncties die beschikbaar zijn voor het bewerken van metagegevens kunnen niet alle in de metagegevens gevonden details worden weergegeven. U kunt de modelgestuurde app **Browser voor metagegevens** installeren, waarmee u alle entiteiten en metagegevenseigenschappen kunt weergeven die in het systeem te vinden zijn. Meer informatie: [Bladeren door de metagegevens voor uw omgeving](https://docs.microsoft.com/dynamics365/customer-engagement/developer/browse-your-metadata).
  
<a name="BKMK_CreateNewOrUseExistingMetadata"></a>

## <a name="create-new-metadata-or-use-existing-metadata"></a>Nieuwe metagegevens maken of bestaande metagegevens gebruiken?

CDS voor Apps wordt geleverd met een aantal standaardentiteiten die de kernactiviteiten van bedrijfstoepassingen ondersteunen. Zo zijn de entiteiten account of contactpersoon bijvoorbeeld bedoeld om gegevens over uw klanten of potentiële klanten op te slaan.  
  
Elk van deze entiteiten bevat ook een aantal velden die veelgebruikte gegevens vertegenwoordigen die het systeem mogelijk moet opslaan voor de betreffende entiteit.  
  
Voor de meeste organisaties is het in uw voordeel om de standaardentiteiten en -kenmerken te gebruiken voor de doeleinden waarvoor ze zijn gemaakt. 
  
Als u een oplossing installeert, kunt u verwachten dat de oplossingsontwikkelaar de standaardentiteiten en -kenmerken heeft gebruikt. Wanneer u een nieuwe aangepaste entiteit maakt die een systeementiteit of -kenmerk vervangt, betekent dit dat de beschikbare oplossingen mogelijk niet werken voor uw organisatie.  
  
Daarom raden wij u aan de aangeboden standaardentiteiten, -velden en -entiteitsrelaties op te zoeken en te gebruiken wanneer ze zinvol zijn voor uw organisatie. Als ze niet zinnig zijn en niet kunnen worden bewerkt om aan uw behoeften te voldoen, moet u evalueren of het nodig is een nieuwe entiteit, een nieuw veld of nieuwe entiteitsrelaties te maken. 

<!--  Can we say this yet? 
    
> [!NOTE]
> The [Common Data Model](/powerapps/common-data-model/overview) will provide a capability to add additional standard entities. 

-->

Vergeet niet dat u de weergavenaam van een entiteit kunt wijzigen zodat deze overeenkomt met de naamgeving die uw organisatie gebruikt. Zo wordt de weergavenaam van de accountentiteit vaak gewijzigd in *Bedrijf* of de naam van de entiteit Contactpersoon in *Persoon*. De naam van entiteiten of kenmerken kan worden gewijzigd zonder het gedrag van de entiteit te veranderen. Zie [De naam van een entiteit wijzigen](edit-entities.md#change-the-name-of-an-entity)voor meer informatie over het wijzigen van entiteitnamen.
  
U kunt standaardentiteiten, -velden en -entiteitsrelaties niet verwijderen. Deze worden beschouwd als onderdeel van de systeemoplossing, en er wordt verwacht dat elke organisatie ze heeft. Als u een standaardentiteit wilt verbergen, wijzigt u de rechten van de beveiligingsrollen van uw organisatie om het leesrecht voor die entiteit te verwijderen. Hiermee verwijdert u de entiteit uit de meeste onderdelen van de toepassing. Als er een systeemveld is dat u niet nodig hebt, verwijdert u het uit het formulier en eventuele weergaven die het gebruiken. Wijzig de waarde **Doorzoekbaar** in de definities van de veld- en entiteitsrelaties, zodat ze niet worden gevonden met geavanceerde zoekopdrachten. 
  
<a name="BKMK_LimitationsOnMetadata"></a>   

## <a name="limitations-on-creating-metadata-items"></a>Beperkingen voor het maken van metagegevensitems  

Er is een limiet aan het aantal entiteiten dat u kunt maken. Informatie over het maximumaantal is te vinden op de pagina **[Instellingen](../model-driven-apps/advanced-navigation.md#settings)** > **Beheer** > **Resources in gebruik**. Als u meer aangepaste entiteiten nodig hebt, neem dan contact op met de technische ondersteuning. Deze limiet kan worden aangepast.  
  
Binnen elke entiteit is er een limiet aan het aantal velden dat u kunt maken. Deze limiet is gebaseerd op de technische beperkingen van de hoeveelheid gegevens die kan worden opgeslagen in een rij van een databasetabel. Het is moeilijk een ​​specifiek aantal te geven, omdat elk type veld een andere hoeveelheid ruimte kan gebruiken. De bovenste limiet hangt af van de totale ruimte die wordt gebruikt door alle velden van de entiteit.  
  
De meeste mensen maken niet zo veel aangepaste velden dat de limiet wordt bereikt, maar als u van plan bent honderden aangepaste velden aan een entiteit toe te voegen, zou u zich af moeten vragen of dit wel het beste ontwerp is. Beschrijven alle velden die u wilt toevoegen eigenschappen voor een record voor die entiteit? Verwacht u echt dat mensen die uw organisatie gebruiken een formulier kunnen beheren met een dergelijk hoog aantal velden? Het aantal velden dat u aan een formulier toevoegt, verhoogt de hoeveelheid gegevens die moet worden overgedragen telkens wanneer een record wordt bewerkt, en heeft invloed op de prestaties van het systeem. Houd rekening met deze factoren wanneer u aangepaste velden aan een entiteit toevoegt.  
  
Optiesetvelden bieden een reeks opties die worden weergegeven in een vervolgkeuzemenu op een formulier of in een besturingselement met een keuzelijst bij gebruik van geavanceerd zoeken. Uw omgeving kan duizenden opties binnen een optieset ondersteunen, maar u moet dit niet als de bovengrens beschouwen. Bruikbaarheidsstudies hebben aangetoond dat mensen problemen hebben met het gebruik van een systeem waarbij een vervolgkeuzemenu grote aantallen opties biedt. Gebruik optiesetvelden om categorieën voor gegevens te definiëren. Gebruik geen optiesetvelden om categorieën te selecteren die feitelijk afzonderlijke gegevens vertegenwoordigen. Bijvoorbeeld: in plaats van een optiesetveld te onderhouden waar elk van de honderden mogelijke fabrikanten van een type apparatuur wordt opgeslagen, kunt u overwegen om een ​​entiteit te creëren waar verwijzingen naar elke fabrikant worden opgeslagen, en een opzoekveld gebruiken in plaats van een optieset.  
  
## <a name="next-steps"></a>Volgende stappen 

[Entiteiten (recordtypen) maken of bewerken](create-edit-entities.md)<br />
[Relaties tussen entiteiten maken en bewerken](create-edit-entity-relationships.md)

