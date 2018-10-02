---
title: Eigenschappen opgeven voor modelgestuurde Unified Interface-apps in PowerApps | MicrosoftDocs
description: Leer hoe u het rasterbesturingselement kunt configureren voor uw app
keywords: ''
ms.date: 06/06/2018
ms.service: crm-online
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: 3ecea4a7-0d18-4ccd-9609-3a62179e9e1b
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
caps.latest.revision: 0
topic-status: Drafting
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="specify-properties-for-model-driven-unified-interface-apps"></a>Eigenschappen opgeven voor modelgestuurde Unified Interface-apps

Het Unified Interface-raamwerk gebruikt ook goed reagerende ontwerpprincipes om een optimale weergave- en interactie-ervaring te bieden bij elk schermformaat en elke weergavestand. Met modelgestuurde apps die gebruikmaken van het Unified Interface-raamwerk, reageert het besturingselement voor raster(weergave) goed. Als het formaat van de container afneemt, bijvoorbeeld op telefoons en kleinere schermen, wordt het raster getransformeerd in een lijst. 

Het alleen-lezen rasterbesturingselement geeft aan hoe een raster moet worden weergegeven bij verschillende schermformaten. Als u als maker van apps werkt met een Unified Interface-app, kunt u het alleen-lezen rasterbesturingselement en de bijbehorende eigenschappen configureren voor aangepaste rasters en lijsten.
- Eigenschap **Kaartformulier**: gebruik een kaartformulier voor lijsten in plaats van de standaardlijstsjabloon. Kaartformulieren bieden meer informatie voor lijstitems dan de standaard lijstsjabloon.
- Eigenschap **Gedrag opnieuw plaatsen**: gebruik deze parameter om op te geven of een raster moet worden weergegeven als een lijst of niet.

## <a name="allow-grid-to-reflow-into-list"></a>Raster toestaan om te worden weergegeven als lijst

Als u het alleen-lezen rRasterbesturingselement toevoegt aan uw lijst met besturingselementen, kunt u de volgende onderdelen configureren: 
- Een raster toestaan te worden weergegeven als lijst op kleine beeldschermen zoals mobiel.
- Geef alleen raster of alleen lijst op als weergavemodus.  

1. Open [oplossingenverkenner](advanced-navigation.md#solution-explorer).
2. Vouw in het navigatiedeelvenster **Entiteiten** uit, selecteer de juiste entiteit (zoals **Account** of **Contactpersoon**) en selecteer vervolgens op het tabblad **Besturingselementen** de optie **Besturingselement toevoegen**.

    ![Besturingselement voor toevoegen openen](media/UnifiedInterface_ReadOnlyGrid_AddControl.png "Besturingselement voor toevoegen openen")

3. Selecteer **Alleen-lezen raster** in de lijst met besturingselementen en kies vervolgens **Toevoegen**.

    Het besturingselement wordt toegevoegd aan de lijst met beschikbare besturingselementen.
   
    ![Een besturingselement selecteren](media/UnifiedInterface_ReadOnlyGrid_SelectControl.png "Een besturingselement selecteren")
    
4. Selecteer de apparaten (**Web**, **Telefoon** of **Tablet**) waarvoor u het raster alleen-lezen wilt maken.

    ![Het apparaattype selecteren](media/UnifiedInterface_ReadOnlyGrid_SelectDevice.png "Apparaten selecteren")

5. Configureer de eigenschap **Kaartformulier**.

    U kunt de eigenschap Kaartformulier gebruiken om lijstitems weer te geven in plaats van de standaard lijstsjabloon. Kaartformulieren bieden meer informatie voor lijstitems dan de standaard lijstsjabloon.    

    a. Kies het potloodpictogram naast **Kaartformulier**.

    ![Kaartformulier bewerken](media/UnifiedInterface_ReadOnlyGrid_CardForm.png "Kaartformulier bewerken")

    b.  Selecteer de typen **Entiteit** en **Kaartformulier**.

    ![Eigenschappen van kaartformulier](media/UnifiedInterface_ReadOnlyGrid_CardFormProperties.png "Eigenschappen van kaartformulier")

    c. Kies **OK**.
6. Configureer de eigenschap **Gedrag opnieuw plaatsen**. 
    
    a. Kies het potloodpictogram naast **Gedrag opnieuw plaatsen**.

    ![Gedrag opnieuw plaatsen bewerken](media/UnifiedInterface_ReadOnlyGrid_EditReflow.png "Gedrag opnieuw plaatsen bewerken")

    b. Selecteer het stroomtype voor rasters in de vervolgkeuzelijst **Binden aan statische opties**.
    |Stroomtype|Beschrijving|
    |--------------|--------------------|
    |**Opnieuw plaatsen**|Hiermee wordt toegestaan dat het raster wordt weergegeven in de lijstmodus afhankelijk van of er voldoende schermruimte is.|
    |**Alleen raster**|Hiermee wordt ingesteld dat het raster in een lijst moet worden weergegeven zelfs als er niet voldoende schermruimte is.|
    |**Alleen lijst**|Wordt alleen weergegeven als een lijst ook als er voldoende ruimte is voor weergave als raster.|
    
     ![Eigenschappen van Gedrag opnieuw plaatsen](media/UnifiedInterface_ReadOnlyGrid_ReflowProperties.png "Eigenschappen van Gedrag opnieuw plaatsen")

    c. Kies **OK**.


7.  Sla de wijzigingen op en publiceer deze. 


## <a name="conditional-image"></a>Voorwaardelijke afbeelding
U kunt met behulp van JavaScript een aangepast pictogram weergeven in plaats van een waarde in een lijst en de logica vaststellen die wordt gebruikt om deze te selecteren op basis van de waarden in een kolom. Voor meer informatie over voorwaardelijke afbeeldingen, raadpleegt u [Aangepaste pictogrammen weergeven in plaats van waarden in lijstweergaven](../common-data-service/display-custom-icons-instead.md).

## <a name="next-steps"></a>Volgende stappen
[Een weergave maken of bewerken](create-edit-views.md)
