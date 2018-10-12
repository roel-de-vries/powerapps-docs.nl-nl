---
title: Gesegmenteerde oplossingen en patches gebruiken om oplossingsupdates te vereenvoudigen met PowerApps | MicrosoftDocs
description: Meer informatie over het gebruik van oplossingssegmentatie om uw oplossingen bij te werken
ms.custom: ''
ms.date: 06/18/2018
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
ms.assetid: 5c05f683-e1bd-4885-be23-b6973128773f
caps.latest.revision: 15
ms.author: matp
manager: kvivek
ms.openlocfilehash: 274e2914d65b6bcb644821c044adb3b0246a75fc
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39677516"
---
# <a name="use-segmented-solutions-and-patches-to-export-selected-entity-assets"></a>Gesegmenteerde oplossingen en patches gebruiken om geselecteerde entiteitsassets te exporteren

Gebruik oplossingssegmentatie om meer controle te krijgen over wat u distribueert in oplossingen en oplossingspatches. Met oplossingssegmentatie kunt u oplossingen met geselecteerde assets, zoals velden, formulieren en weergaven exporteren, in plaats van complete entiteiten met alle assets. Om gesegmenteerde oplossingen en patches te maken, kunt u de gebruikersinterface van oplossingen gebruiken, zonder code te hoeven schrijven.  
  
 Naast dat u meer controle krijgt over wat er in een oplossing zit, hebt u de controle over wat er in een patch zit. U kunt een patch maken voor een bovenliggende oplossing en die als kleine update exporteren naar de basisoplossing. Wanneer u een oplossing kloont, totaliseert het systeem alle gerelateerde patches in de basisoplossing en wordt een nieuwe versie gemaakt.  
  
 Wanneer u werkt met patches en gekloonde oplossingen, houd dan rekening met de volgende informatie:  
  
-   Een patch is een kleine incrementele update van de bovenliggende oplossing. Een patch kan onderdelen en assets in de bovenliggende oplossing toevoegen of bijwerken wanneer deze wordt geïnstalleerd op het doelsysteem, maar kan geen onderdelen of assets verwijderen uit de bovenliggende oplossing.  
  
-   Een patch kan maar één bovenliggende oplossing hebben, maar een bovenliggende oplossing kan één of meer patches hebben.  
  
-   Een patch wordt gemaakt voor onbeheerde oplossingen. U kunt geen patch maken voor een beheerde oplossing.  
  
-   Wanneer u een patch exporteert naar een doelsysteem, moet u die als beheerde patch exporteren. Gebruik geen onbeheerde patches in productieomgevingen.  
  
-   De bovenliggende oplossing moet aanwezig zijn in het doelsysteem om een patch te installeren.  
  
-   U kunt een patch bijwerken of verwijderen.  
  
-   Als u een bovenliggende oplossing verwijdert, worden alle onderliggende patches ook verwijderd. Het systeem geeft een waarschuwingsbericht weer dat u de verwijderactie niet ongedaan kunt maken. De verwijdering wordt uitgevoerd in een enkele actie. Als één van de patches of de bovenliggende oplossing niet kan worden verwijderd, wordt de hele actie teruggedraaid.  
  
-   Nadat u de eerste patch voor de bovenliggende oplossing hebt gemaakt, wordt de oplossing vergrendeld en kunt u geen wijzigingen meer aanbrengen in deze oplossing of de oplossing exporteren. Als u echter alle onderliggende patches verwijdert, wordt de bovenliggende oplossing ontgrendeld.  
  
-   Wanneer u een basisoplossing kloont, worden alle onderliggende patches getotaliseerd in de basisoplossing en wordt het een nieuwe versie. U kunt onderdelen en assets in de gekloonde situatie toevoegen, bewerken of verwijderen.  
  
-   Een gekloonde oplossing is een vervanging van de basisoplossing wanneer die wordt geïnstalleerd op het doelsysteem als beheerde oplossing. Meestal gebruikt u een gekloonde oplossing om een belangrijke update te verzenden naar de voorgaande oplossing.  
  
