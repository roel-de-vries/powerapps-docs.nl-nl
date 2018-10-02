---
title: Gesegmenteerde oplossingen en patches gebruiken om oplossingsupdates te vereenvoudigen met PowerApps | MicrosoftDocs
description: Lees hoe u oplossingssegmentatie kunt gebruiken om uw oplossingen bij te werken
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="use-segmented-solutions-and-patches-to-export-selected-entity-assets"></a>Gesegmenteerde oplossingen en patches gebruiken om geselecteerde entiteitactiva te exporteren

Gebruik oplossingssegmentatie om beter te regelen wat u in oplossingen en oplossingspatches distribueert. Met oplossingsegmentatie kunt u oplossingen met geselecteerde entiteitsonderdelen exporteren, zoals entiteitsvelden, formulieren en weergaven, in plaats van volledige entiteiten met alle onderdelen. Om de gesegmenteerde patches en oplossingen te maken, kunt u de -gebruikersinterface voor oplossingen gebruiken, zonder dat u code hoeft te schrijven.  
  
 Naast dat dit u meer controle geeft over wat een oplossing bevat, kunt u bepalen wat er in een patch gaat. U kunt een patch voor een bovenliggende oplossing maken en exporteren als kleine update naar de basisoplossing. Wanneer u een oplossing kloont, voegt het systeem alle verwante patches samen in de basisoplossing en maakt een nieuwe versie.  
  
 Wanneer u met patches en gekloonde oplossingen werkt, houdt u de volgende informatie in gedachten:  
  
-   Een patch is een incrementele kleine update voor de bovenliggende oplossing. Met een patch kunt u in de bovenliggende oplossing onderdelen toevoegen of bijwerken wanneer deze zijn geïnstalleerd op het doelsysteem, maar u kunt geen onderdelen uit de oplossing verwijderen.  
  
-   Een patch kan slechts één bovenliggende oplossing hebben, maar een bovenliggende oplossing kan een of meer patches hebben.  
  
-   Een patch wordt gemaakt voor een onbeheerde oplossing. U kunt geen patch maken voor een beheerde oplossing.  
  
-   Als u een patch naar een doelsysteem exporteert, moet u deze als beheerde patch exporteren. Gebruik geen onbeheerde patches in productieomgevingen.  
  
-   De bovenliggende oplossing moet aanwezig in het doelsysteem zijn om een patch te installeren.  
  
-   U kunt een patch verwijderen of bijwerken.  
  
-   Als u een bovenliggende oplossing verwijdert, worden alle onderliggende patches eveneens verwijderd. Het systeem geeft u een waarschuwing dat u de verwijdering niet ongedaan kunt maken. De verwijdering wordt uitgevoerd in één transactie. Als een van de patches of de bovenliggende oplossing niet kan worden verwijderd, wordt de volledige transactie teruggedraaid.  
  
-   Nadat u de eerste patch voor een bovenliggende oplossing hebt gemaakt, wordt de oplossing vergrendeld en kunt u geen wijzigingen in deze oplossing maken of deze exporteren. Echter, wanneer u alle onderliggende patches verwijdert, wordt de bovenliggende oplossing ontgrendeld.  
  
-   Wanneer u een basisoplossing kloont, worden alle onderliggende patches samengevoegd in de basisoplossing en ontstaat er een nieuwe versie. U kunt onderdelen toevoegen, bewerken of verwijderen in de gekloonde oplossing.  
  
-   Een gekloonde oplossing is een vervanging van de basisoplossing als deze op het doelsysteem als beheerde oplossing is geïnstalleerd. Normaal gesproken, gebruikt u een gekloonde oplossing om een grote update voor de voorafgaande oplossing te verzenden.  
  
## <a name="understanding-version-numbers-for-cloned-solutions-and-patches"></a>Inzicht in versienummers voor gekloonde oplossingen en patches  
 De versie van een oplossing kent de volgende indeling: primair.secundair.build.revisie. Een patch moet een hogere build of revisienummer hebben dan de bovenliggende oplossing. De patch mag geen hogere primaire of secundaire versie hebben. Bijvoorbeeld, voor een basisoplossing versie 3.1.5.7 kan de patch versie 3.1.5.8 of 3.1.7.0, maar niet versie 3.2.0.0 zijn. Een gekloonde oplossing moet een versienummer hebben dat groter dan of gelijk is aan het versienummer van de basisoplossing. Bijvoorbeeld, voor een basisoplossing versie 3.1.5.7 kan een gekloonde oplossing versie 3.2.0.0 of versie 3.1.5.7 zijn. In de gebruikersinterface kunt u alleen de primaire en secundaire versiewaarden van een gekloonde oplossing instellen, en de build- of revisiewaarden voor een patch.  
  
