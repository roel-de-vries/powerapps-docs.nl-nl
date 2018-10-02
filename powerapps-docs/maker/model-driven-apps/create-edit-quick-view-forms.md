---
title: Snelle-weergaveformulieren voor modelgestuurde apps maken of bewerken in PowerApps | MicrosoftDocs
description: Informatie over het maken of bewerken van een snelle-weergaveformulier
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
ms.assetid: 9b101734-cc11-4d05-bd45-eb611eae9931
caps.latest.revision: 14
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="create-a-model-driven-app-quick-view-form-to-view-information-about-a-related-entity"></a>Een snelle-weergaveformulier voor modelgestuurde apps maken en bewerken om informatie over een gerelateerde entiteit weer te geven

In dit onderwerp leert u hoe u een snelle-weergaveformulier maakt en hoe u een besturingselement voor snelle weergave toevoegt aan een hoofdformulier. 

U kunt een snelle-weergaveformulier aan een ander formulier toevoegen als een besturingselement voor snelle weergave. Het biedt een sjabloon om informatie over een gerelateerde entiteitsrecord weer te geven in een formulier voor een andere entiteitsrecord. Dit betekent dat uw app-gebruikers niet naar een andere record hoeven te navigeren om de benodigde gegevens te zien die ze nodig hebben om hun werk te doen.  
  
 De snelle-weergavefuncties worden gekoppeld met een opzoekveld dat in een formulier is opgenomen. Als de opzoekveldwaarde niet is ingesteld, is het snelle-weergavebesturingselement niet zichtbaar. Gegevens in snelle-weergavebesturingselementen zijn niet bewerkbaar en snelle-weergaveformulieren ondersteunen geen formulierscripts.  
  
 Omdat de snelle-weergaveformulieren met een snelle-weergavebesturingselement worden weergegeven in een formulier, bevatten ze geen, kop- of voettekst of navigatiegebieden. De beveiligingsrollen kunnen niet worden toegewezen aan snelle-weergaveformulieren en deze kunnen niet worden geactiveerd of gedeactiveerd zijn.  
  
<a name="BKMK_CreateQFV"></a>   
## <a name="create-a-quick-view-form"></a>Een snelle-weergaveformulier maken  
 U maakt snelle weergaveformulieren met de formuliereneditor op dezelfde manier waarop u andere formulieren maakt. Snelle weergaveformulieren zijn alleen-lezen. Gebruik deze om formulieren te maken die alleen bedoeld zijn om te lezen.  
  
1. Op de site [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) selecteert u **Modelgestuurd** (linkerbenedenhoek van het navigatievenster).  

    ![Modelgestuurde ontwerpmodus](media/model-driven-switch.png)

    > [!IMPORTANT]
    > Als de **modelgestuurde** ontwerpmodus niet beschikbaar is, moet u mogelijk [een omgeving maken](https://docs.microsoft.com/powerapps/administrator/create-environment).     
  
2. Vouw **Gegevens** uit, selecteer **Entiteiten**, selecteer de gewenste entiteit en selecteer het tabblad **Formulieren**. 
  
3. Selecteer **Formulier toevoegen** > **Snelle-weergaveformulier** op de werkbalk.  
  
4. Selecteer **Formuliereigenschappen** op de werkbalk van de formuliereneditor.  
  
5. Voer in het dialoogvenster **Formuliereigenschappen** een **formuliernaam** en **beschrijving** in om dit snelle-weergaveformulier te onderscheiden van andere formulieren. Selecteer **OK** om het dialoogvenster **Formuliereigenschappen** te sluiten.  
  
6. In de formulierontwerper sleept u de gewenste velden van **Veldverkenner** naar de sectie in het formulier. 
  
    > [!IMPORTANT]
    >  Als u een veld toevoegt en **Veldvereiste** > **Onderneming vereist** selecteert en vervolgens dat opslaat, kunt u het veld niet verwijderen.  
  
7. Selecteer **Opslaan** om de formuliereneditor op te slaan en te sluiten.  

8. Selecteer **Publiceren** om het nieuwe formulier in de toepassing te bekijken.
  
<a name="BKMK_EditQVF"></a>   
## <a name="edit-a-quick-view-form"></a>Een snelle-weergaveformulier bewerken  
 De snelle-weergaveformulieren hebben een vereenvoudigde indeling omdat ze zijn ontworpen om in een formulierensectie te worden weergegeven. Slechts één enkel kolomtabblad is beschikbaar. U kunt alleen extra enkele kolomsecties, velden, subgrids, en verbindingsstukken toevoegen.   
  
> [!NOTE]
>  U kunt een veld dat **Onderneming vereist** is, niet verwijderen. U ontvangt dit bericht als u probeert om het veld te verwijderen: “Het veld dat u probeert te verwijderen, is vereist voor het systeem of de onderneming.” Als u het veld niet op het formulier wilt hebben, moet u het volledige formulier verwijderen en vervolgens opnieuw maken.  
  
 Wanneer u een snelle-weergaveformulier bewerkt, moet u de wijzigingen publiceren voordat ze in de toepassing zichtbaar zijn.  
  
<a name="BKMK_AddQVF"></a>   
## <a name="add-a-quick-view-control-to-a-main-form"></a>Voeg een snelle-weergavebesturingselement toe aan een hoofdformulier  
 De snelle-weergaveformulieren kunnen alleen worden toegevoegd aan een hoofdformulier waar een opzoekveld voor die zich op de entiteit van het snelle-weergaveformulier richt.  
  
1.  Op de site [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) selecteert u **Modelgestuurd** (linkerbenedenhoek van het navigatievenster).  

    > [!IMPORTANT]
    > Als de **modelgestuurde** ontwerpmodus niet beschikbaar is, moet u mogelijk [een omgeving maken](https://docs.microsoft.com/powerapps/administrator/create-environment).     
  
2.  Vouw **Gegevens** uit, selecteer **Entiteiten**, selecteer de gewenste entiteit en selecteer het tabblad **Formulieren**.  

3. Selecteer een formulier waarvoor **Hoofd** is ingesteld bij **Type**.

4. Selecteer in de formulierontwerper het tabblad **Invoegen** en selecteer vervolgens **Snelle-weergaveformulier** op de werkbalk.  
  
5.  Stel in het dialoogvenster **Eigenschappen van besturingselement snelle weergave** de eigenschappen voor het besturingselement snelle weergave in, zoals **Naam**, **Label** en **Snelle-weergaveformulier**. Meer informatie: [Eigenschappen van besturingselement snelle weergave](quick-view-control-properties-legacy.md).  
  
6.  Selecteer **OK** om het dialoogvenster **Eigenschappen van besturingselement snelle weergave** te sluiten.  
  
7.  Selecteer het tabblad **Start** en selecteer **Publiceren** om het besturingselement Snelle weergave weer te geven in het formulier.  
  
## <a name="next-steps"></a>Volgende stappen   
 [Formulieren maken en ontwerpen](create-design-forms.md)   
 [Formulieren voor snelle invoer maken of bewerken](create-edit-quick-create-forms.md)
