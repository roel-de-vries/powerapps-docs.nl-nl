---
title: Openbare weergaven of systeemweergaven in modelgestuurde apps maken of bewerken met de appontwerper in PowerApps | MicrosoftDocs
description: Weergaven maken of bewerken met de appontwerper
keywords: ''
ms.date: 05/24/2018
ms.service: crm-online
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: 666ab3f3-abda-468c-b248-3a0b410286b0
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
caps.latest.revision: 1
topic-status: Drafting
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="tutorial-create-and-edit-public-or-system-model-driven-app-views-by-using-the-app-designer"></a>Zelfstudie: Openbare weergaven of systeemweergaven in modelgestuurde apps maken of bewerken met de appontwerper in PowerApps

In deze zelfstudie voert u verschillende taken uit die vereist zijn om te werken met weergaven, bijvoorbeeld een openbare weergave maken, een bestaande weergave aan een app toevoegen en kolommen, filters en de sorteervolgorde voor een weergave wijzigen.

In PowerApps bepalen weergaven hoe records voor een bepaalde entiteit worden weergegeven. Een weergave bepaalt het volgende:
-  De kolommen (kenmerken) die worden weergegeven
-  De breedte van de kolommen
-  Hoe de records standaard worden gesorteerd
-  Welke filters worden toegepast om te bepalen welke records standaard in de lijst worden weergegeven

Normaal gesproken worden weergaven onderverdeeld in drie typen:
- **Persoonlijk:** individuele gebruikers kunnen persoonlijke weergaven maken op basis van persoonlijke vereisten. Deze weergaven zijn alleen zichtbaar voor de gebruiker die ze heeft gemaakt en iedereen waarmee de weergaven worden gedeeld. 
- **Openbaar:** als appmaker kunt u openbare weergaven maken en bewerken om te voorzien in de behoeften van uw organisatie. Deze weergaven zijn beschikbaar in de weergaveselectie en u kunt ze gebruiken in subrasters in een formulier of als lijst in een dashboard.
- **Systeem:** als appmaker kunt u systeemweergaven ook aanpassen zodat deze aan de vereisten van uw organisatie voldoen. Dit zijn speciale speciale weergaven waarvan de toepassing afhankelijk is: zij bestaan voor systeementiteiten of zijn automatisch gemaakt bij het maken van aangepaste entiteiten. Deze weergaven zijn beschikbaar voor sommige of alle gebruikers, afhankelijk van hun machtigingen.

Meer informatie: [Inzicht in weergaven](create-edit-views.md)

