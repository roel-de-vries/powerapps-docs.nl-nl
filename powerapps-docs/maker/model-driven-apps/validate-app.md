---
title: Een modelgestuurde app valideren en publiceren met de appontwerper | MicrosoftDocs
description: Informatie over hoe u een modelgestuurde app valideert en publiceert
keywords: ''
ms.date: 06/08/2018
ms.service: crm-online
ms.custom: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: 5a9ec120-9ddc-4d92-b48c-0fee8c57d3c3
ms.author: matp
manager: kvivek
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
caps.latest.revision: 10
topic-status: Drafting
ms.openlocfilehash: e3802ef423e7012974c24311c36b78cd56f8ed06
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39677543"
---
# <a name="validate-and-publish-a-model-driven-app-using-the-app-designer"></a>Een modelgestuurde app valideren en publiceren met de appontwerper

Valideer een app om te controleren op assetafhankelijkheden die nodig zijn om de app te kunnen gebruiken, maar die nog niet aan de app zijn toegevoegd. Wanneer de app is gevalideerd, publiceert u de app. 
  
U hebt bijvoorbeeld een prestatiedashboard van de klantenservice toegevoegd aan de app, die gebruikmaakt van diagrammen, zoals Combinatie van aanvragen (op prioriteit) of Tendens van aanvraagafsluitingen (op dag) die u niet hebt toegevoegd. Wanneer u deze app valideert, krijgt u een lijst met alle ontbrekende vereiste assets.  
  
Wanneer u de app valideert, worden op het canvas van de appontwerper details weergegeven over de assets die ontbreken.  
  
1.  Selecteer **Valideren** in de appontwerper.  
  
     Er wordt een meldingsbalk weergegeven waarin wordt vermeld of er voor de app fouten of waarschuwingen zijn. Op de meldingsbalk worden waarschuwingen weergegeven wanneer een entiteit bijvoorbeeld geen formulieren of weergaven bevat, of de app geen onderdelen bevat. Er kan een fout worden weergegeven als er geen siteoverzicht is geconfigureerd voor de app. U kunt een app publiceren zonder dat u iets doet met de waarschuwingen. Fouten moeten echter worden opgelost voordat u kunt publiceren.  
  
     ![Meldingsbalk waarop waarschuwingen worden weergegeven in de app](media/app-designer-warning-notification.png "Meldingsbalk waarop waarschuwingen worden weergegeven in de app")  
  
     In de appontwerper wordt ook een waarschuwingssymbool weergegeven met het aantal afhankelijkheden voor elk artefact of elke assettegel waarvoor een vereiste asset ontbreekt.  
  
     ![Waarschuwing voor ontbrekende onderdelen op de tegel van de appontwerper](media/warning--button-on-app-designer-tile.png "Waarschuwing voor ontbrekende onderdelen op de tegel van de appontwerpertegel")  
  
2.  Als u de vereiste assets wilt toevoegen, selecteert u het tabblad **Vereist** aan de rechterkant van het canvas. Het tabblad **Vereist** wordt weergegeven wanneer ten minste één vereiste asset in de app ontbreekt.  
  
     Het tabblad bevat een lijst met vereiste onderdelen.  
  
     ![Op het tabblad Vereist wordt een lijst met ontbrekende onderdelen in de app weergegeven](media/app-designer-required-components-tab.png "Op het tabblad Vereist wordt een lijst met ontbrekende onderdelen in de app weergegeven")  
  
3.  Selecteer de assets die u wilt toevoegen en selecteer vervolgens **Afhankelijkheden toevoegen**. Wanneer u een vereiste asset toevoegt, vermindert het aantal op de tegel waarvoor u de asset hebt toegevoegd.  
  
    > [!NOTE]
    >  Als een veelvoorkomende asset vereist is voor verschillende onderdelen van de app, een formulier is bijvoorbeeld vereist voor een dashboard en een entiteit, en u voegt die asset slechts één keer toe vanuit de afhankelijkheidsstructuur van het dashboard, vermindert het aantal afhankelijkheden alleen op de dashboardtegel, maar niet op de entiteitstegel. De afhankelijkheid is echter voor beide opgelost.  
    >   
    >  Selecteer **Meest recente afhankelijkheden ophalen** ![de knop Meest recente afhankelijkheden ophalen in de appontwerper](media/app-designer-get-latest-dependencies.png "de knop Meest recente afhankelijkheden ophalen in de appontwerper") of selecteer nogmaals **Valideren** om de meest recente afhankelijkheden op te halen. Deze knoppen worden pas weergegeven nadat u uw app hebt opgeslagen.  
  
     Selecteer **Afhankelijkheden verbergen** als u de voorgestelde vereiste onderdelen niet wilt toevoegen. Niet-opgeloste waarschuwingen worden opnieuw weergegeven wanneer u de app opent in de appontwerper en **Valideren** of **Meest recente afhankelijkheden ophalen** ![de knop Meest recente afhankelijkheden ophalen in de appontwerper](media/app-designer-get-latest-dependencies.png "de knop Meest recente afhankelijkheden ophalen in de appontwerper") selecteert.  
  
    > [!NOTE]
    >  Als u de afhankelijkheden nu verbergt en deze app op een later tijdstip wilt exporteren, worden al deze afhankelijkheden opnieuw weergegeven.  
  
## <a name="publish-an-app-using-the-app-designer"></a>Een app publiceren met de appontwerper

Publiceer een app om deze beschikbaar te maken voor gebruikers.  
  
 Nadat u onderdelen hebt toegevoegd, de app hebt gevalideerd en opgeslagen, selecteert u **Publiceren** op de opdrachtbalk. U kunt de app ook vanuit de apptegel publiceren op de pagina [Mijn apps](advanced-navigation.md#my-apps). In de weergave **Apps die worden bewerkt** selecteert u in de rechterbenedenhoek van de apptegel die u wilt publiceren de knop **Meer opties** (**...**) en selecteert u vervolgens **Publiceren**.  
  
 De appstatus wordt gewijzigd in Gepubliceerd. Dit wordt weergegeven in de rechterbovenhoek van de appontwerper. De app wordt verplaatst van de weergave **Apps die worden bewerkt** naar de weergave **Gepubliceerde apps** en de publicatiedatum wordt op de apptegel weergegeven.  
  
> [!NOTE]
> - Als uw app een validatiefout heeft, wordt de fout op een meldingsbalk vermeld. U kunt de app pas publiceren als u de fout hebt opgelost.  
> - U kunt een app pas publiceren als u deze hebt opgeslagen.  

## <a name="next-steps"></a>Volgende stappen  
[Een app die is gebaseerd op een model delen met PowerApps](https://docs.microsoft.com/powerapps/maker/model-driven-apps/share-model-driven-app) <br/>
 [Een modelgestuurde app uitvoeren op een mobiel apparaat](https://docs.microsoft.com/powerapps/user/run-app-client-model-driven)   
 
