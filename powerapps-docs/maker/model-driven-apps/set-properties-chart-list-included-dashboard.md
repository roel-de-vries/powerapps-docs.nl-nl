---
title: Eigenschappen instellen voor een grafiek of lijst voor modelgestuurde apps in een dashboard in PowerApps | MicrosoftDocs
description: Lees hoe u eigenschappen kunt instellen voor een grafiek of een lijst in een dashboard
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
ms.assetid: 50fb2ab0-5c1a-4a5e-8ebc-5603fecc4da0
caps.latest.revision: 26
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="set-properties-for-a-model-driven-app-chart-or-list-included-in-a-dashboard"></a>Eigenschappen instellen voor een grafiek of lijst voor modelgestuurde apps in een dashboard

Als u een grafiek- of lijstonderdeel in de dashboard-editor wilt bewerken, selecteert u de betreffende grafiek of lijst en selecteert u Onderdeel bewerken op de werkbalk van de dashboard-editor.   
  > [!div class="mx-imgBorder"] 
  > ![Grafiekonderdeel bewerken in dashboard-editor](media/dashboard-chart-select.png)

Het dialoogvenster **Eigenschappen instellen** wordt dan geopend.

  > [!div class="mx-imgBorder"] 
  > ![Eigenschappen instellen voor grafiek](media/set-properties-chart.png)  
 
U kunt de volgende grafiekeigenschappen instellen in het dialoogvenster **Eigenschappen instellen**:  
  
- **Name**. Unieke naam voor het diagram. Het systeem stelt een waarde voor, maar u kunt deze wijzigen.  
  
- **Label**. Het label dat boven aan de grafiek wordt weergegeven.  
  
- **Label op het dashboard weergeven**. Selecteer of wis dit selectievakje om het grafieklabel weer te geven of te verbergen.  
  
- **Entiteit**. Selecteer de entiteit (recordtype) waarop de grafiek moet worden gebaseerd. Deze instelling bepaalt de beschikbare waarden voor de standaardweergave en de eigenschappen van de standaardgrafiek.  
  
- **Standaardweergave**. Selecteer de weergave die wordt gebruikt voor het ophalen van de gegevens voor de grafiek.  
  
- **Standaardgrafiek**. Selecteer de standaardgrafiek die moet worden weergegeven als het dashboard de eerste keer wordt geopend. De beschikbare waarden worden bepaald door de waarde die voor de eigenschap Entiteit is ingesteld. Deze eigenschap werkt samen met de eigenschap Grafiekselectie weergeven. Een gebruiker kan het type grafiek wijzigen als de optie **Grafiekselectie weergeven** is ingeschakeld, maar de grafiek wordt weer de standaardgrafiek wanneer het dashboard de volgende keer wordt geopend.  
  
- **Alleen grafiek weergeven**. Schakel dit selectievakje in als u alleen de grafiek wilt weergeven. Schakel dit selectievakje uit als u de grafiek en de gekoppelde gegevens wilt weergeven.  
  
- **Grafiekselectie weergeven**. Schakel dit selectievakje in als u wilt dat gebruikers het type grafiek kunnen wijzigen (kolom, staaf, cirkel, enzovoort) wanneer ze het dashboard gebruiken. Als de gebruiker het type grafiek wijzigt, worden de instellingen niet opgeslagen. Het diagramtype keert terug naar de instelling Standaardgrafiek wanneer het dashboard wordt gesloten.  
  
U kunt de volgende lijsteigenschappen instellen in het dialoogvenster **Eigenschappen instellen**:  
  
- **Name**. Unieke naam voor de lijst. Het systeem stelt een waarde voor, maar u kunt deze wijzigen.  
  
- **Label**. Het label dat boven aan de lijst wordt weergegeven.  
  
- **Label op het dashboard weergeven**. Selecteer of wis dit selectievakje om het lijstlabel weer te geven of te verbergen.  
  
- **Entiteit**. Selecteer de entiteit (recordtype) waarop de lijst moet worden gebaseerd. Deze instelling bepaalt de beschikbare waarden voor de standaardweergave en de eigenschappen van de standaardlijst.  
  
- **Standaardweergave**. Selecteer de weergave die wordt gebruikt om de gegevens in de lijst op te halen. Een gebruiker kan de weergave veranderen maar de lijst keert naar de standaardweergave terug wanneer het dashboard de volgende keer wordt geopend.  
  
- **Zoekvak weergeven**. Schakel dit selectievakje in als u boven aan de lijst een zoekvak wilt weergeven. Als het zoekvak is opgenomen, kunt u of andere gebruikers records in de lijst zoeken tijdens runtime.  
  
- **Index weergeven**. Schakel dit selectievakje in als u onder aan de lijst de A tot Z-filters wilt weergeven. Als de A tot Z-filters worden weergegeven, kunt u of kunnen andere gebruikers een letter selecteren om naar records te gaan die met die letter beginnen.  
  
- **Weergave selecteren**. Maak een keuze uit de volgende waarden:  
  
    - **Uit**. De weergaveselector niet weergeven. U of andere gebruikers kunt de weergaven niet wijzigen tijdens runtime.  
  
    - **Alle weergaven weergeven**. Verschaf een volledige lijst met weergaven die zijn gekoppeld aan de waarde die is ingesteld in de eigenschap Entiteit.  
  
    - **Geselecteerde weergaven weergeven**. Selecteer deze instelling om de lijst met weergaven te beperken die tijdens runtime beschikbaar is. Als u de specifieke weer te geven weergaven wilt selecteren, houdt u de toets Ctrl ingedrukt en selecteert u elke weergave die u wilt opnemen.  
 
## <a name="next-steps"></a>Volgende stappen  
 [Dashboards maken of aanpassen](create-edit-dashboards.md)