## <a name="create-a-public-view-in-powerapps"></a>Een openbare weergave maken in PowerApps
Als appmaker kunt u openbare weergaven maken of bewerken met PowerApps.
1. Op de site [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) selecteert u **Modelgestuurd** (linkerbenedenhoek van het navigatievenster).  

     ![Modelgestuurde ontwerpmodus](media/model-driven-switch.png)

    > [!IMPORTANT]
    > Als de **modelgestuurde** ontwerpmodus niet beschikbaar is, moet u mogelijk [een omgeving maken](https://docs.microsoft.com/powerapps/administrator/create-environment).   
  
2.  Vouw **Gegevens** uit, selecteer **Entiteiten**, selecteer de gewenste entiteit en selecteer het tabblad **Weergaven**. 

3. Selecteer **Weergave toevoegen** op de werkbalk. 

4. Geef in het dialoogvenster **Eigenschappen weergeven** een naam en desgewenst een beschrijving voor de weergave op en selecteer **OK**. 
    
5. In de weergaveontwerper selecteert u **Kolommen toevoegen** om extra kolommen toe te voegen die u in de weergave wilt opnemen. Meer informatie: [Een kolom toevoegen aan uw weergave](#add-a-column-to-your-view)
6. Selecteer **Filtercriteria bewerken** om de filters op de volgende manieren te wijzigen: 
    -  Filtercriteria toepassen om de gegevens te verfijnen die in de weergave worden getoond. Meer informatie: [Filtercriteria definiëren](#define-filter-criteria). 
    - De filters groeperen door de opties **EN** of **OF** te gebruiken en de gegevens die in de weergave worden getoond verder te verfijnen. Meer informatie: [Meerdere filters groeperen](#group-multiple-filters)
7. Selecteer **Sorteren configureren** om de volgorde van de gegevens te wijzigen door de primaire en secundaire sorteervolgorde voor kolommen te configureren. Meer informatie: [De primaire en secundaire kolomsorteervolgorde instellen](#set-primary-and-secondary-sort-order-for-columns)
8. (Optioneel) Configureer kolombreedte: 
  
    a. Selecteer een kolom. Het tabblad **Eigenschappen** wordt geopend.
    
    b. Configureer **Breedte instellen** met de gewenste kolombreedte.
    
    > [!NOTE]
    > De waarde voor de kolombreedte varieert van 25 pixels tot en met 300 pixels.
9. (Optioneel) Herorden kolommen door een kolom naar de gewenste positie te slepen. 

    U ziet een visuele indicator wanneer u de kolom boven een positie houdt waar deze naartoe kan worden verplaatst.

    ![Kolom herordenen](media/ViewAppDesigner_ReorderColumn.png "Kolommen in een weergave herordenen")

    > [!NOTE]
    > U kunt ook de kolomvolgorde wijzigen met behulp van toetsenbordsneltoetsen. Knip de kolom door Ctrl + X te selecteren, selecteer een kolom en plak vervolgens door CTRL + V te selecteren. De kolom wordt rechts van de geselecteerde kolom geplaatst.
10. (Optioneel) Voeg een pictogram of een bestand toe aan een kolom om deze van andere kolommen te onderscheiden tijdens de uitvoeren. Meer informatie: [Een webresource definiëren](#define-a-web-resource)
11. **Sla de weergave op en sluit** deze. 
12. Kies **Publiceren** om de weergave beschikbaar te stellen aan andere gebruikers in uw organisatie. 
   

## <a name="open-and-add-a-view-in-the-app-designer"></a>Een weergave openen en toevoegen in de app-ontwerper

De volgende stappen wordt uitgelegd hoe u een weergave opent en toevoegt in de app-ontwerper.
1. In de oplossingenverkenner selecteert u **Apps** en vervolgens selecteert u de app die u wilt bewerken om deze in de appontwerper te openen. 

2. Selecteer in de sectie **Entiteitsweergave** de optie **Weergaven**.

    In dit voorbeeld hebben wij **Weergaven** geselecteerd vanuit de entiteit **Account**.

    ![Weergave van app-ontwerper](media/ViewAppDesigner_AccountAppDesignerView.png "Weergave van app-ontwerper van entiteit Account")

3. Als u een weergave wilt toevoegen, selecteert u deze door een van de weergavetypen te gebruiken zoals Openbaar, Geavanceerd zoeken, Gekoppeld en Opzoeken. De weergave wordt automatisch toegevoegd aan de lijst **Weergaven**.

    > [!NOTE]
    > Weergaven worden weergegeven op basis van de entiteit die u hebt geselecteerd. Als u bijvoorbeeld **Account** selecteert, worden weergaven die zijn gerelateerd aan de entiteit Account weergegeven.

Meer informatie over de app-ontwerper: [Aangepaste bedrijfsapps ontwerpen met de app-ontwerper](design-custom-business-apps-using-app-designer.md)


## <a name="add-a-column-to-your-view"></a>Een kolom toevoegen aan uw weergave
In weergaven worden records weergegeven in een tabel die rijen en kolommen bevat. Elke rij is een record, en de velden die u weergeeft uit de record worden bepaald door de kolommen die u toevoegt aan de weergave.

1. Selecteer in de appontwerper op het tabblad **Onderdelen** de lijst **Kolomkenmerken** voor **Primaire entiteit** of **Gerelateerde entiteit**.

    ![Een kolom toevoegen](media/ViewAppDesigner_AddColumn.png "Een kolom toevoegen aan een weergave") 

2. Selecteer in de lijst het gewenste kenmerk en sleep het naar de kolomkop. U kunt ook het kenmerk toevoegen door erop te dubbelklikken.
3. Herhaal stap 2 totdat u alle kenmerken hebt toegevoegd die u wilt tonen in uw weergave.

Terwijl u kenmerken toevoegt, kunt u deze naar elke gewenste positie onder bestaande kopteksten verslepen. U kunt ook kolommen verplaatsen nadat u deze hebt toegevoegd aan uw weergave.


## <a name="define-filter-criteria"></a>Filtercriteria definiëren
U kunt filtercriteria zo instellen dat alleen een subset van de records wordt getoond in een weergave. Wanneer een gebruiker de weergave opent, worden alleen de records die aan de gedefinieerde filtercriteria voldoen weergegeven. U kunt velden selecteren van zowel de primaire als de gerelateerde entiteiten om op te filteren.
1. Vouw in de appontwerper de sectie **Filtercriteria** uit.
   
    ![Filtercriteria instellen](media/ViewAppDesigner_FilterCriteria.png "Filtercriteria instellen") 

2. Selecteer **Filter toevoegen**
3. Selecteer een kenmerk uit de vervolgkeuzelijst in de eerste kolom. 
4. Selecteer operator uit de vervolgkeuzelijst in de tweede kolom.

    ![Operator voor filtercriteria instellen](media/ViewAppDesigner_FilterCriteriaOption.png "Operator voor filtercriteria instellen")

5. Voereen waarde in om op te filteren in de derde kolom.

U kunt gegevens niet alleen filteren op basis van de kenmerken van de primaire entiteit maar ook op die van gerelateerde entiteiten. 

1. Selecteer op het tabblad **Onderdelen** de lijst **Kolomkenmerken** voor **Gerelateerde entiteit**, selecteer de pijl-omlaag voor **Een entiteit kiezen** in het bovenste veld en kies vervolgens de entiteit die u wilt.

    Hiermee wordt een afzonderlijke sectie toegevoegd.

2. Herhaal stap 2 tot en met 5 van de vorige procedure.

Meer informatie: [Relaties tussen entiteiten maken en bewerken](../common-data-service/create-edit-entity-relationships.md)

## <a name="group-multiple-filters"></a>Meerdere filters groeperen
U kunt meerdere filters toevoegen aan uw weergave als u records wilt filteren op meer dan één veld. 

1. Selecteer de filters die u wilt groeperen.
    ![Groepsfilter instellen](media/ViewAppDesigner_GroupFilter.png "Groepsfilter instellen")
2. Selecteer Groeperen En of Groeperen Of om de filters te groeperen.
    ![Selectie van groepsfilter](media/ViewAppDesigner_GroupFilterSelection.png "Een groepsfilter selecteren") Als u **Groeperen En** selecteert, worden alleen records getoond in de weergave die aan beide criteria voldoen. Als u **Groeperen Of** selecteert, worden records waarin een van beide filtercriteria voldoen weergegeven. Als u bijvoorbeeld alleen records wilt weergeven met de prioriteit Hoog of Normaal en de status Actief, selecteert u **Groeperen En**.

U kunt het filter uit een groep verwijderen door de groep te selecteren en vervolgens **Groep opheffen** te selecteren. 

## <a name="set-primary-and-secondary-sort-order-for-columns"></a>Primaire en secundaire kolomsorteervolgorde instellen voor kolommen
Wanneer een weergave wordt geopend, worden de records gesorteerd in de volgorde die u hebt ingesteld bij het maken van de weergave.   Standaard worden records gesorteerd op basis van de eerste kolom in een weergave als geen sorteervolgorde is geselecteerd. U kunt ervoor kiezen om op één kolom te sorteren of u kunt twee kolommen kiezen, één primaire en één secundaire, om op te sorteren. Als de weergave wordt geopend, worden de records eerst gesorteerd op de kolom die u voor de primaire sorteervolgorde wilt gebruiken en vervolgens op de kolom die u als secundaire sorteervolgorde wilt gebruiken. 

> [!NOTE]
> U kunt alleen de primaire en secundaire sorteervolgorde instellen op kolomkenmerken die u hebt toegevoegd vanuit de primaire entiteit.

1. Selecteer de kolom die u wilt gebruiken om op te sorteren.
2. Selecteer de pijl-omlaag, en kies daarna **Primaire sorteerbewerking** of **Secundaire sorteerbewerking**.
 
    ![Sorteerrecord](media/ViewAppDesigner_SortRecords.png "Sorteerrecords gebaseerd op primaire en secundaire sorteervolgorden") 

Als u de kolom verwijdert die u hebt gekozen voor de primaire sorteervolgorde, wordt de kolom die u voor de secundaire sorteervolgorde hebt gekozen de primaire sorteervolgorde.

## <a name="define-a-web-resource"></a>Een webresource definiëren
Geef een webresource of scripttype op om een kolom aan uw weergave te koppelen. Deze scripts helpen om pictogrammen weer te geven voor kolommen.

1. Selecteer de kolom waaraan u een webresource wilt toevoegen.
2. Selecteer op het tabblad **Eigenschappen** de optie **Geavanceerd**.
3. Selecteer in de vervolgkeuzelijst **Webresource** de webresource die u wilt gebruiken.
4. Voer in het vak **Functienaam** een functienaam in.

## <a name="edit-a-public-or-system-view"></a>Een openbare weergave of systeemweergave bewerken
U kunt de manier wijzigen waarop een openbare weergave of systeemweergave wordt weergegeven door kolommen toe te voegen, te configureren of te verwijderen.
1. Selecteer in de lijst **Weergaven** voor een entiteit de pijl-omlaag **Lijst met verwijzingen weergeven** ![Vervolgkeuzepijl](media/DownArrow.png "Vervolgkeuzepijl").
    ![Weergave bewerken](media/ViewAppDesigner_EditView.png "Een openbare weergave of systeemweergave bewerken")
2. Selecteer naast de weergave die u wilt bewerken de optie **De weergaveontwerper openen** ![Weergaveontwerper openen](media/dynamics365-open-designer.png "Weergaveontwerper openen"). 

    De weergave wordt geopend in de weergaveontwerper. 

Wanneer u een openbare weergave of systeemweergave bewerkt, moet u uw wijzigingen opslaan en publiceren voordat ze zichtbaar worden in de toepassing.


## <a name="community-tools"></a>Community-hulpprogramma's
**View Layout Replicator** en **View Designer** zijn hulpprogramma's die de XrmToolbox-community heeft ontwikkeld voor Dynamics 365 Customer Engagement.

Meer informatie: [Hulpmiddelen voor ontwikkelaars](https://docs.microsoft.com/dynamics365/customer-engagement/developer/developer-tools).

> [!NOTE]
> Deze hulpprogramma's zijn afkomstig van XrmToolBox en worden niet ondersteund door Microsoft. Als u vragen hebt over het hulpprogramma, raadpleegt u de uitgever hiervan. Meer informatie: [XrmToolBox](https://www.xrmtoolbox.com/). 

### <a name="next-steps"></a>Volgende stappen
[Maak 1:N (een-op-veel) of N:1 (veel-op-een) relaties](../common-data-service/create-edit-1n-relationships.md)
