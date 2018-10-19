---
title: Navigatie in een formulier voor modelgestuurde apps wijzigen in PowerApps | MicrosoftDocs
description: Lees hoe u de navigatie kunt wijzigen binnen een formulier
ms.custom: ''
ms.date: 06/06/2018
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
ms.assetid: 4c379202-9f0e-4003-a49c-efff53e7f79f
caps.latest.revision: 63
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="change-navigation-within-a-model-driven-app-form"></a>Navigatie in een formulier voor modelgestuurde apps wijzigen

 Met navigatie binnen een formulier kunnen gebruikers van apps lijsten met gerelateerde records bekijken. Elke entiteitsrelatie heeft eigenschappen om te beheren of de relatie moet worden weergegeven. Meer informatie: [Navigatiedeelvensteritem voor primaire entiteit](../common-data-service/create-edit-1n-relationships-solution-explorer.md#navigation-pane-item-for-primary-entity)  
  
 Alle entiteitsrelaties die zijn geconfigureerd om te worden weergegeven, kunnen worden genegeerd in de formuliereneditor. U kunt ook navigatiekoppelingen opnemen om webresources of andere websites weer te geven via formuliernavigatie.  
  
 Zie voor stapsgewijze instructies [Entiteitsrelaties voor Common Data Service voor Apps maken en bewerken](../common-data-service/create-edit-entity-relationships.md)  
  
 Als u de bewerking van navigatie wilt inschakelen, moet u eerst **Navigatie** selecteren in de groep **Selecteren** van het tabblad **Start** in de formulierontwerper.  
 
> [!div class="mx-imgBorder"] 
> ![Navigatieopdracht](media/navigation-command.png)
 
 In de rechterdeelvenster kunt u in **Relatieverkenner** filteren op 1:N- (een-op-veel) of N:N-relaties (veel-op-veel) of alle beschikbare relaties bekijken. Het **selectievakje Alleen ongebruikte relaties weergeven** is uitgeschakeld en geselecteerd. U kunt elke relatie dus slechts één keer toevoegen.  
 
 > [!div class="mx-imgBorder"] 
 > ![Relatieverkenner](media/relationship-explorer.png)

 Als u een relatie vanuit **Relatieverkenner** wilt toevoegen, dubbelklikt u op die relatie om deze toe te voegen onder de momenteel geselecteerde relatie in het navigatiegebied. Dubbelklik op een relatie in het navigatiegebied en u kunt het label op het tabblad **Weergeven** wijzigen. Op het tabblad **Naam** kunt u informatie over de relatie zien. Gebruik de knop **Bewerken** om de definitie van de entiteit te openen.  
  
 Er zijn vijf groepen in het navigatiegebied. U kunt ze verslepen om ze te verplaatsen en erop dubbelklikken om het label te wijzigen, maar u kunt ze niet verwijderen. Deze groepen worden alleen weergegeven wanneer er iets in zit. Dus als u een groep wilt weergeven, moet er u niets aan toevoegen.  
  
 Gebruik de knop **Navigatiekoppeling** in de groep **Besturingselement** van het tabblad **Invoegen** om een koppeling naar een webresource of een externe URL toe te voegen.  
 
 ![Navigatiekoppeling](media/navigation-link.png)
 
<a name="BKMK_NavigationLinkProperties"></a>   
### <a name="navigation-link-properties"></a>Eigenschappen van navigatiekoppeling  
 Navigatiekoppelingen hebben de volgende eigenschappen:  
  
|Eigenschap|Beschrijving|  
|--------------|-----------------|  
|Naam|**Vereist**: Tekst om weer te geven als label.|  
|Pictogram|Gebruik een 32x32-pixelwebresource. U wordt aangeraden een PNG-afbeelding met een transparante achtergrond te gebruiken.|  
|Webresource|Geef een webresource die wordt weergegeven in het hoofddeelvenster van het formulier.|  
|Externe URL|Geef de URL van een pagina op die wordt weergegeven in het hoofdvenster van het formulier.|  

<a name="BKMK_PrivacyNotices"></a>   

## <a name="privacy-notices"></a>Privacyverklaringen  
 [!INCLUDE[cc_privacy_crm_website_preview_control](../../includes/cc-privacy-crm-website-preview-control.md)]    
  
 [!INCLUDE[cc_privacy_multimedia_control](../../includes/cc-privacy-multimedia-control.md)]  

## <a name="next-steps"></a>Volgende stappen

[Overzicht van de gebruikersinterface van de formuliereneditor](form-editor-user-interface-legacy.md)
