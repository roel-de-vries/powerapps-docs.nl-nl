---
title: Eigenschappen opgeven voor modelgestuurde Unified Interface-apps in PowerApps | MicrosoftDocs
description: Instructies voor het configureren van het rasterbesturingselement voor uw app
keywords: ''
ms.date: 06/06/2018
ms.service: crm-online
ms.custom: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: 3ecea4a7-0d18-4ccd-9609-3a62179e9e1b
ms.author: matp
manager: kvivek
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
caps.latest.revision: 0
topic-status: Drafting
ms.openlocfilehash: 007ac566e317ee99bd85ab0675e5a53839800bb4
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39675420"
---
# <a name="specify-properties-for-model-driven-unified-interface-apps"></a>Eigenschappen opgeven voor modelgestuurde Unified Interface-apps

Voor het Unified Interface-framework worden responsieve ontwerpprincipes gebruikt voor een optimale weergave- en interactie-ervaring voor elke schermgrootte en -richting. Met modelgestuurde apps die het Unified Interface-framework gebruiken, kan het raster (weergave) responsief worden bestuurd. Naarmate de grootte van de container kleiner wordt, bijvoorbeeld op telefoons en kleinere viewports, wordt het raster omgezet in een lijst. 

Het besturingselement Alleen-lezenraster geeft aan hoe de stroom van een raster moet worden gewijzigd voor verschillende schermgrootten. Als u als app-maker met een Unified Interface-app werkt, kunt u het besturingselement Alleen-lezenraster en de bijbehorende eigenschappen configureren voor aangepaste rasters en lijsten.
- De eigenschap **Kaartformulier**: gebruik een kaartformulier voor lijsten in plaats van de standaardlijstsjabloon. Kaartformulieren bieden meer informatie voor lijstitems dan de standaardlijstsjabloon.
- De eigenschap **Gedrag stroomwijziging**: gebruik deze parameter om al dan niet een rasterstroomwijziging in een lijst op te geven.

## <a name="allow-grid-to-reflow-into-list"></a>Toestaan dat raster terugstroomt in lijst

Door het besturingselement Alleen-lezenraster aan uw lijst met besturingselementen toe te voegen, kunt u de volgende functies configureren: 
- Sta toe dat een raster op kleine beeldschermen, zoals op mobiele telefoons, terugstroomt in een lijst.
- Geef de renderingsmodus op als Alleen-raster of Alleen-lijst.  

1. Open de [oplossingsverkenner](advanced-navigation.md#solution-explorer).
2. Vouw in het navigatiedeelvenster **Entiteiten** uit, selecteer de toepasselijke entiteit (zoals **Account** of **Contactpersoon**) en selecteer vervolgens op het tabblad **Besturingselementen** de optie **Besturingselement toevoegen**.

    ![Het besturingselement Toevoegen openen](media/UnifiedInterface_ReadOnlyGrid_AddControl.png "Het besturingselement Toevoegen openen")

3. Selecteer **Alleen-lezenraster** vanuit de lijst met besturingselementen en kies vervolgens **Toevoegen**.

    Het besturingselement wordt toegevoegd aan de lijst met beschikbare besturingselementen.
   
    ![Een besturingselement selecteren](media/UnifiedInterface_ReadOnlyGrid_SelectControl.png "Een besturingselement selecteren")
    
4. Selecteer de apparaten (**internet**, **telefoon** of **tablet**) waarvoor u het raster Alleen-lezen wilt maken.

    ![Het apparaattype selecteren](media/UnifiedInterface_ReadOnlyGrid_SelectDevice.png "Apparaten selecteren")

5. Configureer de eigenschap **Kaartformulier**.

    U kunt de eigenschap Kaartformulier gebruiken om lijstitems weer te geven in plaats van de standaardlijstsjabloon. Kaartformulieren bieden meer informatie voor lijstitems dan de standaardlijstsjabloon.    

    a. Kies het potloodpictogram naast **Kaartformulier**.

    ![Kaartformulier bewerken](media/UnifiedInterface_ReadOnlyGrid_CardForm.png "Kaartformulier bewerken")

    b.  Selecteer de typen **Entiteit** en **Kaartformulier**.

    ![Kaartformuliereigenschappen](media/UnifiedInterface_ReadOnlyGrid_CardFormProperties.png "Kaartformuliereigenschappen")

    c. Kies **OK**.
6. Configureer de eigenschap **Gedrag stroomwijziging**. 
    
    a. Kies het potloodpictogram naast **Gedrag stroomwijziging**.

    ![Gedrag stroomwijziging bewerken](media/UnifiedInterface_ReadOnlyGrid_EditReflow.png "Gedrag stroomwijziging bewerken")

    b. Selecteer het rasterstroomtype vanuit de vervolgkeuzelijst**Binden aan statische opties**.
    |Stroomtype|Beschrijving|
    |--------------|--------------------|
    |**Opnieuw stromen**|Hiermee staat u toe dat het raster wordt weergegeven in de lijstmodus als er niet voldoende weergaveruimte is.|
    |**Alleen raster**|Hiermee beperkt u het raster zodat dit ook in de lijst kan terugstromen als er niet voldoende weergaveruimte is.|
    |**Alleen lijst**|Hiermee geeft u de items alleen als een lijst weer, zelfs wanneer er genoeg ruimte is om de items als raster weer te geven.|
    
     ![Eigenschappen stroomwijzigingsgedrag](media/UnifiedInterface_ReadOnlyGrid_ReflowProperties.png "Eigenschappen stroomwijzigingsgedrag")

    c. Kies **OK**.


7.  Sla de wijzigingen op en publiceer deze. 


## <a name="conditional-image"></a>Voorwaardelijke afbeelding
U kunt een aangepast pictogram weergeven in plaats van een waarde in een lijst en de logica vaststellen die wordt gebruikt om deze te selecteren op basis van de waarden van een kolom met behulp van JavaScript. Zie [Aangepaste pictogrammen weergeven in plaats van waarden in de lijst](../common-data-service/display-custom-icons-instead.md) voor meer informatie over voorwaardelijke afbeeldingen.

## <a name="next-steps"></a>Volgende stappen
[Een weergave maken of bewerken](create-edit-views.md)