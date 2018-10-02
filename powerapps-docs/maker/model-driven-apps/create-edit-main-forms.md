---
title: Hoofdformulieren voor modelgestuurde apps maken of bewerken in PowerApps | MicrosoftDocs
description: Informatie over het maken of bewerken van een hoofdformulier
ms.custom: ''
ms.date: 05/23/2018
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
ms.assetid: <needs new guid>
caps.latest.revision: 18
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-or-edit-a-model-driven-app-main-form-for-an-entity"></a>Een hoofdformulier voor modelgestuurde apps maken of bewerken 

In dit onderwerp leert u hoe u een hoofdformulier voor een entiteit maakt of bewerkt.

Als u een nieuw formulier voor een entiteit maakt, is het formuliertype Hoofd. Als het nieuwe formulier wordt geopend, is dit identiek aan het formulier Informatie. U kunt velden, secties, tabbladen, navigatie en eigenschappen voor het formulier toevoegen of bewerken en het formulier vervolgens opslaan.

Elk hoofdformulier bestaat uit een of meer tabbladen. Elk tabblad kan uit een of meer secties bestaan. Elke sectie bevat een of meer velden of IFRAMES. Als u uw nieuwe formulier wilt baseren op een bestaand formulier, kunt u een formulier klonen. 

Zorg dat u de beveiligingsrol systeembeheerder of systeemaanpasser of gelijkwaardige machtigingen hebt om deze taak te kunnen uitvoeren.

## <a name="how-to-create-or-edit-a-main-form"></a>Een hoofdformulier maken of bewerken
  
1.   Op de site [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) selecteert u **Modelgestuurd** (linkerbenedenhoek van het navigatievenster).  

     ![Modelgestuurde ontwerpmodus](media/model-driven-switch.png)

> [!IMPORTANT]
> Als de **modelgestuurde** ontwerpmodus niet beschikbaar is, moet u mogelijk [een omgeving maken](https://docs.microsoft.com/powerapps/administrator/create-environment).   
  
2.  Vouw **Gegevens** uit, selecteer **Entiteiten**, selecteer de gewenste entiteit en selecteer het tabblad **Formulieren**. 

3. Als u een nieuw hoofdformulier wilt maken, selecteert u **Formulier toevoegen** > **Hoofdformulier** op de werkbalk.  
    \-Als u een bestaand hoofdformulier wilt bewerken, selecteert u een formulier van het type **Ho** **ofd**.
  
3.  Wijzig het formulierontwerp op een van de volgende manieren, indien nodig:
    -   Een tabblad toevoegen aan een formulier
    -   Een sectie toevoegen aan een formulier
    -   Een veld toevoegen aan een formulier
    -   Een formulier-IFRAME toevoegen of bewerken
    -   Een subraster op een formulier toevoegen of bewerken
    -   Een formulierwebresource toevoegen of bewerken
    -   Formuliernavigatie toevoegen of bewerken voor gerelateerde entiteiten
    -   Formulierkop- en voetteksten bewerken
    -   Een tabblad, sectie, veld of IFRAME verwijderen
    -   De Formulierenassistent in- of uitschakelen
    
4.  Bewerk desgewenst de eigenschappen voor delen van het formulier:
    -   Formuliereigenschappen bewerken
    -   Formulierveldeigenschappen bewerken
    -   Tabbladeigenschappen bewerken
    -   Sectie-eigenschappen bewerken

5.  Voeg naar wens gebeurtenisscripts toe. 

6.  Bepaal met welke beveiligingsrollen het formulier kan worden weergegeven. Meer informatie: [Beveiligingsrollen toewijzen aan een formulier](https://docs.microsoft.com/dynamics365/customer-engagement/admin/assign-security-roles-form)

7.  Vooraf bekijken hoe het hoofdformulier wordt weergegeven en hoe gebeurtenissen werken:
    - Selecteer op het tabblad **Start** de optie **Voorbeeld** en selecteer vervolgens **Formulier maken**, **Formulier bijwerken** of **Alleen-lezen formulier**.
    - Als u het formulier Voorbeeld wilt sluiten, selecteert u **Sluiten** in het menu **Bestand**.

8.  Als u klaar bent met het bewerken van het formulier, selecteert u **Opslaan als**, voert u een naam voor het formulier in en selecteert u **OK**.

9.  Als de aanpassingen zijn voltooid, publiceert u deze:
    -   Als u aanpassingen voor alleen het onderdeel dat u momenteel bewerkt wilt publiceren, klikt u onder **Onderdelen** op de entiteit waaraan u hebt gewerkt en klikt u op **Publiceren**.
    -   Als u aanpassingen wilt publiceren voor alle niet-gepubliceerde onderdelen tegelijk, klikt u onder op **Onderdelen** **Entiteiten** en klikt u vervolgens op de opdrachtbalk op **Alle aanpassingen publiceren**.
    
 
### <a name="next-steps"></a>Volgende stappen  
[Overzicht van de gebruikersinterface van de formuliereneditor](form-editor-user-interface-legacy.md)
 