## <a name="understanding-version-numbers-for-cloned-solutions-and-patches"></a>Informatie over versienummers voor gekloonde oplossingen en patches  
 De versie van een oplossing heeft de volgende indeling: major.minor.build.revision. Een patch moet een hoger build- of revisienummer hebben dan de bovenliggende oplossing. Er mag geen hogere major- of minorversie bestaan. Voor een basisoplossing met versienummer 3.1.5.7 zou een patch bijvoorbeeld versie 3.1.5.8 of versie 3.1.7.0 kunnen zijn, maar niet versie 3.2.0.0. Het versienummer van een gekloonde oplossing moet groter of gelijk zijn aan het versienummer van de basisoplossing. Voor een basisoplossing met versienummer 3.1.5.7. kan een gekloonde versie bijvoorbeeld versie 3.2.0.0 of 3.1.5.7 zijn. In de gebruikersinterface kunt u alleen de major- en minorversiewaarden voor een gekloonde oplossing instellen en de build- of revisiewaarden voor een patch.  
  
## <a name="create-a-segmented-solution-with-the-entity-assets-you-want"></a>Een gesegmenteerde oplossing maken met de gewenste entiteitsassets  
 Om een gesegmenteerde oplossing te maken, begint u met het maken van een onbeheerde oplossing en de bestaande bronnen toe te voegen. U kunt meerdere systeem- of aangepaste entiteiten toevoegen en voor elke entiteit kiest u de assets die u in de oplossing wilt opnemen. De wizardachtige opzet helpt u stapsgewijs door het proces om entiteitsassets toe te voegen.  
  
