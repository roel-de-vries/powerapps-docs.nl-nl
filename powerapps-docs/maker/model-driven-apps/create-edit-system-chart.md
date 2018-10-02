---
title: Een systeemgrafiek voor modelgestuurde apps maken of bewerken in PowerApps | MicrosoftDocs
description: Leren hoe u een grafiek maakt of bewerkt
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
  - PowerApps
author: Mattp123
ms.assetid: e02d58f7-6b1c-4a51-b801-a4d9f24729c5
caps.latest.revision: 29
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-a-model-driven-app-system-chart"></a>Een systeemgrafiek voor modelgestuurde apps maken of bewerken

In dit onderwerp leert u hoe u een systeemgrafiek maakt. Systeemgrafieken zijn grafieken die eigendom zijn van de organisatie. Hierdoor zijn ze toegankelijk voor iedereen die de app uitvoert met leestoegang. Systeemgrafieken kunnen niet worden toegewezen aan of gedeeld met specifieke appgebruikers.  
  
1. Op de site [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) selecteert u **Modelgestuurd** (linkerbenedenhoek van het navigatievenster).  

     ![Modelgestuurde ontwerpmodus](media/model-driven-switch.png)

    > [!IMPORTANT]
    > Als de **modelgestuurde** ontwerpmodus niet beschikbaar is, moet u mogelijk [een omgeving maken](https://docs.microsoft.com/powerapps/administrator/create-environment).     
  
2. Vouw **Gegevens** uit, selecteer **Entiteiten**, selecteer de gewenste entiteit en selecteer het tabblad **Grafieken**.  
  
3.  Selecteer **Grafiek toevoegen** op de werkbalk.  
  
4.  Geef het grafiektype op en bepaal hoe de gegevens in de grafiek worden weergegeven.  
  
    -   Voer de grafieknaam in, bijvoorbeeld *Aantal medewerkers per account*.  
  
    -   In de vervolgkeuzelijsten **Veld selecteren**: 
        - Selecteer in de vervolgkeuzelijst **Veld selecteren** **voor de reeksas** een veld zoals **Aantal werknemers**.  
        - Selecteer in de vervolgkeuzelijst **Veld selecteren** **voor de categorieas** een veld zoals **Accountnaam**.
  
    -   Voeg een beschrijving toe om het doel van de grafiek aan te duiden, zoals *In deze kolomgrafiek wordt het aantal werknemers op accountnaam weergegeven*. 

    > [!div class="mx-imgBorder"] 
    > ![Voorbeeldgrafiek](media/sample-chart.png)
  
5.  Kies **Opslaan en sluiten**.  

## <a name="next-steps"></a>Volgende stappen  
[Dashboards maken of bewerken](create-edit-dashboards.md)
