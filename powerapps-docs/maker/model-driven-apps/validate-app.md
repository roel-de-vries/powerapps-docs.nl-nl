---
title: Een modelgestuurde app valideren en publiceren met de appontwerper | MicrosoftDocs
description: Leer hoe u een modelgestuurde app kunt valideren en publiceren
keywords: ''
ms.date: 06/08/2018
ms.service: crm-online
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: 5a9ec120-9ddc-4d92-b48c-0fee8c57d3c3
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
caps.latest.revision: 10
topic-status: Drafting
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="validate-and-publish-a-model-driven-app-using-the-app-designer"></a>Een modelgestuurde app valideren en publiceren met de appontwerper

U valideert een app om te controleren of er activumafhankelijkheden zijn die nodig zijn om de app te laten functioneren, maar die nog niet aan de app zijn toegevoegd. Na een succesvolle validatie publiceert u de app. 
  
U hebt bijvoorbeeld een dashboard met Klantenserviceprestaties aan de app toegevoegd, met grafieken als Aanvragenmix (op prioriteit) of Afsluitingstrend voor aanvragen (Per dag) die u niet hebt toegevoegd. Wanneer u deze app valideert, wordt een lijst weergegeven met alle ontbrekende, vereiste activa.  
  
Wanneer u de app valideert, ziet u op het canvas van de appontwerper details over de activa die ontbreken.  
  
1.  Selecteer in de appontwerper de optie **Valideren**.  
  
     Er wordt een meldingsbalk weergegeven waarop wordt aangegeven of de app fouten of waarschuwingen heeft. De meldingsbalk toont waarschuwingen in aanvragen waarin een entiteit bijvoorbeeld geen formulieren of weergaven heeft of wanneer de app bevat geen onderdelen bevat. Er kan een fout verschijnen als er geen siteoverzicht is geconfigureerd voor de app. U kunt een app publiceren zonder adresseringswaarschuwingen, maar u moet alle fouten oplossen voordat u de app publiceert.  
  
     ![Meldingsbalk met waarschuwingen in de app](media/app-designer-warning-notification.png "Meldingsbalk met waarschuwingen in de app")  
  
     De appontwerper geeft ook een waarschuwingssymbool weer met het aantal afhankelijkheden voor elke artefact of activategel waar een vereiste activum ontbreekt.  
  
     ![Waarschuwing voor ontbrekend onderdeel op de appontwerpertegel](media/warning--button-on-app-designer-tile.png "Waarschuwing voor ontbrekend onderdeel op de appontwerpertegel")  
  
2.  Als u de vereiste activa wilt toevoegen, selecteert u het tabblad **Vereist** aan de rechterkant van het canvas. Het tabblad **Vereist** is zichtbaar als minstens één vereist activum ontbreekt uit de app.  
  
     Het tabblad geeft een lijst met vereiste onderdelen weer.  
  
     ![Tabblad Vereist met een lijst van ontbrekende onderdelen in de app](media/app-designer-required-components-tab.png "Tabblad Vereist met een lijst van ontbrekende onderdelen in de app")  
  
3.  Selecteer de activa die u wilt toevoegen en selecteer vervolgens **Afhankelijkheden toevoegen**. Wanneer u een vereist activum toevoegt, vermindert het aantal op de tegel waaraan u het activum hebt toegevoegd.  
  
    > [!NOTE]
    >  Als meerdere apponderdelen hetzelfde vereiste activum hebben, bijvoorbeeld een formulier dat vereist is voor een dashboard en een entiteit, en u dat activum slechts één keer toevoegt vanuit de structuur voor dashboardafhankelijkheden, wordt het aantal afhankelijkheden wel verlaagd op de dashboardtegel, maar niet op de entiteitstegel. De afhankelijkheid wordt echter voor beide opgelost.  
    >   
    >  Selecteer **Meest recente afhankelijkheden ophalen** ![Knop Meest recente afhankelijkheden ophalen in de appontwerper](media/app-designer-get-latest-dependencies.png "Knop Meest recente afhankelijkheden ophalen in de appontwerper") of selecteer **Valideren** opnieuw om de meest recente set met afhankelijkheden te verkrijgen. U ziet deze knoppen pas nadat u de app hebt opgeslagen.  
  
     Selecteer **Afhankelijkheden verbergen** als u de voorgestelde vereiste onderdelen niet wilt toevoegen. Er verschijnen opnieuw niet-opgeloste waarschuwingen wanneer u de app opent in de appontwerper en **Valideren** of **Meest recente afhankelijkheden ophalen** ![Knop Meest recente afhankelijkheden ophalen in de appontwerper](media/app-designer-get-latest-dependencies.png "Knop Meest recente afhankelijkheden ophalen in de appontwerper") selecteert.  
  
    > [!NOTE]
    >  Als u afhankelijkheden nu verbergt en deze app later wilt exporteren, worden alle afhankelijkheden opnieuw weergegeven.  
  
## <a name="publish-an-app-using-the-app-designer"></a>Een app publiceren met de appontwerper

Publiceer een app om deze beschikbaar te maken voor gebruikers.  
  
 Nadat u onderdelen hebt toegevoegd en gevalideerd, en de app hebt opgeslagen, selecteert u **Publiceren** op de opdrachtbalk. U kunt de app ook van de apptegel op de pagina [Mijn apps](advanced-navigation.md#my-apps) publiceren. Selecter in de weergave **Apps die worden bewerkt** in de rechterbenedenhoek van de apptegel die u wilt publiceren de knop **Meer opties** (**...**) en selecteer vervolgens **Publiceren**.  
  
 De appstatus verandert in Gepubliceerd. U kunt dit in de rechterbovenhoek van de appontwerper zien. De app wordt van de weergave **Apps die worden bewerkt** naar de weergave **Gepubliceerde apps** verplaatst en de publicatiedatum wordt weergegeven op de apptegel.  
  
> [!NOTE]
> - Als uw app een validatiefout bevat, wordt de fout op een meldingsbalk weergegeven. U kunt de app pas publiceren als u de fout hebt opgelost.  
> - U kunt een app pas publiceren als u deze hebt opgeslagen.  

## <a name="next-steps"></a>Volgende stappen  
[Een modelgestuurde app delen met PowerApps](https://docs.microsoft.com/powerapps/maker/model-driven-apps/share-model-driven-app) <br/>
 [Een modelgestuurde app uitvoeren op een mobiel apparaat](https://docs.microsoft.com/powerapps/user/run-app-client-model-driven)   
 