## <a name="create-a-segmented-solution-with-the-entity-assets-you-want"></a>Maak een gesegmenteerde oplossing met de gewenst entiteitsonderdelen  
 Om een gesegmenteerde oplossing te maken, begint u met het maken van een onbeheerde oplossing en het toevoegen van de bestaande resources. U kunt meerdere systeem- of aangepaste entiteiten toevoegen, en voor elke entiteit de onderdelen kiezen die u in de oplossing wilt opnemen. De wizard-achtige installatie leidt u stap voor stap door het proces van het toevoegen van entiteitsonderdelen.  
  
1. Ga naar **[Instellingen](../model-driven-apps/advanced-navigation.md#settings)** > **Oplossingen**.   
  
2.  Selecteer **Nieuw** en maak een oplossing. Voer gegevens in de verplichte velden in. Kies **Opslaan en sluiten**.  
  
3.  Open de oplossing die u zojuist hebt gemaakt. Selecteer in de vervolgkeuzelijst **Bestaande toevoegen** de optie **Entiteit**.  
  
4.  In het dialoogvenster **Oplossingsonderdelen selecteren**, selecteert u een of meerdere entiteiten die u wilt toevoegen aan de oplossing. Selecteer **OK**.  
  
5.  De wizard wordt geopend. Volg de wizard om voor elke geselecteerde entiteit activa toe te voegen aan de oplossing.  
  
6.  Selecteer **Publiceren** om de wijzigingen van kracht te laten worden.  
  
 De volgende illustraties bieden een voorbeeld van het maken van een gesegmenteerde oplossing door entiteitsactiva uit de entiteiten `Account`, `Case` en `Contact` te kiezen.  
  
 Kies eerst het onderdeel **Entiteit**.  
  
 ![Bestaande bronnen toevoegen.](media/solution-segmentation-add-existing-resources-admin.png "Bestaande bronnen toevoegen.")  
  
 Selecteer vervolgens de oplossingsonderdelen.  
  
 ![De onderdelen van de oplossing selecteren.](media/solution-segmentation-select-components-admin.png "De onderdelen van de oplossing selecteren.")  
  
 Volg de wizard. Begin bij stap 1 in alfabetische volgorde met het selecteren van de activa voor de eerste entiteit, de `Account`-entiteit, die hier te zien is.  
  
 ![De wizard starten.](media/solution-segmentation-wizard-starts-admin.png "De wizard starten.")  
  
 Open het tabblad **Velden** en selecteer het veld **Accountnummer**.  
  
 ![De activa van de accountentiteit selecteren.](media/solution-segmentation-select-account-assets-admin.png "De activa van de accountentiteit selecteren.")  
  
 Voeg in stap 2 voor de entiteit **Aanvraag** alle activa toe.  
  
 ![De activa van de aanvraagentiteit selecteren.](media/solution-segmentation-select-case-assets-admin.png "De activa van de aanvraagentiteit selecteren.")  
  
 In Stap 3, voeg het **Speciale datum**-veld toe voor de **Contactpersoon**-entiteit.  
  
 ![De activa van de contactentiteit selecteren.](media/solution-segmentation-select-contact-assets-admin.png "De activa van de contactentiteit selecteren.")  
  
 Hierdoor bevat de gesegmenteerde oplossing die wordt gemaakt, drie entiteiten: `Account`, `Case` en `Contact`. Elke entiteit bevat alleen de activa die u hebt gekozen.  
  
 ![Oplossing met entiteiten.](media/solution-segmentation-solution-entities-admin.png "Oplossing met entiteiten.")  
  
## <a name="create-a-solution-patch"></a>Een oplossingspatch maken  
 Een bevat patch wijzigingen aan de bovenliggende oplossing, zoals het toevoegen of bewerken van onderdelen en activa weer. U hoeft de onderdelen van het bovenliggende element alleen op te nemen als u van plan bent ze te bewerken.  
  
 #### <a name="create-a-patch-for-an-unmanaged-solution"></a>Een patch maken voor een onbeheerde oplossing.  
  
1. Ga naar **[Instellingen](../model-driven-apps/advanced-navigation.md#settings)** > **Oplossingen**.   
  
2.  Selecteer in de lijst een onbeheerde oplossing om een patch voor te maken. Selecteer **Een patch klonen**. Het dialoogvenster dat wordt geopend, bevat de naam en het patchversienummer van de basisoplossing. Selecteer **Opslaan**.  
  
3.  In het raster, zoek en open de zojuist gemaakte patch. Net als bij de basisoplossing, volgt u de wizard om de gewenste onderdelen en activa toe te voegen.  
  
4.  Selecteer **Publiceren** om de wijzigingen van kracht te laten worden.  
  
 De volgende illustraties bieden een voorbeeld van het maken van een patch voor een bestaande oplossing. Selecteer eerst **Een patch klonen** (in de gecomprimeerde weergave wordt het pictogram **Een patch klonen** weergegeven als twee kleine vierkanten, zie onderstaande afbeelding).  
  
 ![Een patchpictogram klonen.](media/solution-segmentation-click-patch-icon-admin.png "Een patchpictogram klonen.")  
  
 In het dialoogvenster **Een patch klonen** ziet u dat het versienummer van de patch op het versienummer van de bovenliggende oplossing is gebaseerd, maar het buildnummer met één wordt verhoogd. Elke volgende patch heeft een hoger build- of revisienummer dan de voorgaande patch.  
  
 ![Dialoogvenster Klonen naar patch gebruiken.](media/solution-segmentation-clone-patch-dialog-admin.png "Dialoogvenster Klonen naar patch gebruiken.")  
  
 Het volgende screenshot toont de basisoplossing **SegmentedSolutionExample**, versie **1.0.1.0** en de patch **SegmentedSolutionExample_Patch**, versie **1.0.2.0**.  
  
 ![Een raster met oplossingen en patches.](media/solution-segmentation-solution-patch-grid-admin.png "Een raster met oplossingen en patches.")  
  
 In de patch hebben we een nieuwe aangepaste entiteit toegevoegd met de naam `Book` en alle activa van de `Book`-entiteit in de patch opgenomen.  
  
 ![Aangepaste entiteit toevoegen in de patch.](media/solution-segmentation-add-book-patch-admin.png "Aangepaste entiteit toevoegen in de patch.")  
  
## <a name="clone-a-solution"></a>Een oplossing klonen  
 Wanneer u een onbeheerde oplossing kloont, worden alle patches die aan deze oplossing zijn gerelateerd samengevoegd in de gemaakte versie van de oorspronkelijke oplossing.  
  
1. Ga naar **[Instellingen](../model-driven-apps/advanced-navigation.md#settings)** > **Oplossingen**.   
  
2.  In de lijst, selecteert u een onbeheerde oplossing die u wilt klonen. Selecteer **Oplossing klonen**. Het dialoogvenster dat wordt geopend, bevat de naam en het nieuwe versienummer van de basisoplossing. Selecteer **Opslaan**.  
  
3.  Selecteer **Publiceren** om de wijzigingen van kracht te laten worden.  
  
 In het voorbeeld ziet u in het dialoogvenster **Klonen naar oplossing** het nieuwe oplossingversienummer.  
  
 ![Dialoogvenster Klonen naar oplossing gebruiken.](media/solution-segmentation-clone-solution-dialog-admin.png "Dialoogvenster Klonen naar oplossing gebruiken.")  
  
 Na het klonen bevat de nieuwe oplossingversie drie oorspronkelijke entiteiten (`Account`, `Case` en `Contact`) en de aangepaste entiteit met de naam `Book`, die is toegevoegd aan de patch. Elke entiteit bevat alleen de activa die zijn toegevoegd in het voorbeeld.  
  
 ![Een gekloonde oplossing met samgevouwen patch.](media/solution-segmentation-solution-rolled-up-patch-admin.png "Een gekloonde oplossing met samgevouwen patch.")  
  
## <a name="next-steps"></a>Volgende stappen  
 [Oplossingsoverzicht](solutions-overview.md) [Patches maken om oplossingupdates te vereenvoudigen]

