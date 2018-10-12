---
title: Navigatie wijzigen binnen een modelgestuurd app-formulier in PowerApps | Microsoft Docs
description: Informatie over het wijzigen van de navigatie binnen een formulier
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
ms.openlocfilehash: 5a8156875f669854a4ba4649e50a23e340f3ceff
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39673871"
---
# <a name="change-navigation-within-a-model-driven-app-form"></a>Navigatie wijzigen binnen een modelgestuurd app-formulier

 Navigatie binnen een formulier zorgt ervoor dat app-gebruikers lijsten met gerelateerde records kunnen weergeven. Elke entiteitsrelatie heeft eigenschappen om te bepalen of deze moet worden weergegeven. Meer informatie: [Item op navigatiedeelvenster voor primaire entiteit](../common-data-service/create-edit-1n-relationships-solution-explorer.md#navigation-pane-item-for-primary-entity)  
  
 Alle entiteitsrelaties die zijn geconfigureerd om te worden weergegeven kunnen worden overschreven in de formulier-editor. U kunt ook navigatiekoppelingen opnemen om webresources of andere websites via formuliernavigatie weer te geven.  
  
 Zie voor stapsgewijze instructies [Entiteitsrelaties maken en bewerken voor Common Data Service for Apps](../common-data-service/create-edit-entity-relationships.md)  
  
 Om het bewerken van navigatie in te schakelen, moet u eerst **Navigatie** selecteren uit de groep **Selecteren** op het tabblad **Start** van de formulierontwerper.  
 
 ![Navigatie-opdracht](media/navigation-command.png)
 
 In het rechterdeelvenster kunt u vanuit de **Relatieverkenner** filteren op 1:N-relaties (een-op-veel) of N:N-relaties (veel-op-veel) of alle beschikbare relaties weergeven. Het selectievakje **Alleen ongebruikte relaties weergeven** is uitgeschakeld en geselecteerd. U kunt dus elke relatie slechts één keer toevoegen.  
  
 ![Relatieverkenner](media/relationship-explorer.png)

 Als u een relatie wilt toevoegen vanuit de **Relatieverkenner**, dubbelklikt u op de relatie. Deze wordt dan toegevoegd onder de momenteel geselecteerde relatie in het navigatiedeelvenster. Dubbelklik op een relatie in het navigatieveld en u kunt het label wijzigen op het tabblad **Weergave**. Op het tabblad **Naam** ziet u meer informatie over de relatie. Gebruik de knop **Bewerken** om de definitie van de entiteit te openen.  
  
 Er zijn vijf groepen in het navigatiedeelvenster. U kunt deze slepen om ze te verplaatsen en erop dubbelklikken als u het label wilt wijzigen, maar u kunt ze niet verwijderen. Deze groepen worden alleen weergegeven wanneer ze niet leeg zijn. Dus als u niet wilt dat een groep wordt weergegeven, moet u deze gewoon leeg laten.  
  
 Gebruik de knop **Navigatiekoppeling** in de groep **Besturing** op het tabblad **Invoegen** om een koppeling naar een webresource of externe URL toe te voegen.  
 
 ![Navigatiekoppeling](media/navigation-link.png)
 
<a name="BKMK_NavigationLinkProperties"></a>   
### <a name="navigation-link-properties"></a>Eigenschappen van navigatiekoppeling  
 Navigatiekoppelingen hebben de volgende eigenschappen:  
  
|Eigenschap|Beschrijving|  
|--------------|-----------------|  
|Naam|**Vereist**: tekst die moet worden weergegeven als een label.|  
|Pictogram|Gebruik een webresource van 32x32 pixels. We raden aan een PNG-afbeelding met een transparante achtergrond te gebruiken.|  
|Webresource|Geef een webresource op om weer te geven in het hoofdvenster van het formulier.|  
|Externe URL|Geef een URL van een pagina op om weer te geven in het hoofdvenster van het formulier.|  

<a name="BKMK_PrivacyNotices"></a>   

## <a name="privacy-notices"></a>Privacyverklaringen  
 [!INCLUDE[cc_privacy_crm_website_preview_control](../../includes/cc-privacy-crm-website-preview-control.md)]    
  
 [!INCLUDE[cc_privacy_multimedia_control](../../includes/cc-privacy-multimedia-control.md)]  

## <a name="next-steps"></a>Volgende stappen

[Overzicht van gebruikersinterface van de formulier-editor](form-editor-user-interface-legacy.md)