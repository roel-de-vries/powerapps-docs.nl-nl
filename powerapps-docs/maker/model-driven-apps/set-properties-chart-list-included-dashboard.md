---
title: Eigenschappen instellen voor een modelgestuurde app-grafiek of -lijst in een dashboard in PowerApps | Microsoft Docs
description: Informatie over hoe u eigenschappen instelt voor grafieken of lijsten in een dashboard
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
ms.openlocfilehash: c88fef0412060516ef448c89f5ddfdc9cad00e20
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39679588"
---
# <a name="set-properties-for-a-model-driven-app-chart-or-list-included-in-a-dashboard"></a>Eigenschappen instellen voor een modelgestuurde app-grafiek of -lijst in een dashboard

Als u een grafiek of lijstonderdeel wilt bewerken in de Dashboard Designer, selecteert u de grafiek of lijst van uw keus en selecteert u Onderdeel bewerken in de Dashboard Designer-werkbalk.   

  ![Grafiekonderdeel bewerken in Dashboard Designer](media/dashboard-chart-select.png)

Hiermee opent u het dialoogvenster **Eigenschappen instellen**.

  ![Grafiekeigenschappen instellen](media/set-properties-chart.png)  
 
U kunt de volgende grafiekeigenschappen instellen vanuit het dialoogvenster **Eigenschappen instellen**:  
  
- **Naam**. Unieke naam voor de grafiek. Het systeem stelt een waarde voor, maar deze kunt u wijzigen.  
  
- **Label**. Het label dat bovenaan de grafiek verschijnt.  
  
- **Label weergeven op het Dashboard**. Schakel dit selectievakje in of uit als u het grafieklabel wilt weergeven of verbergen.  
  
- **Entiteit**. Selecteer de entiteit (recordtype) waarop de grafiek wordt gebaseerd. Deze instelling bepaalt de beschikbare waarden voor de eigenschappen Standaardweergave en Standaardgrafiek.  
  
- **Standaardweergave**. Selecteer de weergave die wordt gebruikt om de gegevens voor de grafiek op te halen.  
  
- **Standaardgrafiek**. Selecteer de standaardgrafiek die u wilt weergeven wanneer het dashboard wordt geopend. De beschikbare waarden worden bepaald door de waarde die wordt ingesteld voor de eigenschap Entiteit. Deze eigenschap werkt samen met de eigenschap Grafiekselectie weergeven. Een gebruiker kan het type grafiek wijzigen als de optie **Grafiekselectie weergeven** is ingeschakeld, maar de grafiek wordt bij de volgende keer dat het dashboard wordt geopend weer als de standaardgrafiek weergegeven.  
  
- **Alleen grafiek weergeven**. Schakel dit selectievakje in als u alleen de grafiek wilt weergeven. Schakel dit selectievakje uit als u de grafiek en de bijbehorende gegevens wilt weergeven.  
  
- **Grafiekselectie weergeven**. Schakel dit selectievakje in als u wilt dat gebruikers het soort grafiek (kolom, balk, taart enz.) kunnen wijzigen wanneer zij het dashboard gebruiken. Als de gebruiker het soort grafiek wijzigt, worden de instellingen niet opgeslagen. Wanneer het dashboard wordt gesloten, wordt het soort grafiek teruggezet naar de standaardgrafiek.  
  
U kunt de volgende lijsteigenschappen instellen vanuit het dialoogvenster **Eigenschappen instellen**:  
  
- **Naam**. Unieke naam voor de lijst. Het systeem stelt een waarde voor, maar deze kunt u wijzigen.  
  
- **Label**. Het label dat bovenaan de lijst verschijnt.  
  
- **Label weergeven op het Dashboard**. Schakel dit selectievakje in of uit als u het lijstlabel wilt weergeven of verbergen.  
  
- **Entiteit**. Selecteer de entiteit (recordtype) waarop de lijst wordt gebaseerd. Deze instelling bepaalt de beschikbare waarden voor de eigenschap Standaardweergave voor de lijst.  
  
- **Standaardweergave**. Selecteer de weergave die wordt gebruikt om de gegevens in de lijst op te halen. Een gebruiker kan de weergave wijzigen, maar de lijst wordt bij de volgende keer dat het dashboard wordt geopend weer in de Standaardweergave weergegeven.  
  
- **Zoekvak weergeven**. Schakel dit selectievakje in als u het zoekvak bovenaan de lijst wilt weergeven. Als het zoekvak is ingeschakeld, kunnen u of andere gebruiker tijdens runtime zoeken naar records in de lijst.  
  
- **Index weergeven**. Schakel dit selectievakje in als u onderaan de lijst de filters A tot Z wilt weergeven. Wanneer de filters A tot Z worden weergegeven, kunnen u of andere gebruikers een letter selecteren om snel naar de records te gaan die met die letter beginnen.  
  
- **Weergaveselectie**. Selecteer één van de volgende waarden:  
  
    - **Uit**. De weergaveselectie niet weergeven. U of andere gebruikers kunnen tijdens de runtime geen weergaven wijzigen.  
  
    - **Alle weergaven weergeven**. Dit biedt een volledige lijst van weergaven die bij de ingestelde waarde in de eigenschap Entiteit horen.  
  
    - **Geselecteerde weergaven weergeven**. Selecteer deze instelling om de lijst met weergaven tijdens de runtime te beperken. Als u de weer te geven specifieke weergaven wilt selecteren, houdt u de Ctrl-toets ingedrukt en tikt u op of selecteert u elke weergave die u wilt opnemen.  
 
## <a name="next-steps"></a>Volgende stappen  
 [Dashboards maken of aanpassen](create-edit-dashboards.md)