1. Ga naar **[Instellingen](../model-driven-apps/advanced-navigation.md#settings)** > **Oplossingen**.   
  
2.  Selecteer **Nieuw** en maak een oplossing. Voer de gegevens in de vereiste velden in. Selecteer **Opslaan en sluiten**.  
  
3.  Open de oplossing die u net hebt gemaakt. Selecteer **Entiteit** in de vervolgkeuzelijst **Bestaande toevoegen**.  
  
4.  Selecteer een of meer entiteiten die u wilt toevoegen in de oplossing in het dialoogvenster **Oplossingsonderdelen selecteren**. Selecteer **OK**.  
  
5.  De wizard wordt geopend. Volg de wizard om assets toe te voegen aan de oplossing voor elke geselecteerde entiteit.  
  
6.  Selecteer **Publiceren** om de wijzigingen van kracht te laten worden.  
  
 De volgende illustraties geven een voorbeeld van het maken van een gesegmenteerde oplossing door entiteitsassets te kiezen van de `Account`-, `Case`- en `Contact`-entiteiten.  
  
 Begin met het onderdeel **Entiteit** te kiezen.  
  
 ![Voeg bestaande resources toe.](media/solution-segmentation-add-existing-resources-admin.png "Voeg bestaande resources toe.")  
  
 Selecteer vervolgens de oplossingsonderdelen.  
  
 ![Selecteer de oplossingsonderdelen.](media/solution-segmentation-select-components-admin.png "Selecteer de oplossingsonderdelen.")  
  
 Volg de instructies van de wizard. Selecteer in stap 1 in alfabetische volgorde de assets voor de eerste entiteit, de `Account`-entiteit zoals hier wordt weergegeven.  
  
 ![Start de wizard.](media/solution-segmentation-wizard-starts-admin.png "Start de wizard.")  
  
 Open het tabblad **Velden** en selecteer het veld **Accountnummer**.  
  
 ![Selecteer de assets van de entiteit Account.](media/solution-segmentation-select-account-assets-admin.png "Selecteer de assets van de entiteit Account.")  
  
 Voeg in stap 2 alle assets voor de entiteit **Case** toe.  
  
 ![Selecteer de assets van de entiteit Case.](media/solution-segmentation-select-case-assets-admin.png "Selecteer de assets van de entiteit Case.")  
  
 Voeg in stap 3 het veld **Anniversary** toe voor de entiteit **Contact**.  
  
 ![Selecteer de assets van de entiteit Contact.](media/solution-segmentation-select-contact-assets-admin.png "Selecteer de assets van de entiteit Contact.")  
  
 Als gevolg hiervan bevat de gemaakte gesegmenteerde oplossing drie entiteiten: `Account`, `Case` en `Contact`. Elke entiteit bevat alleen de assets die zijn gekozen.  
  
 ![Oplossing met entiteiten.](media/solution-segmentation-solution-entities-admin.png "Oplossing met entiteiten.")  
  
## <a name="create-a-solution-patch"></a>Een oplossingspatch maken  
 Een patch bevat wijzigingen aan de bovenliggende oplossing zoals het toevoegen of wijzigen van onderdelen en assets. U hoeft de onderdelen van de bovenliggende oplossing niet bij te voegen, tenzij u van plan bent die te wijzigen.  
  
 #### <a name="create-a-patch-for-an-unmanaged-solution"></a>Een patch maken voor een beheerde oplossing  
  
1. Ga naar **[Instellingen](../model-driven-apps/advanced-navigation.md#settings)** > **Oplossingen**.   
  
2.  Selecteer in de lijst een onbeheerde oplossing voor een patch. Selecteer **Een patch klonen**. Het dialoogvenster dat wordt geopend, bevat de naam van de basisoplossing en het versienummer van de patch. Selecteer **Opslaan**.  
  
3.  Zoek in het raster de net gemaakte patch en open deze. Net als met de basisoplossing, volgt u de instructies van de wizard om gewenste onderdelen en assets toe te voegen.  
  
4.  Selecteer **Publiceren** om de wijzigingen van kracht te laten worden.  
  
 De volgende illustraties tonen een voorbeeld van het maken van een patch voor een bestaande oplossing. Begin door **Een patch klonen** te selecteren (in de samengevouwen weergave wordt het pictogram **Een patch klonen** weergegeven als twee vierkantjes, zoals hieronder is te zien).  
  
 ![Pictogram Een patch klonen.](media/solution-segmentation-click-patch-icon-admin.png "Pictogram Een patch klonen.")  
  
 In het dialoogvenster **Een patch klonen** ziet u dat het versienummer van de patch is gebaseerd op het versienummer van de bovenliggende oplossing, maar het build-nummer is met één opgehoogd. Elke volgende patch heeft een hoger build- of revisienummer dan de voorgaande patch.  
  
 ![Dialoogvenster Kloon gebruiken om te patchen.](media/solution-segmentation-clone-patch-dialog-admin.png "Dialoogvenster Kloon gebruiken om te patchen.")  
  
 De volgende schermafbeelding laat de basisoplossing **SegmentedSolutionExample**, versie **1.0.1.0** zien en de patch **SegmentedSolutionExample_Patch**, versie **1.0.2.0**.  
  
 ![Een raster met oplossingen en patches.](media/solution-segmentation-solution-patch-grid-admin.png "Een raster met oplossingen en patches.")  
  
 In de patch hebben we een nieuwe aangepaste entiteit genaamd `Book` toegevoegd en alle assets van de entiteit `Book` in de patch bijgevoegd.  
  
 ![Aangepaste entiteit in de patch voegen.](media/solution-segmentation-add-book-patch-admin.png "Aangepaste entiteit in de patch voegen.")  
  
## <a name="clone-a-solution"></a>Een oplossing klonen  
 Wanneer u een onbeheerde oplossing kloont, worden alle daaraan gerelateerde patches getotaliseerd in de nieuw gemaakte versie van de oorspronkelijke oplossing.  
  
1. Ga naar **[Instellingen](../model-driven-apps/advanced-navigation.md#settings)** > **Oplossingen**.   
  
2.  Selecteer in de lijst een onbeheerde oplossing die u wilt klonen. Selecteer **Oplossing klonen**. Het dialoogvenster dat wordt geopend, bevat de naam van de basisoplossing en het nieuwe versienummer. Selecteer **Opslaan**.  
  
3.  Selecteer **Publiceren** om de wijzigingen van kracht te laten worden.  
  
 Als u doorgaat met het voorbeeld, ziet u het dialoogvenster **Kloon naar oplossing** dat het nieuwe versienummer van de oplossing toont.  
  
 ![Het dialoogvenster Kloon naar oplossing gebruiken.](media/solution-segmentation-clone-solution-dialog-admin.png "Het dialoogvenster Kloon naar oplossing gebruiken.")  
  
 Na het klonen bevat de nieuwe oplossingsversie drie oorspronkelijke entiteiten (`Account`, `Case` en`Contact`) en de aangepaste entiteit genaamd `Book` die is toegevoegd in de patch. Elke entiteit bevat alleen de assets die zijn toegevoegd in het voorbeeld.  
  
 ![Een gekloonde oplossing met getotaliseerde patch.](media/solution-segmentation-solution-rolled-up-patch-admin.png "Een gekloonde oplossing met getotaliseerde patch.")  
  
## <a name="next-steps"></a>Volgende stappen  
 [Oplossingsoverzicht](solutions-overview.md) [Patches maken om oplossingsupdates te vereenvoudigen]

