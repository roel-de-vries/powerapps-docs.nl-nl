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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="entities-and-metadata-in-common-data-service-for-apps"></a>Entiteiten en metagegevens in Common Data Service voor Apps

Common Data Service voor Apps is ontworpen zodat u snel en gemakkelijk een gegevensmodel voor uw toepassing kunt maken. Normaal gesproken hoeft u zich niet bezig te houden met bepaalde details over metagegevens die in dit onderwerp worden geïntroduceerd. Maar als u meer inzicht wilt krijgen in de manier waarop apps werken die CDS voor Apps gebruiken of als u wilt evalueren wat de mogelijkheden zijn, kan het nuttig zijn u meer te verdiepen in de metagegevens die door CDS voor Apps worden gebruikt.

Onder *Metagegevens* verstaan we 'gegevens over gegevens'. CDS voor Apps biedt u een flexibel platform omdat u relatief gemakkelijk de definities kunt bewerken van de gegevens die de omgeving gebruikt. In CDS voor Apps vormen de metagegevens een verzameling van entiteiten. Entiteiten beschrijven de gegevenssoorten die worden opgeslagen in de database.  Elke entiteit komt overeen met een databasetabel en ieder veld (ook bekend als kenmerk) binnen een entiteit vertegenwoordigt een kolom in die tabel. Entiteitmetagegevens besturen de recordtypen die u kunt maken en welke actiesoorten erop kunnen worden uitgevoerd. Wanneer u de aanpassingshulpprogramma´s voor het maken of bewerken van entiteiten, velden en entiteitsrelaties gebruikt, bewerkt u deze metagegevens. 
  
Verschillende clients die gebruikers gebruiken om te werken met de gegevens in uw omgeving, zijn afhankelijk van de entiteitsmetagegevens en worden aangepast als u de metagegevens aanpast. Deze clients zijn ook afhankelijk van andere gegevens om te bepalen welke visuele elementen worden weergegeven, welke aangepaste logica moet worden toegepast en hoe u functies voor beveiliging toepast. Deze systeemgegevens worden ook opgeslagen in entiteiten, maar de entiteiten zijn niet beschikbaar voor aanpassing.

U kunt leren over standaardentiteiten, kenmerken en entiteitsrelaties die standaard zijn opgenomen in CDES voor Apps door de [Entiteitverwijzing](/powerapps/developer/common-data-service/reference/about-entity-reference) bekijken.

