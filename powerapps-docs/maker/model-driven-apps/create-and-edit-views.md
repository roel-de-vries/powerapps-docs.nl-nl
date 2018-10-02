---
title: Een weergave voor modelgestuurde apps maken of bewerken in PowerApps | MicrosoftDocs
description: Een weergave maken of bewerken
ms.custom: ''
ms.date: 06/11/2018
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
ms.assetid: bd1d393d-16ea-40ac-8136-26643c37dd2a
caps.latest.revision: 25
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-or-edit-a-model-driven-app-view"></a>Een weergave voor modelgestuurde apps maken of bewerken

<a name="BKMK_CreatingAndEditingViews"></a>   

 In dit onderwerp maakt u een nieuwe aangepaste openbare weergave. U bewerkt ook een bestaande weergave.  
  
### <a name="create-a-new-view"></a>Een nieuwe weergave maken  
  
1.  Op de site [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) selecteert u **Modelgestuurd** (linkerbenedenhoek van het navigatievenster).  

    ![Modelgestuurde ontwerpmodus](media/model-driven-switch.png)

    > [!IMPORTANT]
    > Als de **modelgestuurde** ontwerpmodus niet beschikbaar is, moet u mogelijk [een omgeving maken](https://docs.microsoft.com/powerapps/administrator/create-environment). 

2.  Vouw **Gegevens** uit, selecteer **Entiteiten**, selecteer de entiteit **Account** en selecteer het tabblad **Weergaven**. 

3.  Selecteer **Weergave toevoegen** op de werkbalk.  

4.  Geef in het dialoogvenster **Eigenschappen weergeven** een **naam** op, zoals **Accounts met 25 medewerkers of meer**, en eventueel een **beschrijving** voor de weergave. Selecteer vervolgens **OK**.

    > [!div class="mx-imgBorder"] 
    > ![Eigenschappen weergeven](media/view-properties.png)
  
5.  Selecteer in het rechterdeelvenster Algemene taken de optie **Kolommen toevoegen**. Selecteer in het dialoogvenster **Kolommen toevoegen** de optie **Aantal werknemers** en **OK**.  

    > [!div class="mx-imgBorder"] 
    > ![Kolom Aantal werknemers](media/column-no-employees.png)
  
6. Selecteer in het rechterdeelvenster Algemene taken de optie **Filtercriteria bewerken**. Selecteer vervolgens in het dialoogvenster Filtercriteria bewerken achtereenvolgens **Aantal werknemers**, **Is groter dan of gelijk aan** en **25**.  

    > [!div class="mx-imgBorder"] 
    > ![Filtercriteria bewerken](media/edit-filter-criteria.png)

7.  Selecteer **OK** om het dialoogvenster **Filtercriteria bewerken** te sluiten en selecteer vervolgens **Opslaan en sluiten** in de weergave-editor.  
  
8.  Uw weergave is nu beschikbaar op het tabblad **Weergaven** op de PowerApps-site en kan dus worden toegevoegd aan een app.
  
### <a name="edit-a-view"></a>Een weergave bewerken  
  
1.  Selecteer op het tabblad **Weergaven** op de PowerApps-site de weergave **Aantal werknemers**.
  
2.  Wijzig de **naam** voor de weergave in **Accounts met 25 of meer werknemers in Utrecht** en selecteer **OK**.  

3.  Selecteer in het rechterdeelvenster Algemene taken de optie **Kolommen toevoegen**. Selecteer in het dialoogvenster **Kolommen toevoegen** vervolgens de optie **Adres 1: plaats** en **OK**.  

4. Selecteer in het rechterdeelvenster Algemene taken de optie **Filtercriteria bewerken** en voeg in het gelijknamige dialoogvenster een tweede filtercomponent toe. Selecteer **Adres 2: provincie**, selecteer **Is gelijk aan** en voer **Utrecht** in. 

    > [!div class="mx-imgBorder"] 
    > ![Adres 2: provincie](media/column-address-2-state.png)

5. Selecteer **OK** om het dialoogvenster **Filtercriteria bewerken** te sluiten en selecteer vervolgens **Opslaan en sluiten** in de weergave-editor.  
  

## <a name="create-a-new-view-from-an-existing-view"></a>Een nieuwe weergave maken van een bestaande weergave  
 Volg de procedure voor het bewerken van een weergave, behalve dat u niet **Opslaan en sluiten**, maar **Opslaan als** selecteert en een nieuwe **naam** en **beschrijving** voor de weergave invoert.  
 
### <a name="next-steps"></a>Volgende stappen
[Kolommen kiezen en configureren](choose-and-configure-columns.md)  
  
[Filtercriteria bewerken](edit-filter-criteria.md)  
  
[De sortering configureren](configure-sorting.md)  
