---
title: Een weergavedefinitie voor modelgestuurde apps openen | MicrosoftDocs
description: In dit onderwerp leert u hoe u entiteitsweergaven opent
ms.custom: ''
ms.date: 06/12/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
author: Mattp123
ms.assetid: 034c8bef-0d1c-4ef9-8da7-f81343c4553a
caps.latest.revision: 25
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="access-a-model-driven-app-view-definition-in-powerapps"></a>Een weergavedefinitie voor modelgestuurde apps openen in PowerApps

 In dit onderwerp opent u een weergavedefinitie om eigenschappen en opties voor het configureren van de weergave weer te geven. U kunt in PowerApps op verschillende manieren weergavedefinities openen. 
  
  
## <a name="open-a-view-in-powerapps"></a>Een weergave openen in PowerApps

1.  Op de site [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) selecteert u **Modelgestuurd** (linkerbenedenhoek van het navigatievenster).  

    ![Modelgestuurde ontwerpmodus](media/model-driven-switch.png)

    > [!IMPORTANT]
    > Als de **modelgestuurde** ontwerpmodus niet beschikbaar is, moet u mogelijk [een omgeving maken](https://docs.microsoft.com/powerapps/administrator/create-environment). 

2.  Vouw **Gegevens** uit, selecteer **Entiteiten** en selecteer de entiteit **Account**.   
3. Selecteer het tabblad **Weergaven** en selecteer vervolgens **Filter verwijderen**.

    > [!div class="mx-imgBorder"] 
    > ![Weergavedefinities voor Account](media/account-view-definitions.png)

4. Selecteer de weergave die u wilt openen, zoals de accountentiteitsweergave **Alle accounts**.

    > [!div class="mx-imgBorder"] 
    > ![Weergave Alle accounts](media/all-accounts-view.png)

5. Vanuit de weergave-editor kunt u verschillende taken uitvoeren: 
 
- [Records in een weergave sorteren](configure-sorting.md)
- [Kolommen kiezen en configureren in weergaven](choose-and-configure-columns.md)
- [Aangepaste besturingselementen gebruiken voor gegevensvisualisatie](use-custom-controls-data-visualizations.md) 

## <a name="open-a-view-from-an-app"></a>Een weergave openen vanuit een app

Bij elke lijstweergave voor een entiteit in de opdrachtbalk vindt u de volgende opdrachten wanneer u de knop met de drie puntjes (...) selecteert:  
- **Weergave**: hiermee wordt de definitie van de huidige weergave in de standaardoplossing geopend.  
  
- **Nieuwe systeemweergave**: hiermee wordt een nieuw venster geopend om een nieuwe weergave voor de huidige entiteit in de standaardoplossing te maken.  
  
- **Entiteit aanpassen**: hiermee gaat u naar de definitie van de huidige entiteit in de standaardoplossing waar u vervolgens **Weergaven** kunt selecteren.  
  
- **Systeemweergaven**: hiermee wordt hetzelfde venster geopend als bij **Entiteit aanpassen**, behalve dat **Weergaven** is geselecteerd.  

## <a name="open-a-view-in-solution-explorer"></a>Een weergave openen in oplossingenverkenner 
  
1.  Open [oplossingenverkenner](advanced-navigation.md#solution-explorer).  
  
2.  Vouw onder **Onderdelen** achtereenvolgens **Entiteiten** en de gewenste entiteit uit.  
  
3.  Selecteer **Weergaven**.  
  
4.  Dubbelklik op de weergave die u wilt openen.  
  
 Deze lijst met weergaven heeft vier filters die u kunt gebruiken om gemakkelijker de gewenste weergaven te vinden:  
  
    - **Alle actieve weergaven**  
  
    - **Actieve openbare weergaven**  
  
    - **Inactieve openbare weergaven**  
  
    - **Actieve systeemgedefinieerde weergaven**  
  
 Als de entiteit waaraan de weergave is gekoppeld deel uitmaakt van een onbeheerde oplossing, kunt u nog steeds weergaven voor die entiteit maken of bewerken in de standaardoplossing. Systeemweergaven zijn gekoppeld aan een entiteit en zijn niet beschikbaar als aparte oplossingsonderdelen. In tegenstelling tot velden, maken weergaven geen gebruik van een aanpassingsvoorvoegsel in een unieke naam die consistent moet zijn in een oplossing. U hoeft dus geen weergaven te maken in de context van een oplossing. 
 
## <a name="next-steps"></a>Volgende stappen
[Inzicht in weergaven ](create-edit-views.md)