> [!TIP]
> Met de beschikbare ontwerpers om metagegevens te bewerken kunnen niet alle details worden weergegeven die zich in de metagegevens bevinden. U kunt een modelgestuurde app installeren met de naam **Metadata Browser** waarmee u alle entiteiten en metagegevenseigenschappen kunt weergeven die zich in het systeem bevinden. Meer informatie: [Bladeren door de metagegevens voor uw organisatie](https://docs.microsoft.com/dynamics365/customer-engagement/developer/browse-your-metadata).
  
<a name="BKMK_CreateNewOrUseExistingMetadata"></a>

## <a name="create-new-metadata-or-use-existing-metadata"></a>Nieuwe metagegevens maken of bestaande metagegevens gebruiken?

CDS voor Apps wordt geleverd met een aantal standaardentiteiten die de kernmogelijkheden van bedrijfstoepassingen ondersteunen. Bijvoorbeeld: gegevens over uw actuele klanten of potentiële klanten zijn bedoeld om te worden opgeslagen met behulp van de entiteiten Account of Contactpersoon.  
  
Elk van deze entiteiten bevat tevens een aantal velden voor algemene gegevens die mogelijk moeten worden opgeslagen voor de desbetreffende entiteit.  
  
Voor de meeste organisaties is het in uw voordeel om de standaardentiteiten en kenmerken te gebruiken voor de doelen waarvoor ze zijn geleverd. 
  
Als u een oplossing wilt installeren, dan kunt u verwachten dat de oplossingsontwikkelaar de standaardentiteiten en kenmerken heeft bewerkt. Het maken van een nieuwe aangepaste entiteit die een systeementiteit of een kenmerk vervangt zal betekenen dat alle beschikbare oplossingen wellicht niet voor uw organisatie zullen werken.  
  
We adviseren om deze redenen dat u de geleverde standaardentiteiten, velden en entiteitsrelaties zoekt en gebruikt wanneer ze van betekenis zijn voor uw organisatie. Als ze niet van betekenis zijn en niet kunnen worden bewerkt om aan uw behoefte te voldoen, dan moet u evalueren of u een nieuwe entiteit, nieuw veld of nieuwe entiteitsrelatie moet maken. 

<!--  Can we say this yet? 
    
> [!NOTE]
> The [Common Data Model](/powerapps/common-data-model/overview) will provide a capability to add additional standard entities. 

-->

U kunt de weergavenaam van een entiteit wijzigen zodat deze overeenkomt met nomenclatuur die uw organisatie gebruikt. Het is bijvoorbeeld zeer gebruikelijk voor mensen om de weergavenaam van de accountentiteit te wijzigen in *Bedrijf* of de naam van de contactpersoonentiteit in *Individu*. Dit kan is mogelijk op entiteiten of kenmerken zonder het gedrag van de entiteit te wijzigen. Voor meer informatie over de naam van entiteiten wijzigen raadpleegt u [De naam van een entiteit wijzigen](edit-entities.md#change-the-name-of-an-entity).
  
U kunt geen standaardentiteiten, velden of entiteitsrelaties verwijderen. Ze worden opgevat als onderdeel van de systeemoplossing en elke organisatie moet ze hebben. Als u een standaardentiteit wilt verbergen, wijzigt u de beveiligingsrolbevoegdheden voor uw organisatie om de leesbevoegdheid voor die entiteit te verwijderen. Hiermee wordt de entiteit uit de meeste onderdelen van de toepassing verwijderd. Als er een systeemveld is dat u niet nodig hebt, dan kunt u het vanuit het formulier en weergaven die het gebruiken verwijderen. Wijzig de waarde **Kan worden doorzocht** in de definities van veld en entiteitsrelatie zodat deze niet in de resultaten van geavanceerde zoekopdrachten verschijnen. 
  
<a name="BKMK_LimitationsOnMetadata"></a>   

## <a name="limitations-on-creating-metadata-items"></a>Beperkingen bij het maken van metagegevensitems  

Er geldt een limiet voor het aantal entiteiten dat u kunt maken. U kunt informatie over het maximumaantal vinden op de pagina **[Instellingen](../model-driven-apps/advanced-navigation.md#settings)** > **Beheer** > **Resources in gebruik**. Als u meer aangepaste entiteiten nodig hebt, neemt u contact op met de technische ondersteuning. Deze bovengrens kan worden aangepast.  
  
In elke entiteit bestaat er een bovengrens op het aantal velden dat u kunt maken. Deze limiet is gebaseerd op de technische beperkingen op de hoeveelheid gegevens die kan worden bewaard in een rij van een databasetabel. Het is moeilijk om een specifiek aantal te geven omdat elk veldtype een verschillende hoeveelheid ruimte kan gebruiken. De bovengrens is afhankelijk van de totale ruimte die wordt gebruikt door alle velden voor de entiteit.  
  
De meeste mensen maken niet voldoende aangepaste velden om de limiet te bereiken, maar als u voorneemt om honderden aangepaste velden aan een entiteit toe te voegen, dan is het verstandig om te overwegen of dit het beste ontwerp is. Beschrijven alle velden die u van plan toe te voegen eigenschappen voor een record voor die entiteit? Verwacht u werkelijk dat gebruikers van uw organisatie een formulier kunnen beheren dat een dergelijk groot aantal velden bevat? Het aantal velden dat u toevoegt aan een formulier doet de hoeveelheid gegevens toenemen die moet worden overgedragen wanneer een record wordt bewerkt en zal de prestaties van het systeem beïnvloeden. Neem de volgende factoren in overweging wanneer u aangepaste velden aan een entiteit toevoegt.  
  
Optiesetvelden geven een optieverzameling die in een vervolgkeuzelijst op een formulier of in een selectielijst zal worden weergeven wanneer geavanceerd zoeken wordt gebruikt. Uw omgeving kan duizenden opties ondersteunen in een optieset, maar dit is niet een werkbare bovengrens. Bruikbaarheidsstudies hebben aangetoond dat mensen moeite hebben met het gebruik van een systeem waarin een vervolgkeuzelijstbesturingselement grote aantallen opties bevat. Gebruik optiesetvelden om categorieën voor gegevens definiëren. Gebruik geen optiesetvelden om categorieën te selecteren die afzonderlijke gegevensitems representeren. Bijvoorbeeld: in plaats van een optiesetveld te onderhouden dat elk van honderden fabrikanten van een apparatuurtype bewaart, kunt u een entiteit maken die verwijzingen naar iedere fabrikant bevat en een opzoekveld gebruiken in plaats van een optieset.  
  
## <a name="next-steps"></a>Volgende stappen 

[Entiteiten maken of bewerken (recordtypen)](create-edit-entities.md)<br />
[Relaties tussen entiteiten maken en bewerken](create-edit-entity-relationships.md)

